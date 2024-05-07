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
At the core of JS, lies the concept of prototype. Every object in JS is associate with a protorype object, which acts as a **blueprint** for that object. 

In short; object prototype servers as  a template for creating new objects.

This prototype object contains properties and method that are accessible to all instances created from it.🍰

**Inheritance** is acheived by linking objects through their prototypes. 
Consider **Object.create()**  that we used above. It is an method that creates a new object.

### Static Method

(Code snippets are in proper formats, do try too see result)

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
			    console.log(`I am ${this.name}. and I ${this.eatsAppleDaily ? "eat" :"don't eat"} apple daily.`);
			  }
			};
		
		const myFriend = Object.create(me); // Creating a myFriend Object inheriting from me. He is my child now😃.  
			
		myFriend.name = "Ladoo";
		myFriend.eatsAppleDaily = true;

		console.log(me.printAbout());
		// Expected Output: I am Abhishek. and I don't eat apple daily.
		console.log(myFriend.printAbout());
		// Expected Output: I am Ladoo. and I eat apple daily.
	```

6. **Object.entries()**
	
	Return array of he given object's own enumerable string-keyed property key-value pair😒.
	It returns an array where each element is a key-value pair of the object. Each key-value pair si represented as an array with two elements: the key as the first element and the corresponding value as the second element.

   	```js
		const me = { name:"Abhishek", age:21 }
		console.log(Object.entries(me))
		// Expected output: [ [ 'name', 'Abhishek' ], [ 'age', 21 ] ]
	```

7. **Object.fromEntries()**
		Object.fromEntries transforms a list of key-value pairs into an object.
		TL;DR Opp. of Object.entries().

	```js
		const me = [ [ 'name', 'Abhishek' ], [ 'age', 21 ] ]
		console.log(Object.fromEntries(me))
		// Expected output: { name: 'Abhishek', age: 21 }
	```
	
9. **Object.groupBy()**

10. **Object.freeze()**
		The Object.freeze() is a method that "freezes" an object. When you freeze an object, you prevent new properties from being added to it, existing properties from being removed or changed, and also prevent the prototype from being changed.
		
	```js
		const me = { name:"Abhishek", age:21 }
		Object.freeze(me); // Freezing the object
		me.name = "scorcism";
		me.age = 22;
		console.log(me) 
		// Expected output: { a: 1, b: 2 }
	```
	You can see changes are not affected to the object
	
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

Now, lets focus on 
### Inheritance static method

1. bind
2. call
3. apply
4. toString

These are the most common one to use, You can explore more [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) 
