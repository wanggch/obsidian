数组
数组重新排序

```js
// 打乱数组
shuffle(arr) {
  let newArr = arr.map(item => ({ val: item, ram: Math.random() }));
  newArr.sort((a, b) => a.ram - b.ram);
  arr.splice(0, arr.length, ...newArr.map(i => i.val));
  return arr;
}
```