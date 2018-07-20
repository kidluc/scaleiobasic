# Introduce
## What is ScaleIO?
ScaleIO là 1 software sử dụng local disk của server và mạng LAN để tạo ra 1 virtual SAN với chi phí thấp. ScaleIO sử dụng local internal storage để biến thành internal shared block storage (bộ nhớ lưu trữ chia sẻ nội bộ).  
Các thành phần của ScaleIO được cài đặt trên server ứng dụng và giao tiếp với nhau thông qua mạng LAN để xử lý các yêu cầu I/O 	được gửi đến các block volume.  
ScaleIO được thiết kế với khả năng tự phục hồi, ScaleIO cho phép thêm hoặc xóa bỏ các node mà sau đó nó sẽ ngay lập tức đáp ứng những thay đổi, cân bằng lại sự phân bố lưu trữ.  
ScaleIO cũng cho phép hoạt động hiệu quả với nhiều loại disk khác nhau như HDD, SSD, PCIe...  

