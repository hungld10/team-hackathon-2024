# Thành Phần 5: Huấn Luyện Mô Hình (Model Training)

Huấn luyện mô hình là quá trình quan trọng trong học máy, nơi một mô hình được "học" từ dữ liệu để đưa ra các dự đoán chính xác hoặc thực hiện các nhiệm vụ cụ thể. Trong quá trình này, các thuật toán học máy sẽ điều chỉnh các tham số của mô hình dựa trên dữ liệu huấn luyện để tối ưu hóa độ chính xác của dự đoán.

---

## 1. Chuẩn Bị Dữ Liệu Cho Huấn Luyện

Trước khi bắt đầu quá trình huấn luyện, dữ liệu cần được chuẩn bị kỹ càng để đảm bảo chất lượng mô hình. Các bước chính trong việc chuẩn bị dữ liệu bao gồm:

- **Chia Tập Dữ Liệu (Data Splitting)**:
  - Chia dữ liệu thành ba phần: **Dữ Liệu Huấn Luyện (Training Data)**, **Dữ Liệu Kiểm Tra (Validation Data)**, và **Dữ Liệu Kiểm Định (Test Data)**.
  - **Dữ Liệu Huấn Luyện** dùng để dạy mô hình.
  - **Dữ Liệu Kiểm Tra** dùng để tinh chỉnh các tham số của mô hình.
  - **Dữ Liệu Kiểm Định** dùng để đánh giá hiệu suất của mô hình sau khi hoàn thành huấn luyện.

- **Chuẩn Hóa và Tiêu Chuẩn Hóa Dữ Liệu**:
  - **Chuẩn Hóa (Normalization)**: Chuyển đổi dữ liệu vào khoảng giá trị [0, 1] để đảm bảo sự đồng nhất.
  - **Tiêu Chuẩn Hóa (Standardization)**: Chuyển đổi dữ liệu để có mean = 0 và standard deviation = 1.

- **Giải Quyết Dữ Liệu Bị Mất (Handling Missing Data)**:
  - Xử lý các giá trị bị thiếu trong dữ liệu thông qua việc điền giá trị trung bình, trung vị, hoặc loại bỏ hàng chứa giá trị thiếu.

- **Xử Lý Dữ Liệu Không Cân Bằng (Handling Imbalanced Data)**:
  - Sử dụng các kỹ thuật như **Over-sampling**, **Under-sampling**, hoặc **SMOTE** để xử lý tập dữ liệu không cân bằng.

---

## 2. Các Tham Số Cần Điều Chỉnh Khi Huấn Luyện

Trong quá trình huấn luyện, có nhiều tham số quan trọng cần được điều chỉnh để tối ưu hóa mô hình. Các tham số này có thể ảnh hưởng đến hiệu suất của mô hình:

- **Học Tốc (Learning Rate)**:
  - Quyết định tốc độ mà mô hình điều chỉnh các trọng số dựa trên lỗi tính toán.
  - Learning Rate quá cao có thể làm mô hình không ổn định, trong khi quá thấp sẽ làm quá trình học chậm.

- **Số Lượng Epoch**:
  - Số lần toàn bộ tập dữ liệu huấn luyện được đưa qua mô hình.
  - Số lượng Epoch cao hơn có thể giúp mô hình học kỹ hơn, nhưng cũng có nguy cơ gây ra quá khớp (overfitting).

- **Kích Thước Batch (Batch Size)**:
  - Số lượng mẫu dữ liệu được xử lý trước khi cập nhật trọng số mô hình.
  - Batch Size nhỏ có thể giúp quá trình học chính xác hơn nhưng sẽ chậm, Batch Size lớn sẽ nhanh hơn nhưng có thể bỏ sót các chi tiết nhỏ.

- **Regularization (L2, L1)**:
  - Kỹ thuật điều chỉnh để tránh tình trạng quá khớp bằng cách thêm vào hàm lỗi một thành phần để phạt các trọng số lớn.
  - **L1 Regularization**: Sử dụng trị tuyệt đối của trọng số.
  - **L2 Regularization**: Sử dụng bình phương của trọng số.

---

## 3. Kỹ Thuật Để Cải Thiện Hiệu Suất Mô Hình

Trong quá trình huấn luyện, có một số kỹ thuật quan trọng có thể được áp dụng để cải thiện hiệu suất và độ chính xác của mô hình:

