# CONCEPTUAL

## I. Tổng quát

### 1. Định nghĩa

Thiết kế cơ sở dữ liệu ở mức conceptual là quá trình tạo ra một mô hình trừu tượng của cơ sở dữ liệu (ER hoặc EER), bao gồm các **thực thể** (entities), các **mối quan hệ** (relationships) giữa chúng và các **thuộc tính** (attributes) của chúng. Mức thiết kế này tập trung vào việc mô tả các đối tượng trong thế giới thực và cách chúng **tương tác** với nhau. Thiết kế cơ sở dữ liệu ở mức conceptual không liên quan đến cụ thể hóa cơ sở dữ liệu trên một hệ quản trị cơ sở dữ liệu nào.

![Quy trình thiết kế cơ sỡ dữ liệu](/image/conceptual1.png)

### 2. Bộ ký hiệu (Notation)

Ở mình giới thiệu cho các bạn 2 bộ ký hiệu thông dụng là **Chen Notation** và **Crow's foot Notation**.

#### 2.1 Chen Notation

các bạn xem ở đây nhen. vì mình hong dùng bộ ký hiệu này ví dụ ở đây nên các bạn xem thêm cho biết :))) [Chen Notation](https://www.vertabelo.com/blog/chen-erd-notation/)

#### 2.2 Crow's foot Notation (ký hiệu chân chim)

bộ ký hiệu này thì khá là giống với table trong cơ sở dữ liệu. 



<h2>Entity (gồm tên entity và các thuộc tính)</h2>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-attributes.png" alt="Mô tả ảnh" width="50%" height="50%">

<h2>Các loại thuộc tính</h2>


<h2>Các loại mối kết hợp</h2>
<h3>Zero to Many</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-zero-or-many.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>One to Many</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one-or-many.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>One and only One</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one.png" alt="Mô tả ảnh" width="50%" height="50%">

<h3>Zero to One</h3>
<img src="https://www.vertabelo.com/blog/crow-s-foot-notation/crows-foot-notation-one-or-zero.png" alt="Mô tả ảnh" width="50%" height="50%">

