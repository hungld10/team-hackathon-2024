# Thành Phần 2: Xử Lý Dữ Liệu (Data Preprocessing)

Xử lý dữ liệu (Data Preprocessing) là bước quan trọng trong quy trình phát triển AI, nhằm biến dữ liệu thô thành dữ liệu chất lượng cao để cung cấp cho mô hình. Việc xử lý dữ liệu giúp mô hình AI hoạt động hiệu quả hơn, tăng độ chính xác và giảm sai số. Trong phần này, chúng ta sẽ tìm hiểu chi tiết từng bước xử lý dữ liệu và cách chúng góp phần vào chất lượng của mô hình.

---

## 1. Mục Đích của Xử Lý Dữ Liệu

Mục đích chính của quá trình xử lý dữ liệu bao gồm:

- **Làm Sạch Dữ Liệu**: Loại bỏ dữ liệu lỗi hoặc không đầy đủ để đảm bảo tính chính xác.
- **Chuẩn Hóa Dữ Liệu**: Chuyển đổi dữ liệu về định dạng nhất quán, phù hợp với các thuật toán.
- **Giảm Thiểu Sai Lệch**: Loại bỏ hoặc điều chỉnh các giá trị bất thường (outliers) để tránh sai số.

---

## 2. Các Bước Chính Trong Xử Lý Dữ Liệu

Quá trình xử lý dữ liệu thường bao gồm các bước sau:

1. **Làm Sạch Dữ Liệu (Data Cleaning)**
2. **Chuyển Đổi Dữ Liệu (Data Transformation)**
3. **Chuẩn Hóa Dữ Liệu (Data Normalization)**
4. **Giảm Kích Thước Dữ Liệu (Dimensionality Reduction)**
5. **Phân Chia Dữ Liệu (Data Splitting)**

---

## 3. Chi Tiết Từng Bước

### Bước 1: Làm Sạch Dữ Liệu (Data Cleaning)

Dữ liệu thực tế thường gặp các vấn đề như giá trị bị thiếu, lỗi sai cú pháp, hoặc dữ liệu không hợp lệ. Làm sạch dữ liệu giúp loại bỏ các lỗi này, đảm bảo rằng chỉ có dữ liệu chính xác và đáng tin cậy được đưa vào mô hình.

- **Xử Lý Dữ Liệu Bị Thiếu (Missing Data)**:
  - Phương pháp xử lý bao gồm xóa dữ liệu thiếu, điền giá trị trung bình (mean), trung vị (median), hoặc giá trị phổ biến (mode).
  - **Ví dụ**: Trong một bảng dữ liệu có nhiều hàng bị thiếu giá trị trong cột tuổi, có thể điền giá trị trung bình của cột này hoặc loại bỏ các hàng thiếu dữ liệu.

- **Loại Bỏ Ngoại Lệ (Outlier Removal)**:
  - Các giá trị bất thường có thể làm sai lệch mô hình, do đó cần phát hiện và loại bỏ chúng.
  - **Ví dụ**: Nếu độ tuổi của người dùng trong tập dữ liệu có giá trị là 200, đây là một giá trị bất thường và cần phải loại bỏ.

- **Sửa Lỗi Cú Pháp (Syntax Correction)**:
  - Đảm bảo định dạng và cú pháp của dữ liệu đúng chuẩn, như sửa lỗi chính tả, định dạng ngày tháng, đơn vị đo lường.
  - **Ví dụ**: Sửa các giá trị như “Jan” thành “January” để nhất quán định dạng tháng.

---

### Bước 2: Chuyển Đổi Dữ Liệu (Data Transformation)

Sau khi làm sạch, dữ liệu cần được chuyển đổi để chuẩn bị cho các thuật toán học máy. Quá trình này có thể bao gồm mã hóa, tổng hợp hoặc thay đổi định dạng dữ liệu.

- **Mã Hóa Dữ Liệu Danh Mục (Categorical Encoding)**:
  - Chuyển đổi các biến danh mục thành biến số để mô hình học máy có thể xử lý.
  - **Phương pháp**: Sử dụng One-Hot Encoding để chuyển đổi các giá trị danh mục thành các vector nhị phân, hoặc Label Encoding để chuyển đổi thành giá trị số.

- **Biến Đổi Log (Log Transformation)**:
  - Được sử dụng cho dữ liệu phân phối lệch để giảm thiểu sự chênh lệch giữa các giá trị lớn và nhỏ.
  - **Ví dụ**: Chuyển đổi doanh thu để giảm sự ảnh hưởng của các giá trị cực lớn.

- **Chuẩn Hóa Dữ Liệu Văn Bản (Text Normalization)**:
  - Áp dụng cho dữ liệu văn bản bằng cách loại bỏ ký tự đặc biệt, chuyển đổi chữ hoa thành chữ thường, hoặc loại bỏ các từ không cần thiết.
  - **Ví dụ**: Xử lý văn bản để loại bỏ các từ dừng như “a,” “an,” và “the” khi thực hiện phân tích ngôn ngữ tự nhiên (NLP).

---

### Bước 3: Chuẩn Hóa Dữ Liệu (Data Normalization)

