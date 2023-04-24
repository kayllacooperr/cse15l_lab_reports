# Lab #2 Servers and Bugs
*April 24, 2023*

>Part 1: String Server

>Part 2: Lab 3 Bugs

The reversed() method given originally is shown below. It's goal is to take in an array and return a 
new array with the elements in reversed order.

```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After trying multiple JUnit Tests, I deduced that the code would only work in empty and one-element 
arrays, such as { } or {3}. 
```
@Test
 public void testReversed1() {
   int[] input1 = { };
   ArrayExamples.reverseInPlace(input1);
   assertArrayEquals(new int[]{ }, input1);
 }
```
But wouldn't work any bigger arrays, such as {1,2,3,4}.
```
@Test
 public void testReversed3() {
   int[] input1 = {1, 2, 3, 4};
   assertArrayEquals(new int[]{4, 3, 2, 1}, ArrayExamples.reversed(input1));
 }
```
As shown when only the empty/one-element arrays passed the JUnit tests, while the other arrays
did not.

![Junit Output](lab3_junit_output.png)

After the testing, I realized that there were two bugs causing the symptoms. The original assigned 
the elements of the new array to the original array (instead of vice versa) and also returned the 
original array rather than the new array. After fixing this, the working code looked like the 
following.

```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }
```

This works because now the for loop is assigning the elements in reverse order to the correct (new) array, and the method itself is returning the correct array.

>Part 3: What I Learned

Prior to week #2's lab and Lab Report #2, I had never used URLHandlers, ports, or any of the  
methods/classes we used. Considering the whole concept was new to me, I learned a lot about the basics of web servers and how to manipulate them and their methods to produce different outputs.
