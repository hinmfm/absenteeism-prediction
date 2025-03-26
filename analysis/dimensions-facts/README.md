# Giải thích file

## I. Về cấu trúc dữ liệu
Các DSD phía dưới được thiết kế riêng cho mục đích phân tích trong PBI, sao cho phần mềm PowerBI có thể hoạt động hiệu quả, tối ưu nhất. 

1. Sơ đồ DSD từ <b>PowerBI</b>:

![image](https://github.com/user-attachments/assets/985218fd-dd50-42f0-947f-cee1e02337d8)

2. Sơ đồ DSD chi tiết (giải thích tốt hơn, vẽ bởi tác giả):

![image](https://github.com/user-attachments/assets/ccef3157-c87a-4dc7-8e08-1a5556defe90)

## II. Data Dictionary
Phía dưới sẽ là Data Dictionary của từng bảng đã xuất hiện trong sơ đồ trên.

1. <b> Bảng fact_abst_dt (Bảng chính của dữ liệu, chứa thông tin giá trị của các thuộc tính)</b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| line_value        	| index  |
| age     	| Độ tuổi|
| atih         	| Thời gian nhân viên vắng mặt ở nơi làm  |
| bmi       	| [Chỉ số BMI](https://www.vinmec.com/vie/bai-viet/chi-so-bmi-bao-nhieu-la-binh-thuong-vi#:~:text=Ch%E1%BB%89%20s%E1%BB%91%20BMI%20Body%20Mass,nam%20v%C3%A0%20n%E1%BB%AF%20tr%C6%B0%E1%BB%9Fng%20th%C3%A0nh) |
| childern    	| Số con cái	|
| dailyWorkLoadAverage  	| Khối lượng công việc trung bình hằng ngày (Đơn vị: phút)	|
| dateInWeek_value   	| Giá trị danh nghĩa đại diện cho ngày trong tuần lần lượt từ 0 tới 6, với 0 tương ứng thứ Hai, 6 là Chủ Nhật      |
| distanceToWork       	| Khoảng cách (Đơn vị: km)|
| education_value         	| Giá trị danh nghĩa đại diện cho các trình độ học vấn |
| pets       	| Số thú cưng 	|
| month_value      	| Giá trị danh nghĩa đại diện cho các tháng tương ứng từ 1 tới 12|
| reason_category_value      	| Giá trị danh nghĩa đại diện cho các lý do tương ứng từ 0 tới 3, với 0 là lý do A, 3 là lý do D|
| transportationExpense         	| Các chi phí liên quan tới đi lại bao gồm nhiên liệu, tiền gửi xe và đồ ăn |

2. <b> Bảng dim_diw (Dimension - date in week: Bảng ngày trong tuần) </b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| dateInWeek_value   	| Giá trị danh nghĩa đại diện cho ngày trong tuần lần lượt từ 0 tới 6, với 0 tương ứng thứ Hai, 6 là Chủ Nhật      |
| dateInWeek_name   	| Ngày trong tuần      |

3. <b> Bảng dim_edu (Dimension - education: Bảng học vấn) </b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| education_value         	| Giá trị danh nghĩa đại diện cho các trình độ học vấn |
| education_name         	| Học vấn |

4. <b> Bảng dim_reason (Dimension - reason: Bảng lý do) </b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| reason_category_value      	| Giá trị danh nghĩa đại diện cho các lý do tương ứng từ 0 tới 3, với 0 là lý do A, 3 là lý do D|
| reason_category_name      	| Tên lý do|
| Các cột Reason_A, Reason_B, Reason_C, Reason_D        	| Chứa giá trị 0 hoặc 1, tương ứng với Sai/Đúng. Nếu là 0, nhân viên không nghỉ vì lý do này; nếu là 1, nhân viên nghỉ vì lý do này. |

5. <b> Bảng dim_atih_prediciton (Dimension - absenteeism time in hours prediction: Bảng chứa kết quả dự đoán thời gian vắng mặt của từng dòng dữ liệu) </b>

<i>Note: Bảng này được tạo ra do sự bất cẩn của tác giả khi nhập dữ liệu vào PowerBI. Cụ thể, tác giả nhập nhầm dữ liệu gốc (dữ liệu chưa có kết quả dự đoán) vào và làm hết các báo cáo trước khi nhận ra.</i>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| line_value        	| index  |
| atih_prediction       	| Thời gian vắng mặt dự đoán 	|

6. <b> Bảng dim_month (Dimension - month: Bảng tháng) </b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| month_value      	| Giá trị danh nghĩa đại diện cho các tháng tương ứng từ 1 tới 12|
| month_name      	| Tên tháng|
| season_value      	| Giá trị danh nghĩa đại diện cho các mùa tương ứng từ 0 tới 3, với 0 là mùa Xuân, 3 là mùa Đông|

7. <b> Bảng dim_month (Dimension - month: Bảng tháng) </b>

| Tên cột      	| Ý nghĩa      	|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| season_value      	| Giá trị danh nghĩa đại diện cho các mùa tương ứng từ 0 tới 3, với 0 là mùa Xuân, 3 là mùa Đông|
| season_name      	| Tên mùa|
