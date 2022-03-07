# Execution context in JS comes to picture, when we run any JS code in a web browser.

--The browser's JavaScript engine plays a pivotal role in creating a special environment (or space) to deal with the transformation and execution of this JavaScript code. 
This is what is called the Execution Context.

--During the Execution Context run-time, two components(or sub-spaceces) are created, i.e. memory and code blocks.

![dc52b8ab85f44201a343eec2248fa530-0001](https://user-images.githubusercontent.com/71059909/156985845-3214f131-3d62-43de-95f2-1c8073943661.jpg)

--For the better understanding, I have attached a diagram in order to explain how **Excecution Context** works. 

--First, when we run any JS scripts file, it automatically create a **Excecution Context**, known as **Global Execution Context (GEC)**. So let us first go deep into how EC works then we go to **Function Execution Context (FEC)**.

--Considering **Excecution Context** as Big container which consist of two blocks as **Memory** (for storing some data) amd **Code** (for executing codes).
1. **Memory**: Variables and functions are stored in memory in the form of key and value pairs. This is also know as *Variable Environment*
2. **Code**: This is the place where codes are being executed line by line.  This is also know as *Thread of execution*

Lastly, From the diagram we infer that JavaScript is a synchronous(*execute code in a specific order*) single-threaded(*JS can execute one command one at a time*) language.


Reference:
https://www.youtube.com/watch?v=ZvbzSrg0afE&t=203s
https://www.freecodecamp.org/news/execution-context-how-javascript-works-behind-the-scenes/
