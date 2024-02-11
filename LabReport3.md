# CSE 15L Lab Report 3 - Bugs and Commands
By: Athena Taylor

***

## Part 1
* Bugged Code
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```
* Failure-inducing Input
```
@Test
  public void failureInducingInput() {
    double[] testArray = {2.0, 2.0, 4.0, 6.0};
    double expectedOutput = 5.0;
    double actualOutput = ArrayExamples.averageWithoutLowest(testArray); 
    assertEquals(expectedOutput, actualOutput, 0.001);
  }
```
* Non-failure-inducing Input
```
@Test
  public void nonFailureInducingInput() {
    double[] testArray = {2.0};
    double expectedOutput = 0.0;
    double actualOutput = ArrayExamples.averageWithoutLowest(testArray); 
    assertEquals(expectedOutput, actualOutput, 0.001);
  }
```
* Symptom
![Image](Lab5Symptom)
* Fixed Code
* 
