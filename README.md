storage-backed-object [![Build Status](https://api.travis-ci.org/intelligentgolf/storage-backed-object.png?branch=master)](https://travis-ci.org/intelligentgolf/storage-backed-object)
=====================

Simple AngularJS service to store an object of key/values in HTML5 storage. This can be useful when wanting to store complex data that survives browser refreshes.

Usage
-----
   
    // Create the object
    var users = StorageBackedObject('users');
    
    // Store an item by key
    users.set(1234, {name: 'John Smith'})
    
    // Fetch an item by key
    var user = users.get('1234');
    
    // Remove an item by key
    users.remove(1234);
    

Properties
----------

Repeated calls to `get` returns the exact same value.

	users.set(1234, {name: 'John Smith'});
    users.get(1234) === users.get(1234); // True
    
This makes it safe to repeatedly call `get` for the same key, without using more memory.
    
    
Under the hood
--------------

All the values are fetched from HTML5 storage when the object is created.

Each value of the object is stored in a separate HTML5 storage item. This avoids long json encodes / decodes when setting elements.

    
    
    
