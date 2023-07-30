# 问：请实现一个transform方法，使得输入数据的key命名为下划线的情况下转换成驼峰大小写形式。例如：
# {get_key: 1, item_list: [],get_key: 1, item_list: [],get_key: 1, item_list: []} => {getKey: 1, itemList: []}

 

```js
function transform(obj) {
  if(typeof obj !== "Object") {return}
  for(let item of obj) {

  }
}
```

```js
function changeName(str) { // str:get_ket => getKey
  let arr = [...str];
  arr.forEach((item,index)=>{
    if (item=='_') {
      arr.splice(index,1)
    }
    arr.index = arr.index.toUpperCase()
  })
  return arr.join('')
}
```