# Json

**JSON** stands for JavaScript Object Notation. It is a format for structuring data. This format is used by different web applications to communicate with each other. It is the replacement of the XML data exchange format. It is easy to struct the data compare to XML. It supports data structures like arrays and objects and the JSON documents that are rapidly executed on the server.


### # Why JSON ?
It is a Language-Independent format that is derived from JavaScript. It is Human-readable and writable. It is a lightweight text-based data interchange format which means, it is simpler to read and write when compared to XML. Though it is derived from a subset of JavaScript, yet it is Language independent. Thus, the code for generating and parsing JSON data can be written in any other programming language.

**Syntax Rules :** Data is in name/value pairs and they are separated by commas. It uses curly brackets to hold the objects and square brackets to hold the arrays.

Example:
```js
{
    "Data Structures": [
        {
            "Name" : "Trees",
            "Course" : "Intoduction of Trees",
            "Content" : [ "Binary Tree", "BST",
                        "Generic Tree"]
        },
        {
            "Name" : "Graphs",
            "Topics" : [ "BFS", "DFS", "Topological Sort" ]
        }
    ]
}
```

### # Advantages of JSON:
- It stores all the data in an array so that data transfer makes easier. That’s why it is the best for sharing data of any size even audio, video, etc.
- Its syntax is very small, easy, and light-weighted that’s the reason it executes and responds in a faster way.
- It has a wide range for browser support compatibility with the operating systems. It doesn’t require much effort to make it all browser compatible.
- On the server-side parsing is the most important part that developers want. If the parsing will be fast on the server side then the user can get a fast response, so in this case, JSON server-side parsing is the strong point compared to others.


**Disadvantages of JSON :**

- The main disadvantage is that there is no error handling. If there was a slight mistake in the script then you will not get the structured data.
- It becomes quite dangerous when you used it with some unauthorized browsers. Like JSON service return a JSON file wrapped in a function call that has to be executed by the browsers if the browsers are unauthorized then your data can be hacked.
- It has limited supported tools that we can use during the development.


### # JSON Methods :

- JSON.stringify to convert objects into JSON.
- JSON.parse to convert JSON back into an object.

Example :
```js
const user = {
    name:'john',
    last:'doe',
    age:150,
}

// object to json

const jsonData = JSON.stringify(user)
console.log(jsonData)
// output : 
// {
//     'name':'john',
//     'last':'doe',
//     'age':150,
// }

// json to object
const objData = JSON.parse(jsonData)
console.log(objData)
// output :
// {
//     name:'john',
//     last:'doe',
//     age:150,
// }

```