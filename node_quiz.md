### Node.js Quiz
Welcome to your Node.js weekly assessment! Please select the best answer for each question. There is only **one** correct answer for each question. Below the numbered questions are five fill-in-the-code style questions. Please answer those to the best of your ability in Node (back-end) JavaScript. Please do not use **any** 3rd party JavaScript packages. If any built-in method is disallowed for a specific problem, the question will state so. `i.e. Please do not use `.sort` on this question.`

1. What is an example of a Web Client?  
    A. A Browser - key  
    B. A Server  
    C. Node.js  
    D. The D.O.M.  

2. If one runs the file `myScript.js` as follows: `node myScript.js myArgument`, how does one access the myArgument argument inside of the JavaScript file's code?  
    A. process[1]  
    B. process.argv[2] - key  
    C. arguments[0]  
    D. process.argv[0]  

3. What is Node.js most notably used for?  
    A. Synchronous execution of server-side code  
    B. Multi-threaded clusters  
    C. The basis for webservers - key  
    D. Asset compilation, scripting, and monitoring  

4. Which of the following is not an accessible object in Node.js?  
    A. Document   - key  
    B. Console  
    C. Object  
    D. Process  

5. What is the most accurate description of what this block of code is checking?        
    ```js
    var a = 5;
    var b = 5;
    console.log(a === b)
    ```  
    A. If `a` and `b` are the same value  
    B. Whether the type and value of `a` and `b` are equal - key  
    C. If `a` has the same object ID as `b`  
    D. Whether the object IDs of both objects are the same  

6. What will `parseInt('  5  ')` return?  
    A. The string of '  5  '  
    B. undefined  
    C. NaN  
    D. The integer 5 - key  

7. What is the best description of the function accomplishes in Node? `module.exports = myVar`  
    A. To import the myVar variable into this JavaScript file.  
    B. To load the myVar file into another file  
    C. To export the variable myVar to the file server.js.  
    D. To make the variable myVar available for `require` in other JavaScript files. - key  

8. What is one of the purposes of creating modules of different JavaScript code?  
    A. To minify our code for best practices  
    B. To access JavaScript in the file explorer  
    C. So we can send our code via email  
    D. So we can access our code in different `.js` files - key   

9. Examine the following code block. What will be logged to the console?           
    ```js
    var myVar = {1: 'hello', 2: 'world', 3: 'jasmine tea'};
    console.log(myVar[2] + myVar[1]);
    ```
    A. 'helloworld'  
    B. 'worldhello' - key  
    C. 'hello'  
    D. undefined  

10. What will the following code block return?         
    ```js
    function myFunction(integer){
        return integer % 2 === 0;
    }
    myFunction(10);
    ```
    A. 0  
    B. true - key  
    C. false  
    D. 10  

11. If `fs.writeFile` does not find the file it has been given to write to, what will occur?  
    A. An error  
    B. Node will create one for us with the expected text contained within it - key  
    C. A silent fail will occur  
    D. `fs` will prompt us to confirm file creation  

12. Is reading or writing to a file using the `fs` package Synchronous or Asynchronous?  
    A. Synchronous  
    B. We don't need to care, Node is multi-threaded.  
    C. Asynchronous  
    D. It can be either depending on what `fs` function we use. - key  

13. What will the following code block return?    
    ```js
    "My Friend Phil".split(" ");
    ```
    A. ["My Friend Phil"]  
    B. [ 'MyFriendPhil' ]  
    C. [ 'My', 'Friend', 'Phil' ] - key  
    D. undefined  

14. What is the most accurate definition of a server?  
    A. A computer in a data center.  
    B. A piece of software that sends email or SMS.  
    C. Hardware or software that takes requests and/or does things. - key  
    D. A code-based database manager

15. What will be logged to the console when the following block of code is executed?       
    ```js
    var arr = [1, 2, 3]
    for(var i = 0; i < arr.length; i++){
      console.log(arr[i]);
    };
    ```
    A. 3, 2, 1  
    B. 3, 3, 3  
    C. 1, 1, 1  
    D. 1, 2, 3 - key  

16. What is the best description of what an if/else statement used for in JavaScript?  
    A. Returning a boolean  
    B. Conditionally rendering different components  
    C. Executing code blocks based on a condition - key  
    D. Switching to a different JavaScript function  

17. What is the request package used for making in Node?  
    A. Requests to Google.com  
    B. An AJAX request to any URL of our choosing  
    C. A HTTP GET request  
    D. Any HTTP request - key  

