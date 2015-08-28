# HTML5 Lockable Storage 

Manage concurrency between browser tabs running independent processes by (a)synchronizing the localStorage resource.

This is the implementation by *Benjamin Dumke-von der Ehe* as posted in his 2012 article [JavaScript concurrency and locking the HTML5 localStorage](http://balpha.de/2012/03/javascript-concurrency-and-locking-the-html5-localstorage/).

## Install

    bower install lockablestorage

or

```
  npm install lockable-storage
```

## Usage

    LockableStorage.lock('key', function () {
        // exclusive access to localStorage['key']
    });
