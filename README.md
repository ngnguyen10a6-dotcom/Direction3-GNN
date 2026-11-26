# Hướng 3 — Graph Neural Network (GNN)

**Người thực hiện:** Giảng Nguyên (Member 3)  
**Thời điểm tổng hợp:** 26/11/# Hướng 3 — Graph Neural Network (GNN)

**Người thực hiện:** Giảng Nguyên (Member 3)  
**Thời điểm tổng hợp:** 26/11/2026  

## Mục tiêu
Kế thừa dữ liệu từ **Hướng 2 – Knowledge Graph**, xây dựng mô hình **Graph Neural Network (GNN)** để học mối quan hệ giữa người dùng, sản phẩm, thương hiệu và danh mục sản phẩm nhằm hỗ trợ gợi ý sản phẩm.

## Dữ liệu đầu vào
* `All_Beauty_Cleaned_Merged_GitHub.xlsx` : Dataset đã được làm sạch và chuẩn hóa.
* `Direction2_KG_Predictions.csv` : Kết quả dự đoán từ Hướng 2 – Knowledge Graph.
* `Direction3_User_Profile_From_H2.csv` : Hồ sơ người dùng kế thừa từ Hướng 2.

## Phương pháp thực hiện
* Xây dựng **Knowledge Graph** từ dữ liệu đầu vào.
* Sử dụng mô hình **R-GCN** kết hợp **DistMult**.
* Huấn luyện mô hình với **200 epochs**, **embedding dimension 32**.
* Tạo danh sách gợi ý **Top-10** bằng **cosine similarity**.
* Đánh giá bằng **MRR** và **Hits@10**.

## Cấu trúc thư mục mã nguồn
* `Direction3_GNN.ipynb` : Notebook chính thực thi xây dựng đồ thị, huấn luyện R-GCN kết hợp DistMult, tạo gợi ý Top-10 và đánh giá.
* `Direction3_GNN_Predictions.csv` : File kết quả dự đoán từ mô hình GNN.
* `Direction3_GNN_Metrics.csv` : File lưu các chỉ số đánh giá thực nghiệm.
* `Direction3_User_Profile_From_H2.csv` : File hồ sơ người dùng kế thừa từ Hướng 2.
* `Direction2_Baseline_Audit.csv` : File kiểm tra / đối chiếu baseline từ Hướng 2.
* `GNN_Training_Loss.png` : Biểu đồ quá trình huấn luyện mô hình qua 200 epochs.
* `GNN_Top10_Score.png` : Biểu đồ điểm số gợi ý Top-10.
* `GNN_Brand_Distribution.png` : Biểu đồ phân bổ thương hiệu.

## Kết quả thực nghiệm
Thực nghiệm xây dựng đồ thị và đánh giá khả năng dự đoán liên kết trên Knowledge Graph:

| Chỉ số | Kết quả |
| :--- | :---: |
| Entities | 49 |
| Relations | 10 |
| Base Triples | 97 |
| MRR | 0.4296 |
| Hits@10 | 0.7895 |

> **Lưu ý:** `MRR` và `Hits@10` đánh giá dự đoán liên kết KG, không phải độ chính xác gợi ý sản phẩm.

## Biểu đồ trực quan hóa
Biểu đồ so sánh chi tiết quá trình huấn luyện, điểm số Top-10 và phân bổ thương hiệu đã được lưu tại: `GNN_Training_Loss.png`, `GNN_Top10_Score.png`, `GNN_Brand_Distribution.png`.

## Công nghệ sử dụng
Python, Pandas, NumPy, PyTorch, Matplotlib, Google Colab và GitHub.

## Kết luận
Mô hình **R-GCN** kết hợp **DistMult** đã được xây dựng và thực nghiệm trên Knowledge Graph. Kết quả bước đầu cho thấy khả năng dự đoán liên kết trong đồ thị tri thức.

## Mục tiêu
Kế thừa dữ liệu từ **Hướng 2 – Knowledge Graph**, xây dựng mô hình **Graph Neural Network (GNN)** để học mối quan hệ giữa người dùng, sản phẩm, thương hiệu và danh mục sản phẩm nhằm hỗ trợ gợi ý sản phẩm.

## Dữ liệu đầu vào
* `All_Beauty_Cleaned_Merged_GitHub.xlsx` : Dataset đã được làm sạch và chuẩn hóa.
* `Direction2_KG_Predictions.csv` : Kết quả dự đoán từ Hướng 2 – Knowledge Graph.
* `Direction3_User_Profile_From_H2.csv` : Hồ sơ người dùng kế thừa từ Hướng 2.

## Phương pháp thực hiện
* Xây dựng **Knowledge Graph** từ dữ liệu đầu vào.
* Sử dụng mô hình **R-GCN** kết hợp **DistMult**.
* Huấn luyện mô hình với **200 epochs**, **embedding dimension 32**.
* Tạo danh sách gợi ý **Top-10** bằng **cosine similarity**.
* Đánh giá bằng **MRR** và **Hits@10**.

## Cấu trúc thư mục mã nguồn
* `Direction3_GNN.ipynb` : Notebook chính thực thi xây dựng đồ thị, huấn luyện R-GCN kết hợp DistMult, tạo gợi ý Top-10 và đánh giá.
* `Direction3_GNN_Predictions.csv` : File kết quả dự đoán từ mô hình GNN.
* `Direction3_GNN_Metrics.csv` : File lưu các chỉ số đánh giá thực nghiệm.
* `Direction3_User_Profile_From_H2.csv` : File hồ sơ người dùng kế thừa từ Hướng 2.
* `Direction2_Baseline_Audit.csv` : File kiểm tra / đối chiếu baseline từ Hướng 2.
* `GNN_Training_Loss.png` : Biểu đồ quá trình huấn luyện mô hình qua 200 epochs.
* `GNN_Top10_Score.png` : Biểu đồ điểm số gợi ý Top-10.
* `GNN_Brand_Distribution.png` : Biểu đồ phân bổ thương hiệu.

## Kết quả thực nghiệm
Thực nghiệm xây dựng đồ thị và đánh giá khả năng dự đoán liên kết trên Knowledge Graph:

| Chỉ số | Kết quả |
| :--- | :---: |
| Entities | 49 |
| Relations | 10 |
| Base Triples | 97 |
| MRR | 0.4296 |
| Hits@10 | 0.7895 |

> **Lưu ý:** `MRR` và `Hits@10` đánh giá dự đoán liên kết KG, không phải độ chính xác gợi ý sản phẩm.

## Biểu đồ trực quan hóa
Biểu đồ so sánh chi tiết quá trình huấn luyện, điểm số Top-10 và phân bổ thương hiệu đã được lưu tại: `GNN_Training_Loss.png`, `GNN_Top10_Score.png`, `GNN_Brand_Distribution.png`.

## Công nghệ sử dụng
Python, Pandas, NumPy, PyTorch, Matplotlib, Google Colab và GitHub.

## Kết luận
Mô hình **R-GCN** kết hợp **DistMult** đã được xây dựng và thực nghiệm trên Knowledge Graph. Kết quả bước đầu cho thấy khả năng dự đoán liên kết trong đồ thị tri thức.
