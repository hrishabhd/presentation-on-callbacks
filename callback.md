**##What is callbacks function in javascript?**

If you used  javascript then probably you used callbacks function, you haven't than you not doing real javascript programming.

A callback function, also known as a higher-order function, is a function that is passed to another function (let’s call this other function “otherFunction”) as a parameter, and the callback function is called (or executed) inside the otherFunction. A callback function is essentially a pattern (an established solution to a common problem), and therefore, the use of a callback function is also known as a callback 
pattern.

so, In javascript function is just like a object. Object pass into as a argument. you can pass other function as argument and execute at some extends.

Ex: 

``` 
            		let x = function () {		
                            console.log("I am Inside Function")
                }

                let y = function () {

                        console.log("I am Function Y")

                }

			y(x);
```

*So here Function X pass as a argument in Function Y*

##Just keep aside all this jagans and understand by normal story.

Imagine this scenario: you are expecting a package in a couple of  days. The package is a gift for your neighbor. Therefore, once you get  the package, you want it brought over to the neighbors. You are out of  town, and so you leave instructions for your spouse. 

You could tell them to get the package and bring it to the neighbors.  If your spouse was as stupid as a computer, they would sit at the door and wait for the package until it came (NOT DOING ANYTHING ELSE) and  then once it came they would bring it over to the neighbors. But there's a better way. Tell your spouse that ONCE they receive the package, they  should bring it over the neighbors. Then, they can go about life  normally UNTIL they receive the package.

In our example, the receiving of the package is the "event" and the  bringing it to the neighbors is the "callback". Your spouse "runs" your  instructions to bring the package over only *when* the package arrives. Much better!

This kind of thinking is obvious in daily life, but computers don't have the same kind of common sense.

**##Let's Go deeper and understand Why we need callbacks?**

JavaScript is an event driven language. This means that instead of waiting for a response before moving on, JavaScript will keep executing while listening for other events

But what if function first contains some sort of code that can’t be executed immediately? For example, an API request where we have to send the request then wait for a response? To simulate this action, were 
going to use `setTimeout` which is a native JavaScript method that calls a function after a specified delay

It’s not important that you understand how `setTimeout()` works right now (although if you’re curious, go to the documentation.)

## A Real World Example

**##How Callbacks works?**

```javascript
                T.get('search/tweets', params, function(err, data, response) {
                  if(!err){
                    // This is where the magic will happen
                  } else {
                    console.log(err);
                  }
                });
```

- `T.get` simply means we are making a GET request to Twitter.
- There are three parameters in this request: `‘search/tweets’`, which is the route of our request, `params` which are our search parameters, and then an anonymous function which is our callback.

A callback is important here because we need to wait for a  response from the server before we can move forward in our code. We  don’t know if our API request is going to be successful or not so after  sending our parameters to `search/tweets` via a GET request, we wait. Once Twitter responds, our callback function is invoked. Twitter will either send an `err` (error) object or a `response` object back to us. In our callback function we can use an `if()` statement to determine if our request was successful or not, and then act upon the new data accordingly.

