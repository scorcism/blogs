
## JavaScript Objects
Similar to other programming languages javascript objects is a collection of key-value pairs, where each key is a string and each value can be of any data type. 

### Ways to create JavaScript Object
1. **Object liternal Notation**
	The simplests way that you will use 98% of time.
	```js
		const scorcism = {
			name: "Abhishek",
			age:21
		}
	```
	The key-value pairs are enclosed within curly braces `{}`
2. **Using the `new` Keyword**
	Creating objects with constructor functions and the `new` keyword. You will use this only 1.8% of the time
	```js
		function About(name, age, city) {
		    this.name = name;
		    this.age = age;
		    this.city = city;
		}	
		
		const me = new About("Abhishek", 21, "Mumbai");	
	```
3. **Using Object.create()**
	This method allows creating a new object with specified prototype object. 
	You will use this only 0.2% of the time 
	```js
		const aboutData = {
			greet:function(){
					return `Hello, my is ${this.name}`; // {this.name} is the key of this object
				}
		}
		const me = Object.create(aboutData);
		me.name = 'Abhishek'
		me.age = 21;
	```
	Don't worry much about this :)
	
### Accessing Object Properties
Properties of JS object can be accessed using dot notation and bracket notation.
```js
	const me = {
			name: "Abhishek",
			age:21
	}
	console.log(me.name);	
	console.log(me["age"]);
```
Try run the code snippet. 
(The `undefined` after each console log is the return value fo the `console.log` function itself. Relax, Nothing to worry🕺)

### Object Prototypes and Inheritance
At the core of JS, lies the concept of prototype. Every object in JS is associated with a prototype object, which acts as a **blueprint** for that object. 

In short; object prototype serves as  a template for creating new objects.

This prototype object contains properties and method that are accessible to all instances created from it.🍰

**Inheritance** is acheived by linking objects through their prototypes. 
Consider **Object.create()**  that we used above. It is an method that creates a new object.

### Static Method

(Code snippets are in proper formats, do try😃)

1. **Object.keys()**

	Returns an array of a given object's own enumerable property **names**. 
	TL;DR Object.keys() method will return list of keys. 
	
	**NOTE:** Own enumerable refers to the properties of an object that are both owned by the object itself (Not inherited from its property chain) 
	
	```js
		const aboutMe= {
			name: "Abhishek",
			age:21
		}
		let aboutMeKeys = Object.keys(aboutMe);
		// Expected Output: [ 'name', 'age' ]
	```

2. **Object.values()**

	Return an array of a given object's own enumerable property **values**.
	
	TL;DR Object.values() method will return list of values.

	```js
				const aboutMe= {
					name: "Abhishek",
					age:21
				}
				let aboutMeKeys = Object.values(aboutMe);
				// Expected Output: [ 'Abhishek', 21 ]
	```

4. **Object.assign()**

	Copies the values of all enumerable own properties from one or more source objects to a target object.
	```js
		const target = {age: 21}
		const source = {name: "Abhishek"}
		const merged = Object.assign(target, source);
		console.log(merged)
		// Expected Output: { age: 21, name: 'Abhishek' }
	```
	**Note:** You can add any number of source args. 
	
	**target** will contain the modified object.
	
	```js
		console.log(merged === target)
		// Expected Output: true
	```
5. **Object.create()**

	Create new object, using an existing object as the prototype.
	
	```js
		const me = {
			  name: "Abhishek",
			  eatsAppleDaily: false,
			  printAbout: function(){
			    console.log(`I am ${this.name}. and I ${this.eatsAppleDaily ? "eat" :"don't eat"} 
							    apple daily.`);
			  }
			};
		
		// Creating a myFriend Object inheriting from me. 
		const myFriend = Object.create(me); // He is my child now😃.  
		
		myFriend.name = "Ladoo";
		myFriend.eatsAppleDaily = true;

		console.log(me.printAbout());
		// Expected Output: I am Abhishek. and I don't eat apple daily.
		console.log(myFriend.printAbout());
		// Expected Output: I am Ladoo. and I eat apple daily.
	```

6. **Object.entries()**
	
	Return array of he given object's own enumerable string-keyed property key-value pair😒.
	
	It returns an array where each element is a key-value pair of the object. Each key-value pair is represented as an array with two elements: the key as the first element and the corresponding value as the second element.

   	```js
		const me = { name:"Abhishek", age:21 }
		console.log(Object.entries(me))
		// Expected output: [ [ 'name', 'Abhishek' ], [ 'age', 21 ] ]
	```

