
# PS

2726. Calculator with Method Chaining


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



