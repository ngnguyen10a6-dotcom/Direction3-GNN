# Hướng 3 – GNN trên Knowledge Graph kế thừa từ Hướng 2

## 1. Phạm vi và dữ liệu
- Kiểm tra notebook Hướng 2 được cung cấp cho thấy phần khởi tạo `G` là đồ thị rỗng (`nx.Graph()`), các lệnh thêm cạnh đang để chú thích; danh sách user kiểm thử và item mẫu cũng được tạo bằng chuỗi giả lập. Do đó, không thể xem CSV này là bằng chứng của một KG Hướng 2 đã huấn luyện trên tương tác thực tế.
- Dữ liệu sản phẩm: `All_Beauty_Cleaned_Merged_GitHub.xlsx` (30 sản phẩm).
- Dữ liệu đầu ra Hướng 2: `Direction2_KG_Predictions.csv` (4 dòng dự đoán).
- Mô hình: R-GCN (Relational Graph Convolutional Network) với bộ giải mã DistMult để học và dự đoán liên kết trong đồ thị tri thức.
- Thực thể: Product, Brand, Category, Subcategory, User.
- Quan hệ: HAS_BRAND, IN_CATEGORY, IN_SUBCATEGORY, PREFERS_BRAND, PREFERS_CATEGORY và các quan hệ đảo chiều.

## 2. Cách kế thừa Hướng 2
Do notebook Hướng 2 hiện là mã khung/mô phỏng, Hướng 3 trong gói này được triển khai như một nguyên mẫu R-GCN độc lập trên KG tái dựng từ bảng thuộc tính sản phẩm Excel, đồng thời kế thừa metadata đầu ra Hướng 2. Trường `schema_metadata` trong CSV được phân tích để tạo các cạnh sở thích yếu của người dùng tới Brand/Category. Đây là tín hiệu hồ sơ được suy ra từ metadata của kết quả Hướng 2, không phải lịch sử mua hàng/đánh giá thực tế. Trường `score_kg` được giữ làm thông tin đối chứng, không dùng làm nhãn tương tác thật để huấn luyện GNN.

## 3. Kết quả chạy
- Số thực thể: 49
- Số loại quan hệ: 10
- Số bộ ba KG gốc: 97
- MRR link prediction (negative sampling 20 candidates): 0.4296
- Hits@10 link prediction (negative sampling 20 candidates): 0.7895
- Số epoch: 200; embedding dimension: 32.

**Lưu ý:** MRR và Hits@10 ở đây đo khả năng khôi phục bộ ba tri thức bị giữ lại, không phải Precision@K/Recall@K/NDCG của gợi ý sản phẩm. Do không có ground-truth user-item interactions, không thể kết luận GNN tốt hơn Hướng 2 về độ chính xác gợi ý.

## 4. Giới hạn dữ liệu cần nêu trong báo cáo
Có 4 / 4 mã sản phẩm được Hướng 2 đề xuất không khớp với mã sản phẩm trong Excel. Vì vậy không thể đối chiếu trực tiếp các mã sản phẩm Hướng 2 với danh mục 30 sản phẩm. Vì notebook Hướng 2 có phần tạo dữ liệu giả lập và CSV hiện tại chỉ có 4 dòng, kết quả GNN này chỉ là nguyên mẫu minh họa phương pháp. GNN sinh Top-10 trong danh mục Excel bằng cosine similarity giữa embedding User và Product đã học từ KG. Đây là kết quả thử nghiệm nguyên mẫu dựa trên đồ thị và metadata, không phải đánh giá người dùng thực tế.

## 5. Tệp kết quả
- `Direction3_GNN_Predictions.csv`: danh sách Top-10 do R-GCN xếp hạng.
- `Direction3_GNN_Metrics.csv`: chỉ số link prediction trên KG.
- `Direction2_Baseline_Audit.csv`: kiểm tra mã sản phẩm Hướng 2 có nằm trong danh mục Excel hay không.
- `Direction3_User_Profile_From_H2.csv`: hồ sơ User suy ra từ metadata.
- `GNN_Training_Loss.png`, `GNN_Top10_Score.png`, `GNN_Brand_Distribution.png`: biểu đồ.
