### Part1

For reversed(int[] arr) method in ArrayExamples.java:

A failure-inducing input for the buggy program: 
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
@Test public void testReversed1() { 
    int[] input1 = {3,4,5}; 
    assertArrayEquals(new int[]{5,4,3}, ArrayExamples.reversed(input1)); 
    } 
```
The result is: Expected [5] but was [0]

An input that doesn’t induce a failure:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
@Test 
	public void testReverseInPlace1() {
    int[] input1 = { };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ }, input1);
	}
```

Symptom:

