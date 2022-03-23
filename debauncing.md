# Debouncing
- It is a very important concept in `JavaScript` for performance optimization. 
- The most common use case where a function is invoked frequently due to some action from user end, it might greatly affect the performance of the browser. 
- It enhances the time-consuming computations.
 # Example:
Below is the code for search box, when the user user types something, it will fetching data based on some apt words (entered by user).
 ```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
</head>
<body>
	<input type="text" onkeyup="getData()"/>
</body>

<script type="text/javascript">
	let counter = 0;
	const getData = () => {
		console.log("fetching data...", counter++) //actual function
	}
</script>
</html>
```
Below is gif of user action. If I type (say laptob), we get 6 times `fetching data...` in console with counter value as 5. So here what happened is console runs as many times as the user hit any key. 
But in real life scenario, we don't want this, 
- 1st, it will call many API request to show some suggestions.
- 2nd, Backend Code needs to know what is the actual user input, which will be known when the user complete its typing for any search.

![debounce-1](https://user-images.githubusercontent.com/71059909/159651542-ff061c95-102f-41ce-82cb-98f62fbbcf52.gif)

In order to address this major problem, we have `Debouncing` concept in JS, which can handle this smoothly using majorly `setTimeout()`, `clearTimeout()` and 
callback function.

Below is the code for debouncing implementation:

```
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
</head>
<body>
	<input type="text" onkeyup="betterFunction()"/>    
	// getData() is replaced with betterFunction() in above eventListner.
</body>

<script type="text/javascript">
	let counter = 0;
	const getData = () => {
		console.log("fetching data...", counter++) //actual function
	}
// ++++ added code for debouncing
    const debounceFunc = function (fn, delay) {  
		let timer;
        return function (){
        	let context = this;
        	args = arguments;
        	clearTimeout(timer);
        	timer = setTimeout(() => {
        		getData.apply(context, arguments);
        	}, delay);
        }
	}
	const betterFunction = debounceFunc(getData, 300); 
// ++++	
</script>
</html>

```
In the above code, we have used variable assigned function, that return another function based some time-delay. Here, this is very important role of time, because as a developer, we give some standarised time to take break after typing, then only the code call for API fetch request.

![debounce-2](https://user-images.githubusercontent.com/71059909/159655738-add98e64-fff1-4d45-b806-86e95e7c74c1.gif)

In above gif, we see that, I have typed continously many letters, then I took a pause and type many letters. But in console we have only 3 print of `fetching data...`. So this is very simple demonstration of debouncing and can be widely used many use cases like in any resizer, scroll-effect.

### Ref: 
- [Akash Saini vide0](https://www.youtube.com/watch?v=Zo-6_qx8uxg&t=234s)
- [GeekForGeek Explaination](https://www.geeksforgeeks.org/debouncing-in-javascript/#:~:text=Debouncing%20is%20a%20programming%20practice,which%20a%20function%20gets%20invoked.&text=%22executed%20once%20every%203%20seconds!!%22%20)

 

