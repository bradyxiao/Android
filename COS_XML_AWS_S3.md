##[对照 COS_XML_V2版本测试 AWS S3 Android SDK接口]

#测试前准备：
1）域名：aws s3 android sdk中请求域名格式是 bucket.region.amazonaws.com；而 cos的域名格式为 bucket-appid.cos.region.myqcloud.com; 因此，需要在 aws s3 android sdk中修改 region配置，即添加 cos的region,
如下所述,在 com.amazonaws.regions.RegionDefaults中添加cos region配置：
```java
Reion region = new Region("ap-beijing-1","");
ret.add(region);
updateRegion(region, "s3", "cos.ap-beijing-1.myqcloud.com", true, false);

Reion region = new Region("cn-south","");
ret.add(region);
updateRegion(region, "s3", "cn-south.myqcloud.com", true, false);

Region region = new Region("service.cos", "");
ret.add(region);
updateRegion(region, "s3", "service.cos.myqcloud.com", true, false);
```

2）bucket: 因为aws s3 sdk中 bucket作为请求域名的一部分，是必须参数，参照 1），得出 访问cos时，需要将
cos的 bucket-appid 这种格式 作为 aws s3 sdk中 bucket值.如：
```java
String bucket = "tjtest-1253653367"; // 是cos中 appid = 1253653367, bucket = "tjtest";
```

3）签名：因为 aws s3 sdk中 默认使用的签名 为 aws s3 v4 版本，且 改签名会修改 body即 会加上 chunk-signature header(如图所示),但是 cos 后台目前不支持，因此，需要修改，如在 body中不使用 chunk-signature header；
![](https://github.com/bradyxiao/Android/blob/master/s3.jpg)

修改：取消 chunk-signature
```java
com.amazonaws.services.s3.internal.AWSS3V4Signer.useChunkEncoding(Request<?> request){
	returen false;
}
```

#Service 接口

<table>
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 sdk api</th></tr>

<tr><th>getService</th><th>兼容</th><th>listBuckets</th></tr>
</table>

#Bucket 接口

<table>
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 sdk api</th></tr>

<tr><th>put bucket</th><th>兼容</th><th> createBucket</th></tr>

<tr><th>head bucet</th><th>兼容</th><th> doesBucketExist</th></tr>

<tr><th>get bucket</th><th>兼容</th><th> listObjects</th></tr>

<tr><th>list multipart uploads</th><th>兼容</th><th> listMultipartUploads</th></tr>

<tr><th>put bucket acl</th><th>兼容</th><th> setBucketAcl</th></tr>

<tr><th>get bucket acl</th><th>兼容</th><th> getBucketAcl</th></tr>

<tr><th>put bucket lifecycle</th><th>兼容</th><th> setBucketLifecycleConfiguration</th></tr>

<tr><th>get bucket lifecycle</th><th>兼容</th><th> getBucketLifecycleConfiguration</th></tr>

<tr><th>delete bucket liffecycle</th><th>兼容</th><th> deleteBucketLifecycleConfiguration</th></tr>

<tr><th>put bucket cros</th><th>兼容</th><th> setBucketCrossOriginConfiguration</th></tr>

<tr><th>get bucket cros</th><th>兼容</th><th> getBucketCrossOriginConfiguration</th></tr>

<tr><th>delete bucket cros</th><th>兼容</th><th> deleteBucketCrossOriginConfiguration</th></tr>

<tr><th>get bucket location</th><th>兼容</th><th> getBucketLocation</th></tr>

<tr><th>delete bucket</th><th>兼容</th><th> deleteBucket</th></tr>
</table>

#Object 接口

<table>
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 sdk api</th></tr>

<tr><th>put object</th><th>兼容</th><th> putObject</th></tr>

<tr><th>get object</th><th>兼容</th><th> getObject</th></tr>

<tr><th>head object</th><th>兼容</th><th> doesObjectExist</th></tr>

<tr><th>delete object</th><th>兼容</th><th> deleteObject</th></tr>

<tr><th>delete multiple objects</th><th>兼容</th><th> deleteObjects</th></tr>

<tr><th>append object</th><th>不兼容</th><th> 无</th></tr>

<tr><th>initate multipart upload</th><th>兼容</th><th>initiateMultipartUpload</th></tr>

<tr><th>list parts</th><th>兼容</th><th>listParts</th></tr>

<tr><th>upload part</th><th>兼容</th><th>uploadPart</th></tr>

<tr><th>complete multipart</th><th>兼容</th><th>completeMultipartUpload</th></tr>

<tr><th>abort multipart upload</th><th>兼容</th><th>abortMultipartUpload</th></tr>

<tr><th>put object copy</th><th>不兼容</th><th> 出错，因为 cos的 x-cos-copy-source 与 aws s3 的 x-cos-copy-source定义不一样</th></tr>

<tr><th>put object acl</th><th>兼容</th><th>setObjectAcl</th></tr>

<tr><th>get object acl</th><th>兼容</th><th>getObjectAcl</th></tr>

<tr><th>options object</th><th>不兼容</th><th> 无</th></tr>
</table>
