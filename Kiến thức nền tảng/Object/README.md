# Đối tượng (Object) trong JavaScript

## 1. Object Properties (Thuộc tính của đối tượng)

Một chiếc xe hơi ngoài đời thực có các thuộc tính như: tên, mẫu mã, trọng lượng, màu sắc.

Hãy tưởng tượng bạn có một chiếc xe hơi. Chiếc xe đó có đặc điểm gì? Nó có tên (Mazda, Toyota), có màu sắc (đỏ, xanh, trắng), có trọng lượng, v.v. Những đặc điểm này trong lập trình được gọi là các thuộc tính (properties).

Ví dụ:

-   car.name = Fiat
-   car.model = 500
-   car.weight = 850kg
-   car.color = white

Các đối tượng xe hơi đều có các thuộc tính giống nhau, nhưng giá trị của mỗi xe lại khác nhau. Giống như tất cả mọi người đều có tên, nhưng tên của mỗi người lại khác nhau.

## 2. Object Methods (Phương thức của đối tượng)

Một chiếc xe hơi ngoài đời thực có các hành động như: khởi động, lái, phanh, dừng lại.

Hãy nghĩ về những gì chiếc xe có thể làm - nó có thể khởi động, chạy, phanh lại, dừng. Những hành động này trong lập trình được gọi là các phương thức (methods).

Ví dụ:

-   car.start() - xe khởi động
-   car.drive() - xe chạy
-   car.brake() - xe phanh
-   car.stop() - xe dừng lại

Các đối tượng xe hơi đều có các phương thức giống nhau, nhưng mỗi xe thực hiện các hành động này vào thời điểm khác nhau, tùy thuộc vào người lái.

## 3. Đối tượng trong JavaScript

Đối tượng có thể chứa nhiều giá trị khác nhau. Nếu biến thông thường giống như một hộp đựng một món đồ, thì đối tượng giống như một tủ đồ có nhiều ngăn, mỗi ngăn chứa một vật khác nhau.

Ví dụ:

```js
const car = { type: 'Fiat', model: '500', color: 'white' };
```

Ở đây, `car` là một tủ đồ với 3 ngăn: ngăn "type" chứa "Fiat", ngăn "model" chứa "500", và ngăn "color" chứa "white".

> **Lưu ý:** Thông thường, nên khai báo object bằng từ khóa `const`. Điều này không có nghĩa là đối tượng không thể thay đổi, mà chỉ có nghĩa là tham chiếu đến đối tượng không thể thay đổi.

## 4. Cách khai báo một đối tượng

### 4.1. Sử dụng Object Literal

Object literal là cách phổ biến và đơn giản nhất, giống như việc bạn liệt kê tất cả đồ đạc có trong tủ.

```js
const person = { firstName: 'John', lastName: 'Doe', age: 50, eyeColor: 'blue' };
```

Để dễ đọc hơn, bạn có thể viết trên nhiều dòng:

```js
const person = {
	firstName: 'John',
	lastName: 'Doe',
	age: 50,
	eyeColor: 'blue',
};
```

Mỗi thuộc tính gồm một tên (key) và một giá trị (value), giống như mỗi ngăn trong tủ đồ có nhãn và vật dụng bên trong.

### 4.2. Tạo object rỗng rồi thêm thuộc tính

Cách này giống như bạn mua một tủ rỗng về, sau đó mới lần lượt cho đồ vào từng ngăn.

```js
const person = {}; // Tạo một đối tượng rỗng - tủ đồ trống

// Thêm từng thuộc tính - bỏ đồ vào từng ngăn
person.firstName = 'John';
person.lastName = 'Doe';
person.age = 50;
person.eyeColor = 'blue';
```

### 4.3. Sử dụng từ khóa `new Object()`

```js
const person = new Object(); // Tạo một đối tượng rỗng - tủ đồ trống

// Thêm từng thuộc tính
person.firstName = 'John';
person.lastName = 'Doe';
person.age = 50;
person.eyeColor = 'blue';
```

> **Lưu ý:** Hai cách này cho kết quả giống nhau, nhưng nên dùng object literal (cách 4.1) vì nó ngắn gọn, dễ đọc và có hiệu suất tốt hơn.

## 5. Thuộc tính của đối tượng

Các giá trị được đặt tên trong object gọi là **thuộc tính** (property). Mỗi thuộc tính có một tên và một giá trị, giống như mỗi ngăn kéo có nhãn và đồ vật bên trong.

