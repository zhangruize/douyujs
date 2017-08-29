DouyuTV API Wrapper
===================

NodeJS Wrapper for DouyuTV APIs

Supported Platforms
-------------------

This library has been tested with:

- IO.js v2.5.0

Installation
------------

	npm install douyu

API Usage
---------

	// Import library
	var douyu = require('douyu');

	// Initialize Room entity
	var roomID = "424559";
	var room = new douyu.ChatRoom(roomID);

	// System level events handler
	room.on('connect', function(message){
		console.log('DouyuTV ChatRoom #' + roomID + ' connected.');
	});
	room.on('error', function(error){
		console.error('Error: ' + error.toString());
	});
	room.on('close', function(hasError){
		console.log('DouyuTV ChatRoom #' + roomID + ' disconnected' + hasError ? ' because of error.' : '.');
	});

	// Chat server events
	room.on('chatmsg', function(message){
		console.log('[' + message.nn + ']: ' + message.txt);
	});

	// Knock, knock ...
	room.open();

More
---------

Read the [official API pdf](http://dev-bbs.douyutv.com/forum.php?mod=attachment&aid=MjYxfGZjZWY1M2Q5fDE1MDM5OTY2NjF8MHwxMTU%3D) for more usage.
