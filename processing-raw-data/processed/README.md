# Giải thích file

## [absenteeism-data-processing.ipynb](https://github.com/hinmfm/absenteeism-prediction/blob/main/processing-raw-data/processed/absenteeism-data-processing.ipynb)
- File chứa quy trình xử lý dữ liệu từ đầu tới hoàn thiện trong Python. Quy trình này bao gồm: Nhập dữ liệu, làm sạch dữ liệu, xử lý dữ liệu, làm giàu dữ liệu và xuất dữ liệu.
- Tất cả các bước thực hiện đã được mô tả trong file.

## [clean-absenteeism-data.csv](https://github.com/hinmfm/absenteeism-prediction/blob/main/processing-raw-data/processed/cleaned-absenteeism-data.csv)
- Chứa bảng dữ liệu mới đã được làm sạch và xuất ra dưới dạng file .csv.<b> Data Dictionary </b> của dữ liệu như sau:

| Tên cột      	| Ý nghĩa|
|--------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Các cột Reason_A, Reason_B, Reason_C, Reason_D        	| Chứa giá trị 0 hoặc 1, tương ứng với Sai/Đúng. Nếu là 0, nhân viên không nghỉ vì lý do này; nếu là 1, nhân viên nghỉ vì lý do này. |
| Month Value      	| Giá trị danh nghĩa đại diện cho các tháng tương ứng từ 1 tới 12|
| Day In Week Value   	| Giá trị danh nghĩa đại diện cho ngày trong tuần lần lượt từ 0 tới 6, với 0 tương ứng thứ Hai, 6 là Chủ Nhật      |
| Transportation Expense         	| Các chi phí liên quan tới đi lại bao gồm nhiên liệu, tiền gửi xe và đồ ăn |
| Distance to Work       	| Khoảng cách (Đơn vị: km)|
| Age     	| Độ tuổi|
| Daily Work Load Average  	| Khối lượng công việc trung bình hằng ngày (Đơn vị: phút)	|
| Body Mass Index       	| [Chỉ số BMI](https://www.vinmec.com/vie/bai-viet/chi-so-bmi-bao-nhieu-la-binh-thuong-vi#:~:text=Ch%E1%BB%89%20s%E1%BB%91%20BMI%20Body%20Mass,nam%20v%C3%A0%20n%E1%BB%AF%20tr%C6%B0%E1%BB%9Fng%20th%C3%A0nh) |
| Education         	| Giá trị danh nghĩa đại diện cho các trình độ học vấn |
| Childern    	| Số con cái	|
| Pets       	| Số thú cưng 	|
| Absenteeism Time in Hours         	| Thời gian nhân viên vắng mặt ở nơi làm
