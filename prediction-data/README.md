# Giải thích file

## [absenteeism-predictive-analysis.ipynb](https://github.com/hinmfm/absenteeism-prediction/blob/main/prediction-data/absenteeism-predictive-analysis.ipynb)
- File chứa quy trình làm giàu dữ liệu cho dự đoán, chọn mô hình dự đoán, thực hiện các điều chỉnh tham số và đưa ra dự đoán về số giờ vắng mặt dựa trên từng thuộc tính xuất hiện trong bảng dữ liệu.
- Tất cả các bước thực hiện đã được mô tả trong file.

## [absenteeism-prediction.csv](https://github.com/hinmfm/absenteeism-prediction/blob/main/prediction-data/absenteeism-prediction.csv)
- Chứa bảng dữ liệu mới đã được làm giàu, thiết kế chỉ dành cho mục đích dự đoán, đã được dự đoán và xuất ra dưới dạng file .csv.
- <b> Data Dictionary </b> của dữ liệu như sau:

| Tên cột      	| Ý nghĩa|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Các cột Reason_A, Reason_B, Reason_C, Reason_D        	| Chứa giá trị 0 hoặc 1, tương ứng với Sai/Đúng. Nếu là 0, nhân viên không nghỉ vì lý do này; nếu là 1, nhân viên nghỉ vì lý do này |
| Season Value      	| Giá trị danh nghĩa đại diện cho các mùa tương ứng từ 0 tới 3, với 0 là mùa Xuân, 3 là mùa Đông|
| Day In Week Value   	| Giá trị danh nghĩa đại diện cho ngày trong tuần lần lượt từ 0 tới 6, với 0 tương ứng thứ Hai, 6 là Chủ Nhật      |
| Transportation Expense         	| Các chi phí liên quan tới đi lại bao gồm nhiên liệu, tiền gửi xe và đồ ăn |
| Distance to Work       	| Khoảng cách (Đơn vị: km)|
| Age     	| Độ tuổi|
| Daily Work Load Average  	| Khối lượng công việc trung bình hằng ngày (Đơn vị: phút)	|
| Body Mass Index       	| [Chỉ số BMI](https://www.vinmec.com/vie/bai-viet/chi-so-bmi-bao-nhieu-la-binh-thuong-vi#:~:text=Ch%E1%BB%89%20s%E1%BB%91%20BMI%20Body%20Mass,nam%20v%C3%A0%20n%E1%BB%AF%20tr%C6%B0%E1%BB%9Fng%20th%C3%A0nh) |
| Education         	| Giá trị danh nghĩa đại diện cho các trình độ học vấn |
| Childern    	| Số con cái	|
| Pets       	| Số thú cưng 	|
| Absenteeism Time in Hours         	| Thời gian nhân viên vắng mặt ở nơi làm	|
| AITH_prediction       	| Thời gian vắng mặt dự đoán 	
