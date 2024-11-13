# Thành Phần 3: Khai Thác Đặc Trưng (Feature Engineering)

Khai thác đặc trưng (Feature Engineering) là quá trình tạo ra, chuyển đổi và lựa chọn các đặc trưng tốt nhất từ dữ liệu thô để tăng cường khả năng dự đoán của mô hình AI. Việc xây dựng các đặc trưng phù hợp giúp cải thiện độ chính xác và hiệu suất của mô hình học máy.

---

## 1. Mục Đích của Khai Thác Đặc Trưng

- **Tăng Cường Hiệu Suất**: Chọn và xây dựng các đặc trưng giúp mô hình có thể dự đoán chính xác hơn.
- **Giảm Thiểu Độ Phức Tạp**: Đơn giản hóa tập dữ liệu mà không làm mất thông tin quan trọng.
- **Khám Phá Các Mối Quan Hệ**: Tìm ra các mối quan hệ tiềm ẩn giữa các biến số trong dữ liệu.
- **Tối Ưu Hóa Thời Gian Huấn Luyện**: Giảm số lượng đặc trưng không cần thiết để tăng tốc độ huấn luyện.

---

## 2. Các Bước Chính Trong Khai Thác Đặc Trưng

Quá trình khai thác đặc trưng thường bao gồm các bước sau:

1. **Tạo Đặc Trưng Mới (Feature Creation)**
2. **Biến Đổi Đặc Trưng (Feature Transformation)**
3. **Chọn Đặc Trưng (Feature Selection)**
4. **Mã Hóa Đặc Trưng (Feature Encoding)**

---

## 3. Chi Tiết Từng Bước

### Bước 1: Tạo Đặc Trưng Mới (Feature Creation)

Tạo đặc trưng mới là quá trình tạo ra các thuộc tính mới từ dữ liệu hiện có, thường thông qua các phép tính toán học hoặc phân tích dữ liệu.

- **Tạo Đặc Trưng Tương Tác (Interaction Features)**:
  - Kết hợp hai hoặc nhiều đặc trưng hiện có để tạo ra đặc trưng mới.
  - **Ví dụ**: Tạo đặc trưng mới bằng cách nhân hai cột, như `Chiều Cao * Cân Nặng` để tính chỉ số BMI.

- **Tổng Hợp Dữ Liệu Theo Nhóm (Aggregating Features)**:
  - Tạo ra đặc trưng mới bằng cách tổng hợp dữ liệu theo nhóm, chẳng hạn tính giá trị trung bình hoặc tổng số lượng theo từng nhóm.
  - **Ví dụ**: Tính tổng doanh thu hàng tháng từ dữ liệu doanh thu hàng ngày.

- **Trích Xuất Đặc Trưng Từ Dữ Liệu Văn Bản (Text Feature Extraction)**:
  - Áp dụng các kỹ thuật như phân tích tần suất từ (TF-IDF), n-gram, hoặc trích xuất từ khóa để tạo ra đặc trưng mới từ dữ liệu văn bản.
  - **Ví dụ**: Trích xuất số lần xuất hiện của một từ cụ thể trong các đánh giá sản phẩm.

---

### Bước 2: Biến Đổi Đặc Trưng (Feature Transformation)

Biến đổi đặc trưng liên quan đến việc thay đổi định dạng hoặc cấu trúc của dữ liệu hiện tại để làm cho nó dễ hiểu và dễ xử lý hơn cho mô hình.

- **Chuẩn Hóa (Normalization)**:
  - Chuyển đổi dữ liệu về một phạm vi nhất định, thường là [0, 1], để đảm bảo tính nhất quán.
  - **Ví dụ**: Chuyển đổi dữ liệu giá cả từ [0, 1000] về phạm vi [0, 1] để đảm bảo các đặc trưng có cùng tầm quan trọng.

