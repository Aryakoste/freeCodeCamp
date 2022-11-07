---
id: 587d7b8f367417b2b2512b64
title: Implement the filter Method on a Prototype
challengeType: 1
forumTopicId: 301231
dashedName: implement-the-filter-method-on-a-prototype
---

# --description--

قد تتعلم الكثير عن دالة `filter` إذا قمت بتنفيذ الإصدار الخاص بك منها. من المستحسن أن تستخدم حلقات `for` التكرارية أو `Array.prototype.forEach()`.

# --instructions--

اكتب `Array.prototype.myFilter()`الخاص بك، والذي يجب أن يتصرف مثل `Array.prototype.filter()`. يجب ألا تستخدم دالة `filter` المدمجة. يمكن الوصول إلى مثيل (instance) `Array` في دالة `myFilter` باستخدام `this`.

# --hints--

`new_s` يجب أن يساوي `[23, 65, 5]`.

```js
assert(JSON.stringify(new_s) === JSON.stringify([23, 65, 5]));
```

يجب ألا يستخدم الكود الخاص بك دالة `filter`.

```js
assert(!code.match(/\.?[\s\S]*?filter/g));
```

# --seed--

## --seed-contents--

```js
// The global variable
const s = [23, 65, 98, 5];

Array.prototype.myFilter = function(callback) {
  // Only change code below this line
  const newArray = [];
  // Only change code above this line
  return newArray;
};

const new_s = s.myFilter(function(item) {
  return item % 2 === 1;
});
```

# --solutions--

```js
const s = [23, 65, 98, 5];

Array.prototype.myFilter = function(callback) {
  const newArray = [];
  for (let i = 0; i < this.length; i++) {
    if (callback(this[i])) newArray.push(this[i]);
  }
  return newArray;
};

const new_s = s.myFilter(function(item) {
  return item % 2 === 1;
});
```