7. **Object.fromEntries()**
		Object.fromEntries transforms a list of key-value pairs into an object.
		TL;DR Oppsite of Object.entries().

	```js
		const me = [ [ 'name', 'Abhishek' ], [ 'age', 21 ] ]
		console.log(Object.fromEntries(me))
		// Expected output: { name: 'Abhishek', age: 21 }
	```
	
10. **Object.freeze()**
		The Object.freeze() is a method that "freezes" an object. 

	When you freeze an object, you prevent new properties from being added to it, existing properties from being removed or changed, and also prevent the prototype from being changed.
			
	```js
			const me = { name:"Abhishek", age:21 }
			Object.freeze(me); // Freezing the object
			me.name = "scorcism";
			me.age = 22;
			console.log(me) 
			// Expected output: { a: 1, b: 2 }
	```
	Changes are not affected to the object
		
11. **Object.isFrozen()**
		 Determines if the object is frozen
	```js
		const me = { name:"Abhishek", age:21 }
		Object.freeze(me); 
		console.log(Object.isFrozen(me))
		// Expected output: true
	```
 
12. **Object.seal()** 
		Object.seal() is a method that "seals" an object.
		
	Sealing an object prevent new properties from being added to it and marks all existing properties an non-configurable (i.e prevent them from bein deleted or theri attributes from being changed).
	```js
		 const me = { name:"Abhishek", age:21 }
		 Object.seal(me); 
		me.name = "scorcism"; // This change will be affected 
		delete me.age; // This deleting will not take effect
		console.log(me)
		// Expected Output: { name: 'scorcism', age: 21 }
	```
	
	**Note:** `Object.freeze()` prevents any changes to the object, while `Object.seal()` allows changes to existing properties but prevents addition or removal of properties.
		 
12. **Object.isSealed()** 
			Determines if an object is sealed.
	```js
		const me = { name:"Abhishek", age:21 }
		 Object.seal(me); 	
		 console.log(Object.isSealed(me));
		 // Expected output: true
	```


### Inheritance static method

Before moving to instance method, Lets get idea of `this` keyword in object

Suppose we have an Object
```js
	const person = { name: 'Abhishek' };
```
So If we add a function in the object; `this` will refer to all the properties of the same object 
```js
	const person = { 
		name: 'Abhishek',
		sayMyName: function() {
			return `My name is ${this.name}`;
		}
	};

	console.log(person.sayMyName());
	// Expected Output: My name is Abhishek
```
As you can observe here, `this.name` is replaced with the key `name` value.

Now that you have idea of `this` keyword use, lets continue further

1. **prototype.bind()**
	The `bind()` method creates a new function that, when called, has its `this` keyword set to the provided value.
	This is usefull when we want to borrow a method from one object and use it in the context of other object,
```js
	function sayMyName (){
		return `My name is ${this.name}`
	}
	
	const person = { 
		name: 'Abhishek',
		sayMyName: sayMyName
	};
	
	console.log(person.sayMyName());
	// Expected Output: My name is Abhishek
	
	const person2 = {
		name: 'Walter'
	}
	
	const person2NameFunc = sayMyName.bind(person2);
	
	console.log(person2NameFunc());
	// Expected Output: My name is Walter
	
```

for the person2NameFunc the person object `this.name` is taken from the person2 object as we have bind the `sayMyName` function with person2 object.

2. **prototype.call()**
	The `call()` method is used to call a function with given `this` value and arguments provided individaully.
	```js
		function introduce(language) {
			  console.log(`I code in ${language}. My name is ${this.name}.`);
		}
		
		const mySelf = {
			name: "Abhishek"
		}

		introduce.call(mySelf, 'Java');
		// Expected output: I code in Java. My name is Abhishek.
		
	```
	here; we have a function `introduce` that take an argument language and it simples does a console log of language and name. So to pass name to the function we have a object `mySelf` that has a key `name`. So using `bind` we did bind the function with the object so that function now have access to the object keys.


3. **prototype.apply()**
	The `apply()` method is similar to `call()`, but insted of accepting arguments individually, it accepts arguments as an array.
	```js
		function add(...args){
			let sum = args.reduce((acc, curr)=> acc + curr, 0 );
			console.log(sum);
		}
		const numbers = [1,2,3,4,5];
		add.apply(null, numbers)
		// Expected output: 15
	```

### When to use call, bind and apply
- **call**:  Use `call` when you want to execute a function immediately and specify what `this` should refer to
- **bind**: Use `bind` when you want to create a new function that, when executed later, has a predeterminf `this` value
- **apply**" Use `apply` when you have an array of arguments that you want to pass to a function.

---
PS: The reason to use my name everywhere is that, while reading, whenever you see my name, you will tend to try it with your name too

These are the most common one to use, You can explore more [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye🍕**
