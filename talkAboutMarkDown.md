
---

# Giới thiệu cú pháp Markdown

Markdown là một ngôn ngữ đánh dấu nhẹ, được sử dụng phổ biến để định dạng văn bản trên các nền tảng trực tuyến. Dưới đây là các cú pháp cơ bản:

## 1. Tiêu đề (Heading)

Sử dụng dấu `#` để tạo tiêu đề. Số lượng `#` xác định cấp độ tiêu đề:

```markdown
# Tiêu đề cấp 1
## Tiêu đề cấp 2
### Tiêu đề cấp 3
#### Tiêu đề cấp 4
##### Tiêu đề cấp 5
###### Tiêu đề cấp 6
```

Kết quả:

# Tiêu đề cấp 1  
## Tiêu đề cấp 2  
### Tiêu đề cấp 3  
#### Tiêu đề cấp 4  
##### Tiêu đề cấp 5  
###### Tiêu đề cấp 6  

---

## 2. Văn bản (Text)

### 2.1 Chữ nghiêng  
Sử dụng dấu * để tạo chữ nghiêng:  
```markdown
*Chữ nghiêng* hoặc _Chữ nghiêng_
```

### 2.2 Chữ đậm  
Sử dụng dấu ** để tạo chữ đậm:  
```markdown
**Chữ đậm** hoặc __Chữ đậm__
```

### 2.3 Chữ gạch ngang  
Sử dụng dấu ~~ để gạch ngang chữ:  
```markdown
~~Chữ gạch ngang~~
```

Kết quả:  
*Chữ nghiêng*  
**Chữ đậm**  
~~Chữ gạch ngang~~

---

## 3. Danh sách

### 3.1 Danh sách không thứ tự  
Sử dụng `-`:

```markdown
- Mục 1
- Mục 2
  - Mục con
  - Mục con
- Mục 3
```

Kết quả:  
- Mục 1  
- Mục 2  
  - Mục con  
  - Mục con  
- Mục 3  

### 3.2 Danh sách có thứ tự  
Sử dụng các số:

```markdown
1. Mục 1
2. Mục 2
3. Mục 3
```

Kết quả:  
1. Mục 1  
2. Mục 2  
3. Mục 3  

---

## 4. Liên kết và Hình ảnh

### 4.1 Liên kết  
Sử dụng cú pháp:  
```markdown
[Text hiển thị](URL)
```

Ví dụ:  
```markdown
[OpenAI](https://openai.com)
```

Kết quả: [OpenAI](https://openai.com)

### 4.2 Hình ảnh  
Sử dụng cú pháp tương tự liên kết, nhưng thêm `!` phía trước:  
```markdown
![Mô tả ảnh](URL_ảnh)
```

Ví dụ:  
```markdown
![OpenAI Logo](https://via.placeholder.com/150)
```

---

## 5. Trích dẫn (Blockquote)

Sử dụng `>` để tạo trích dẫn:  
```markdown
> Đây là một trích dẫn.
> Trích dẫn có thể nhiều dòng.
```

Kết quả:  
> Đây là một trích dẫn.  
> Trích dẫn có thể nhiều dòng.

---

## 6. Đường kẻ ngang (Horizontal Line)

Sử dụng `---` để tạo đường kẻ ngang:

```markdown
---
```

---

## 7. Đoạn mã (Code)

### 7.1 Đoạn mã nội tuyến  
Sử dụng \``` để đánh dấu đoạn mã nội tuyến:  
```plaintext
    ```

        Đây là đoạn mã

    ```
```


Kết quả: 
```
Đây là đoạn mã
```

### 7.2 Đoạn mã nhiều dòng  
Sử dụng dấu ``` để tạo đoạn mã nhiều dòng:

```plaintext
    ```ngôn_ngữ

        Mã nguồn  

    ```
```

Ví dụ:  
```plaintext
    ```javaScript

        console.log("Hello, Markdown!"); 

    ```
```

Kết quả:  
```javascript
console.log("Hello, Markdown!");
```

---

## 8. Bảng (Table)

Sử dụng `|` và `-` để tạo bảng:

```markdown
| Cột 1 | Cột 2 | Cột 3 |
|-------|-------|-------|
| Dòng 1 | Dữ liệu 1 | Dữ liệu 2 |
| Dòng 2 | Dữ liệu 3 | Dữ liệu 4 |
```

Kết quả:  
| Cột 1 | Cột 2    | Cột 3    |  
|-------|----------|----------|  
| Dòng 1 | Dữ liệu 1 | Dữ liệu 2 |  
| Dòng 2 | Dữ liệu 3 | Dữ liệu 4 |  

---