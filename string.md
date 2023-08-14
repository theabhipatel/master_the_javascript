# String 
covers all string methods in general.
---

#### 1. String.prototype.at() : 
The at() method of String values takes an integer value and returns a new String consisting of the single UTF-16 code unit located at the specified offset. This method allows for positive and negative integers. Negative integers count back from the last string character.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

let index = 5;

console.log(`Using an index of ${index} the character returned is ${sentence.at(index)}`);
// Expected output: "Using an index of 5 the character returned is u"

index = -4;

console.log(`Using an index of ${index} the character returned is ${sentence.at(index)}`);
// Expected output: "Using an index of -4 the character returned is d"
```

#### 2. String.prototype.charAt() : 
The charAt() method of String values returns a new string consisting of the single UTF-16 code unit at the given index. it returns the character at the specified index in the string.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// Expected output: "The character at index 4 is q"

```

#### 3. String.prototype.charCodeAt() : 
The charCodeAt() method of String values returns an integer between 0 and 65535 representing the UTF-16 code unit at the given index.

charCodeAt() always indexes the string as a sequence of UTF-16 code units, so it may return lone surrogates.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character code ${sentence.charCodeAt(index)} is equal to ${sentence.charAt(index)}`);
// Expected output: "The character code 113 is equal to q"
```

#### 4. String.prototype.codePointAt() : 
The codePointAt() method of String values returns a non-negative integer that is the Unicode code point value of the character starting at the given index. Note that the index is still based on UTF-16 code units, not Unicode code points.
```js
const icons = '☃★♲';

console.log(icons.codePointAt(1));
// Expected output: "9733"

```
#### 5. String.prototype.concat() : 
The concat() method of String values concatenates the string arguments to this string and returns a new string. Combines two or more strings and returns a new string.
```js
const str1 = 'Hello';
const str2 = 'World';
const str3 = 'My world'

console.log(str1.concat(' ', str2, ' ', str3));
// Expected output: "Hello World My world"

```

#### 5.5. String.prototype.startsWith() : 
The startsWith() method of String values determines whether this string begins with the characters of a specified string, returning true or false as appropriate.
```js
const str1 = 'Saturday night plans';

console.log(str1.startsWith('Sat'));
// Expected output: true

console.log(str1.startsWith('Sat', 3));
// Expected output: false
```

#### 6. String.prototype.endsWith() : 
The endsWith() method of String values determines whether a string ends with the characters of this string, returning true or false as appropriate.
```js
const str1 = 'Cats are the best!';

console.log(str1.endsWith('best!'));
// Expected output: true

console.log(str1.endsWith('best', 17));
// Expected output: true

const str2 = 'Is this a question?';

console.log(str2.endsWith('question'));
// Expected output: false
```

#### 7. String.prototype.includes() : 
The includes() method of String values performs a case-sensitive search to determine whether a given string may be found within this string, returning true or false as appropriate.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

const word = 'fox';

console.log(`The word "${word}" ${sentence.includes(word) ? 'is' : 'is not'} in the sentence`);
// Expected output: "The word "fox" is in the sentence"
```

#### 8. String.prototype.indexOf() : 
The indexOf() method of String values searches this string and returns the index of the first occurrence of the specified substring. It takes an optional starting position and returns the first occurrence of the specified substring at an index greater than or equal to the specified number.
```js
const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';

const searchTerm = 'dog';
const indexOfFirst = paragraph.indexOf(searchTerm);

console.log(`The index of the first "${searchTerm}" from the beginning is ${indexOfFirst}`);
// Expected output: "The index of the first "dog" from the beginning is 40"

console.log(`The index of the 2nd "${searchTerm}" is ${paragraph.indexOf(searchTerm, indexOfFirst + 1)}`);
// Expected output: "The index of the 2nd "dog" is 52"
```

#### 9. String.prototype.lastIndexOf() : 
The lastIndexOf() method of String values searches this string and returns the index of the last occurrence of the specified substring. It takes an optional starting position and returns the last occurrence of the specified substring at an index less than or equal to the specified number.
```js
const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';

const searchTerm = 'dog';

console.log(`The index of the first "${searchTerm}" from the end is ${paragraph.lastIndexOf(searchTerm)}`);
// Expected output: "The index of the first "dog" from the end is 52"
```

#### 10. String.prototype.match() : 
The match() method of String values retrieves the result of matching this string against a regular expression.
```js
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
const regex = /[A-Z]/g;
const found = paragraph.match(regex);

console.log(found);
// Expected output: Array ["T", "I"]
```

#### 11. String.prototype.matchAll() : 
The matchAll() method of String values returns an iterator of all results matching this string against a regular expression, including capturing groups.
```js
const regexp = /t(e)(st(\d?))/g;
const str = 'test1test2';

const array = [...str.matchAll(regexp)];

console.log(array[0]);
// Expected output: Array ["test1", "e", "st1", "1"]

console.log(array[1]);
// Expected output: Array ["test2", "e", "st2", "2"]
```

#### 12. String.prototype.padStart() : 
The padStart() method of String values pads this string with another string (multiple times, if needed) until the resulting string reaches the given length. The padding is applied from the start of this string.
```js
const str1 = '5';

console.log(str1.padStart(2, '0'));
// Expected output: "05"

const fullNumber = '2034399002125581';
const last4Digits = fullNumber.slice(-4);
const maskedNumber = last4Digits.padStart(fullNumber.length, '*');

console.log(maskedNumber);
// Expected output: "************5581"
```

#### 13. String.prototype.padEnd() : 
The padEnd() method of String values pads this string with a given string (repeated, if needed) so that the resulting string reaches a given length. The padding is applied from the end of this string.
```js
const str1 = 'Breaded Mushrooms';