- **Tiêu Chuẩn Hóa (Standardization)**:
  - Chuyển đổi dữ liệu để có mean = 0 và standard deviation = 1, giúp giảm sự khác biệt về độ lớn giữa các đặc trưng.
  - **Ví dụ**: Chuyển đổi điểm thi của học sinh thành Z-score.

- **Log Transformation**:
  - Áp dụng hàm log lên dữ liệu để giảm sự ảnh hưởng của các giá trị lớn hoặc phân phối không đồng đều.
  - **Ví dụ**: Chuyển đổi dữ liệu doanh thu để giảm thiểu tác động của các giá trị lớn.

---

### Bước 3: Chọn Đặc Trưng (Feature Selection)

Chọn đặc trưng là quá trình chọn ra những thuộc tính quan trọng nhất từ tập dữ liệu để mô hình học máy có thể học một cách hiệu quả mà không bị nhiễu bởi những đặc trưng không liên quan.

- **Loại Bỏ Đặc Trưng Không Cần Thiết (Removing Unnecessary Features)**:
  - Xóa các cột không chứa thông tin hữu ích hoặc không ảnh hưởng đến kết quả dự đoán.
  - **Ví dụ**: Trong một bài toán dự đoán giá nhà, loại bỏ các cột như mã số nhà hoặc địa chỉ chi tiết.

- **Phân Tích Tương Quan (Correlation Analysis)**:
  - Sử dụng các kỹ thuật phân tích tương quan để xác định mối quan hệ giữa các đặc trưng, từ đó loại bỏ những đặc trưng có tương quan quá cao với nhau.
  - **Ví dụ**: Nếu hai cột có hệ số tương quan > 0.9, có thể giữ lại một cột và loại bỏ cột còn lại để tránh dư thừa.

- **Sử Dụng Các Kỹ Thuật Lựa Chọn Đặc Trưng (Feature Selection Techniques)**:
  - Sử dụng các phương pháp như Recursive Feature Elimination (RFE), Lasso Regression, hoặc Random Forest để chọn lọc các đặc trưng quan trọng.
  - **Ví dụ**: Sử dụng RFE để chọn ra top 10 đặc trưng quan trọng nhất từ 100 đặc trưng ban đầu.

---

### Bước 4: Mã Hóa Đặc Trưng (Feature Encoding)

Mã hóa đặc trưng là quá trình chuyển đổi dữ liệu dạng phân loại (categorical) hoặc dạng văn bản thành dữ liệu dạng số để mô hình có thể hiểu và xử lý.

- **Mã Hóa Nhị Phân (Binary Encoding)**:
  - Chuyển đổi các đặc trưng dạng phân loại thành dạng nhị phân (0 và 1) cho mỗi giá trị duy nhất.
  - **Ví dụ**: Mã hóa cột `Giới Tính` thành `Nam = 0` và `Nữ = 1`.

- **Mã Hóa One-Hot (One-Hot Encoding)**:
  - Tạo ra các cột riêng biệt cho mỗi giá trị duy nhất trong cột phân loại, giá trị trong mỗi cột là 0 hoặc 1.
  - **Ví dụ**: Mã hóa cột `Màu Sắc` thành các cột `Màu_Đỏ`, `Màu_Xanh`, và `Màu_Vàng`.

- **Mã Hóa Thứ Tự (Ordinal Encoding)**:
  - Sử dụng các con số để biểu thị thứ tự của các giá trị trong cột phân loại.
  - **Ví dụ**: Mã hóa các cấp độ `Thấp`, `Trung Bình`, `Cao` thành các số 0, 1, và 2 tương ứng.

- **Mã Hóa Bằng Embedding** (sử dụng cho các mô hình học sâu):
  - Chuyển đổi dữ liệu phân loại thành các vector nhiều chiều thông qua các kỹ thuật embedding để mô hình hiểu sâu hơn về các mối quan hệ tiềm ẩn.
  - **Ví dụ**: Sử dụng embedding trong dữ liệu văn bản để mã hóa các từ thành vector số có ý nghĩa.

---
