# KẾ HOẠCH VÀ THEO DÕI TIẾN ĐỘ THỰC HÀNH LAB 3 - KHAI PHÁ DỮ LIỆU

- **Môn học**: Khai phá dữ liệu (Data Mining - IT1.231.3)
- **Sinh viên**: Nguyễn Thành Trí
- **Mã số sinh viên (MSSV)**: `6451071079`
- **Giảng viên hướng dẫn**: ThS. Nguyễn Thiện Dương
- **Tài liệu tham chiếu**:
  - [docs/lab3.pdf](docs/lab3.pdf) (Tài liệu hướng dẫn thực hành 29 trang)
  - [docs/Template nộp bài LAB3.docx](docs/Template%20nộp%20bài%20LAB3.docx) (Biểu mẫu báo cáo)
  - [docs/Link truy cập dataset.txt](docs/Link%20truy%20cập%20dataset.txt) (Dữ liệu thực hành)

---

## 1. QUY CHUẨN THỰC HIỆN VÀ NỘP BÀI

1. **Cấu trúc lưu trữ**:
   - Tất cả các notebook được lưu trong thư mục duy nhất: `model/`.
   - Đặt tên file theo cú pháp: `model/<MSSV>_LAB3_Bai<X>.ipynb`.
   - Dữ liệu nguồn lưu tại thư mục: `Dataset/`.
2. **Quy chuẩn mã nguồn trong Notebook**:
   - Mỗi câu hỏi gồm cặp: **Cell Markdown (Đề bài)** $\rightarrow$ **Cell Code (Mã nguồn giải)**.
   - Bắt buộc in định danh sinh viên ở mỗi câu:
     ```python
     print("Họ tên: Nguyễn Thành Trí - MSSV: 6451071079")
     ```
   - Tuyệt đối **không thêm icon hay emoji** vào bất kỳ vị trí nào trong mã nguồn (chuỗi in, chú thích, tiêu đề biểu đồ, v.v.).
   - Trực quan hóa bằng Matplotlib, Seaborn, Plotly: Luôn thiết lập tiêu đề (`plt.title`), nhãn trục (`plt.xlabel`, `plt.ylabel`), chú thích (`plt.legend`) và lưới (`plt.grid(True, alpha=0.3)`). Hiển thị trực tiếp bằng `plt.show()`.
3. **Quy tắc Git Commit**:
   - Mỗi câu hỏi sau khi thực thi thành công và kiểm tra kết quả thì commit một lần.
   - Cú pháp commit message: `feature<name>: message` (ví dụ: `feature<bai1_caua>: doc va kiem tra tap du lieu iris`).
   - Tác giả: Dùng cấu hình máy (`git config user.name`, `git config user.email`). Tuyệt đối không thêm dòng `Co-Authored-By: Claude...`.
4. **Báo cáo Word**:
   - Dán mã nguồn và chụp hình minh chứng kết quả vào file [docs/Template nộp bài LAB3.docx](docs/Template%20nộp%20bài%20LAB3.docx).

---

## 2. DANH MỤC NHIỆM VỤ CHI TIẾT (TASK CHECKLIST)

