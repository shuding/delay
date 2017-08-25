An one line implementation of `sleep function` in JavaScript with yield + generator.  
Without any callbacks or promises.

__Warning: this is an experiment and not safe for production!__

## Source

One line, just copy & paste:

```javascript
let d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t)
```

## Demo

Just run this in your Chrome console (Chrome >= 35, Firefox >= 38, Edge >= 13).

```javascript
let d=(f,t=f(),r=t.next())=>r.done||setTimeout(d,r.value,f,t)  // <- source code
d(function *() {                                               // <- wrapper
                                                               // <- magic
  console.log('foo')  // output 'foo'
  yield 1000          // wait for 1 sec
  console.log('bar')  // output 'bar'
  yield 1000          // wait for 1 sec
  console.log('baz')  // output 'baz'
  
})
```

## ...

You could rename the `d` function to avoid conflicts.  
Or just use it under a safe scope. 

## About

@quietshu https://github.com/quietshu/delay

MIT licensed.
