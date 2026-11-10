# BÁO CÁO THỰC HÀNH BUỔI 3: KHAI PHÁ DỮ LIỆU
## CHỦ ĐỀ: MẠNG NƠ-RON (NEURAL NETWORK) & GIẢI THUẬT GOM CỤM (CLUSTERING)
### MÔN HỌC: KHAI PHÁ DỮ LIỆU (DATA MINING - IT1.231.3)

---

## 1. THÔNG TIN SINH VIÊN VÀ HỌC PHẦN

- **Họ và tên sinh viên**: Nguyễn Thành Trí
- **Mã số sinh viên (MSSV)**: `6451071079`
- **Lớp**: CQ.64.CNTT
- **Đơn vị đào tạo**: Phân hiệu Trường Đại học Giao thông Vận tải tại TP. Hồ Chí Minh - Bộ môn Công nghệ Thông tin
- **Giảng viên hướng dẫn**: ThS. Nguyễn Thiện Dương
- **Kho lưu trữ GitHub**: [https://github.com/TriNguyenThanh/6451071079_Lab23](https://github.com/TriNguyenThanh/6451071079_Lab23)
- **Tài liệu tham chiếu**: [docs/lab3.pdf](docs/lab3.pdf), [docs/Template nộp bài LAB3.docx](docs/Template%20nộp%20bài%20LAB3.docx), [task.md](task.md)

---

## 2. TỔNG QUAN NỘI DUNG THỰC HÀNH

Kho lưu trữ này chứa toàn bộ mã nguồn, dữ liệu thực nghiệm và kết quả phân tích cho bài thực hành **Lab 3: Mạng nơ-ron và các thuật toán gom cụm dữ liệu**:

1. **Phần 1: Mạng nơ-ron nhân tạo (Neural Network - Keras / TensorFlow)**
   - Xây dựng mô hình phân lớp nhiều tầng (Multilayer Perceptron - MLP) trên bộ dữ liệu hoa Iris và tập ảnh chữ số viết tay MNIST.
   - Kỹ thuật phân chia dữ liệu: Train / Validation / Test và kiểm định chéo $K$-Fold Cross Validation ($k = 10$).
   - Trực quan hóa biến thiên Accuracy và Loss qua từng chu kỳ học (Epochs) và từng Fold.
   - Đánh giá toàn diện qua ma trận nhầm lẫn (Confusion Matrix), Accuracy, Precision, Recall, Macro F1-score và phân tích các trường hợp phân lớp sai.
2. **Phần 2: Giải thuật gom cụm dữ liệu (Clustering Algorithms - $k$-Means)**
   - Phân đoạn khách hàng (Customer Segmentation) trên tập dữ liệu Mall Customers.
   - Xác định số cụm tối ưu $k$ bằng phương pháp khuỷu tay (Elbow Method - WSS / Inertia) và hệ số dáng điệu (Silhouette Coefficient).
   - Trực quan hóa kết quả phân cụm trong không gian 2D và không gian 3D tương tác (Plotly / Matplotlib 3D).
   - Ứng dụng gom cụm ảnh chữ số MNIST và lượng tử hóa màu sắc (Color Quantization) để nén dung lượng file ảnh.
   - Ứng dụng phân cụm tế bào học hỗ trợ chẩn đoán khối u ung thư vú Wisconsin (Benign / Malignant) kết hợp kỹ thuật giảm chiều dữ liệu PCA (Principal Component Analysis).

---

## 3. DANH SÁCH BÀI TẬP VÀ MÃ NGUỒN (NOTEBOOKS)

Toàn bộ các bài tập được lưu trữ tại thư mục duy nhất: [model/](model/):

| Bài tập | Tập tin Notebook | Tập dữ liệu | Giải thuật & Kỹ thuật chính |
| :--- | :--- | :--- | :--- |
| **Bài 1** | [model/6451071079_LAB3_Bai1.ipynb](model/6451071079_LAB3_Bai1.ipynb) | `sklearn.datasets.load_iris` | Decision Tree, Naïve Bayes, KNN, Keras MLP, Dự đoán mẫu mới |
| **Bài 2** | [model/6451071079_LAB3_Bai2.ipynb](model/6451071079_LAB3_Bai2.ipynb) | `keras.datasets.mnist` | Keras Sequential (Flatten, Dense 128, Dropout 0.2, Dense 10), Đồ thị Epochs, Phân tích 5 ca lỗi |
| **Bài 3** | [model/6451071079_LAB3_Bai3.ipynb](model/6451071079_LAB3_Bai3.ipynb) | `keras.datasets.mnist` | MNIST Neural Network kết hợp 10-Fold Cross Validation, Thống kê Mean/Std, Đánh giá Best Model |
| **Bài 4** | [model/6451071079_LAB3_Bai4.ipynb](model/6451071079_LAB3_Bai4.ipynb) | `sklearn.datasets.load_iris` | Iris Neural Network kết hợp 10-Fold Cross Validation, Đo lường từng lớp, Dự đoán 3 mẫu mới |
| **Bài 5** | [model/6451071079_LAB3_Bai5.ipynb](model/6451071079_LAB3_Bai5.ipynb) | `Dataset/Mall_Customers.csv` | Gom cụm khách hàng bằng $k$-Means, Phương pháp Elbow, Hệ số Silhouette, Biểu đồ 2D & 3D Plotly |
| **Bài 6** | [model/6451071079_LAB3_Bai6.ipynb](model/6451071079_LAB3_Bai6.ipynb) | `keras.datasets.mnist` | Gom cụm không giám sát chữ số MNIST bằng $k$-Means ($k=10$), Ánh xạ Majority Voting, Trực quan hóa 10 tâm cụm |
| **Bài 7** | [model/6451071079_LAB3_Bai7.ipynb](model/6451071079_LAB3_Bai7.ipynb) | `Dataset/dog.png` | Lượng tử hóa 32 màu chủ đạo bằng $k$-Means, Tái tạo ảnh 3D, Nén file ảnh và so sánh dung lượng |
| **Bài 8** | [model/6451071079_LAB3_Bai8.ipynb](model/6451071079_LAB3_Bai8.ipynb) | `sklearn.datasets.load_breast_cancer` | Chuẩn hóa StandardScaler, $k$-Means ($k=2$), Đánh giá độ tương đồng với chẩn đoán y khoa, Chiếu PCA 2D |

---

## 4. CẤU TRÚC THƯ MỤC DỰ ÁN

```text
lab3/
├── Dataset/                            # Dữ liệu cục bộ và sản phẩm xuất ra
│   ├── Mall_Customers.csv              # Tập dữ liệu mua sắm khách hàng (Bài 5)
│   ├── dog.png                         # Ảnh gốc dùng để thử nghiệm nén màu (Bài 7)
│   └── compressed_image.png            # Ảnh đã được lượng tử hóa màu và nén (Bài 7)
├── docs/                               # Tài liệu hướng dẫn, template và đường dẫn
│   ├── lab3.pdf                        # Tài liệu hướng dẫn thực hành 29 trang
│   ├── Link truy cập dataset.txt       # Liên kết tải dữ liệu từ giảng viên
│   ├── task.md                         # Danh mục câu hỏi và tiến độ chi tiết
│   └── Template nộp bài LAB3.docx      # Biểu mẫu báo cáo kết quả thực hành
├── model/                              # Thư mục lưu trữ duy nhất cho toàn bộ mã nguồn
│   ├── 6451071079_LAB3_Bai1.ipynb      # Phân lớp Iris (4 mô hình)
│   ├── 6451071079_LAB3_Bai2.ipynb      # Phân lớp MNIST (Train/Val/Test)
│   ├── 6451071079_LAB3_Bai3.ipynb      # Phân lớp MNIST (10-Fold CV)
│   ├── 6451071079_LAB3_Bai4.ipynb      # Phân lớp Iris (10-Fold CV)
│   ├── 6451071079_LAB3_Bai5.ipynb      # Phân cụm Mall Customers
│   ├── 6451071079_LAB3_Bai6.ipynb      # Gom cụm chữ số MNIST
│   ├── 6451071079_LAB3_Bai7.ipynb      # Nén ảnh / Giảm số màu
│   └── 6451071079_LAB3_Bai8.ipynb      # Phân cụm ung thư vú Wisconsin
├── requirements.txt                    # Danh sách các thư viện phụ thuộc
├── task.md                             # Bảng theo dõi tiến độ công việc
├── CLAUDE.md                           # Bản đặc tả quy chuẩn cho Claude Code
├── AGENTS.md                           # Bản đặc tả quy chuẩn chung cho các AI Agent
└── README.md                           # Tài liệu tổng quan dự án
```

---

## 5. HƯỚNG DẪN CÀI ĐẶT VÀ CHẠY THỰC NGHIỆM

### 5.1. Khởi tạo môi trường ảo Python

Khuyến nghị sử dụng Python phiên bản 3.10 trở lên:

```bash
# Khởi tạo môi trường ảo .venv
python3 -m venv .venv

# Kích hoạt môi trường trên Linux / macOS
source .venv/bin/activate

# Hoặc kích hoạt trên Windows PowerShell
# .\.venv\Scripts\Activate.ps1
```

### 5.2. Cài đặt các thư viện cần thiết

Cài đặt thông qua tập tin `requirements.txt`:

```bash
pip install -r requirements.txt
```

*Các gói thư viện chính được sử dụng bao gồm*: `numpy`, `pandas`, `scikit-learn`, `tensorflow`, `keras`, `matplotlib`, `seaborn`, `plotly`, `pillow`, `ipykernel`, `nbformat`, `nbclient`.

### 5.3. Đăng ký Kernel cho Jupyter

```bash
python -m ipykernel install --user --name venv_lab3 --display-name "Python 3 (.venv)"
```

### 5.4. Khởi chạy và xem kết quả

Mở giao diện Jupyter Notebook hoặc mở trực tiếp trên VSCode với kernel `Python 3 (.venv)`:

```bash
jupyter notebook
```

---

## 6. QUY CHUẨN MÃ NGUỒN VÀ BÁO CÁO HỌC THUẬT

- **In định danh sinh viên**: Mỗi câu hỏi đều bắt buộc in định danh ở đầu cell code:
  ```python
  print("Họ tên: Nguyễn Thành Trí - MSSV: 6451071079")
  ```
- **Chuẩn hóa đồ thị**: Tất cả các đồ thị biểu diễn kết quả đều được thiết lập tiêu đề (`plt.title`), nhãn trục (`plt.xlabel`, `plt.ylabel`), chú thích (`plt.legend`) và lưới nền (`plt.grid(True, alpha=0.3)`).
- **Trực quan hóa không gian ba chiều**: Sử dụng cả biểu đồ 3D tương tác của `Plotly` và biểu đồ tĩnh của `Matplotlib 3D` nhằm tối ưu khả năng quan sát phân bố dữ liệu đa chiều.
- **Quy chuẩn Git Commit**: Mỗi câu hỏi sau khi thực thi và kiểm tra kết quả thành công được tạo một commit riêng biệt theo cú pháp `feature<name>: message` với tác giả chuẩn xác từ hệ thống (`trislord`).
