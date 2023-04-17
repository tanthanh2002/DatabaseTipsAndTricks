# CONCEPTUAL

## I. Tổng quát

### 1. Định nghĩa

Thiết kế cơ sở dữ liệu ở mức conceptual là quá trình tạo ra một mô hình trừu tượng của cơ sở dữ liệu (ER hoặc EER), bao gồm các **thực thể** (entities), các **mối quan hệ** (relationships) giữa chúng và các **thuộc tính** (attributes) của chúng. Mức thiết kế này tập trung vào việc mô tả các đối tượng trong thế giới thực và cách chúng **tương tác** với nhau. Thiết kế cơ sở dữ liệu ở mức conceptual không liên quan đến cụ thể hóa cơ sở dữ liệu trên một hệ quản trị cơ sở dữ liệu nào.

![Quy trình thiết kế cơ sỡ dữ liệu](/image/conceptual1.png)

### 2. Bộ ký hiệu (Notation)

Ở mình giới thiệu cho các bạn 2 bộ ký hiệu thông dụng là **Chen Notation** và **Crow's foot Notation**.

#### 2.1. Chen Notation

các bạn xem ở đây nhen. vì mình hong dùng bộ ký hiệu này ví dụ ở đây nên các bạn xem thêm cho biết :))) [Chen Notation](https://www.vertabelo.com/blog/chen-erd-notation/)

#### 2.2. Crow's foot Notation (ký hiệu chân chim)

bộ ký hiệu này thì khá là giống với table trong cơ sở dữ liệu. 



<h2>Entity (gồm tên entity và các thuộc tính)</h2>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-attributes.png" alt="Mô tả ảnh" width="50%" height="50%">

<h2>Các loại thuộc tính</h2>


* <u>identifier</u>: định danh hay còn gọi là khoá. Có thể là định danh đơn giản (1 thuộc tính hoặc định danh kết hợp nhiều thuộc tính). 
* patial key(gạch chân nét đứt): khoá riêng phần. Tức là nó không thể nào đủ để tự định danh của nó mà phải dựa thêm vào khoá của một thực thể khác để định danh.
> ví dụ: có thực thể hoá đơn(mahoadon,....), hoá đơn chi tiết(masanpham,soluong,...). ở hoá đơn chi tiết thì nếu chỉ dùng mã sản phẩm thì chưa thể định danh được hoá đơn chi tiết mà phải cần thêm mã hoá đơn để biết được chi tiết hoá đơn này thuộc hoá đơn nào 

* composite attribute(value1,value2,...): thuộc tính kết hợp
> ví dụ: địa chỉ(quận, huyện, thành phố)

* [Derived attribute]: thuộc tính suy diễn. 
> ví dụ: tổng tiền :được suy ra từ sum(số lượng * giá) của các sản phẩm trong đơn hàng
* {mutivalued attribute}: thuộc tính đa trị. Là có nhiều giá trị :)))
> ví dụ: một khách hàng có thể có nhiều số điện thoại thì số điện thoại là thuộc tính đa trị


<h2>Các loại mối kết hợp</h2>
<h3>Zero to Many</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-zero-or-many.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>One to Many</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one-or-many.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>One and only One</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>Zero to One</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one-or-zero.png" alt="Mô tả ảnh" width="50%" height="50%">


## II. Các bước thiết kế ở mức conceptual
### 1. Xác định thực thể
#### 1.1. xác định thực thể và ví dụ
Thực thể là một đối tượng, sự việc, hoặc khái niệm có thể được định danh và xử lý trong hệ thống thông tin. 
Ví dụ: Khách hàng, Sản phẩm, Đơn hàng, Nhân viên, Bài viết trên mạng xã hội, Thành phố, Quốc gia, ...

*Thực thể nên là:*
* một đối tượng có nhiều thể hiện trong cơ sở dữ liệu. Ví dụ: ta thiết kế cơ sỡ dữ liệu quản lý công ty cho một công ty thì không nên xem công ty là một thực thể vì nó chỉ có duy nhất 1 thể hiện.
* một đối tượng bao gồm nhiều thuộc tính. Nếu ít quá thì xem xét lại. Ví dụ: Role: ta có thể xem xét nếu 1 người có nhiều role thì có thể xem là một thực thể còn không thì xem là thuộc tính của thực thể người luôn.
* một đối tượng cần thiết để mô hình hoá. cái nào cần thì mới cho vào :))))))

*Thực thể không nên là:*
* một người dùng của hệ thống. Ví dụ: admin
* một output của hệ thống: báo cáo, báo biểu. Nhưng thứ này có thể tính toán cho ra được.
#### 1.2. Xác định thuộc tính

chú ý khi chọn thuộc tính định danh:
* tránh nhưng định danh có khả năng bị thay đổi theo thời gian như CMND -> CCCD đổi thể là có khả năng đi xa :))) 
* nên thay thế các định danh phức tạp bằng một loại đơn giản hơn (surrogate key hay alternative key).


khi chọn thuộc tính nên xem xét kĩ cái nào cần cái nào không nhé.
#### 1.3. Xác định ràng buộc
Xác định tất cả các ràng buộc của các thuộc tính: ràng buộc miền giá trị, ràng buộc liên thuộc tính(giữa nhiều thuộc tính với nhau. Ví dụ: trong thực thể môn học thì số tiết thực hành phải ít hơn số tiết lý thuyết),.... nói chung là xác định tất cả ràng buộc.

### 2. Xác định các mối quan hệ (relationships) giữa các thực thể
## 2.1. Các loại mối kết hợp
* Unary Relationship: mối kết hợp phản thân. Ví dụ: Một nhân viên được quản lý bởi 1 nhân viên.
* Binary Relationship: mối kết hợp nhị phân: Ví dụ: học sinh thuộc lớp
* Tenary Relationship: mối kêt hợp đa phân (từ 3 trở lên nhưng nên tránh :> ).
xác định bảng số của mối kết hợp dựa vào ràng buộc. Ví dụ một học sinh thuộc (1-n) lớp mỗi lớp có (1-n) học sinh. Thì mối kết hợp là n-n (dựa vào max của 2 bảng số). Mối học sinh học (1-1) ngành và mỗi ngành có (1-n) học sinh học thì mỗi kết hợp này là (1-n).

### 3. Thiết kế sơ đồ Entity-Relationship (ER diagram)

#### 3.1. Phân tích yêu cầu
Ở đây mình highlight màu vàng các danh từ có khả năng là thực thể và màu xanh cho các từ có thể là thuộc tính. màu đỏ cho những động từ có thể là mối kết hợp.
![phân tích](/image/eranalyst.png)


Mình vẽ erd dựa vào những gì đã highligh. Cứ vẽ đi đã rồi chỗ nào không ổn mình chỉnh sửa tiếp :>
![erd](/image/erd.png)

### 4. Kiểm tra và cải thiện thiết kế cơ sở dữ liệu ở mức conceptual
* Kiểm tra tính toàn vẹn của thiết kế
* Kiểm tra tính chính xác và phù hợp với nhu cầu của người dùng
* Cải thiện thiết kế nếu cần thiết