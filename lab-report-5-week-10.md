# Lab Report 5 - Analyzing Different Outputs
*Author: Matthew Tan*

Instructions: <br>
In lab 9, you experimented with the many tests provided from commonmark-spec. For this lab report, choose any two tests from the 652 commonmark-spec tests where your implementation (or a representative implementation from your group) had different answers than the implementation we provided for lab 9. Note that this is the implementation in the markdown-parse repository, not the one you did today in lab 10. The tests with different answers should correspond to different bugs – that is, you couldn’t easily fix both with one code change.

Explain: <br>
- How you found the tests with different results (Did you use diff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)
- For each test: <br>
    - Describe which implementation is correct, or if you think neither is correct, by showing both actual outputs and indicating what the expected output is.
    - For the implementation that’s not correct (or choose one if both are incorrect), describe the _bug (the problem in the code). You don’t have to provide a fix, but you should be specific about what is wrong with the program, and show the code that should be fixed.

<br>

<a target="_blank" rel="noopener noreferrer" href="https://github.com/ucsd-cse15l-w22/markdown-parse/tree/main/test-files">commonmark-spec test files</a>

## How did I find the tests with different results?

I found both of the tests with different results simply by manually checking outputs. Using this method, it did not take me very long to find different results between my implementation of MarkdownParse and the one given in week 9.

## Analyzing Output - Test File 1

### 1. Which implementation was correct?
Output from my implementation: <br>


<br>

Output from given implementation: <br>


<br>

### 2. The bug behind the symptom(s):



<br>

## Analyzing Output - Test File 2

### 1. Which implementation was correct?
Output from my implementation: <br>


<br>

Output from given implementation: <br>


<br>

### 2. The bug behind the symptom(s):


