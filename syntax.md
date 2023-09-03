### 兼容性表
```angular2html
JavaScript 是一门还在发展中的语言，定期会添加一些新的功能。要查看它们在基于浏览器的引擎及其他引擎中的支持情况，请看：
https://caniuse.com —— 每个功能的支持表，例如，查看哪个引擎支持现代加密（cryptography）函数：https://caniuse.com/#feat=cryptography。
https://kangax.github.io/compat-table —— 一份列有语言功能以及引擎是否支持这些功能的表格。
```
### 注释
```angular2html
js可以加; 也可以省略。
注释是 /* */
不支持注释嵌套！
```
### 严格模式
```angular2html
有人可能会建议在脚本的最顶部放置 "use strict" 这行代码…… 但你知道更酷的方式吗？

现代 JavaScript 支持 “class” 和 “module” —— 高级语言结构（本教程后续章节会讲到），它们会自动启用 use strict。因此，如果我们使用它们，则无需添加 "use strict" 指令。
```

### 声明变量
```angular2html
let — 现代的变量声明方式。
var — 老旧的变量声明方式。一般情况下，我们不会再使用它。但是，我们会在 老旧的 "var" 章节介绍 var 和 let 的微妙差别，以防你需要它们。
const — 类似于 let，但是变量的值无法被修改。
```

### 基本的数据类型
```
JavaScript 中有八种基本的数据类型（译注：前七种为基本数据类型，也称为原始数据类型，而 object 为复杂数据类型）。
七种原始数据类型：
number 用于任何类型的数字：整数或浮点数，在 ±(253-1) 范围内的整数。
bigint 用于任意长度的整数。
string 用于字符串：一个字符串可以包含 0 个或多个字符，所以没有单独的单字符类型。
boolean 用于 true 和 false。
null 用于未知的值 —— 只有一个 null 值的独立类型。
undefined 用于未定义的值 —— 只有一个 undefined 值的独立类型。
symbol 用于唯一的标识符。
以及一种非原始数据类型：
object 用于更复杂的数据结构。
我们可以通过 typeof 运算符查看存储在变量中的数据类型。

通常用作 typeof x，但 typeof(x) 也可行。
以字符串的形式返回类型名称，例如 "string"。
typeof null 会返回 "object" —— 这是 JavaScript 编程语言的一个错误，实际上它并不是一个 object。
```


### 用户交互的 3 个浏览器的特定函数
```angular2html
alert("Hello");
let test = prompt("Test", ''); // <-- 用于 IE 浏览器
let isBoss = confirm("Are you the boss?");
```

### 类型转换
```angular2html
对 undefined 进行数字型转换时，输出结果为 NaN，而非 0。
对 "0" 和只有空格的字符串（比如：" "）进行布尔型转换时，输出结果为 true

Boolean(1)
Number(str)
```

### 链式赋值（Chaining assignments）
```angular2html
let a, b, c;

a = b = c = 2 + 2;

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

### 比较
```
严格相等运算符 === 在进行比较时不会做任何的类型转换。
```

### ?
```
(company == 'Netscape') ?
   alert('Right!') : alert('Wrong.');
```

### ??
```
常见使用场景是提供默认值
let firstName = null;
let lastName = null;
let nickName = "Supercoder";

// 显示第一个已定义的值：
alert(firstName ?? lastName ?? nickName ?? "匿名"); // Supercoder
```

### 函数
```
函数也可以访问外部变量

这两种声明的函数是一样的。   
let sayHi = function() { // (1) 创建
  alert( "Hello" );
};

let func = sayHi;
// ...


函数表达式是在代码执行到达时被创建，并且仅从那一刻起可用。

一旦代码执行到赋值表达式 let sum = function… 的右侧，此时就会开始创建该函数，并且可以从现在开始使用（分配，调用等）。

函数声明则不同。

在函数声明被定义之前，它就可以被调用。

例如，一个全局函数声明对整个脚本来说都是可见的，无论它被写在这个脚本的哪个位置。

这是内部算法的缘故。当 JavaScript 准备 运行脚本时，首先会在脚本中寻找全局函数声明，并创建这些函数。我们可以将其视为“初始化阶段”。

在处理完所有函数声明后，代码才被执行。所以运行时能够使用这些函数。
```

### 箭头函数/匿名函数
```
创建函数还有另外一种非常简单的语法，并且这种方法通常比函数表达式更好。

它被称为“箭头函数”，因为它看起来像这样：

let func = (arg1, arg2, ..., argN) => expression;
这里创建了一个函数 func，它接受参数 arg1..argN，然后使用参数对右侧的 expression 求值并返回其结果。

换句话说，它是下面这段代码的更短的版本：

let func = function(arg1, arg2, ..., argN) {
  return expression;
};
```