# Delay for JavaScript
One-line `JS sleep function` based on generator. Without callbacks, promises, never stack overflow. Inspired by tj/co.

__Caution: this is an experiment project, not safe for production. Please use co or Q.__

## Source

One line, just copy & paste:

```javascript
var $=(f,c,t,r)=>(r=(t=t||f()).next()).done?c&&c(r.value):setTimeout(()=>$(f,c,t),r.value); 
```

## How to use it?

Just run this in your Chrome console (Chrome >= 35, Firefox >= 38, Edge >= 13).

```javascript
var $=(f,c,t,r)=>{(r=(t=t||f()).next()).done?c&&c(r.value):setTimeout(()=>$(f,c,t),r.value)}; // <- the source
$(function *() {                                                                              // <- wrapper
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

## About

@quietshu https://github.com/quietshu/delay

MIT licensed.
