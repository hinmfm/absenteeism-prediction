# Giải thích

_File này chứa các file phân tích dưới hai định dạng: .pdf và .pbix. Trong đó, file .pbix được thiết kế để hiển thị báo cáo động, cho phép tùy chỉnh tiêu chí theo từng biểu đồ, trong khi file .pdf cung cấp báo cáo tĩnh, không hỗ trợ điều chỉnh tiêu chí._

Ta cùng bước vào phần phân tích. Các đầu mục trong phần phân tích bao gồm:

## Danh mục nội dung
- [Các từ viết tắt](#Các-từ-viết-tắt)
- [Bối cảnh](#Bối-cảnh)
- [Tổng quan](#Tổng-quan)
- [Các thông tin giá trị](#Các-thông-tin-giá-trị)
    - [Các xu hướng vắng mặt](#Các-xu-hướng-vắng-mặt)
    - 

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

## Tổng quan
Tổng số giờ vắng mặt của tất cả nhân viên trong khoảng thời gian nghiên cứu của bộ dữ liệu là 4733 giờ, với mỗi nhân viên vắng mặt sẽ vắng 6.76 tiếng trong một ca làm việc. Trong số các lý do vắng mặt, nhóm lý do gây vắng mặt nhiều nhất là lý do D với 418 lần các nhân viên vắng mặt vì lý do thuộc nhóm này. Nhóm lý do gây mất mát nhiều giờ làm việc nhất là lý do A, với tổng cộng 2269 giờ vắng mặt. 

Phần lớn các nhân viên vắng mặt rơi vào độ tuổi trung niên có một con và không có thú cưng, với độ tuổi trung bình của các nhân viên này là 36.42, số con cái trung bình là 1.02 và số thú cưng trung bình là 0.69. Ngoài ra, những người vắng mặt hầu hết đều bị thừa cân, với BMI trung bình của họ là 26.74. Để tham khảo thêm về chia khoảng BMI, có thể nhấp vào link [này](https://medlatec.vn/media/24658/file/Ch%e1%bb%89-s%e1%bb%91-BMI-4+(3).png).

Mỗi nhân viên vắng mặt có khối lượng công việc trung bình hằng ngày là 271.80 phút. Trung bình mỗi ngày các nhân viên này phải di chuyển gần 30km (29.89) để tới công ty, với chi phí đi lại trung bình là 222.35$.

## Các thông tin giá trị.
### Các xu hướng về thời gian.

- Trung bình mỗi tháng công ty <b>mất 394 giờ làm việc</b>, với các <b>tháng 3, 4, 7, 11, 12 là các tháng nhân viên vắng mặt lâu hơn trung bình</b>.
  - <b>Tháng 3</b> là tháng có <b>nhiều nhân viên vắng mặt nhất</b>, đồng thời <b>vắng lâu nhất</b> với <b>87 nhân viên báo cáo vắng và 765 giờ làm việc bị mất</b>.
  - <b>Tháng 2 và tháng 10</b> là hai tháng có <b>nhiều nhân viên báo vắng thứ hai và thứ ba</b>, với lần lượt <b>72 và 71 nhân viên báo vắng</b> trong các tháng này.

- <b>Số giờ vắng/ngày</b> của công ty là <b>676 giờ</b>, với các <b>thứ đầu tuần (thứ Hai, Ba, Tư)</b> và ngày làm việc (chính thức) cuối cùng trong tuần <b>(thứ Sáu)</b> có <b>tổng thời gian vắng mặt lâu hơn trung bình.</b>
  - <b>Thứ Hai, Ba, Tư đều có trên 1000 giờ vắng mặt</b>, <b>nhiều hơn so với các ngày còn lại</b> trong tuần.
  - Tuy có thể là ngày OT và tổng cộng chỉ có <b>4 người báo vắng</b> trong suốt khoảng thời gian của dữ liệu nhưng <b>thứ Bảy lại có số giờ vắng trung bình cao thứ hai (8.5 giờ)</b>, chỉ <b>kém gần 1 giờ</b> so với <b>thứ Hai (9.4 giờ).</b>

![image](https://github.com/user-attachments/assets/06215e0c-3ec7-42c8-b1e1-2f79b7b04df6)

### Sự ảnh hưởng của các yếu tố đời sống.
