# How to use Reduce in JavaScript?

The [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) function of an `Array` is one of the most versatile functions in JavaScript. With it you can accomplish a lot of the functions from the [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) and [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) objects. It's job is to start with an array, and reduce those elements into some other type of data... which sounds vague, but you could use it to convert from an array to an object, an array to another array, an array to a number or an array to a boolean. Understanding how it works opens up a world of possibilities.

A few of the Math/Array functions we will cover in this article:

- [Math.min()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
- [Math.max()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
- [Array.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
- [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [Array.prototype.find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
- [Array.prototype.every()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
- [Array.prototype.some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
- [Array.prototype.flat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)

## Let's Recreate Reduce

Before we see all of reduce's flexibility, let's understand how it works! Reduce's job is to iterate over each element of an array, calling a function (callback), and passing both the current element and what is called an "accumulator" value. The callback's job is to take the accumulator and the array element and return the new version of that accumulator.

![reduce](https://cdn.hashnode.com/res/hashnode/image/upload/v1676893090127/y0OFvY81f.png?auto=compress)

This may mean taking an accumulator that is a number and returning its value + 1, or taking an accumulator which is an array and returning that array with an additional element on the end. It's up to you, depending what type of data you would like to _reduce_ your array to.

We also need an _initial value_, which will be the first value our accumulator takes before the callback is ever called.

```js
function reduce(array, callback, initial) {
  // start our accumulator off as the initial value
  let acc = initial;
  // iterate over each element in the array
  for (let i = 0; i < array.length; i++) {
    // pass the accumulator and current element to callback function
    // override the accumulator with the callback's response
    acc = callback(acc, array[i], i);
  }
  // return the final accumulator value
  return acc;
}

result = reduce([1, 2, 3], (acc, num) => acc + num, 0);
```
## Learn 10 different use cases of reduce()

The JavaScript reduce() method is very versatile, with some really handy use cases, even though it is widely considered to be the most confusing of all JavaScript iterators.

Let's take a look at some use cases for the JavaScript reduce() method.

### Counting Array Length

The data we are starting with is an array of objects which represent people:

```js
const people = [
  { id: "1", name: "Leigh", age: 35 },
  { id: "2", name: "Jenny", age: 30 },
  { id: "3", name: "Heather", age: 28 },
];
```

Although `people.length` would be the more performant and better solution, we can count an array's length by using reduce. Our initial value is 0, and each iteration will add 1 to the previous accumulated value.

```js
result = people.reduce((acc, person) => acc + 1, 0);
```

### 1. Sum Numbers

We can sum numbers using reduce. Much like the length example above, we can start with 0, and instead of adding 1 upon each iteration, we can add the `person.age` property to our accumulated value.

```js
result = people.reduce((acc, person) => acc + person.age, 0);
```

### 2. Mapping with Reduce

Yup... you can map using reduce! In this case our initial value is an empty array, and upon each iteration we can return an array with its previous value, plus the newest value added to the end of our array.

```js
result = people.reduce((acc, person) => [...acc, person.name], []);
```

### 3. Array to Object

This is a technique I use all the time when I have an array of some object with an `id`, and I want to easily access these objects by their ID, rather than having to find them in an array each time. By having an object with each person's ID as the key, I can access them using the ID's value.

```js
result = people.reduce((acc, person) => {
  return { ...acc, [person.id]: person };
}, {});
```

### 4. Find Max Value

The `Math.max()` function can be immitated using reduce by checking if the current element's value is greater than the accumulator. If it is, that becomes (by returning the value) the new max value, otherwise the previous accumulator (current max value) is returned.

```js
result = people.reduce((acc, person) => {
  if (acc === null || person.age > acc) return person.age;
  return acc;
}, null);
```

### 5. Find Min Value

The `Math.min()` function can be immitated using reduce by checking if the current element's value is less than the accumulator. If it is, that becomes (by returning the value) the new min value, otherwise the previous accumulator (current min value) is returned.

```js
result = people.reduce((acc, person) => {
  if (acc === null || person.age < acc) return person.age;
  return acc;
}, null);
```

### 6. Find Matching Element

The reduce callback function when immitating `Array.prototype.find()` contains three possibilities:

- The accumulator is not null, meaning we have already found the value, so let's return it.
- The current array element meets our criteria, so let's return it.
- By returning null we tell the next iteration that the value has not yet been found.

```js
result = people.reduce((acc, person) => {
  if (acc !== null) return acc;
  if (person.name === "Leigh") return person;
  return null;
}, null);
```

### 7. Check If Every Value Matches

When checking if every value matches specific criteria, we will start with the assumption that every value will match... very optimistic!! If the accumulator becomes false, our callback will continue to return false, since every value must match, and otherwise will return `true` or `false` for the current element.

```js
result = people.reduce((acc, person) => {
  if (!acc) return false;
  return person.age > 18;
}, true);
```

### 8. Check If Some Value Matches

Checking if some value matches a condition in our array involves a bit of pessimism. We'll start off with the assumption of `false`, and our callback function will return true as soon as the accumulator is true for the first time, and otherwise will return `true` or `false` on the current element.

```js
result = people.reduce((acc, person) => {
  if (acc) return true;
  return person.age > 18;
}, false);
```

### 9. Group and Count Occurrences

As we've seen in the "Array to Object" example above, we can convert an array to an object, but this time we are looking to count the occurrences for a given key, in this case the `status`. Our return value will take the existing accumulated object, adding 1 for the current key's value (or initializing it to 0 if this is the first occurrence).

```js
const orders = [
  { id: "1", status: "pending" },
  { id: "2", status: "pending" },
  { id: "3", status: "cancelled" },
  { id: "4", status: "shipped" },
];

result = orders.reduce((acc, order) => {
  return { ...acc, [order.status]: (acc[order.status] || 0) + 1 };
}, {});
```

### 10. Flatten Nested Arrays

In this last example we will start with an array of nested arrays, and reduce it into a flattened array of values. Because we will need to recursively reduce (flatten) arrays, we'll need to give our callback function a name (so it can be called within itself).

If the current element is an `Array`, it means we must reduce it until we arrive at at an element that can be appended to the end of the array we are producing. The _initial_ value of our inner reduce call is the _current_ accumulator value.

```js
const folders = [
  "index.js",
  ["flatten.js", "map.js"],
  ["any.js", ["all.js", "count.js"]],
];

function flatten(acc, element) {
  if (Array.isArray(element)) {
    return element.reduce(flatten, acc);
  }
  return [...acc, element];
}

result = folders.reduce(flatten, []);
```

## Mistakes to Avoid

If you don’t pass in an initial value, reduce will assume the first item in your array is your initial value. This worked fine in the first few examples because we were adding up a list of numbers.

If you’re trying to tally up fruit, and you leave out the initial value then things get weird. Not entering an initial value is an easy mistake to make and one of the first things you should check when debugging.

Another common mistake is forgetting to return the total. You must return something for the reduce function to work. Always double-check and make sure that you’re actually returning the value you want.

## Conclusion

Knowing the use cases of some built-in functions in JavaScript can help you to improve your coding skills. Learning the use cases can gain some insights for you. You can implement some functions elegantly.
The reduce() method in JavaScript is also a useful built-in function. If you know how to use it, it is powerful. It helps you to write a smaller number of code lines, as in the example of summing numbers and so on.

## Tools, Tips & References

Everything in this post came from a fantastic video on Youtube ["Reduce: 10 Different Examples"](https://youtu.be/NiLUGy1Mh4U). I give [Leigh Halliday](https://www.leighhalliday.com/) full credit and I am grateful to him for everything I now know about using the Reduce Method In JavaScript​. I have tried to rewrite much of what he explains in my own words as an exercise to better understand each concept. Also, it’s easier for me to reference an article, as opposed to a video, when I need to remember how to do something.
The [MDN Reduce documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) labels what I called a total the accumulator. It is important to know this because most people will refer to it as an `accumulator` if you read about it online. Some people call it `prev` as in previous value. It all refers to the same thing. I found it easier to think of a total when I was learning reduce.
If you would like to practice using reduce I recommend signing up for [freeCodeCamp](https://www.freecodecamp.org) and completing as many of the [intermediate algorithms](https://www.freecodecamp.org/learn/#nested-collapseIntermediateAlgorithmScripting) as you can using the reduce javascript method.

Thanks for the read! Now go practice & build something awesome!
