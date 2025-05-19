# Scope trong JavaScript

Scope (phạm vi) trong JavaScript xác định tính khả dụng của các biến. Có ba loại scope chính trong JavaScript: Global Scope, Function Scope, và Block Scope.

## 1. Global Scope

Biến được khai báo trong global scope có thể được truy cập từ bất kỳ đâu trong mã nguồn.

```javascript
var globalVar = 'I am a global variable';

function globalScopeExample() {
	console.log(globalVar); // I am a global variable
}

globalScopeExample();
```

## 2. Function Scope

Biến được khai báo trong một hàm chỉ có thể được truy cập từ bên trong hàm đó.

```javascript
function functionScopeExample() {
	var functionVar = 'I am a function variable';
	console.log(functionVar); // I am a function variable
}

functionScopeExample();
console.log(functionVar); // ReferenceError: functionVar is not defined
```

## 3. Block Scope

Biến được khai báo bằng `let` hoặc `const` trong một khối mã (block) chỉ có thể được truy cập từ bên trong khối đó.

```javascript
if (true) {
	let blockVar = 'I am a block variable';
	console.log(blockVar); // I am a block variable
}

console.log(blockVar); // ReferenceError: blockVar is not defined
```

## 4. Lexical Scope

JavaScript sử dụng lexical scoping, nghĩa là phạm vi của một biến được xác định bởi vị trí của nó trong mã nguồn.

```javascript
function outerFunction() {
	var outerVar = 'I am an outer variable';

	function innerFunction() {
		console.log(outerVar); // I am an outer variable
	}

	innerFunction();
}

outerFunction();
```

## 5. Scope Chain

Khi một biến được tham chiếu, JavaScript sẽ tìm kiếm biến đó trong phạm vi hiện tại, sau đó là phạm vi bao quanh nó, và tiếp tục như vậy cho đến khi tìm thấy biến hoặc đạt đến global scope.

```javascript
var globalVar = 'I am a global variable';

function outerFunction() {
	var outerVar = 'I am an outer variable';

	function innerFunction() {
		var innerVar = 'I am an inner variable';
		console.log(innerVar); // I am an inner variable
		console.log(outerVar); // I am an outer variable
		console.log(globalVar); // I am a global variable
	}

	innerFunction();
}

outerFunction();
```

## 6. Hoisting

JavaScript hoists (nâng lên) các khai báo biến và hàm lên đầu phạm vi của chúng. Tuy nhiên, chỉ có khai báo được hoisted, không phải gán giá trị.

```javascript
console.log(hoistedVar); // undefined
var hoistedVar = 'I am hoisted';

hoistedFunction(); // I am a hoisted function
function hoistedFunction() {
	console.log('I am a hoisted function');
}
```

## 7. Closures

Closure là một hàm có quyền truy cập vào phạm vi của hàm cha ngay cả sau khi hàm cha đã kết thúc.

```javascript
function closureExample() {
	var closureVar = 'I am a closure variable';

	return function () {
		console.log(closureVar); // I am a closure variable
	};
}

var myClosure = closureExample();
myClosure();
```

## Kết luận

Hiểu rõ về scope là rất quan trọng để viết mã JavaScript hiệu quả và tránh các lỗi không mong muốn. Scope giúp quản lý tính khả dụng của các biến và tránh xung đột tên biến.