| Thuộc tính | Giá trị |
| ---------- | ------- |
| firstName  | John    |
| lastName   | Doe     |
| age        | 50      |
| eyeColor   | blue    |

Đối tượng trong JavaScript hoạt động như một bảng tra cứu, nơi bạn có thể nhanh chóng tìm thấy giá trị bằng cách sử dụng tên. Điều này giống với:

-   Từ điển (Dictionary) trong Python: bạn tra từ và tìm thấy nghĩa
-   Bảng tra cứu (Lookup table) trong nhiều ngôn ngữ khác
-   Tủ đựng hồ sơ trong đời thực, nơi mỗi ngăn được dán nhãn

## 6. Truy cập thuộc tính của đối tượng

Có 2 cách để lấy giá trị từ một đối tượng:

### Cách 1: Sử dụng dấu chấm (.)

```js
person.lastName; // Trả về "Doe"
```

Giống như bạn nói: "Tôi muốn xem ngăn có nhãn 'lastName' trong tủ đồ 'person'".

### Cách 2: Sử dụng dấu ngoặc vuông []

```js
person['lastName']; // Trả về "Doe"
```

Cách này hữu ích khi tên thuộc tính được lưu trong một biến hoặc khi tên thuộc tính có khoảng trắng:

```js
let propertyName = 'lastName';
person[propertyName]; // Trả về "Doe"

person['full name'] = 'John Doe'; // Tạo thuộc tính có khoảng trắng
```

## 7. Phương thức của đối tượng (Object Methods)

Phương thức là các hàm được lưu trữ như thuộc tính của đối tượng. Chúng là các hành động mà đối tượng có thể thực hiện.

Nếu thuộc tính giống như đặc điểm của đối tượng (một chiếc xe có màu đỏ), thì phương thức giống như hành động của đối tượng (chiếc xe có thể chạy).

```js
const person = {
	firstName: 'John',
	lastName: 'Doe',
	id: 5566,

	// Đây là một phương thức
	fullName: function () {
		return this.firstName + ' ' + this.lastName;
	},
};

// Gọi phương thức
console.log(person.fullName()); // Kết quả: "John Doe"
```

Trong ví dụ này:

-   Đối tượng `person` có 3 thuộc tính (firstName, lastName, id) và 1 phương thức (fullName)
-   Phương thức `fullName()` sử dụng từ khóa `this` để truy cập các thuộc tính của chính đối tượng đó

Từ khóa `this` đề cập đến "chủ sở hữu" của phương thức này, tức là đối tượng `person`. Giống như khi bạn nói "Chiếc xe này", từ "này" đề cập đến một chiếc xe cụ thể.

### Cách viết ngắn gọn cho phương thức (ES6)

```js
const person = {
	firstName: 'John',
	lastName: 'Doe',

	// Cú pháp ngắn gọn
	fullName() {
		return this.firstName + ' ' + this.lastName;
	},
};
```

## 8. Tổng kết về Object

-   Đối tượng (Object) là khái niệm cốt lõi trong JavaScript, giống như "gạch xây dựng" cho mọi thứ phức tạp hơn.
-   Một đối tượng là tập hợp các thuộc tính (đặc điểm) và phương thức (hành động).
-   Có thể hình dung đối tượng như một tủ đồ, mỗi ngăn (thuộc tính) chứa một giá trị, và một số ngăn có thể chứa các công cụ (phương thức).

### Hầu hết mọi thứ trong JavaScript đều là object:

-   Mảng (Array) là đối tượng đặc biệt với các chỉ số số
-   Hàm (Function) là đối tượng có thể thực thi
-   Date, Math, RegExp, Map, Set, v.v. đều là các đối tượng

Điều này tương tự như trong đời thực, hầu hết mọi thứ đều có thể được mô tả bằng đặc điểm và hành động.

## 9. Giá trị nguyên thủy (Primitive) và Object

### Giá trị nguyên thủy (Primitive)

Giá trị nguyên thủy là đơn giản, không thể chia nhỏ hơn. Giống như các nguyên tố hóa học không thể phân tách thành chất đơn giản hơn.

JavaScript có 7 kiểu dữ liệu nguyên thủy:

-   string (chuỗi): "Hello"
-   number (số): 3.14
-   boolean: true/false
-   null: giá trị null đặc biệt
-   undefined: biến chưa được gán giá trị
-   symbol: định danh duy nhất
-   bigint: số nguyên lớn

