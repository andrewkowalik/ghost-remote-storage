# Ghost S3

This is an remote storage file module for Ghost blogs. Currently supports S3 and CloudFront.

Originally forked from https://github.com/screenrev/ghost-s3. 



## Install

	npm install --save git+https://github.com/infecto/ghost-remote-storage


## Configure

In your ghost config.js file under "development" and "production" add

	aws: {
	    accessKeyId: 'your aws access key id>',
	    secretAccessKey: 'your AWS secret access key>',
	    bucket: 'your-bucket-name',
	    region: 'the AWS region your bucket is in'
	},


## Plug In

Until Ghost has a file module system, you will have to change the file ```storage/index```

```javascript
	storage = require('./' + storageChoice);
```

becomes

```javascript
	storage = require('ghost-s3')({
	    errors: errors,
	    config: require('../config')().aws
	});
```


