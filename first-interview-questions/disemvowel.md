# Disemvowel


## Prompt

Write a function that accepts a String as input and returns
a String with all vowels removed.


## Clarifying Questions & Assumptions

Answers to questions the fellows may ask:
* Is "y" considered a vowel? _Yes_
* Could the input String ever be null? _Yes_
* Should the function do anything with spaces or punctuation? _No; leave them as is_
* Can I used a regular expression? _Kudos for the idea, but let's do it without regex_

## Sample Inputs & Outputs

* `disemvowel("Hello World!")` returns `"Hll Wrld!"`
* `disemvowel("abcdef")` returns `"bcdf"`
* `disemvowel("")` returns `""`
* `disemvowel("aaa eee")` returns `"  "`

## Hints

If a fellow has been stuck for several minutes,
it's OK to offer a hint to keep things moving:
* If they really don't know where to begin, ask how they might be able to look at each character in the string one at a time. (i.e. iterate over it with a loop)
* If they don't know what to do inside the loop, ask what it is that we want to determine about each character. (i.e. check whether it's a vowel)
* If they're stuck trying to modify the input String, point out it's OK to create a new String to return.


## Solution Overview

General steps:
* Declare a empty String that will be populated with our return value
* Iterate through the characters of the input String with a loop
* For each character check if it is a vowel (aeiouy)
  * If yes, continue to next loop iteration
  * If no, concatenate onto the end of the output String
* After loop is done, return output String


## Solution Code

```java
// Java
public static String disemvowel(String str) {
  if (str == null || str.isEmpty()) {
    return str;
  }

  StringBuilder sb = new StringBuilder();

  for (int i = 0; i < str.length()) {
    if (!isVowel(str.charAt(i))) {
      sb.append(str.charAt(i));
    }
  }
  return sb.toString();
}

public static boolean isVowel(char c) {
  c = Character.toLowerCase(c);
  return c == 'a' ||
    c == 'e' ||
    c == 'i' ||
    c == 'o' ||
    c == 'u' ||
    c == 'y';
}
```


```javascript
// Javascript
function disemvowel(str) {
  if (str == null || str === "") {
    return str;
  }

  var output = "";

  for (var i = 0; i < str.length; i++) {
    if (!isVowel(str[i])) {
      output += str[i];
    }
  }

  return output;
}

// Helper method is optional! Can include this logic in disemvowel method.
function isVowel(char) {
  char = char.toLowerCase();
  return char === 'a' ||
    char === 'e' ||
    char === 'i' ||
    char === 'o' ||
    char === 'u' ||
    char === 'y';
}
```

```swift
//Swift
func disemvowel(_ str: String) -> String {
    let vowels = "aeiouy"
    return str.filter{!vowels.contains(Character(String($0).lowercased()))}
}
```
