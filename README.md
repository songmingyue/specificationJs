# js 规范

## 1. 文件名以驼峰形式命名

允许
```
detail.js || detailAbout.js
```
不允许
::: warning
detail-about.js || Detail.js || Detail-about.js||Detailabout.js

:::

## 2. 结构

### 2.2.1 空格
`消除行尾空白`

示例：

```
console.log('消除行尾空白')
```

`{前必须有一个空格, 等号前后需有空格, 生命对象{}须有空格`

示例

```
const a = {
}

if (true) {
}

private funcName() {
}

let a = [
  { lebal: '', value: '' }
]
```

`二元运算符两侧必须有一个空格，一元运算符与操作对象之间不允许有空格`

示例
```
const a = 10;
const b = 10
const c = 10
a++;
a = b + c;
```

`if / else / for / while / function / switch / do / try / catch / finally 关键字后，必须有一个空格`

示例：
```
if (condition) {
} else {

}

while (condition) {
}

(function () {
})();
```

`在对象创建时，属性中的 : 之后必须有空格，: 之前不允许有空格`

示例：

```
var obj = {
    a: 1,
    b: 2,
    c: 3
};
```

`函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格`

示例：

```
function funcName() {
}

var funcName = function funcName() {
};

funcName();
```

`, 和 ; 前不允许有空格。`

示例：

```
// good
private callFunc(a, b);

// bad
private callFunc(a , b) ;
```

`在函数调用、函数声明、括号表达式、属性访问、if / for / while / switch / catch 等语句中，() 和 [] 内紧贴括号部分不允许有空格`

示例：

```
// good

callFunc(param1, param2, param3);

save(this.list[this.indexes[i]]);

needIncream && (variable += increament);

if (num > list.length) {
}

while (len--) {
}


// bad

callFunc( param1, param2, param3 );

save( this.list[ this.indexes[ i ] ] );

needIncreament && ( variable += increament );

if ( num > list.length ) {
}

while ( len-- ) {
}
```

### 2.2.2 换行

`每个独立语句结束后必须换行`

示例

```
// good
const a = 1
const b = 10

//bad
const a = 1; const b = 10
```

`运算符处换行时，运算符必须在新行的行首`

示例

```
// good
if (user.isAuthenticated()
    && user.isInRole('admin')
    && user.hasAuthority('add-admin')
    || user.hasAuthority('delete-admin')
) {
    // Code
}

var result = number1 + number2 + number3
    + number4 + number5;


// bad
if (user.isAuthenticated() &&
    user.isInRole('admin') &&
    user.hasAuthority('add-admin') ||
    user.hasAuthority('delete-admin')) {
    // Code
}

var result = number1 + number2 + number3 +
    number4 + number5;

```

`在函数声明、函数表达式、函数调用、对象创建、数组创建、for语句等场景中，不允许在 , 或 ; 前换行`

示例

```
// good
var obj = {
    a: 1,
    b: 2,
    c: 3
};

foo(
    aVeryVeryLongArgument,
    anotherVeryLongArgument,
    callback
);


// bad
var obj = {
    a: 1
    , b: 2
    , c: 3
};

foo(
    aVeryVeryLongArgument
    , anotherVeryLongArgument
    , callback
);
```

### 2.3 命名

`变量 使用 Camel（驼峰）命名法`

示例：

```
const loadingModules = {};
```

`函数 使用 Camel（驼峰）命名法`


示例：

```
private getList() {

}
```

`参数 使用 Camel（驼峰）命名法 && 尽量少使用any`

```
// good
private getList(pageNumber: number) {

}

// bad
private getList(pagenumber: any) {

}
```

`类 使用 Pascal命名法`

示例：

```
function TextNode(options) {
}
```

`类的 方法 / 属性 使用 Camel命名法`

示例：

```
function TextNode(value, engine) {
    this.value = value;
    this.engine = engine;
}

TextNode.prototype.clone = function () {
    return this;
};

```

### 2.4 注释

`单行注释 // 前后都要有空格`

示例：

```
const a = 10 // 变量
```


`多行注释`

示例：

```
/**
 * a作用
 */
const a = '10';
```

## 3.1 变量

`变量在使用前必须通过 const, let 定义 尽量不使用var 定义`

示例：

```
// good
const name = 'MyName';
// good
let name = '';
name = 'songsong'

// bad
name = 'MyName';

// bad
var name = 'MyName';
```

## 3.2 条件

`在 Equality Expression 中使用类型严格的 === !==`

示例：

```
// good
if (age === 18) {
  console.log(age)
}

// bad
if (age == 30) {
    // ......
}
```

`尽可能使用简洁的表达式`

示例：

```
// 字符串为空

// good
if (!name) {
    // ......
}

// bad
if (name === '') {
    // ......
}
```

`if  嵌套尽量不超过两层`

示例：

```
// good 
if (age && school && name) {
  console.log('ddd')
}
// bad
if (age) {
  if (name) {
    if (school) {
      console.log('ddd')
    }
  }
}
```