### BÀI 1: Phân lớp dữ liệu Iris bằng Decision Tree, Naïve Bayes, KNN và Neural Network
- **Tập tin**: `model/6451071079_LAB3_Bai1.ipynb`
- **Vị trí tài liệu**: Trang 1 - 4 PDF (Mục II.1)
- **Tập dữ liệu**: `Iris dataset` (`sklearn.datasets.load_iris`)
- **Danh sách câu hỏi**:
  - [x] **Câu a**: Đọc bộ dữ liệu Iris từ thư viện `sklearn`.
  - [x] **Câu b**: Khảo sát bộ dữ liệu:
    - [x] In tên các thuộc tính và tên thuộc tính phân lớp (`feature_names`, `target_names`).
    - [x] In số lượng mẫu, số lượng thuộc tính (`data.shape`, `target.shape`).
    - [x] In 5 mẫu dữ liệu đầu tiên.
    - [x] Thống kê mô tả (count, mean, std, min, max, tứ phân vị) qua `DataFrame.describe()`.
  - [x] **Câu c**: Chuẩn hóa dữ liệu về đoạn $[0, 1]$ bằng cách chia mỗi giá trị cho giá trị lớn nhất trong cột tương ứng.
  - [x] **Câu d**: Phân chia tập dữ liệu thành tập train và test theo tỷ lệ 8:2 (`train_test_split`).
  - [x] **Câu e**: Xây dựng mô hình **Cây quyết định (DecisionTreeClassifier)**:
    - [x] Huấn luyện mô hình trên tập train.
    - [x] Dự đoán nhãn lớp cho tập test.
    - [x] Tính và in Accuracy trên tập test.
    - [x] Tính và in Precision, Recall, F1-score (từng lớp và trung bình) bằng `classification_report`.
    - [x] Hiển thị ma trận nhầm lẫn (Confusion Matrix) bằng Heatmap với Seaborn.
  - [x] **Câu f**: Xây dựng mô hình **Naïve Bayes (GaussianNB)**:
    - [x] Huấn luyện, dự đoán, tính Accuracy, Precision, Recall, F1-score và vẽ Heatmap Confusion Matrix.
  - [x] **Câu g**: Xây dựng mô hình **K-Nearest Neighbors (KNeighborsClassifier)**:
    - [x] Huấn luyện, dự đoán, tính Accuracy, Precision, Recall, F1-score và vẽ Heatmap Confusion Matrix.
  - [x] **Câu h**: Xây dựng mô hình **Mạng nơ-ron (Neural Network - Keras)**:
    - [x] Thiết kế kiến trúc mạng: 2 lớp ẩn (Hidden 1: 10 nơ-ron, ReLU, `input_shape=(4,)`; Hidden 2: 20 nơ-ron, ReLU) và 1 lớp ra (Output: 3 nơ-ron, Softmax).
    - [x] Biên dịch mô hình với optimizer `adam`, loss `sparse_categorical_crossentropy`, metric `accuracy`.
    - [x] Huấn luyện mô hình (`epochs=100`, `batch_size=1`, `verbose=1`).
    - [x] Dự đoán nhãn cho tập test (dùng `predict` kết hợp `np.argmax`).
    - [x] Tính Accuracy, Precision, Recall, F1-score và vẽ Heatmap Confusion Matrix.
  - [x] **Câu i**: Sử dụng cả 4 mô hình đã huấn luyện (e, f, g, h) dự đoán nhãn cho 3 mẫu dữ liệu mới:
    - Mẫu 1: `[6.2, 2.9, 4.3, 1.3]`
    - Mẫu 2: `[5.1, 3.5, 1.4, 0.2]`
    - Mẫu 3: `[7.3, 2.8, 6.4, 2.1]`
  - [x] **Câu j**: Nhận xét, so sánh tổng hợp hiệu suất của các mô hình đã huấn luyện.

---

### BÀI 2: Phân lớp ảnh chữ số viết tay MNIST với Neural Network
- **Tập tin**: `model/6451071079_LAB3_Bai2.ipynb`
- **Vị trí tài liệu**: Trang 5 - 7 PDF (Mục II.2)
- **Tập dữ liệu**: `MNIST` (`keras.datasets.mnist`)
- **Danh sách câu hỏi**:
  - [ ] **Câu a**: Đọc bộ dữ liệu train, test của MNIST từ Keras.
  - [ ] **Câu b**: In ra kích thước `shape` của tập train và test.
  - [ ] **Câu c**: Chuẩn hóa các giá trị pixel về đoạn $[0, 1]$ bằng cách chia cho 255.0.
  - [ ] **Câu d**: Phân chia tập train ban đầu thành tập train mới và validation theo tỷ lệ 8:2 bằng `train_test_split`. In kích thước sau khi chia.
  - [ ] **Câu e**: Xây dựng mạng nơ-ron tuần tự gồm các tầng:
    - [ ] Flatten layer: Làm phẳng ma trận $28 \times 28$ thành vector 784 chiều.
    - [ ] Dense layer: 128 nơ-ron, hàm kích hoạt ReLU.
    - [ ] Dropout layer: Tỷ lệ 0.2 (ngẫu nhiên tắt 20% nơ-ron để chống overfitting).
    - [ ] Dense layer (Output): 10 nơ-ron, hàm kích hoạt Softmax.
  - [ ] **Câu f**: Biên dịch mô hình (optimizer `adam`, loss `sparse_categorical_crossentropy`, metric `accuracy`).
  - [ ] **Câu g**: Huấn luyện mô hình với `epochs=5`, `batch_size=32`, đánh giá cùng tập validation.
  - [ ] **Câu h**: Vẽ đồ thị biến thiên của Accuracy và Loss qua từng epoch (cho cả train và validation).
  - [ ] **Câu i**: Dự đoán phân lớp cho toàn bộ tập test (`predict` và `argmax`).
  - [ ] **Câu j**: Tính và in ra Accuracy của mô hình trên tập test.
  - [ ] **Câu k**: Tính và in Precision, Recall, F1-score từng lớp và trung bình.
  - [ ] **Câu l**: Hiển thị Confusion Matrix bằng Heatmap.
  - [ ] **Câu m**: Dự đoán và hiển thị hình ảnh minh họa cho 5 mẫu đầu tiên trong tập test.
  - [ ] **Câu n**: Tìm và hiển thị hình ảnh của 5 trường hợp đầu tiên mô hình phân lớp sai so với nhãn thực tế.

