# Delay for JavaScript
An one line implementation of `sleep function` in JavaScript with generator.  
Without callbacks or promises. Inspired by tj/co.

__Warning: this is an experiment project and not safe for production use.__

## Source

One line, just copy & paste:

```javascript
var d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t); 
```

## How to use it?

Just run this in your Chrome console (Chrome >= 35, Firefox >= 38, Edge >= 13).

```javascript
var d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t); // <- source code
d(function *() {                                               // <- wrapper
                                                               // <- magic
  console.log('foo'); // output 'foo'
  yield 1000;         // delay 1 sec
  console.log('bar'); // output 'bar'
  yield 1000;         // delay 1 sec
  console.log('baz'); // output 'baz'
  
});
```

## ...

You could rename the `d` function to avoid conflicts.  
Or just using it under a wrapper scope. 

## About

@quietshu https://github.com/quietshu/delay

MIT licensed.
