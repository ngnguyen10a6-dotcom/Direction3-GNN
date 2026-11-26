Hướng 3 — Graph Neural Network (GNN) Recommendation

Người thực hiện: Giảng Nguyên (Member 3)

Đề tài: Phát triển hệ thống gợi ý sản phẩm sử dụng Graph Neural Network (GNN).

1. Mục tiêu

Kế thừa dữ liệu và kết quả từ Hướng 2 — Knowledge Graph Recommendation, xây dựng mô hình Graph Neural Network (GNN) để học biểu diễn người dùng và sản phẩm trên đồ thị tri thức. Từ đó cải thiện khả năng dự đoán và gợi ý sản phẩm.

2. Dữ liệu đầu vào

* Dataset: All_Beauty_Cleaned_Merged_GitHub.xlsx
* User Profile: Direction3_User_Profile_From_H2.csv
* Baseline: Direction2_Baseline_Audit.csv

3. Phương pháp thực hiện

* Xây dựng đồ thị người dùng và sản phẩm.
* Huấn luyện mô hình GNN.
* Tạo điểm dự đoán cho sản phẩm.
* Xếp hạng Top 10 sản phẩm.
* Đánh giá kết quả mô hình.

4. Kết quả thực nghiệm

* Direction3_GNN_Predictions.csv
* Direction3_GNN_Metrics.csv
* GNN_Top10_Score.png
* GNN_Training_Loss.png
* GNN_Brand_Distribution.png

5. Công cụ sử dụng

* Python
* Pandas
* PyTorch
* Google Colab
* GitHub

6. Kết luận

Hướng 3 ứng dụng Graph Neural Network để khai thác mối quan hệ giữa người dùng và sản phẩm, tạo cơ sở cho việc phát triển hệ thống gợi ý sản phẩm thông minh hơn.
