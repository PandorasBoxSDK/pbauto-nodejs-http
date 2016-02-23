# pbauto-nodejs-http
This project is part of the Pandoras Box SDK. It implements an interface to access the Pandoras Box Automation.

## Requirements
* node.js
* Pandora's Box Manager with web server enabled

## Installation
```
npm install pbauto-nodejs-http
```

## Usage
Create a new PBAuto instance by passing in IP and Port of the Pandoras Box Web Server Service.

```javascript
var PBAuto = require('pbauto-nodejs-http');

var connection = new PBAuto("2.0.0.1", 6214);
```

You can then proceed to use all api functions. You can provide an optional callback to retrieve the response values.

```javascript
connection.getSelectedDeviceCount( function(response){
	// response.http holds the HTTP status code
	// response.code holds the Automation Command code
	// both are considered for the convenience value response.ok
	if(response.ok) // check if request was successful
	{
		// response values are automatically parsed and put on the response object
		console.log(response);
	}
});
```
Response (Raw JSON)
```json
{
	http: 200,
	ok: true,
	code: 81,
	selectedDevicesCount: 2
}
```

## Versioning
The version consists of a major, a minor and a revision field. (major.minor.revision)
If the major version changes, then these changes are incompatible with prior versions. Changes to the minor version indicate backwards compatibility. The revision field is reserved for the Pandoras Box revision that is required to use all features. It might be possible to use the SDK with an older revision of Pandoras Box, but not all the commands will work.

## Contributing
Most of the files in this repository are generated. Please contribute to the template files instead.
https://github.com/PandorasBoxSDK/pbauto-generator

v3.2.12086, generated on 2016-02-23