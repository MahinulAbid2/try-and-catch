# What is it?
* `try{ } catch() {}` are used to handle errors.
* It can only be used inside of `async function`.
* Why should I use `try and catch`? It is used to `error handling`.
```javascript
const x = async () =>{ 
  try{
    /*
    - execute any function, promise
    - you can execute anything here. no issues.
    */
  } catch(err) {  
    /*
    - But if there is any error while executing try{ } block
    - then, try { } block stops execution and catch() {} starts execution.
    */
  }
}
```

<br>

* It says - `try` this code,
* If you find `error` then 
* `catch` the error.
```javascript
const a = false;

const b =  () => {
    if(a=== true) {
        console.log("logIn success");
    }else{
        throw new Error("login failed") // throwing an error
    }
}

const x = async () => {
    try{
        b();
    }catch(err) { // "err" is the error given by try{} block
        console.log('running catch function')
        console.log(err)
    }
}

x();

```
On the code: 
* `b` is a function that checks a variable. If the variable is `a === false` then `throw an Error`.
* `x()` is a `async function`.
* `try{}` block runs the `b()` function and finds error.
* If it gives an error <ins>only then</ins>  `catch(){}` function will run.

<br>
<br>

### This works differently when working with `promise` or `async` function.
```javascript
const x = false;
const a  = new Promise((res, rej) => {
    if( x == true ) {
        res( "login success" );
    } else if ( x === false ) {
        rej ( "Login failed" )
    }
})

const m = async ( ) =>{
    try {

        console.log( a );  // promise doesn't require a(). it is not a function

    } catch( err ) {  // in this code, the catch() {} will not be executed. WHY?

        console.log( "do something" ) 
        console.log( err )

    }
}

m( );

```

<br>

### Why:
* 













