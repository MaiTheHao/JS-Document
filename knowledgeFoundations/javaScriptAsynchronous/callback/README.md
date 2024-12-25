****Callback Functions**** (Hàm gọi lại)

Là những hàm được truyền vào như đối số cho một hàm khác và sẽ được gọi khi tác vụ bất đồng bộ hoàn thành.
Ví dụ: 
  function doSomethingAsync(callback) {
      setTimeout(() => {
          console.log("Đã hoàn thành công việc!");
          callback();
      }, 1000);
  }
  
  doSomethingAsync(() => {
      console.log("Callback đã được gọi!");
  });
