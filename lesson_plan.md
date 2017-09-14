# An Introduction to Big O & Algorithms

### **Instructor Note**
This lesson is meant to be taught immediately after students have been exposed to basic algorithm writing and bubble sort on the first whiteboarding day. It is very valuable and highly recommended to stop and take questions often from students - many will feel confused and/or overwhelmed after the first whiteboarding day. Especially so if they do not have a background in math of computer science. There are already scheduled question periods denoted through the lesson. If students are having a difficult time articulating what they don't understand, have them get together in groups of 2-3 and write out a list of things they can't figure out. Have them slack you these, and go through them during the question periods.

### **Class Goals**
* This lesson seeks to begin go over what Big O is, introduce students to the notion of time complexity, and show them how to calculate & express it in Big O notation.
* Go over linear, constant, and O(n<sup>2</sup>) time complexity.
* Have students understand enough in order to begin seeing what time complexities they are introducing into their own code.
* **NOTE: This is a lecture & discussion heavy class. No question is too simple or stupid today - emphasize this to students at the start of class.**

## Instructor Talk: What is Big O?
* Start out by welcoming students, and letting them know that this will be one of the more challenging classes. It will introduce completely new concepts in Computer Science.
* Big O, also known as time & space complexity, is a way computer scientists measure how memory efficient or fast an algorithm is as the given input grows larger & larger.
* This is really just fancy CS talk for: We want our algorithms to run as quickly as possible, and use as little computer memory as possible. As the input scales towards infinity.
* Explain that as they may have guessed, time complexity is essentially a measure of how fast code runs, and space complexity is a measure of how much memory it will take up. **Emphasize that this is all relative to the input**.
* **Instructor Note**: Let students know that we will only cover basic time complexity in this lesson, more advanced concepts & space complexity will be covered in the next lesson.

### Instructor Talk: But Wait, What in the World is an Algorithm?
* An algorithm, or algo, is just a function or collection of functions that accomplish a specific task.
* For example, we have all used Google. Google uses a extremely powerful search algorithm in order to find your results as fast as possible when you search for something!
* Another algo you may have been exposed to at this point is Bubble Sort. Bubble sort is an inefficient, but basic, sorting algorithm. More on its complexity later this lesson!

### Instructor Talk: Big O - Time Complexity
* Go over how in calculating how efficient algorithms are time wise, we need to evaluate how many operations the algo must do to return a result. There is a best-case, worst-case, and average case scenario. Today, we will not focus much on these separate cases, instead looking at the 'approximate' worst-case scenario.
* Explain how Big O describes, in a computer science way, how code will respond to different inputs. Will it be much slower if we give it a 10,000 item long input, or even a million item long input, as opposed to a 5 item input?



### Students Do: Time Complexity
* Instructor: Slack out the following code to the students. Ask them to discuss with a partner(for 5min):
1) Is this an algorithm? Why?
2) In the worst case, how many iterations will the for loop run?
3) What is the best case for iterations?

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
  * Its worst case scenario is that it has to go through all the items in the array, checking each one against the `targetItem`.
  * The best case solution is that it finds the `targetItem` at the start of the array (position 0), and returns true.
* **Instructor Note:** Now comes the tricky part. We will go straight into Big O notation. Be ready to field questions and explain how the    notation is just a CS way of describing the runtime relative to the input, which is usually denoted as `n`.
* Now that we have a grasp on what our algo does, and what the worst case scenario is, we're ready to learn how to express that in Big O.
* **The time complexity of this algo can be expressed as O(n).**
* Explain to students that all time complexity is expressed as the function O (Hence, big O), and the argument(s) to that function is the number of operations relative to the input size (denoted as `n`).
* The (n) part describes how many operations the algo will do on elements of the input.
* Explain how, in this worst case scenario, we must look at every single item in the array. Once.

_**Instructor: Field questions at this point. Then go over the Reference Chart and let students know we just covered O(n), and will also cover O(1) and O(n<sup>2</sup>)**_
#### Common Big O Notations Reference - Listed Most Efficient to Least Efficient
* O(1) - Constant time
* O(log(n) - Logarithmic time
* O(n) - Linear time
* O(n<sup>2</sup>) - Quadratic Time
* O(m<sup>n</sup>) - Exponential  Time
* O(n!) - Factorial Time

##### Linear Time Graph
![Linear Time](linear-time.png)
* **Instructor note** Ask the class to raise their hands and describe how this graph represents O(n) Answers will likely be broad, help them narrow it down to the following:
  * As the input grows infinitely large, the rate of change remains constant.
  * The rate of change is n; aka the length of the array input for the case of `searchThroughArray()`
  * That means that as the input grows very large, the algo will take, at worst, as long as it takes to visit every element and do an equality check using `===`
  * Explain to the students that this equality check(when using ===) takes a constant amount of time in javascript for integers and strings.
    * _Instructor Note 1_ Technically the time complexity is `O(n) + 1`, since we do a constant time operation each time we check equality. If the class is struggling, skip or gloss over this point and field more questions.
    * _Instructor Note 2_ If you cover this point, you will have to cover how time complexity reduces down to the most significant operation. Explain that as the input grows amazingly huge, adding one single operation to it won't make any difference. Prepare to field more questions here - students are oft confused here.

_**Instructor: Field questions at this point**_

### Students Do: Time Complexity Part 2
* Instructor: Slack out the following code to the students. Ask them to answer the following questions with a partner, referencing the below function `returnLastElement`. Spend 5-7 minutes on this group discussion.
1) How many operations does this function do when given an array of length 5?