- **Early Stopping**:
  - Ngừng quá trình huấn luyện khi mô hình bắt đầu có dấu hiệu quá khớp dựa trên dữ liệu kiểm tra.

- **Cross-Validation**:
  - Chia dữ liệu thành nhiều phần (fold) và huấn luyện nhiều lần để đảm bảo tính tổng quát của mô hình.

- **Ensemble Learning**:
  - Kết hợp nhiều mô hình khác nhau để cải thiện độ chính xác, bao gồm các kỹ thuật như Bagging, Boosting, và Stacking.

- **Data Augmentation**:
  - Tạo thêm dữ liệu huấn luyện từ dữ liệu gốc bằng cách thay đổi các đặc tính của dữ liệu, chẳng hạn như xoay ảnh, dịch chuyển hoặc thay đổi màu sắc.

---

## 4. Đánh Giá Mô Hình (Model Evaluation)

Sau khi huấn luyện, việc đánh giá mô hình là bước quan trọng để đảm bảo rằng mô hình hoạt động như mong đợi và có khả năng tổng quát hoá tốt cho dữ liệu mới. Các phương pháp đánh giá mô hình phổ biến bao gồm:

- **Độ Chính Xác (Accuracy)**:
  - Tỷ lệ phần trăm các dự đoán đúng trên tổng số dự đoán.
  - **Công Thức**: 
    \[
    Accuracy = \frac{\text{Số Dự Đoán Đúng}}{\text{Tổng Số Mẫu Dữ Liệu}}
    \]
  - Phù hợp cho các tập dữ liệu cân bằng.

- **Ma Trận Nhầm Lẫn (Confusion Matrix)**:
  - Ma trận cho biết các dự đoán đúng và sai của mô hình đối với từng lớp.
  - Bao gồm các thành phần: True Positive (TP), True Negative (TN), False Positive (FP), và False Negative (FN).

- **F1 Score**:
  - Trung bình điều hòa giữa Precision và Recall, phù hợp khi dữ liệu không cân bằng.
  - **Công Thức**: 
    \[
    F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
    \]

- **ROC Curve và AUC (Area Under Curve)**:
  - Đồ thị biểu diễn mối quan hệ giữa Tỷ Lệ Dương Giả (False Positive Rate) và Tỷ Lệ Dương Thật (True Positive Rate).
  - AUC đo lường diện tích dưới đường cong ROC, giá trị càng cao càng tốt.

- **Loss Function**:
  - Hàm mục tiêu mà mô hình cần tối ưu trong quá trình huấn luyện.
  - **Ví dụ**: Mean Squared Error (MSE), Cross-Entropy Loss.

---

## 5. Điều Chỉnh Siêu Tham Số (Hyperparameter Tuning)

Điều chỉnh siêu tham số là quá trình tìm kiếm các giá trị tốt nhất cho các tham số của mô hình mà không được học trực tiếp từ dữ liệu. Một số phương pháp điều chỉnh siêu tham số bao gồm:

- **Grid Search**:
  - Thử nghiệm tất cả các kết hợp có thể của các tham số trong một lưới xác định.
  - Hiệu quả nhưng tốn nhiều thời gian nếu có nhiều siêu tham số.

- **Random Search**:
  - Thử nghiệm ngẫu nhiên các giá trị trong phạm vi của siêu tham số.
  - Hiệu quả hơn Grid Search trong các bài toán có không gian tìm kiếm lớn.

- **Bayesian Optimization**:
  - Sử dụng mô hình thống kê để dự đoán giá trị tốt nhất của siêu tham số, tối ưu hóa quá trình tìm kiếm.

- **Automated Machine Learning (AutoML)**:
  - Sử dụng các công cụ tự động hóa để tìm kiếm mô hình và siêu tham số tối ưu, như TPOT, AutoKeras, hoặc H2O.ai.

---

## 6. Kết Luận

Quá trình huấn luyện mô hình đòi hỏi sự kết hợp của nhiều yếu tố: từ chuẩn bị dữ liệu, điều chỉnh siêu tham số, đến đánh giá hiệu suất. Một quy trình huấn luyện tốt sẽ đảm bảo rằng mô hình không chỉ học được từ dữ liệu mà còn có khả năng tổng quát hoá cho các tình huống mới. Với các công cụ và kỹ thuật hiện đại, việc tối ưu hóa mô hình trở nên dễ dàng hơn bao giờ hết, mang lại kết quả chính xác và đáng tin cậy.

---