---

### BÀI 3: Phân lớp MNIST bằng Neural Network kết hợp 10-Fold Cross Validation
- **Tập tin**: `model/6451071079_LAB3_Bai3.ipynb`
- **Vị trí tài liệu**: Trang 7 - 8 PDF (Mục II.3)
- **Tập dữ liệu**: `MNIST` (`keras.datasets.mnist`)
- **Danh sách câu hỏi**:
  - [ ] **Câu a, b, c**: Đọc dữ liệu MNIST, in kích thước và chuẩn hóa pixel về đoạn $[0, 1]$.
  - [ ] **Câu d**: Định nghĩa hàm `create_model()` khởi tạo và biên dịch mạng nơ-ron tương tự Bài 2.
  - [ ] **Câu e**: Huấn luyện mô hình bằng K-Fold Cross Validation ($k = 10$):
    - [ ] Thiết lập `KFold(n_splits=10, shuffle=True, random_state=42)`.
    - [ ] Lặp qua 10 fold: huấn luyện với `epochs=5`, `batch_size=32`, lưu Accuracy và Loss của từng fold, lưu mô hình tương ứng.
  - [ ] **Câu f**: Tính và in Mean Accuracy, Standard Deviation Accuracy, Mean Loss, Standard Deviation Loss qua 10 fold.
  - [ ] **Câu g**: Vẽ biểu đồ biểu diễn Accuracy và Loss sau mỗi fold.
  - [ ] **Câu h**: Tìm mô hình có Accuracy cao nhất giữa các fold trong quá trình huấn luyện.
  - [ ] **Câu i**: Dùng mô hình tốt nhất tính và in Accuracy trên tập test.
  - [ ] **Câu j**: Tính và in Precision, Recall, F1-score trên tập test.
  - [ ] **Câu k**: Hiển thị Confusion Matrix bằng Heatmap trên tập test.
  - [ ] **Câu l**: In kết quả phân lớp và hiển thị hình ảnh minh họa cho 5 ảnh đầu tiên trong tập test.

---

### BÀI 4: Phân lớp Iris bằng Neural Network kết hợp 10-Fold Cross Validation
- **Tập tin**: `model/6451071079_LAB3_Bai4.ipynb`
- **Vị trí tài liệu**: Trang 9 PDF (Mục II.4)
- **Tập dữ liệu**: `Iris dataset`
- **Danh sách câu hỏi**:
  - [ ] **Câu a, b**: Đọc bộ dữ liệu Iris và chuẩn hóa dữ liệu về đoạn $[0, 1]$.
  - [ ] **Câu c**: Định nghĩa hàm `create_model()` trả về mạng nơ-ron theo đúng kiến trúc của Bài 1.h.
  - [ ] **Câu d**: Huấn luyện mô hình bằng K-Fold Cross Validation ($k = 10$):
    - [ ] Lưu và in ra Accuracy, Precision, Recall, F1-score sau mỗi fold.
    - [ ] Lưu lại các mô hình sau mỗi fold.
  - [ ] **Câu e**: Tính và in Average Accuracy, Average Recall, Average Precision, Average F1-score qua 10 fold.
  - [ ] **Câu f**: Tính và in Average Recall, Average Precision, Average F1-score cho từng lớp phân loại.
  - [ ] **Câu g**: Sử dụng mô hình có F1-score tốt nhất để dự đoán nhãn cho 3 mẫu dữ liệu mới (giống Bài 1.i).

---

