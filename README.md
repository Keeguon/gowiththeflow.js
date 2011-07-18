# flow.js - a javascript flow control micro library

Flow.js is a javascript asynchronous flow-control micro library. It works in node.js and in browser. It is only 30lines.
It allow to control how your asynchronous code Is executed, sequentially or in parallel.

# how to use it

    Flow().seq(function(next){
        console.log("step 1: started, it will last 1sec");
        setTimeout(function(){
            console.log("step 1: 1sec expired. Step 1 completed");
            next();
        }, 1000);
    }).seq(function(next){
        console.log("step 2: run after step1 has been completed");
    })

It will display the following

    step 1: started, it will last 1sec
    step 1: 1sec expired. Step 1 completed
    step 2: run after step1 has been completed

    

TODO explain
* explain .seq() and .par()
* explain how to pass the error and result to the next step
  * special case if paralell