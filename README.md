# HTML5 Lockable Storage 

Manage concurrency between browser tabs running independent processes by (a)synchronizing the localStorage resource.

This is the implementation by *Benjamin Dumke-von der Ehe* as posted in his 2012 article [JavaScript concurrency and locking the HTML5 localStorage](http://balpha.de/2012/03/javascript-concurrency-and-locking-the-html5-localstorage/).

## About this fork

- Corrects an oversight in the original implementation. Whereas the original implementation [hard-coded the "delay" parameter](https://github.com/elad/LockableStorage/blob/master/LockableStorage.js#L79), this fork's implementation makes it user-configurable, per the spec. For more on the delay parameter, refer to the original paper, on page 5: http://research.microsoft.com/en-us/um/people/lamport/pubs/fast-mutex.pdf. For the 
- It abstracts away `localStorage`, and instead makes the user responsible for passing in a storage mechanism that is compatible with [store.js](https://github.com/marcuswestin/store.js/).

## Install

    bower install lockablestorage

or

```
  npm install lockable-storage
```

## Usage
    import createLocker from 'lockable-storage';
    import store from 'store';

    const locker = createLockableStorage(store);
    locker.lock('key', function () {
        // exclusive access to localStorage['key']
    });