### BÀI 5: Phân cụm khách hàng Mall Customer Segmentation
- **Tập tin**: `model/6451071079_LAB3_Bai5.ipynb`
- **Vị trí tài liệu**: Trang 18 - 24 PDF (Phần 2 - Mục III.2)
- **Tập dữ liệu**: `Dataset/Mall_Customers.csv`
- **Danh sách câu hỏi**:
  - [ ] **Câu 1**: Nhập dữ liệu, thống kê các thông tin cơ bản (`info`, `describe`), kiểm tra và xử lý dữ liệu khuyết thiếu.
  - [ ] **Câu 2**: Vẽ biểu đồ phân phối tần suất (Histogram / Distplot / KDE) cho lần lượt các thuộc tính: `Age`, `Annual Income (k$)`, `Spending Score (1-100)`.
  - [ ] **Câu 3**: Thống kê số lượng mẫu dữ liệu theo thuộc tính `Gender` bằng biểu đồ đếm (`countplot`).
  - [ ] **Câu 4**: Vẽ biểu đồ phân tán (Scatter plot) khảo sát phân bố giữa `Age` và `Annual Income (k$)` theo `Gender`.
  - [ ] **Câu 5**: Vẽ biểu đồ phân tán khảo sát phân bố giữa `Annual Income (k$)` và `Spending Score (1-100)` theo `Gender`.
  - [ ] **Câu 6**: Gom cụm theo thuộc tính `Age` và `Spending Score (1-100)`:
    - [ ] Áp dụng phương pháp khuỷu tay (Elbow method) chạy $k = 1 \dots 10$, tính WSS/Inertia, vẽ biểu đồ đường cong Elbow.
    - [ ] Xác định số cụm tối ưu $k$ (thường chọn $k = 4$).
    - [ ] Tiến hành gom cụm bằng `KMeans(n_clusters=4, init='random')`.
  - [ ] **Câu 7**: Trực quan hóa kết quả gom cụm trên biểu đồ phân tán 2D (tô màu theo nhãn cụm và vẽ vị trí các tâm cụm `centroids`).
  - [ ] **Câu 8**: Đánh giá chất lượng phân cụm bằng hệ số dáng điệu Silhouette (`metrics.silhouette_score`).
  - [ ] **Câu 9**:
    - [ ] Thực hiện lại quy trình tương tự (Elbow $\rightarrow$ $k$-Means $\rightarrow$ Trực quan hóa $\rightarrow$ Silhouette) cho cặp thuộc tính: `Annual Income (k$)` và `Spending Score (1-100)` (thường chọn $k = 5$).
    - [ ] Thực hiện gom cụm theo cả 3 thuộc tính (`Age`, `Annual Income (k$)`, `Spending Score (1-100)`) và vẽ biểu đồ 3D tương tác bằng thư viện `plotly`.

---

### BÀI 6: Gom cụm tập dữ liệu chữ số MNIST bằng K-Means
- **Tập tin**: `model/6451071079_LAB3_Bai6.ipynb`
- **Vị trí tài liệu**: Trang 26 PDF (Phần 2 - Mục IV.5)
- **Tập dữ liệu**: `MNIST`
- **Danh sách công việc**:
  - [ ] Đọc dữ liệu MNIST từ Keras, làm phẳng ma trận thành vector 784 chiều, chuẩn hóa pixel về đoạn $[0, 1]$.
  - [ ] Áp dụng thuật toán `KMeans(n_clusters=10, random_state=42)` để gom thành 10 cụm.
  - [ ] Thiết lập ánh xạ từ số cụm (Cluster ID) sang nhãn chữ số thực tế dựa trên phân bố nhãn chiếm đa số (Majority Voting) trong mỗi cụm.
  - [ ] Đánh giá độ phù hợp của kết quả gom cụm so với nhãn thực tế:
    - [ ] Tính Accuracy, Precision, Recall, F1-score.
    - [ ] Vẽ ma trận nhầm lẫn (Confusion Matrix) dạng Heatmap.
  - [ ] Trực quan hóa 10 vector tâm cụm (Cluster Centroids) dưới dạng hình ảnh $28 \times 28$ pixel để quan sát chữ số đại diện của từng cụm.

---

