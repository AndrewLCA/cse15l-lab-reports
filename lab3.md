# Lab Report 3 - Bugs and Commands #

## Reverse Array Method ## 
**Failure Inducing Test Cases**
```
@Test 
	public void testReverseInPlaceOdd() {
    int[] input1 = { 3,2,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,2,3 }, input1);
	}

  @Test 
  public void testReverseInPlaceEven()
  {
    int[] input1 = {1,2,3,4}; 
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] {4, 3,2,1}, input1);
  }
```
**Test Case without Failure**
```
@Test 
  public void testReverseInPlace()
  {
    int[] input1 = {1}; 
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] {1}, input1);
  }
```
**JUnit Test Using Bash**
```
set -e 
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java                              
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
```
**Output**

![image](JUnit Test Bug.png)

**Reverse Array Code with Bug**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  ```

**Reverse Array Code without Bugs**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i ++) 
    {
      int temp = arr[i]; 
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp; 
    }
  }
```