Chuẩn hóa là quá trình điều chỉnh dữ liệu về phạm vi và định dạng nhất quán. Điều này giúp tăng tính ổn định và hiệu quả khi mô hình học máy học từ dữ liệu.

- **Chuẩn Hóa Min-Max (Min-Max Scaling)**:
  - Chuyển đổi dữ liệu về phạm vi [0, 1] hoặc [-1, 1] để dễ dàng so sánh giữa các thuộc tính khác nhau.
  - **Ví dụ**: Chuyển đổi cột giá trị sản phẩm từ [0, 1000] về phạm vi [0, 1] để không có thuộc tính nào chiếm ưu thế về độ lớn.

- **Chuẩn Hóa Z-score (Standardization)**:
  - Đặt dữ liệu trong một phân phối chuẩn (mean = 0, std = 1) để phù hợp cho các thuật toán yêu cầu dữ liệu có phân phối chuẩn.
  - **Ví dụ**: Điều chỉnh cột điểm thi của học sinh về Z-score để loại bỏ sự chênh lệch về quy mô.

---

### Bước 4: Giảm Kích Thước Dữ Liệu (Dimensionality Reduction)

Giảm kích thước dữ liệu giúp loại bỏ các thuộc tính không cần thiết và tối ưu hóa tốc độ xử lý mà không làm mất thông tin quan trọng. Điều này đặc biệt hữu ích khi làm việc với các tập dữ liệu lớn và phức tạp.

- **Principal Component Analysis (PCA)**:
  - Phương pháp PCA chuyển đổi dữ liệu thành các thành phần chính, giúp giảm số chiều mà vẫn giữ lại phần lớn thông tin.
  - **Ví dụ**: Trong tập dữ liệu hình ảnh, PCA có thể giảm số chiều của các đặc trưng ảnh xuống còn vài chục chiều thay vì hàng ngàn.

- **T-SNE (t-distributed Stochastic Neighbor Embedding)**:
  - Một kỹ thuật giảm kích thước dùng để hiển thị dữ liệu trong không gian 2D hoặc 3D, thường dùng để trực quan hóa dữ liệu.
  - **Ví dụ**: Trực quan hóa các cụm dữ liệu cho bài toán phân cụm (clustering).

- **Lọc Đặc Trưng (Feature Selection)**:
  - Chọn lọc các đặc trưng quan trọng nhất, loại bỏ các đặc trưng ít ảnh hưởng đến kết quả dự đoán.
  - **Ví dụ**: Trong tập dữ liệu y tế, có thể chỉ chọn các đặc trưng như huyết áp, nhịp tim, và BMI cho mô hình phân loại.

---

### Bước 5: Phân Chia Dữ Liệu (Data Splitting)

Để đánh giá độ chính xác của mô hình, dữ liệu cần được chia thành các tập riêng biệt. Điều này giúp mô hình không chỉ ghi nhớ mà còn có khả năng tổng quát hóa.

- **Tập Huấn Luyện (Training Set)**:
  - Dữ liệu dùng để huấn luyện mô hình, chiếm phần lớn dữ liệu.
  - **Phương pháp phổ biến**: Chiếm khoảng 70-80% của toàn bộ tập dữ liệu.

- **Tập Kiểm Tra (Testing Set)**:
  - Dữ liệu để đánh giá độ chính xác của mô hình sau khi huấn luyện, thường chiếm khoảng 20-30% dữ liệu.
  - **Ví dụ**: Một mô hình phân loại email cần được kiểm tra với tập dữ liệu chưa từng thấy để đánh giá khả năng phân loại chính xác.

- **Tập Xác Thực (Validation Set)**:
  - Đôi khi được tách ra từ tập huấn luyện để tối ưu hóa siêu tham số và giảm thiểu tình trạng overfitting.
  - **Ví dụ**: Tinh chỉnh tham số “depth” trong cây quyết định dựa trên hiệu suất của tập xác thực.

---

## 4. Công Cụ và Kỹ Thuật Xử Lý Dữ Liệu

Dưới đây là các công cụ và thư viện phổ biến hỗ trợ xử lý dữ liệu:

- **Pandas**: Thư viện Python mạnh mẽ cho thao tác và phân tích dữ liệu.
- **NumPy**: Hỗ trợ tính toán với mảng và ma trận, giúp chuẩn hóa và chuẩn bị dữ liệu số.
- **Scikit-Learn**: Thư viện có sẵn các hàm xử lý dữ liệu như chuẩn hóa, mã hóa, và chia dữ liệu.
- **NLTK và spaCy**: Các thư viện xử lý ngôn ngữ tự nhiên cho dữ liệu văn bản.
- **TensorFlow và PyTorch**: Các thư viện deep learning cung cấp công cụ xử lý và chuẩn bị dữ liệu cho mô hình học sâu.

---

## 5. Kết Luận

Xử lý dữ liệu là một phần thiết yếu của mọi quy trình phát triển AI. Với một quy trình xử lý dữ liệu đúng đắn và kỹ lưỡng, mô hình sẽ học được từ dữ liệu một cách hiệu quả, dẫn đến khả năng dự đoán và phân tích chính xác hơn. Việc thực hiện đúng các bước xử lý không chỉ giúp cải thiện hiệu suất mà còn đảm bảo tính chính xác và độ tin cậy của mô hình AI.

---