2) How many operations does this function do when given an array of length 10,000?

2) What do you think the Big O time complexity of this algorithm?


```javascript
function returnLastElement(array){
  return array[array.length - 1]
}
```
### Instructor Do: Go Over returnLastElement()
* _Instructor Note_ Field student answers for a good 5-10 minutes here. Encourage discussion!
* If no one landed on the fact that this takes constant time, state that, then move to explanation
* EXPLANATION:
  * Here we do four operations. We calculate the length of the array, subtract one from it, then access the array, and finally return that element we just accessed.
  * The length calculation students may think means we have to iterate the length of the array - we don't! Javascript is awesome in that it stores the length as a property of the array and updates it as needed. This is due to the fact that arrays are technically objects under the hood, but that's a discussion for office hours!
  * Subtracting one from that integer is another operation. This is generally constant time.
  * Accessing the array at the given index is **also** constant time - this is an inherent power of how arrays are built under the hood.
  * A return statement is constant time - we're passing a reference to the array element in memory.
  * So, we have a constant time overall! This algo will almost never take longer, no matter if the array is a million items, or five items.
  * _Instructor Note 1_ Technically the time complexity is `1 + 1 + 1 + 1`, or `O(4)`. If a student points this out, let them know that like the above example, Big O notation is almost always reduced down to its generic expression. Constant time algorithms are denoted by O(1), since O(4) will **also** take a constant amount of time.
  * _Instructor Note 1_ If students are confused about this fact, remind them that this constant time is always **relative**. Therefore, it doesn't matter if we do one or 100 constant time operations, the runtime will be the same for inputs of any size. AKA Constant Time!!

_**Instructor: Field questions at this point**_

### Class Do - Go Over Bubble Sort & Its Time Complexity
* At this point, we should all be somewhat familiar with Bubble Sort, covered in the last class.
* **Instructor Note**: poll the class. If students seem frustrated/lost or don't remember the concept of bubble sort well, slack out the below code and go through the comments with the class.

```javascript
// declare a variable that will act as a flag to let us know once the array has
// finished sorting
var sorted;
function bubbleSort(arr) {
  // everytime we iterate over the array, we know at least the last value has
  // been sorted, so we don't have to iterate to that index again
  var end = arr.length - 1;
  // set flag to true, if we have to swap any values, the flag will be then set
  // to false
  sorted = true;
  for (var i = 0; i < end; i++) {
    // if the value of the current index is less than the next index, we know
    // the list is not properly sorted and swap their positions.
    if (arr[i] > arr[i + 1]) {
      // we have to create a temporary variable to hold a value, so we can swap
      // the values of the two positions
      var temp = arr[i];
      arr[i] = arr[i + 1];
      arr[i + 1] = temp;
      sorted = false;
    }
  }
  end--;
}

do {
  bubbleSort(unsortedArr);
} while (!sorted);

```

_**Instructor: Potential Live Demo if Students are still fuzzy on Bubble Sort**_
* One effective tactic of visualizing Bubble Sort is to bring 4-5 students of varying heights up to the front of class. Organize them tallest to shortest. 'Sort' them shortest to tallen, making sure to call out each time we 'access' and swap them if need be. Have a student keep count of how many operations we have to do for each student.
* Reinforce that we have had to look at each person n(length of student 'array') times, even if there is no swap needed.
* If you're iffy about doing this, here is a digital demonstration: https://upload.wikimedia.org/wikipedia/commons/c/c8/Bubble-sort-example-300px.gif

* Go over the worst case scenario - the array is in reverse order, and each element must bubble up by being checked against each other element.
* Query students about how many operations the function performs on each element.
* Explain that we are performing n operations on each element in the worst case, where n in the length of the input array.
* This leads to a time complexity of O(n * n), or O(n<sup>2</sup>).
* Also mention to students that generally, nested loops lead to O(n<sup>2</sup>) time complexity.

_**Instructor: Field questions at this point.**_

## Instructor DO: Wrap Up & Motivate Students!
* This lesson can be particularly challenging for students without a strong math or CS background.
  * Emphasize that not all interviews involve whiteboarding and Big O analysis.
  * Also emphasize that understanding of these concepts will come with time. They are complex and folks spend entire 4 year degrees mastering them, only to get a PhD to truly master them.
  * Remind students that they can **always** practice Big O analysis on their own code! Encourage them to bring questions to office hours.
* Encourage students to look at online resources.
* End with the caveat that while optimizing and writing your functions in the most efficient way is great, there is a tenet in software engineering that sums up to: `Don't optimize if you don't need to`. As in, students should **not** be driving themselves nuts to not use nested loops in a homework - working code matters more than highly optimized buggy code at this point in their careers!

** If students want more on Bubble Sort & its time complexity, slack them this link at the end of class. http://codingmiles.com/sorting-algorithms-bubble-sort-using-javascript/. It goes through Bubble Sort step by step & covers it's Time Complexity in detail. For  now, more on to analyzing it.
