##[对照 COS_XML_V2版本测试 AWS S3 Android SDK接口]##
|:.......|:......|
|#COS XML 接口 |#AWS S3 接口（AmazonS3Client）|

|##Service 接口||

|#getService:listBuckets||
    

##Bucket 接口

#put bucket: createBucket

#head bucet: doesBucketExist

#get bucket: listObjects

#list multipart uploads: listMultipartUploads

#put bucket acl: setBucketAcl

#get bucket acl: getBucketAcl

#put bucket lifecycle: setBucketLifecycleConfiguration

#get bucket lifecycle: getBucketLifecycleConfiguration

#delete bucket liffecycle: deleteBucketLifecycleConfiguration

#put bucket cros: setBucketCrossOriginConfiguration

#get bucket cros: getBucketCrossOriginConfiguration

#delete bucket cros: deleteBucketCrossOriginConfiguration

#get bucket location: getBucketLocation

#delete bucket: deleteBucket


##Object 接口

#put object: putObject

#get object: getObject

#head object: doesObjectExist

#delete object: deleteObject

#delete multiple objects: deleteObjects

#append object: 无

#initate multipart upload:initiateMultipartUpload

#list parts:listParts

#upload part:uploadPart

#complete multipart:completeMultipartUpload

#abort multipart upload:abortMultipartUpload

#put object copy: 出错，因为 cos的 x-cos-copy-source 与 aws s3 的 x-cos-copy-source定义不一样

#put object acl:setObjectAcl

#get object acl:getObjectAcl

#options object: 无



