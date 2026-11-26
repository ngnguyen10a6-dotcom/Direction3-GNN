HƯỚNG 3 – GRAPH NEURAL NETWORK (GNN)

Người thực hiện: Giảng Nguyên (Member 3)

1. Mục tiêu

Xây dựng mô hình Graph Neural Network (GNN) kế thừa dữ liệu từ Hướng 2 – Knowledge Graph, nhằm học mối quan hệ giữa người dùng, sản phẩm, thương hiệu và danh mục sản phẩm để hỗ trợ gợi ý sản phẩm.

2. Dữ liệu đầu vào

* All_Beauty_Cleaned_Merged_GitHub.xlsx
* Direction2_KG_Predictions.csv
* Direction3_User_Profile_From_H2.csv

3. Phương pháp thực hiện

* Xây dựng Knowledge Graph.
* Sử dụng mô hình R-GCN kết hợp DistMult.
* Huấn luyện mô hình với 200 epochs, embedding dimension 32.
* Tạo danh sách gợi ý Top-10 bằng cosine similarity.
* Đánh giá bằng MRR và Hits@10.

4. Kết quả thực nghiệm

Chỉ số	Kết quả
Entities	49
Relations	10
Base Triples	97
MRR	0.4296
Hits@10	0.7895

5. Source Code và kết quả

* Direction3_GNN.ipynb
* Direction3_GNN_Predictions.csv
* Direction3_GNN_Metrics.csv
* Direction3_User_Profile_From_H2.csv
* Direction2_Baseline_Audit.csv
* GNN_Training_Loss.png
* GNN_Top10_Score.png
* GNN_Brand_Distribution.png

6. Công nghệ sử dụng

Python, Pandas, NumPy, PyTorch, Matplotlib, Google Colab và GitHub.

7. Kết luận

Mô hình R-GCN kết hợp DistMult đã được xây dựng và thực nghiệm trên Knowledge Graph. Kết quả bước đầu cho thấy khả năng dự đoán liên kết trong đồ thị tri thức.

Lưu ý: MRR và Hits@10 đánh giá dự đoán liên kết KG, không phải độ chính xác gợi ý sản phẩm.
