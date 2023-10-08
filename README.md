
# PS



# 2620. Counter

Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).

 

Example 1:

Input: 
n = 10 
["call","call","call"]
Output: [10,11,12]
Explanation: 
counter() = 10 // The first time counter() is called, it returns n.
counter() = 11 // Returns 1 more than the previous time.
counter() = 12 // Returns 1 more than the previous time.
Example 2:

Input: 
n = -2
["call","call","call","call","call"]
Output: [-2,-1,0,1,2]
Explanation: counter() initially returns -2. Then increases after each sebsequent call.


Solution

/**
 * @param {number} n
 * @return {Function} counter
 */
var createCounter = function(n) {  

    return function() { 
         return n++;
    };
};

/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */



// Using an ES6 class:
class Counter {
  constructor(start) {
    this.count = start;
  }
  next() {
    return this.count++;
  }
}

const counter = new Counter(10);
console.log(counter.next()); // 10
console.log(counter.next()); // 11
console.log(counter.next()); // 12



// Using a generator function:

function* createCounter(start) {
  let count = start;
  while (true) {
    yield count++;
  }
}

const counter = createCounter(10);
console.log(counter.next().value); // 10
console.log(counter.next().value); // 11
console.log(counter.next().value); // 12















# 2726. Calculator with Method Chaining


class Calculator {
  
  /** 
   * @param {number} value
   */
  constructor(value) {
      this.result = value;
  }

  /** 
   * @param {number} value
   * @return {Calculator}
   */
  add(value){
    this.result += value;
    return this;
  }

  /** 
   * @param {number} value
   * @return {Calculator}
   */
  subtract(value){
    this.result -= value;
    return this;

  }

  /** 
   * @param {number} value
   * @return {Calculator}
   */  
  multiply(value) {
    this.result *= value;
    return this;

  }

  /** 
   * @param {number} value
   * @return {Calculator}
   */
  divide(value) {
    if (value === 0) {
      throw new Error("Division by zero is not allowed");
    }
    this.result /= value;
    return this;
  }
  
  /** 
   * @param {number} value
   * @return {Calculator}
   */
  power(value) {
    this.result **= value;
    return this;

  }
    
  /** 
   * @return {number}
   */
  getResult() {
      return this.result;
   
  }
}



2727. Is Object Empty

Given an object or an array, return if it is empty.

An empty object contains no key-value pairs.
An empty array contains no elements.
You may assume the object or array is the output of JSON.parse.

 

Example 1:

Input: obj = {"x": 5, "y": 42}
Output: false
Explanation: The object has 2 key-value pairs so it is not empty.
Example 2:

Input: obj = {}
Output: true
Explanation: The object doesn't have any key-value pairs so it is empty.
Example 3:

Input: obj = [null, false, 0]
Output: false
Explanation: The array has 3 elements so it is not empty.
 
Constraints:

obj is a valid JSON object or array
2 <= JSON.stringify(obj).length <= 105

# Solution
/**
 * @param {Object|Array} obj
 * @return {boolean}
 */
 
var isEmpty = function(obj) {
return Object.values(obj).length === 0
};  



