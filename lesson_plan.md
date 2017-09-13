* **Instructor Note**: This lesson is meant to be taught immediately after students have been exposed to basic function writing and bubble sort on the first whiteboarding day. It is valuable to stop and take questions often from students - many will feel confused and/or overwhelmed after the first whiteboarding day. This lesson seeks to enforce why we write algorithms in the way that we do, and why it is important from a computer science standpoint.

# An Introduction to Big O & Algorithms

## Instructor Talk: What is Big O?
* Big O, also known as time & space complexity, is a way computer scientists measure how memory efficient or fast an algorithm is as the given input grows larger & larger.
* This is really just fancy CS talk for: We want our algorithms to run as quickly as possible, and use as little computer memory as possible. As the input scales towards infinity.
* Big O analysis is often a big part of interviews - many interviewers will expect you to be able to analyze how efficient your code is. Don't be intimidated! Analyzing time and space complexity is not as insane as it may sound to you at this point!
* **Instructor Note**: Explain to the students that we will only cover time complexity in this short lesson, space complexity will be covered in the next lesson.

### Instructor Talk: But Wait, What in the World is an Algorithm?
* An algorithm, or algo, is just a function or collection of functions that accomplish a specific task.
* For example, we have all used Google. Google uses a extremely powerful search algorithm in order to find your results as fast as possible when you search for something!
* Another algo you may have been exposed to at this point is Bubble Sort. Bubble sort is an inefficient, but basic, sorting algorithm. More on its inefficiencies later!

### Instructor Talk: Big O - Time Complexity
* In calculating how efficient algorithms are time wise, we need to evaluate how many operations the algo must utilize to return a result. There is a best-case, worst-case, and average case scenario. Today, we will not focus much on these separate cases, instead looking at the 'approximate' worst-case scenario.
* In a simple sense, Big O describes, in a CS way, how code will respond to different inputs. Will it be much slower if we give it a 10,000 item long input, or even a million item long input?

* _Instructor Note_

### Students Do: Time Complexity
* Instructor: Slack out the following code to the students. Ask them to discuss with a partner(for 5min): 1) Is this an algorithm? Why? 2) In the worst case, how many iterations will the for loop run? 3) What is the best case for iterations?

```javascript
function searchThroughArray(arrayOfIntegers, targetInteger){
  for (var i = 0; i < arrayOfIntegers.length; i++) {
    if(arrayOfIntegers[i] === targetInteger){
      return true;
    }
  }
  return false;
};

```

### Instructor Do: Go Over searchThroughArray()
* Ask a stronger student to explain what the purpose of this algo is (its to return true if a given item is in a given array, false otherwise)
* Query the class about their answers to the questions. Help them expound on their answers, guiding them towards the following:
* It is absolutely an algorithm - you can think about it like an analog to `Array.prototype.includes`.
* Explain that its worst case scenario is that it has to go through all the items in the array, checking each one against the `targetItem`.
* The best case solution is that it finds the `targetItem` at the start of the array (position 0), and returns true.
* Instructor Note: Now comes the tricky part. We will go straight into time complexity, tell students to write down their questions if they have any and you will answer them at the end. Keep the ball rolling here!
* Now that we have a grasp on what our algo does, and what the worst case scenario is, we're ready to learn how to express that in Big O.
* **The time complexity of this algo can be expressed as O(n).**
* Explain to students that all time complexity is expressed as the function O (Hence, big O).
* The (n) part describes how many times we will have to "visit", or look at, each element of the input. In the worst case, we must look at every single item in the array. Once.
* Essentially, we will do

_**Instructor: Field questions at this point**_

##### Linear Time Graph
![Linear Time](linear-time.png)
* **Instructor note** Ask the class to raise their hands and describe how this graph represents O(n) Answers will likely be broad, help them narrow it down to the following:
  * As the input grows infinitely large, the rate of change remains constant.
  * The rate of change is n, or the length of the array for the case of `searchThroughArray()`
  * That means that as the input grows very large, the algo will take, at worst, as long as it takes to visit every element and do an equality check using `===`
  * Explain to the students that this equality check takes a constant amount of time in javascript, if this hasn't come up already in a question.
    * _Instructor Note_ Technically the time complexity is `O(n) + 1`, since we do a constant time operation each time we check equality. If the class is struggling, skip or gloss over this point and field more questions.
    * _Instructor Note_ If you cover this point, you will have to cover how time complexity reduces down to the most significant operation. Explain that as the input grows amazingly huge, adding one single operation to it won't make any difference. Prepare to field more questions here - students are oft confused here.

_**Instructor: Field questions at this point**_

### Students Do: Time Complexity Part 2
* Instructor: Slack out the following code to the students. Ask them to discuss with a partner(for 5min): 1) Is this a constant time algorithm? 2) If so, why?

```javascript
function returnLastElement(array){
  return array[array.length - 1]
}
```
### Instructor Do: Go Over returnLastElement()
* _Instructor Note_ Field student answers for a good 5-10 minutes here. Encourage discussion!
* If no one landed on the fact that this is constant time, state that, then move to explanation
* EXPLANATION:
  * Here we do four operations. We calculate the length of the array, subtract one from it, then access the array, and finally return that element we just accessed.
  * The length calculation students may think means we have to iterate the length of the array - we don't! Javascript is awesome in that it stores the length as a property of the array and updates it as needed. This is due to the fact that arrays are technically objects under the hood, but that's a discussion for office hours!
  * Subtracting one from that integer is another operation. This is generally constant time.
  * Accessing the array at the given index is **also** constant time - this is an inherent power of how arrays are built under the hood.
  * A return statement is constant time - we're passing a reference to the array element in memory.
  * So, we have a constant time overall! This algo will NEVER take longer, no matter if the array is a million items, or five items.

_**Instructor: Field questions at this point**_

### Class Do - Go Over Bubble Sort & Its Time Complexity
* At this point, we should all be somewhat familiar with Bubble Sort, covered in the last class.
* **Instructor Note**: poll the class. If students seem frustrated/lost or don't remember the concept of bubble sort well, slack out the below code and go through the comments with the class.

```javascript
function bubbleSort(array) {
  var length = array.length;
  for (var i = 0; i < length; i++) { //Number of passes
    for (var j = 0; j < (length - i - 1); j++) { //Notice that j < (length - i)
      //Compare the adjacent positions
      if(array[j] > array[j+1]) {
        //Swap the numbers
        var temp = array[j];  //Temporary variable to hold the current number
        array[j] = array[j+1]; //Replace current number with adjacent number
        array[j+1] = temp; //Replace adjacent number with current number
      }
    }        
  }
}
```

_**Instructor: Potential Live Demo.**_
* One effective tactic of visualizing Bubble Sort is to bring 4-5 students of varying heights up to the front of class. Organize them tallest to shortest. Then, making sure to call out each time we 'access' and swap them if need be.
* Show students how we have had to look at each person n(length of student 'array') times, even if there is no swap needed.
* If you're iffy about doing this, here is a digital demonstration: https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif

* This means we are performing many operations on each element by using nested `for` loops.
* Explain that we are performing n operations on each element, where n in the length of the input array
* This leads to a time complexity of O(n * n), or O(n<sup>2</sup>).
* Also mention to students that generally, nested `for` loops lead to O(n<sup>2</sup>) time complexity.
_**Instructor: Field questions at this point.**_

** If students want more on Bubble Sort, slack them this link at the end of class. http://codingmiles.com/sorting-algorithms-bubble-sort-using-javascript/. It goes through Bubble Sort step by step & covers it's Time Complexity in detail. For  now, more on to analyzing it.