### BÀI 7: Giảm số màu trong ảnh (nén ảnh) bằng K-Means
- **Tập tin**: `model/6451071079_LAB3_Bai7.ipynb`
- **Vị trí tài liệu**: Trang 26 - 28 PDF (Phần 2 - Mục IV.6)
- **Tập dữ liệu**: File ảnh màu thực tế (`Dataset/dog.png` hoặc ảnh mẫu tương đương)
- **Danh sách công việc**:
  - [ ] Đọc ảnh màu bằng thư viện `PIL.Image`, hiển thị ảnh gốc và in kích thước ảnh `(rows, cols, channels)`.
  - [ ] Chuyển mảng ảnh sang mảng số thực NumPy, chuẩn hóa giá trị màu về đoạn $[0, 1]$ và đổi kích thước thành ma trận 2D `(rows * cols, 3)`.
  - [ ] Chạy thuật toán `KMeans(n_clusters=32, max_iter=300, random_state=42)` để tìm 32 màu chủ đạo.
  - [ ] Thay thế giá trị màu của từng pixel bằng giá trị tâm cụm gần nhất (`kmeans.cluster_centers_[kmeans.predict(data)]`).
  - [ ] Khôi phục lại mảng ảnh thành dạng 3 chiều `(rows, cols, 3)`, chuyển về khoảng $[0, 255]$ với kiểu `np.uint8`.
  - [ ] Hiển thị so sánh song song giữa ảnh gốc và ảnh đã lượng tử hóa màu (32 màu).
  - [ ] Lưu ảnh nén xuống ổ đĩa (`compressed_image.png`) và so sánh dung lượng tệp trước và sau khi nén.

---

### BÀI 8: Gom cụm chẩn đoán khối u ung thư vú Wisconsin
- **Tập tin**: `model/6451071079_LAB3_Bai8.ipynb`
- **Vị trí tài liệu**: Trang 29 PDF (Phần 2 - Mục V.5)
- **Tập dữ liệu**: `Breast Cancer Wisconsin (Diagnostic)` (`sklearn.datasets.load_breast_cancer`)
- **Danh sách công việc**:
  - [ ] Đọc bộ dữ liệu ung thư vú Wisconsin (569 mẫu bệnh nhân, 30 thuộc tính hình thái tế bào, nhãn: Benign - lành tính / Malignant - ác tính).
  - [ ] Khảo sát dữ liệu, phân tích phân phối các thuộc tính.
  - [ ] Chuẩn hóa dữ liệu bằng `StandardScaler` (hoặc `MinMaxScaler`) để đồng nhất thang đo giữa 30 thuộc tính đo đạc.
  - [ ] Gom cụm bằng thuật toán `KMeans(n_clusters=2, random_state=42)`.
  - [ ] So khớp cụm tìm được với nhãn chẩn đoán thực tế.
  - [ ] Đánh giá chất lượng phân cụm:
    - [ ] Tính Accuracy, Precision, Recall, F1-score so với nhãn bác sĩ chẩn đoán.
    - [ ] Vẽ ma trận nhầm lẫn (Confusion Matrix).
    - [ ] Tính hệ số dáng điệu Silhouette Score.
  - [ ] Đưa ra nhận xét, đánh giá về khả năng ứng dụng giải thuật học không giám sát trong hỗ trợ sàng lọc tế bào học y khoa ban đầu.

---

## 3. CÁC NỘI DUNG LÝ THUYẾT & TÍNH TAY THAM KHẢO THÊM TRONG ĐỀ

- [ ] **Phần 1 - Bài 5 (Trang 9 - 11 PDF)**: Mạng nơ-ron hồi quy dự đoán doanh thu bán game (`sales_data_training.csv`, tối ưu MSE, đo lường bằng MAE).
- [ ] **Phần 2 - Mục III.1 (Trang 12 - 17 PDF)**: Bài toán tính tay gom cụm 6 bức tranh (3 thuộc tính: màu, đường nét, hình khối) bằng cả $k$-Means và mạng Kohonen SOM ($epochs=5, R=0, \alpha=0.4$), sau đó gán nhãn cho bức tranh thứ 7.
- [ ] **Phần 2 - Mục IV.1, IV.2, IV.4 (Trang 25 - 26 PDF)**:
  - Định vị 3 cửa hàng pizza mới.
  - Khuyến nghị đơn hàng đồ gia dụng bằng phân cụm giỏ hàng.
  - Gom cụm hành khách tàu Titanic bằng $k$-Means.
- [ ] **Phần 2 - Mục V.1 -> V.4 (Trang 28 - 29 PDF)**:
  - Cài đặt $k$-Medoids, Kohonen SOM, $k$-Means++.
  - Phản biện việc tự động xác định số cụm mà không cần người dùng nhập $k$.
  - Giải thích hiện tượng $k$-Means với 100 dòng cho ra 1 cụm không rỗng.
  - Tìm hiểu các giải thuật gom cụm: $k$-Modes, CLARANS, Chameleon, BIRCH, DBSCAN, OPTICS, STING, CLIQUE.