console.log(str1.padEnd(25, '.'));
// Expected output: "Breaded Mushrooms........"

const str2 = '200';

console.log(str2.padEnd(5));
// Expected output: "200  "
```

#### 14. String.prototype.repeat() : 
The repeat() method of String values constructs and returns a new string which contains the specified number of copies of this string, concatenated together.
```js
const mood = 'Happy! ';

console.log(`I feel ${mood.repeat(3)}`);
// Expected output: "I feel Happy! Happy! Happy! "
```

#### 15. String.prototype.replace() : 
The replace() method of String values returns a new string with one, some, or all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function called for each match. If pattern is a string, only the first occurrence will be replaced. The original string is left unchanged.
```js
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replace('dog', 'monkey'));
// Expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"

const regex = /Dog/i;
console.log(p.replace(regex, 'ferret'));
// Expected output: "The quick brown fox jumps over the lazy ferret. If the dog reacted, was it really lazy?"

```

#### 16. String.prototype.replaceAll() : 
The replaceAll() method of String values returns a new string with all matches of a pattern replaced by a replacement. The pattern can be a string or a RegExp, and the replacement can be a string or a function to be called for each match. The original string is left unchanged.
```js
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replaceAll('dog', 'monkey'));
// Expected output: "The quick brown fox jumps over the lazy monkey. If the monkey reacted, was it really lazy?"

// Global flag required when calling replaceAll with regex
const regex = /Dog/gi;
console.log(p.replaceAll(regex, 'ferret'));
// Expected output: "The quick brown fox jumps over the lazy ferret. If the ferret reacted, was it really lazy?"
```

#### 17. String.prototype.search() : 
The search() method of String values executes a search for a match between a regular expression and this string, returning the index of the first match in the string.
```js
const paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';

// Any character that is not a word character or whitespace
const regex = /[^\w\s]/g;

console.log(paragraph.search(regex));
// Expected output: 43

console.log(paragraph[paragraph.search(regex)]);
// Expected output: "."

```

#### 18. String.prototype.slice() : 
The slice() method of String values extracts a section of this string and returns it as a new string, without modifying the original string.
```js
// slice(indexStart, indexEnd)
const str = 'The quick brown fox jumps over the lazy dog.';

console.log(str.slice(31));
// Expected output: "the lazy dog."

console.log(str.slice(4, 19));
// Expected output: "quick brown fox"

console.log(str.slice(-4));
// Expected output: "dog."

console.log(str.slice(-9, -5));
// Expected output: "lazy"

```

#### 19. String.prototype.split() : 
The split() method of String values takes a pattern and divides this string into an ordered list of substrings by searching for the pattern, puts these substrings into an array, and returns the array.
```js
const str = 'The quick brown fox jumps over the lazy dog.';

const words = str.split(' ');
console.log(words[3]);
// Expected output: "fox"

const chars = str.split('');
console.log(chars[8]);
// Expected output: "k"

const strCopy = str.split();
console.log(strCopy);
// Expected output: Array ["The quick brown fox jumps over the lazy dog."]

```

#### 20. String.prototype.substring() : 
The substring() method of String values returns the part of this string from the start index up to and excluding the end index, or to the end of the string if no end index is supplied.
```js
const str = 'Mozilla';

console.log(str.substring(1, 3));
// Expected output: "oz"

console.log(str.substring(2));
// Expected output: "zilla"

```

#### 21. String.prototype.toLowerCase() : 
The toLowerCase() method of String values returns this string converted to lower case.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

console.log(sentence.toLowerCase());
// Expected output: "the quick brown fox jumps over the lazy dog."
```

#### 22. String.prototype.toUpperCase() : 
The toUpperCase() method of String values returns this string converted to uppercase.
```js
const sentence = 'The quick brown fox jumps over the lazy dog.';

console.log(sentence.toUpperCase());
// Expected output: "THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG."

```

#### 23. String.prototype.toString() : 
The toString() method of String values returns this string value.
```js
const stringObj = new String('foo');

console.log(stringObj);
// Expected output: String { "foo" }

console.log(stringObj.toString());
// Expected output: "foo"

```

#### 24. String.prototype.trim() : 
The trim() method of String values removes whitespace from both ends of this string and returns a new string, without modifying the original string.
```js
const greeting = '   Hello world!   ';

console.log(greeting);
// Expected output: "   Hello world!   ";

console.log(greeting.trim());
// Expected output: "Hello world!";

```

#### 25. String.prototype.trimStart() : 
The trimStart() method of String values removes whitespace from the beginning of this string and returns a new string, without modifying the original string. trimLeft() is an alias of this method.
```js
const greeting = '   Hello world!   ';

console.log(greeting);
// Expected output: "   Hello world!   ";

console.log(greeting.trimStart());
// Expected output: "Hello world!   ";

```

#### 26. String.prototype.trimEnd() : 
The trimEnd() method of String values removes whitespace from the end of this string and returns a new string, without modifying the original string. trimRight() is an alias of this method.
```js
const greeting = '   Hello world!   ';

console.log(greeting);
// Expected output: "   Hello world!   ";

console.log(greeting.trimEnd());
// Expected output: "   Hello world!";

```

#### 23. String.prototype.valueOf() : 
The valueOf() method of String values returns this string value.
```js
const stringObj = new String('foo');

console.log(stringObj);
// Expected output: String { "foo" }

console.log(stringObj.valueOf());
// Expected output: "foo"
```


### Other Methods : 
- String.prototype.isWellFormed()
- String.prototype.toWellFormed()
- String.prototype.localeCompare()
- String.prototype.normalize()
- String.prototype.toLocaleLowerCase()
- String.prototype.toLocaleUpperCase()
- String.prototype.toWellFormed()

- String.raw()