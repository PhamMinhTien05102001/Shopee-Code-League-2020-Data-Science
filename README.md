# Giới thiệu về đề tài
* Đây là bộ dữ liệu được lấy từ cuộc thi “Shopee Code League 2020 Data Science” được tổ chức trên Kaggle (Link: https://www.kaggle.com/davydev/shopee-code-league-20). Cuộc thi tính điểm dựa trên việc phân loại 42 label được đánh nhãn từ “00” đến “41” là các hình ảnh quảng cáo về các món đồ được bán trên shopee. 
* Số lượng ảnh trong các label được thể hiện qua biểu đồ dưới đây
# Method 1
* Ta dùng Transfer learning ResNet50 cho toàn bộ 42 babel
* Kết quả accuracy, loss trên tập train và tập validation:
![resnet50_41label_65](https://user-images.githubusercontent.com/81013330/125044452-2b53f100-e0c6-11eb-94ed-f5b5a8d44f88.png)
* Kết quả dự đoán trên toàn bộ tập dữ liệu ban đầu:
![score_dep](https://user-images.githubusercontent.com/81013330/125044494-3575ef80-e0c6-11eb-8d93-47dc0f9cd655.png)
# Method 2
* Ta chia tập dữ liệu ban đầu ra thành 2 phần, mỗi phần train trên 1 model (đều là Transfer learning với VGG16)
* Model 1: ta train với 21 label ban đầu (từ "00" -> "20"), Model 2: ta train với 21 label ở nửa sau (từ "21" -> "41")
* Khi dự đoán 1 tấm ảnh thì tấm ảnh sẽ được cho qua 2 Model, là lấy kết quả của Model cho kết quả tốt hơn (như ví dụ ở hình dưới)

* Kết quả accuracy, loss trên tập train và tập validation của Model 1:

* Kết quả accuracy, loss trên tập train và tập validation của Model 2:
* Dưới đây lần lượt là 2 hình
![socre_vgg_2model](https://user-images.githubusercontent.com/81013330/125021001-0484c300-e0a4-11eb-924d-0e497cf97327.png)

