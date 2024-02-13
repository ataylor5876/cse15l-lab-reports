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

![Image](Lab5Symptom.png)
* Fixed Code
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    double numLowest = arr.length;
    for(double num: arr) {
      if(num != lowest) { sum += num; numLowest--; }
    }
    return sum / (arr.length - numLowest);
  }
```
> The original code didn't account for a situation in which the array passed in had multiple copies of the lowest number. So, I added a counter variable to keep track of the number of copies of the lowest variable and subtracted it from arr.length at the end instead of 1.
## Part 2 (Find)
* [Information Source for all Options](https://tecadmin.net/linux-find-command-with-examples/)
* -name
> Working directory for both examples: ~/Documents/UCSD Documents/Winter 2024 Classes/CSE 15L/CSE 15L Lab 5/docsearch
```
$ find ./technical -name 'chapter-8.txt'
./technical/911report/chapter-8.txt
```
```
$ find ./technical -name 'athena-taylor.txt'

```
> find [PATH] -name [EXPRESSION] searchs through the directory provided via PATH for files and directories named the string provided via EXPRESSION. As you can see in the first example, if it finds a file or directory that matches the name provided, it will return the path of the file or directory. As you can see in the second example, it won't return anything if it cannot find a file or directory that matches the criteria. This command is useful if you're trying to find a specific file in a massive repository.
* -type
> Working directory for both examples: ~/Documents/UCSD Documents/Winter 2024 Classes/CSE 15L/CSE 15L Lab 5/docsearch
```
$ find ./technical -type f | head
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
```
```
$ find ./technical -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems  
./technical/government/Env_Prot_Agen     
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm    
./technical/plos
```
> find [PATH] -type [EXPRESSION] searches through the directory provided by PATH and outputs the path of everything that is the type provided by EXPRESSION. In the first example, EXPRESSION was f, so the computer outputted the paths of all the files in the technical directory. Since I also used the head command, it only printed out the paths of the first 10 files it found. In the second example, EXPRESSION was d, so the computer outputted the paths of all the directories contained in the technical directory. The command is useful when you want to separate files by type.
* -size
> Working directory for both examples: ~/Documents/UCSD Documents/Winter 2024 Classes/CSE 15L/CSE 15L Lab 5/docsearch
```
$ find ./technical -size +200k
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```
```
$ find ./technical -size -50k | head
./technical
./technical/911report
./technical/911report/chapter-10.txt
./technical/911report/preface.txt
./technical/biomed
./technical/biomed/1468-6708-3-1.txt
./technical/biomed/1468-6708-3-10.txt
./technical/biomed/1468-6708-3-3.txt
./technical/biomed/1468-6708-3-4.txt
./technical/biomed/1468-6708-3-7.txt
```