Giá trị nguyên thủy là bất biến (immutable):

```js
let message = 'Hello';
message[0] = 'J'; // Không thể thay đổi ký tự đầu tiên
console.log(message); // Vẫn là "Hello"
```

Giống như bạn không thể thay đổi số 5 thành số 6, bạn chỉ có thể tạo một giá trị mới.

### So sánh với Object

Đối tượng có thể thay đổi (mutable):

```js
let user = { name: 'John' };
user.name = 'Pete'; // Có thể thay đổi thuộc tính
console.log(user.name); // "Pete"
```

## 10. Tham chiếu và sao chép đối tượng

Khi gán một đối tượng cho một biến, biến đó không lưu trữ chính đối tượng mà lưu "địa chỉ bộ nhớ" - một tham chiếu đến nơi đối tượng được lưu trữ.

Tương tự như trong đời thực: khi bạn đưa cho bạn bè địa chỉ nhà, bạn không đưa chính ngôi nhà mà chỉ đưa thông tin về nơi tìm thấy ngôi nhà.

```js
const person = {
	firstName: 'John',
	lastName: 'Doe',
	age: 50,
};

const x = person; // x không phải là bản sao, mà chỉ là tham chiếu đến person

x.age = 10; // Thay đổi age thông qua tham chiếu x
console.log(person.age); // 10 - đối tượng gốc cũng bị thay đổi
```

Để tạo bản sao thật sự của đối tượng, bạn có thể dùng:

```js
// Cách 1: Object.assign
const person2 = Object.assign({}, person);

// Cách 2: Toán tử spread (ES6)
const person3 = { ...person };
```

## 11. Các ví dụ thực tế về Object trong JavaScript

### Ví dụ 1: Đối tượng sinh viên

```js
const student = {
	// Thuộc tính
	name: 'Nguyễn Văn A',
	age: 20,
	grades: { math: 8.5, physics: 7.0, english: 9.0 },

	// Phương thức
	getAverageGrade() {
		return (this.grades.math + this.grades.physics + this.grades.english) / 3;
	},

	introduce() {
		return `Xin chào, tôi là ${this.name}, ${this.age} tuổi, điểm trung bình ${this.getAverageGrade().toFixed(2)}`;
	},
};

console.log(student.introduce());
```

### Ví dụ 2: Giỏ hàng trực tuyến

```js
const shoppingCart = {
	items: [],

	addItem(product, quantity = 1) {
		this.items.push({ product, quantity });
	},

	removeItem(productId) {
		this.items = this.items.filter((item) => item.product.id !== productId);
	},

	getTotalPrice() {
		return this.items.reduce((total, item) => total + item.product.price * item.quantity, 0);
	},
};

// Sử dụng giỏ hàng
shoppingCart.addItem({ id: 1, name: 'Laptop', price: 20000000 }, 1);
shoppingCart.addItem({ id: 2, name: 'Chuột', price: 500000 }, 2);

console.log(`Tổng giá trị: ${shoppingCart.getTotalPrice().toLocaleString()} VND`);
```

## 12. Một số tính năng nâng cao về Object

### 12.1. Destructuring (Phân rã đối tượng)

```js
const person = { firstName: 'John', lastName: 'Doe', age: 30 };

// Truy cập truyền thống
const first = person.firstName;
const last = person.lastName;

// Sử dụng destructuring
const { firstName, lastName } = person;
console.log(firstName, lastName); // "John Doe"
```

### 12.2. Shorthand properties (Thuộc tính viết tắt)

```js
const name = 'John';
const age = 30;

// Cách truyền thống
const user1 = { name: name, age: age };

// Sử dụng shorthand
const user2 = { name, age }; // Tương đương với {name: name, age: age}
```

### 12.3. Computed property names (Tên thuộc tính được tính toán)

```js
const propertyName = 'jobTitle';
const value = 'Developer';

// Tạo đối tượng với tên thuộc tính động
const employee = {
	name: 'John',
	[propertyName]: value, // Tương đương với {name: "John", jobTitle: "Developer"}
};
```

---

Với hiểu biết sâu về Object, bạn đã nắm được một trong những khái niệm quan trọng nhất của JavaScript. Objects cho phép bạn mô tả và làm việc với những thứ phức tạp, tương tự như cách chúng ta nhìn nhận thế giới thực với các đối tượng có đặc điểm và hành vi riêng.
