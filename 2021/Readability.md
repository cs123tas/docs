# CSCI 1230 Readability Guidelines

Follow these guidelines, and you'll have a **lovelier** relationship with your code (**and your grade**)!

## Table of Contents

* [Naming](#naming)
* [Whitespace](#whitespace)
* [Comments](#comments)
* [Line Width](#line-width)

## Naming
**Name your variables appropriately.** `Humans` are not `Computers`. `TAs` are a subclass of `Humans`. And so are `You`. Use good naming practices

### :(
```cpp
float q(a, b, c) {
  float t = b * b - sqrtf(4 * a * c);
  float bm = 2 * a;
  float r = t / bm;
  return r;
}
```

### :)
```cpp
float quadraticFormula(a, b, c) {
  float top = b * b - sqrtf(4 * a * c);
  float bottom = 2 * a;
  float result = top / bottom;
  return result;
}
```

### Keep in Mind
* Member variables should be prefixed with `m_`. You will see our support code do this!
* Class names should be `StyledLikeThis`.
* Variable and function names should be `styledLikeThis`.
* Constants and macros should be `STYLED_LIKE_THIS`.

## Whitespace
**Indent your code.** Indents make your code much more readable. It also helps you keep track of scope and avoid nasty little typos!

**Use newlines to denote sections of code**. If your code can be broken into little sections, **do it!**

**USE COMMON SENSE!!!**

### :(
```cpp
int getFibonacciAt(int index) {
if (index == 0) return 0;


if (index == 1) return 1;
int num1 =           0;
int num2 = 1;




int num3 = 1;
    while (index    > 2) {
int prevNum3 = num3;
num3 =       num1 + num2;
num1 =   num2;
num2 = prevNum3;
            index --;
}
               return
num3;
}
```
(*slightly* exaggerated)

### :)
```cpp
int getFibonacciAt(int index) {
  if (index == 0) return 0;
  if (index == 1) return 1;
  
  int num1 = 0;
  int num2 = 1;
  int num3 = 1;
  
  while (index > 2) {
    int prevNum3 = num3;
    
    num3 = num1 + num2;
    num1 = num2;
    num2 = prevNum3;
    
    index --;
  }
  
  return num3;
}
```

## Comments

**Comments are good.** Comments make your code readable. Comments make your code maintainable. Use comments.

### :(
```cpp
int led(std::string word1, std::string word2) {
  int len1 = word1.size();
  int len2 = word2.size();
    
  if (len1 == 0) return len2;
  if (len2 == 0) return len1;
  
  int cost;
  
  if (word1[len1 - 1] == word2[len2 - 1]) {
    cost = 0;
  } else {
    cost = 1;
  }
  
  std::string short1 = word1.substr(0, len1 - 1);
  std::string short2 = word2.substr(0, len2 - 1);
  
  return std::min(std::min(
    led(short1, word2) + 1,
    led(word1, short2) + 1),
    led(short1, short2) + cost
  );
}
```

### :)
```cpp
/*
 * Levenshtein edit distance. Calculates the minimum number of changes (removing
 * a letter, adding a letter, or substituting a letter) to a word required to be
 * the same as a second word.
 * Is case sensitive.
 *
 * @param word1 {std::string} The first word to use for the comparison.
 * @param word2 {std::string} The second word to use for the comparison.
 *
 * @return {int} The minimum edit distance calculated using Levenshtein edit distance.
 */
int led(std::string word1, std::string word2) {
  // Get the length of the two words for future use.
  int len1 = word1.size();
  int len2 = word2.size();
  
  // If either one of the strings is empty, then the edit distance becomes the
  // length of the other one. 
  if (len1 == 0) return len2;
  if (len2 == 0) return len1;
  
  // This is where we're going to store the cost of editing the last character of
  // either string.
  int cost;
  
  // Get said cost!
  if (word1[len1 - 1] == word2[len2 - 1]) { // If the last characters are the same,
    cost = 0; // No cost.
  } else { // Otherwise,
    cost = 1; // It costs 1.
  }
  
  // Remove the last character from both strings for the next recursive iteration.
  std::string short1 = word1.substr(0, len1 - 1);
  std::string short2 = word2.substr(0, len2 - 1);
  
  // Finally, return the minimum edit distance if:
  return std::min(std::min(
    led(short1, word2) + 1,    // We remove one character from the first string,
    led(word1, short2) + 1),   // we remove one character from the second string,
    led(short1, short2) + cost // Or we remove one character from both strings.
  );
}
```

## Line Width

Unfortunately, not everyone codes on an ultrawide monitor *(they are the future, I swear)*! Try to keep your lines **to a reasonable length!**

### :(
```cpp
int addFiveNumbers(int num1, int num2, int num3, int num4, int num5) { return (num1 + num2 + num3 + num4 + num5); }
```
(*Why?*)

### :)
```cpp
int addFiveNumbers(int num1, int num2, int num3, int num4, int num5) {
  return (num1 + num2 + num3 + num4 + num5);
}
```
