#TIỀN XỬ LÝ DỮ LIỆU – TITANIC DATASET

1. Tải dữ liệu
Sử dụng thư viện Pandas để đọc dữ liệu từ file CSV vào DataFrame.  
Hiển thị một số dòng đầu và thông tin tổng quan để hiểu cấu trúc dữ liệu, kiểu dữ liệu và số lượng giá trị không rỗng.


2. Kiểm tra dữ liệu thiếu
Sử dụng hàm `isnull().sum()` để xác định số lượng giá trị thiếu trong từng cột.  
Dùng biểu đồ heatmap để trực quan hóa vị trí dữ liệu bị thiếu trong tập dữ liệu.

3. Xử lý dữ liệu thiếu
- Cột số (`Age`) được điền bằng giá trị trung bình (mean)
- Cột phân loại (`Embarked`) được điền bằng giá trị phổ biến nhất (mode)
- Cột `Cabin` bị thiếu quá nhiều nên được loại bỏ  

Sau khi xử lý, dữ liệu không còn giá trị thiếu.

4. Xử lý ngoại lai (Outlier)
Sử dụng biểu đồ boxplot để phát hiện các giá trị ngoại lai trong cột `Fare`.  
Áp dụng phương pháp IQR để xác định ngưỡng hợp lệ:

- Ngưỡng dưới = Q1 - 1.5 * IQR  
- Ngưỡng trên = Q3 + 1.5 * IQR  

Các giá trị nằm ngoài khoảng này được loại bỏ khỏi dữ liệu.

5. Làm sạch dữ liệu
Loại bỏ các dòng còn chứa giá trị thiếu bằng `dropna()`  
Sử dụng `reset_index()` để đánh lại chỉ số dữ liệu sau khi xóa dòng

6. Cân bằng dữ liệu
Dữ liệu ban đầu bị mất cân bằng giữa các lớp trong biến `Survived`  

- Trước xử lý: lớp 0 nhiều hơn lớp 1  
- Sau xử lý: sử dụng phương pháp oversampling  

Thực hiện:
- Tách dữ liệu thành 2 nhóm (major và minor)
- Nhân bản nhóm thiểu số để cân bằng với nhóm đa số  

Kết quả: số lượng mẫu của hai lớp trở nên cân bằng

7. Trực quan hóa dữ liệu
Sử dụng biểu đồ histogram để quan sát phân phối dữ liệu:

- Phân phối của `Age`
- Phân phối của `Fare`

Giúp đánh giá dữ liệu sau khi làm sạch

8. Xuất dữ liệu
Dữ liệu sau khi tiền xử lý được lưu thành file:
cleaned_data.csv
File này được sử dụng cho bước huấn luyện mô hình Deep Learning.
KẾT LUẬN
Quá trình tiền xử lý đã thực hiện:
- Xử lý dữ liệu thiếu
- Loại bỏ ngoại lai
- Làm sạch dữ liệu
- Cân bằng dữ liệu
- Trực quan hóa dữ liệu

Dữ liệu sau xử lý đã sẵn sàng cho việc xây dựng và huấn luyện mô hình.
