# async/await

1. ### **Khái niệm về async/await**

`async/await` là một cú pháp trong JavaScript được giới thiệu trong ECMAScript 2017 (*ES8*), giúp xử lý các tác vụ bất đồng bộ (*asynchronous tasks*) dễ dàng hơn. Trước khi `async/await` ra đời, việc làm việc với các tác vụ bất đồng bộ thường sử dụng Promise và callback. Tuy nhiên, việc sử dụng Promise hoặc callback trong một số trường hợp có thể gây khó khăn trong việc đọc và bảo trì mã, đặc biệt là khi có nhiều tác vụ bất đồng bộ lồng nhau.

Cú pháp async/await giúp giải quyết vấn đề này bằng cách làm cho mã bất đồng bộ trông giống như mã đồng bộ, giúp dễ dàng theo dõi và xử lý lỗi. Điều này làm cho mã dễ hiểu hơn và ngắn gọn hơn so với việc sử dụng `then()` và `catch()` của Promise.

2. ### **Cấu trúc của async/await**

Cú pháp của async/await gồm hai thành phần chính:
- **async:** Biến một hàm thành bất đồng bộ. Khi hàm được khai báo với từ khóa async, hàm đó sẽ luôn trả về một Promise, cho phép sử dụng từ khóa await bên trong hàm.
- **await:** Được sử dụng bên trong một hàm `async` để "dừng" chương trình và chờ đợi kết quả từ một Promise trước khi tiếp tục thực hiện các câu lệnh phía sau. Khi `await` được sử dụng, nó sẽ làm tạm dừng mã và tiếp tục khi Promise hoàn thành (*fulfilled*) hoặc bị lỗi (*rejected*).

3. ## **Cú pháp cơ bản của async/await**

```javascript
// Hàm async trả về một Promise
async function myFunction() {
  let res = await someAsyncTask();  // Chờ Promise hoàn thành
  console.log(res);
}
```

Trong ví dụ trên:
- `myFunction` là một hàm async.
- `await` được sử dụng để "*ngừng*" thực thi của hàm cho đến khi `someAsyncTask()` trả về kết quả.

---

# Chi tiết về async/await

1. ### **async function**
Khi một hàm được khai báo với từ khóa `async`, hàm đó sẽ trả về một Promise. Điều này có nghĩa là ngay cả khi hàm không trả về bất kỳ giá trị gì, nó cũng sẽ tự động trả về một Promise được giải quyết với giá trị `undefined`.

Ví dụ:
```javascript
async function example() {
  return "Hello, world!";
}

example().then(result => console.log(result));  // "Hello, world!"
```

Mặc dù hàm `example` trả về một giá trị (chuỗi "`Hello, world!`"), nhưng nó vẫn trả về một Promise. Bạn có thể sử dụng `then()` hoặc `await` để xử lý kết quả từ Promise đó.

2. ### **await**

`await` chỉ có thể được sử dụng bên trong một hàm `async`. Khi sử dụng `await`, chương trình sẽ dừng lại và đợi Promise được "giải quyết" (*fulfilled*) hoặc bị "từ chối" (*rejected*). Điều này giúp mã bất đồng bộ trông giống như mã đồng bộ, giúp việc theo dõi và xử lý lỗi trở nên dễ dàng hơn.

Cú pháp:
```javascript
let result = await promise;  // Dừng lại cho đến khi promise hoàn thành
```

3. ### **Ví dụ về async/await**
Giả sử bạn có một hàm bất đồng bộ `fetchData()` sử dụng `setTimeout` để mô phỏng việc lấy dữ liệu từ server sau một khoảng thời gian.

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Dữ liệu đã được lấy!");
    }, 2000);
  });
}

async function fetchDataAsync() {
  let result = await fetchData();  // Chờ dữ liệu từ Promise
  console.log(result);  // In ra "Dữ liệu đã được lấy!"
}

fetchDataAsync();
```

*Trong ví dụ trên:*
- `fetchData()` trả về một Promise sau khi thực hiện một tác vụ bất đồng bộ (*mô phỏng độ trễ 2 giây*).
- Hàm `fetchDataAsync` sử dụng `await` để dừng lại và đợi Promise của `fetchData` hoàn thành.
- Khi Promise hoàn thành, kết quả của nó sẽ được in ra console.

--- 

# Quản lý lỗi với async/await

Một trong những lợi ích chính của `async/await` là việc xử lý lỗi trở nên đơn giản và rõ ràng hơn so với việc sử dụng `.then()` và `.catch()` của Promise.

1. ### **Xử lý lỗi với try/catch**

Khi sử dụng `async/await`, bạn có thể dễ dàng quản lý lỗi bằng cách sử dụng `try/catch`, giống như cách xử lý lỗi trong mã đồng bộ. Điều này giúp bạn dễ dàng bắt và xử lý các lỗi trong quá trình thực thi các tác vụ bất đồng bộ.

```javascript
async function fetchDataAsync() {
  try {
    let result = await fetchData();  // Chờ dữ liệu từ Promise
    console.log(result);
  } catch (error) {
    console.error("Lỗi:", error);  // Xử lý lỗi nếu có
  }
}

fetchDataAsync();
```

**Trong ví dụ trên:**
- Nếu `fetchData()` gặp lỗi, lỗi sẽ được bắt trong `catch` và in ra console.
- Điều này giúp bạn không cần phải lồng nhiều `.catch()` như khi sử dụng Promise thuần túy.

2. ### **Quản lý lỗi khi có nhiều Promise**

Khi bạn cần thực hiện nhiều tác vụ bất đồng bộ và đợi tất cả chúng hoàn thành, bạn có thể sử dụng await kết hợp với `Promise.all()`.

```javascript
async function fetchDataAsync() {
  try {
    let results = await Promise.all([fetchData(), fetchData()]);
    console.log(results);  // In ra kết quả của tất cả các Promise
  } catch (error) {
    console.error("Lỗi:", error);  // Xử lý lỗi nếu có
  }
}

fetchDataAsync();
```

Trong ví dụ trên: `Promise.all()` cho phép bạn đợi tất cả các Promise hoàn thành, và nếu một trong các Promise bị lỗi, lỗi đó sẽ được bắt trong `catch`.

---

# Lợi ích của async/await
1. ### **Đơn giản hóa mã bất đồng bộ**
`Async/await` giúp mã bất đồng bộ trở nên dễ đọc và dễ hiểu hơn so với việc sử dụng `.then()` hoặc lồng nhiều callback. Khi sử dụng `async/await`, mã trông gần như đồng bộ, mặc dù nó đang xử lý các tác vụ bất đồng bộ.

2. ### **Dễ dàng xử lý lỗi**
Việc sử dụng `try/catch` với `async/await` giúp xử lý lỗi dễ dàng và trực quan hơn. Bạn không phải lo lắng về việc đặt `.catch()` vào mỗi Promise, mà có thể tập trung vào việc xử lý lỗi một cách tổng thể.

3. ### **Quản lý các tác vụ bất đồng bộ đồng thời**
`Async/await` kết hợp với `Promise.all()` hoặc `Promise.race()` giúp quản lý nhiều tác vụ bất đồng bộ đồng thời một cách dễ dàng.