18. What kind of cycle do most servers utilize to communicate with web clients?  
    A. Receive & Respond  
    B. HTTP & HTTPS  
    C. Request & Response - key  
    D. Synchronous & Asynchronous  

19. What is a `package.json` file used for?  
    A. Managing dependencies. - key  
    B. Packaging our code.  
    C. Creating a new git repository.  
    D. Managing the runtime.  

20. What does this command do when run in the console? `npm install request --save`  
    A. Saves a package called `request` in our `package.json`  
    B. Installs a package called `request` to our global packages  
    C. Requests a package called `save` and lets us know when its ready to install  
    D. Installs a package called `request` and saves it to our `package.json` - key  

21. What is contained in a `node_modules` folder?  
    A. All JavaScript code.  
    B. All of the code related to NPM packages. - key  
    C. All of the dependencies of your code.  
    D. The code you get when you run `git pull origin master`.  

22. What kind of object is returned by most APIs, and in particular the OMDB API?  
    A. String  
    B. JSON - key  
    C. Array  
    D. Response  

23. What is a popular 'NPM' package for creating a command line interface from Node.js?  
    A. Inquirer - key  
    B. Asker  
    C. GeoCoder  
    D. CLI  

24. You are given the following code block. What does the `.then(...)` tell you about the request variable's type? It is..   
    ```js
    request.then(function(response, err){
        console.log(response);
    })
    ```
    A. A HTTP request  
    B. An AJAX request  
    C. A promise - key  
    D. A `request` package object  

25. What best describes the highest level issue with the following code block?      
    ```js
    var x = 5;  
    y  = 7;  

    function multiply (numOne, numTwo) {
        return numOne * numTwo
    }  

    multiply(x, y);
    ```  
    A. There is no semi-colon on line 182 or 185.  
    B. The variable `y` is declared on the global scope. - key  
    C. `numOne` and `numTwo` should be in parenthesis to preserve order of operations.  
    D. the `return` statement on line 182 needs to be indented  

## Code Completion Questions

1. Please write a function that accepts three arguments, two numbers and a string. In the case that string is `divide`, divide the numbers and return the result. In the case that it is not, return a JSON with the key of `error` and the value of `Error: the command is not divide`.
    ```js
    function divideOrError(command, numOne, numTwo){

    }

    console.log(divideOrError('divide', 100, 1) === 100);
    console.log(divideOrError('multiply', 1, 1)) // Should return {'error': "Error: the command is not divide"}.
    ```

2. Please write a function that utilizes JavaScript's `array.sort` to sort an array of integers by their **reverse** numerical order. Remember that checking if your function's answer is correct using `===` will not work!
    ```js
    var myArray = [1, 2, 3];
    var myArrayTwo = [2, 12, 17, 1, 0, 42, 36, 17]
    function reverseSort(array){

    }

    console.log(reverseSort(myArray)) // should be [3, 2, 1]
    console.log(reverseSort(myArrayTwo)) // should be [42, 36, 17, 17, 12, 2, 1, 0]
    ```

3. Please write a function that checks if the last character in a string is a space. It should return true if it is, false otherwise. The console.logs should print `true` when this function is operating properly.         
    ```js
    var stringOne = 'abc  ';
    var stringTwo = 'a fish in the sea'
    var stringThree = 'this is a space '
    function isSpace(string){

    }

    console.log(isSpace(stringOne) === true);
    console.log(isSpace(stringTwo) === false);
    console.log(isSpace(stringThree) === true);
    ```

4. You are given the following JSON: `var myJson =  {1: 2, 3: 4, 5: 6, 7: 8}`. Please complete the below function to accept this JSON and returns the sum of all the values. The console.logs should print `true` when this function is operating properly. Please do not use the Array method `reduce`.       
    ```js
    var myJson =  {1: 2, 3: 4, 5: 6, 7: 8};
    var myJsonTwo = {1: 1, false: 0, true: 5, 'seventeen': 17}
    function addEverything(object) {

    }

    console.log(addEverything(myJson) === 36);
    console.log(addEverything(myJsonTwo) === 23);
    ```

5. This function is supposed to check if a number is prime or not. Remember, prime numbers are numbers that are divisible by 1 and itself, only. It has a bug. Please fix this bug so that the following test cases console.logs `true`. Please do not change the code to use the `Math` module.
    ```js
    function isPrime(number){
      for(var i = 0; i < number; i++) //should be i=2
        if(number % i === 0){
          return false;
        }
      return number !== 0;
    }
    console.log(isPrime(3) === true);
    console.log(isPrime(0) === false);
    ```
