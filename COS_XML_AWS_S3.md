##[对照 COS_XML_V2版本测试 AWS S3 Android SDK接口]



#Service 接口

<table>
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 api</th></tr>

<tr><th>getService</th><th>兼容</th><th>listBuckets</th></tr>
</table>

#Bucket 接口

<table>
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 api</th></tr>

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
<tr><th>cos xml api</th><th>是否兼容</th><th> aws s3 api</th></tr>

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
