# Delay for JavaScript
An one line implementation of `sleep function` in JavaScript with generator.  
Without callbacks, promises, never stack overflow. Inspired by tj/co.

__Warning: this is an experiment project and not safe for production use.__

## Source

One line, just copy & paste:

```javascript
var d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t); 
```

## How to use it?

Just run this in your Chrome console (Chrome >= 35, Firefox >= 38, Edge >= 13).

```javascript
var d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t); // <- the source
d(function *() {                                               // <- wrapper
                                                               // <- magic start
  console.log('foo'); // output 'foo'
  yield 1000;         // delay 1 sec
  console.log('bar'); // output 'bar'
  yield 1000;         // delay 1 sec
  console.log('baz'); // output 'baz'
  yield 1000;         // delay 1 sec
  return 'it works';  // return 'it works'
  
}, function (res) {
  alert(res);         // callback
});
```

## ...

You could rename the `d` function to avoid conflicts.  
Or just using it under a wrapper scope. 

## About

@quietshu https://github.com/quietshu/delay

MIT licensed.
