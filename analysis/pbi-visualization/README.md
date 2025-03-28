# Giải thích

_File này chứa các file phân tích dưới hai định dạng: .pdf và .pbix. Trong đó, file .pbix được thiết kế để hiển thị báo cáo động, cho phép tùy chỉnh tiêu chí theo từng biểu đồ, trong khi file .pdf cung cấp báo cáo tĩnh, không hỗ trợ điều chỉnh tiêu chí._

Ta cùng bước vào phần phân tích. Các đầu mục trong phần phân tích bao gồm:

## Danh mục nội dung
- [Các từ viết tắt](#Các-từ-viết-tắt)
- [Bối cảnh](#Bối-cảnh)
- [Tổng quan](#Tổng-quan)
- [Các thông tin giá trị](#Các-thông-tin-giá-trị)
    - [Các xu hướng vắng mặt](#Các-xu-hướng-vắng-mặt)
    - [Xu hướng của các yếu tố đời sống](#Xu-hướng-của-các-yếu-tố-đời-sống)
    - [Xu hướng của các yếu tố công việc](#Xu-hướng-của-các-yếu-tố-công-việc)
- [Dự đoán](#Dự-đoán)
    - [Phương pháp dự đoán](#Phương-pháp-dự-đoán)
    - [Trọng số đối với dự đoán](#Trọng-số-đối-với-dự-đoán)
    - [Kết quả dự đoán](#Kết-quả-dự-đoán)
        - [Lý do và thời gian](#Lý-do-và-thời-gian)
        - [Yếu tố đời sống](#Yếu-tố-đời-sống)
        - [Yếu tố công việc](#Yếu-tố-công-việc)
- [Đề xuất chính sách](#Đề-xuất-chính-sách)
- [Bài phân tích trên PowerBI đã được thực hiện ra sao?](#Bài-phân-tích-trên-PowerBI-đã-được-thực-hiện-ra-sao?)
  - [Làm sạch và tổ chức dữ liệu](#Làm-sạch-và-tổ-chức-dữ-liệu)
  - [Trực quan hóa dữ liệu](#Trực-quan-hóa-dữ-liệu)

## Bối cảnh
Dữ liệu được sử dụng là dữ liệu mô phỏng cho tình hình vắng mặt tại một công ty được thu thập qua các năm. Ban lãnh đạo muốn tìm ra những <b>xu hướng chính cho sự vắng mặt của các nhân viên tại công ty</b>, sau khi tìm hiểu về những nguyên nhân có thể gây mất mát doanh thu tại một doanh nghiệp.

Ban lãnh đạo cũng muốn có những dự đoán tương lai, một phần để tìm ra số giờ làm việc có thể bị mất, một phần để tìm ra yếu tố có trọng số lớn nhất đối với số giờ vắng mặt. 

Tất cả những phân tích được thực hiện nhằm mục đích ra <b>quyết định liên quan tới chính sách nhân sự.</b>

## Các từ viết tắt và ý nghĩa các nhóm lý do
Các từ viết tắt được liệt kê theo thứ tự xuất hiện trong báo cáo.
| **Tên cột**      	| **Ý nghĩa**      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| TB         	| Trung bình |
| BMI         	| Body Mass Index |
| TBKLCVHN         	| Trung bình khối lượng công việc hằng ngày |
| KC         	| Khoảng cách |
| CTY        	| Công ty |
| CP         	| Chi phí |
| DĐ         	| Dự đoán |

**Về các lý do:**
- Lý do A là các lý do liên quan tới bệnh lý và rối loạn sức khỏe.
- Lý do B là các lý do liên quan tới sức khỏe sinh sản và bẩm sinh.
- Lý do C là các lý do liên quan tới triệu chứng và nguyên nhân ngoại lai.
- Lý do D là các lý do cá nhân và môi trường.

_Người đọc có thể xem thêm về cách chia lý do tại [đây](https://drive.google.com/file/d/1G8FA65FgBqxk-xm1g4tqi7NcKUaIV-Rk/view)_

## Tổng quan
Tổng số giờ vắng mặt của tất cả nhân viên trong khoảng thời gian nghiên cứu của bộ dữ liệu là 4733 giờ, với mỗi nhân viên vắng mặt sẽ vắng 6.76 tiếng trong một ca làm việc. Trong số các lý do vắng mặt, nhóm lý do gây vắng mặt nhiều nhất là lý do D với 418 lần các nhân viên vắng mặt vì lý do thuộc nhóm này. Nhóm lý do gây mất mát nhiều giờ làm việc nhất là lý do A, với tổng cộng 2269 giờ vắng mặt. 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/ace1459b-277d-46fe-92f1-1d8e3ddfe5d9">
    <img width="100%" src="https://github.com/user-attachments/assets/ddc0f981-9d9c-4662-9ee2-891fcbd04a68">
</p>

Phần lớn các nhân viên vắng mặt rơi vào độ tuổi trung niên có một con và không có thú cưng, với độ tuổi trung bình của các nhân viên này là 36.42, số con cái trung bình là 1.02 và số thú cưng trung bình là 0.69. Ngoài ra, những người vắng mặt hầu hết đều bị thừa cân, với BMI trung bình của họ là 26.74. 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/29620d6e-b823-43cc-8570-a35bcd9b6cd4">
</p>

_(Để tham khảo thêm về chia khoảng BMI, có thể nhấp vào link [này](https://medlatec.vn/media/24658/file/Ch%e1%bb%89-s%e1%bb%91-BMI-4+(3).png))._

Đa phần nhân viên vắng mặt có học vấn Đại học, với 83.29%. Những nhân viên có học vấn Đại học cũng vắng lâu hơn khi họ vắng trung bình 6.94 giờ, so với 5.86 giờ của nhân viên có học vấn Hậu Đại học. 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/49969063-c80f-4613-901e-e425727efc3f">
</p>

Mỗi nhân viên vắng mặt có khối lượng công việc trung bình hằng ngày là 271.80 phút. Trung bình mỗi ngày các nhân viên này phải di chuyển gần 30km (29.89) để tới công ty, với chi phí đi lại trung bình là 222.35$.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/aa9cbf99-6566-4d86-8f69-0c96dfe59dcd">
</p>

## Các thông tin giá trị
### Các xu hướng về thời gian

- Trung bình mỗi tháng công ty <b>mất 394 giờ làm việc</b>, với các <b>tháng 3, 4, 7, 11, 12 là các tháng nhân viên vắng mặt lâu hơn trung bình</b>.
  - <b>Tháng 3</b> là tháng có <b>nhiều nhân viên vắng mặt nhất</b>, đồng thời <b>vắng lâu nhất</b> với <b>87 nhân viên báo cáo vắng và 765 giờ làm việc bị mất</b>.
  - <b>Tháng 2 và tháng 10</b> là hai tháng có <b>nhiều nhân viên báo vắng thứ hai và thứ ba</b>, với lần lượt <b>72 và 71 nhân viên báo vắng</b> trong các tháng này.

- <b>Số giờ vắng/ngày</b> của công ty là <b>676 giờ</b>, với các <b>thứ đầu tuần (thứ Hai, Ba, Tư)</b> và ngày làm việc (chính thức) cuối cùng trong tuần <b>(thứ Sáu)</b> có <b>tổng thời gian vắng mặt lâu hơn trung bình.</b>
  - <b>Thứ Hai, Ba, Tư đều có trên 1000 giờ vắng mặt</b>, <b>nhiều hơn so với các ngày còn lại</b> trong tuần.
  - Tuy có thể là ngày OT và tổng cộng chỉ có <b>4 người báo vắng</b> trong suốt khoảng thời gian của dữ liệu nhưng <b>thứ Bảy lại có số giờ vắng trung bình cao thứ hai (8.5 giờ)</b>, chỉ <b>kém gần 1 giờ</b> so với <b>thứ Hai (9.4 giờ).</b>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/06215e0c-3ec7-42c8-b1e1-2f79b7b04df6">
</p>

### Xu hướng của các yếu tố đời sống

- Các <b>nhân viên lớn tuổi</b> có xu hướng <b>vắng lâu hơn</b>, dựa trên biểu đồ <b>YẾU TỐ TUỔI TÁC.</b>
- Những biểu đồ như <b>YẾU TỐ CON CÁI và YẾU TỐ THÚ CƯNG</b> có <b>mẫu số khá bé, do đó chưa thể đưa ra kết luận</b>. Tuy nhiên, có thể thấy việc có <b>nhiều con có thể gây vắng lâu hơn</b>, trong khi <b>nhiều thú cưng giảm thời vắng đi đáng kể.</b>
- Hầu hết các <b>nhân viên vắng lâu</b> có <b>BMI trên mức bình thường</b> (thừa cân, béo phì I, béo phì II) dựa trên biểu đồ <b>YẾU TỐ BMI.</b> Tuy nhiên, dữ liệu lại cho thấy rằng những người có <b>BMI càng cao càng vắng ít hơn</b>.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/92e92e9a-33be-41e2-a982-1f60a6037b2d">
</p>

### Xu hướng của các yếu tố công việc

- Các <b>nhân viên làm ít có xu hướng vắng ít hơn so với các nhân viên làm nhiều</b>, dựa trên biểu đồ <b>YẾU TỐ TBKLCVHN</b>. Tuy nhiên, các <b>nhân viên vắng lâu nhất lại làm việc ít hơn mức công việc trung bình</b> (góc trên cùng bên trái của cùng biểu đồ)
- Dựa trên biểu đồ <b>YẾU TỐ KHOẢNG CÁCH TỚI CTY</b>, các nhân viên nhà <b>càng xa công ty càng vắng ít hơn</b>. Các <b>nhân viên nhà gần thuộc các nhân viên vắng lâu</b>, làm mất nhiều giờ làm việc tại công ty nhất (góc trên cùng bên trái của cùng biểu đồ)
- <b>Không có mối tương quan giữa chi phí đi lại và thời gian vắng</b>, dựa trên biểu đồ YẾU TỐ CP ĐI LẠI. Các nhân viên <b>vắng lâu nhất có chi phí đi lại không quá trung bình</b> (trên cùng, chính giữa biểu đồ)

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/04cd245e-63b1-4630-a920-dbe328a36acf">
</p>

## Dự đoán

### Mô hình dự đoán

Để thực hiện dự đoán, đầu tiên ta xét giữa các mô hình học máy hồi quy phù hợp với dữ liệu có mẫu số nhỏ. Sau sàng lọc, ta chọn được các mô hình sau: 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/92fefca4-8868-4a16-8d30-b8c99a98ac58">
</p>

_(Cụ thể, các mô hình được lựa chọn là: [Random Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestRegressor.html), [Gradient Boosting](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingRegressor.html), [Decision Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html), [Linear](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html), [Lasso](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html), [Ridge](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html), [Support Vector Regression](ble/modules/generated/sklearn.svm.SVR.html), [KNeighbors](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsRegressor.html))._

Các bước tiếp theo đã được mô tả tương đối chi tiết trong file [absenteeism-predictive-analysis.ipynb](https://github.com/hinmfm/absenteeism-prediction/blob/main/prediction-data/absenteeism-predictive-analysis.ipynb). Mô hình học máy sau cùng được lựa chọn là SVR. Người đọc có thể tham khảo thêm về cách lựa chọn mô hình tại file đã đính kèm link ở trên.


### Trọng số đối với dự đoán

Trọng số đối với dự đoán của đã được mô tả khá kỹ trong file [absenteeism-predictive-analysis.ipynb](https://github.com/hinmfm/absenteeism-prediction/blob/main/prediction-data/absenteeism-predictive-analysis.ipynb). Người đọc có thể tham khảo thêm tại file này.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/779f2580-aec8-4fde-8136-5750d57ef6a3">
</p>

### Kết quả dự đoán

Tổng số giờ vắng được dự đoán xấp xỉ 2982 giờ.

<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/985c3c55-efc3-407a-9bf6-1174c47331de">
</p>

Kết quả dự đoán chi tiết về số giờ vắng mặt theo mô hình học máy SVR như sau:

#### Lý do và thời gian

- Mùa Xuân được dự đoán là mùa gây vắng mặt lâu nhất với hơn 875 giờ làm việc được dự đoán bị mất vào mùa này, dựa trên biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO MÙA.
- Củng cố thêm cho dữ liệu này, từ biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO THÁNG, các tháng mùa Xuân (tháng 1, 2, 3) cũng sẽ được dự kiến có số thời gian vắng mặt nhiều hơn so với các tháng còn lại.
    - Các tháng được dự đoán sẽ có số giờ vắng mặt nhiều hơn trung bình lầ tháng 2, 3, 5, 7, 8, 10, 11.
- Đối với các ngày trong tuần, ta chỉ dự đoán tất cả các ngày việc chính thức (từ thứ Hai tới thứ Sáu) do mẫu số để phân tích của các ngày cuối tuần quá nhỏ (chỉ có lần lượt 4 và 9 nhân viên vắng mặt).
    - Dựa trên biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO THỨ, thứ Hai, Ba, Tư, Năm được dự đoán sẽ có thời gian vắng mặt nhiều hơn trung bình. Thứ Hai và thứ Tư dự kiến sẽ là hai thứ làm mất nhiều thời gian làm việc nhất.
- Lý do A và lý do C được dự đoán sẽ là 2 lý do gây vắng mặt nhiều nhất, dựa trên biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO LÝ DO. Lý do B không được đưa vào dự đoán do có mẫu số quá ít (chỉ có 6 nhân viên vắng mặt vì lý do B)

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/d409469d-372b-4a69-8d63-020a83288524">
</p>

#### Yếu tố đời sống

- Các nhân viên học Đại học sẽ vắng lâu hơn, một phần do họ chiếm đa số trong những nhân viên vắng. Do vậy, có thể đây là một dự đoán không quá có ý nghĩa.
- Có sự chênh lệch không quá lớn xét trên mốc trung bình về dự đoán giờ vắng theo độ tuổi, dựa trên biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO TUỔI.
- Các nhân viên có BMI ở mức bình thường được dự đoán sẽ vắng nhiều hơn so với các mức BMI khác.
- Trong 2 biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO SỐ CON CÁI và DỰ ĐOÁN GIỜ VẮNG THEO SỐ THÚ CƯNG, số con cái và số thú cưng > 2 đều bị loại khỏi dự đoán do mẫu số quá ít.
  - Những nhân viên không có con được đự doán có thời gian vắng nhiều hơn trung bình.
  - Những nhân viên không có thú cưng được dự đoán có thời gian vắng nhiều hơn trung bình.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/8f4f1f68-39c4-4b95-a91b-b3a8515dbd09">
</p>

#### Yếu tố công việc

- Dựa trên biểu DỰ ĐOÁN GIỜ VẮNG THEO CP ĐI LẠI, dù những nhân viên vắng lâu nhất có chi phí đi lại thấp hơn trung bình, phần lớn số giờ làm việc bị mất sẽ do đội ngũ nhân viên có chi phí đi lại cao hơn trung bình gây ra.
- Các nhân viên nhà gần với công ty sẽ vắng lâu hơn, đồng thời số giờ làm việc bị mất trên trung bình cũng thuộc nhóm nhân viên này, dựa trên biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO KC TỚI CTY.
- Dù một tập hợp những nhân viên có khối lượng công việc hằng ngày lớn được dự đoán sẽ vắng mặt lâu nhất, những nhân viên làm ít hơn sẽ vắng lâu hơn, theo biểu đồ DỰ ĐOÁN GIỜ VẮNG THEO TBKLCVHN.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/user-attachments/assets/81650aa8-338f-408c-83cf-5a12860ef562">
</p>

## Đề xuất chính sách

Dựa trên những dữ liệu đã phân tích, dưới đây là một số những chính sách được đề xuất đề cải thiện tình hình vắng mặt tại công ty:
- Đối với sự vắng mặt theo thời gian và lý do:
  - Ban lãnh đạo có thể phát động những chương trình giúp các nhân viên có tinh thần làm việc cao hơn vào các mùa hoặc các tháng nhiều lễ hội. Do dữ liệu này lấy từ một công ty của Mỹ, những tháng đầu tiên và cuối cùng trong năm của họ sẽ có nhiều lễ hội hơn bình thường.
  - Lý do A và lý do D là 2 lý do khiến các nhân viên vắng mặt lâu nhất.
    - Như đã giải thích phía trên, lý do A là các lý do liên quan tới bệnh lý, rối loạn sức khỏe. Đây cũng là lý do hiện gây vắng mặt nhiều nhất, đồng thời được dự đoán sẽ gây vắng mặt nhiều nhất. Các gói bảo hiểm sức khỏe có thể được cải thiện để giúp các nhân viên có thể trở lại sớm hơn, hoặc có thể cho nghỉ các nhân viên có vấn đề này để tránh lây lan cũng như giải quyết dứt điểm vấn đề trước khi quay lại công ty.
    - Về lý do D, hay các lý do cá nhân và môi trường. Ban lãnh đạo có thể liên hệ với các nhà quản lý, trưởng phòng các nhân viên vắng mặt theo lý do để hạn chế việc vắng vì những lý do không hợp lý thuộc nhóm này như hiến máu hoặc vắng mặt không lý do.
   
- Đối với sự vắng mặt theo các yếu tố đời sống:
  - Các nhân viên lớn tuổi, có độ tuổi trên trung bình có thể được hỗ trợ di chuyển để tới công ty nhanh hơn.
  - Công ty có thể mở phòng trị liệu tâm lý để hỗ trợ về mặt tinh thần đối với các nhân viên không có con, vì đây có thể là yếu tố gây ra bệnh trầm cảm nếu các nhân viên đã ở độ tuổi trung niên, xế chiều.
  - Các phong trào về nuôi thêm thú cưng cũng có thể được phát động, vì chúng giúp các nhân viên ổn định tinh thần hơn, đồng thời vắng mặt ít hơn.
  - Đối với BMI, các nhân viên có BMI thấp vắng nhiều hơn. Do vậy, ban lãnh đạo có thể thực hiện những cuộc phỏng vấn, khảo sát về chế độ dinh dưỡng để tìm hiểu nguyên nhân tại sao những nhân viên này lại vắng lâu hơn. Việc có chế độ ăn không phù hợp hoặc dinh dưỡng không đúng, đủ điều độ có thể khiến cơ thể bị thiếu hụt năng lượng và ảnh hưởng tới hiệu suất làm việc nói chung.
 
- Đối với sự vắng mặt theo yếu tố công việc:
  - Ban lãnh đạo có thể thực hiện các chính sách hỗ trợ các nhân viên có chi phí đi lại quá cao, như hỗ trợ về phí, tăng lương hoặc bố trí các phương tiện di chuyển.
  - Các nhân viên ở gần vắng mặt nhiều, đồng nghĩa rằng đây có thể là tâm lý chủ quan của những nhân viên nhà gần, hoặc tuyến đường họ lựa chọn để di chuyển chưa hợp lý. Ban lãnh đạo nên thực hiện khảo sát và phỏng vấn để tìm hiểu sâu hơn về vấn đề này.
  - Các nhân viên có khối lượng công việc hằng ngày ít hơn nên được trao đổi kỹ hơn về công việc hiện tại của họ. Có thể công việc không quá đòi hỏi về mặt kỹ năng đã khiến những nhân viên này sỉnh ra tâm lý chán nản đối với vị trí hiện tại. Việc thay đổi vị trí và khối lượng công việc là cần thiết để thực hiện những cải thiện về thời gian vắng. Các nhân viên có khối lượng công việc lớn cũng có thể được giảm tải để tránh bị căng thẳng dẫn tới việc vắng mặt.
 
## Bài phân tích trên PowerBI đã được thực hiện ra sao?

Trong PowerBI, quá trình chủ yếu diễn ra là giúp dữ liệu trở nên sạch hơn, rõ ràng hơn và phân tích mô tả, vẽ biểu đồ. Các bước thực hiện có thể được tóm tắt lại như sau:

### Làm sạch và tổ chức dữ liệu

1. Thêm các cột điều kiện để chứa tên dữ liệu (ví dụ các dữ liệu ở dạng "value" được đổi sang "name"), đổi tên cột để dữ liệu trở nên dễ hiểu hơn.
2. Đổi kiểu dữ liệu, thay đổi thứ tự lọc để cột hiển thị theo đúng giá trị và quy luật kỳ vọng.
3. Tạo các bảng dimensions và loại bỏ các summarizations để PowerBI hoạt động không xảy ra lỗi.

Các bước đã thực hiện chi tiết đối với từng bảng dữ liệu có thể được xem dưới đây:

<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/3db5fb43-6dd3-4af9-9aed-75739419fbb5">
    <p align="center">
    <i>Bảng fact_abst_dt</i>
    </p>
</p>

<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/49516caa-13de-4308-b24e-219d5067e9c0">
    <p align="center">
    <i>Bảng dim_month</i>
    </p>
</p>
<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/43497105-2212-4e5f-91cb-5ae75441eec9">
    <p align="center">
    <i>Bảng dim_diw</i>  
    </p>
</p>
<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/f0df2d30-a188-434b-8209-4ba88115568b">
    <p align="center">
    <i>Bảng dim_edu</i>
    </p>
</p>
<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/1bdbfe45-9bd5-496f-92e2-8eebe68f2632">
    <p align="center">
    <i>Bảng dim_reason</i>
    </p>
</p>
<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/9d269d84-2d0a-44dc-bcdf-c6bed784ad39">
    <p align="center">
    <i>Bảng dim_season</i>
    </p>
</p>
<p align="center" width="100%">
    <img width="33%" src="https://github.com/user-attachments/assets/7e9987bf-34a6-4516-9aa8-f126f1ba26df">
    <p align="center">
    <i>Bảng dim_atih_prediction</i>
    </p>
</p>

Các bảng dimension, fact có thể được xem tại [đây](https://github.com/hinmfm/absenteeism-prediction/tree/main/analysis/dimensions-facts).

### Trực quan hóa dữ liệu

Bước này chỉ đơn thuần thực hiện các biểu đồ trực quan dựa trên tư duy kinh doanh và phân loại biểu đồ phù hợp.
