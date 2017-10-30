##【对照 COS_XML_V2版本测试 AWS S3 Android SDK接口】


|COS XML 接口（CosXmlService）|说明||AWS S3 接口（AmazonS3Client）|说明||
|:------|:-------|:--------|:--------|:--------|
|Service 接口|||||
|get service|getService/getServiceAsync||listBuckets||
|Bucket 接口|||||
|put bucket|putBucket/putBucketAsync||createBucket||
|head bucet|headBucket/headBucketAsync||doesBucketExist||
|get bucket|getBucket/getBucketAsync||listObjects||
|list multipart uploads|listMultiUploads/listMultiUploadsAsync||listMultipartUploads||
|put bucket acl|putBucketACL/putBucketACLAsync||setBucketAcl||
|get bucket acl|getBucketACL/getBucketACLAsync||getBucketAcl||
|put bucket lifecycle|putBucketLifecycle/putBucketLifecycleAsync|| setBucketLifecycleConfiguration||
|get bucket lifecycle||getBucketLifecycleConfiguration|
|delete bucket liffecycle|getBucketLifecycle/getBucketLifecycleAsync||deleteBucketLifecycleConfiguration||
|put bucket cros|putBucketCORS/putBucketCORSAsync||setBucketCrossOriginConfiguration||
|get bucket cros|getBucketCORS/getBucketCORSAsync||getBucketCrossOriginConfiguration||
|delete bucket cros|deleteBucketCORS/deleteBucketCORSAsync||deleteBucketCrossOriginConfiguration||
|get bucket location |getBucketLocation/getBucketLocationAsync||getBucketLocation||
|delete bucket|deleteBucket/deleteBucketAsync||deleteBucket||


|Object 接口 ##|||
|put object|putObject/putObjectAsync||putObject||
|get object|getObject/getObjectAsync||getObject||
|head object|headObject/headObjectAsync||doesObjectExist||
|delete object|deleteObject/deleteObjectAsync||deleteObject||
|delete multiple objects|deleteMultiObject/deleteMultiObjectAsync||deleteObjects||
|append object|appendObject/appendObjectAsync||||
|initate multipart upload|initMultipartUpload/initMultipartUploadAsync||initiateMultipartUpload||
|list parts|listParts/listPartsAsync||listParts||
|upload part|uploadPart/uploadPartAsync||uploadPart||
|complete multipart|completeMultiUpload/completeMultiUploadAsync||completeMultipartUpload||
|abort multipart upload|abortMultiUpload/abortMultiUploadAsync||abortMultipartUpload||
|put object copy|copyObject/copyObjectAsync||copyObject||
|put object acl|putObjectACL/putObjectACLAsync||setObjectAcl||
|get object acl|getObjectACL/getObjectACLAsync||getObjectAcl||
|options object|optionObject/optionObjectAsync||||


