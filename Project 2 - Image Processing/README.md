# Project 02 - Image Processing
## Mục lục
* [Đồ án 2: Image Processing](#c2)
    * [Nội dung đồ án](#c21)
    * [Quy định nộp bài](#c22)
    * [Quy định chấm bài](#c23)
## Đồ án 2: Image Processing <a class="anchor" id="c2"></a>
### Nội dung đồ án <a class="anchor" id="c21"></a>
<ins>Nhắc lại</ins>: Trong đồ án 1, sinh viên đã được giới thiệu về khái niệm lưu trữ ảnh dưới dạng ma trận các điểm ảnh. Mỗi điểm ảnh có thể được biểu diễn bằng một giá trị nguyên (ảnh xám) hoặc một vector (ảnh màu).

Trong đồ án này, sinh viên được yêu cầu thực hiện các chức năng xử lý ảnh cơ bản sau:
    
1. Thay đổi độ sáng cho ảnh (1 điểm)

![img](https://imgur.com/oJ8bTv7.jpg)

2. Thay đổi độ tương phản (1 điểm)

![img](https://imgur.com/wl8MSu3.jpg)

3. Lật ảnh (ngang - dọc) (1 điểm)

![img](https://imgur.com/MOOvIhN.jpg)

4. Chuyển đổi ảnh RGB thành ảnh xám/sepia (2 điểm)

- Ảnh xám

![img](https://imgur.com/XEfRXWE.jpg)

- Ảnh sepia

![img](https://imgur.com/YXUPjHY.jpg)

Keywords: convert RGB to grayscale/sepia

5. Làm mờ/sắc nét ảnh (2 điểm)

- Làm mờ

![img](https://imgur.com/wZT4vUa.jpg)

- Làm sắc nét

![img](https://imgur.com/H2Fq4Ne.jpg)

Tham khảo tại [đây](https://en.wikipedia.org/wiki/Kernel_(image_processing))

6. Cắt ảnh theo kích thước (cắt ở trung tâm) (1 điểm)

![img](https://imgur.com/fXebjfO.jpg)

7. Cắt ảnh theo khung (1 điểm)

- Khung tròn

![img](https://imgur.com/DEpimhC.jpg)

- Khung là 2 hình elip chéo nhau

![img](https://i.imgur.com/fPlYioC.png)

8. Viết hàm main xử lý (1 điểm) với các yêu cầu sau:

- Cho phép người dùng nhập vào tên tập tin ảnh mỗi khi hàm main được thực thi.
- Cho phép người dùng lựa chọn chức năng xử lý ảnh (từ 1 đến 7, đối với chức năng 4 cho phép lựa chọn giữa lật ngang hoặc lật dọc). Lựa chọn 0 cho phép thực hiện tất cả chức năng với tên file đầu ra tương ứng với từng chức năng. Ví dụ:
    - Đầu vào: `cat.png`
    - Chức năng: Làm mờ
    - Đầu ra: `cat_blur.png`
Trong đồ án này, sinh viên <font style='color:red'>**CHỈ ĐƯỢC PHÉP**</font> sử dụng các thư viện sau: `PIL`, `numpy`, `matplotlib`.

Cụ thể, nếu đề yêu cầu sinh viên cài đặt chức năng nào đó, thì sinh viên phải **thực sự cài đặt chức năng** đó mà không phải gọi hàm có sẵn.

- Đối với thư viện PIL và Matplotlib, sinh viên chỉ được sử dụng các hàm sau:
    - `PIL` (`open(), save()` từ `Image`) để đọc và ghi
    - `Matplotlib` (`imshow()` từ `pyplot`) để hiển thị ảnh
    - <ins>Lưu ý:</ins> <font style='color:red'>sử dụng các hàm khác (ngoài các hàm liệt kê trên)</font> $\to$ <font style='color:red'> NHẬN ĐIỂM 0 CHO TOÀN BỘ ĐỒ ÁN</font>

- Được phép sử dụng thư viện `NumPy` tùy ý

<ins>Lưu ý:</ins> Để được **điểm tối đa** cho từng chức năng, thời gian thực thi của mỗi chức năng phải nằm trong khoảng thời gian chấp nhận được. Ví dụ với chức năng làm mờ (phức tạp nhất) có thời gian thực thi trên ảnh với kích thước $512 \times 512$ là dưới 15 giây.

#### Nâng cao - Không bắt buộc (Cộng 0.5 điểm vào điểm đồ án 2)

Sinh viên tìm hiểu và cài đặt chức năng thu nhỏ, phóng to ảnh (zoom out/zoom in)

![img](https://i.imgur.com/DEzRSfe.png)
### Quy định bài nộp <a class="anchor" id="c22"></a>
* Thực hiện toàn bộ bài làm trên 1 tập tin Jupyter Notebook có mẫu theo đúng tập tin `MSSV.ipynb` đính kèm. Mỗi hàm cần có docstrings tương tự như đồ án 1.


* Nộp tập tin `MSSV.zip` được nén từ thư mục MSSV chứa các tập tin sau:
    1. Báo cáo toàn bộ bài làm: `MSSV.pdf`
    2. Mã nguồn: `MSSV.ipynb`


* Trong đó, nội dung tập tin báo cáo gồm có:
    - Thông tin cá nhân: Họ và tên, MSSV
    - Ý tưởng thực hiện, mô tả các hàm chức năng
    - Bảng đánh giá mức độ hoàn thành và hình ảnh kết quả cho từng chức năng (cho một ảnh đầu vào nhất định)

        | **STT** |    **Chức năng/Hàm**    | **Mức độ hoàn thành** | **Ảnh kết quả** |
        |:-------:|:-----------------------:|:---------------------:|:---------------:|
        |    1    | Thay đổi độ sáng        |       [0, 100]%       |                 |
        |    2    | Thay đổi độ tương phản  |       [0, 100]%       |                 |
        |   3.1   | Lật ảnh ngang           |       [0, 100]%       |                 |
        |   3.2   | Lật ảnh dọc             |       [0, 100]%       |                 |
        |   4.1   | RGB thành ảnh xám       |       [0, 100]%       |                 |
        |   4.2   | RGB thành ảnh sepia     |       [0, 100]%       |                 |
        |   5.1   | Làm mờ ảnh              |       [0, 100]%       |                 |
        |   5.2   | Làm sắc nét ảnh         |       [0, 100]%       |                 |
        |    6    | Cắt ảnh theo kích thước |       [0, 100]%       |                 |
        |   7.1   | Cắt ảnh theo khung tròn |       [0, 100]%       |                 |
        |   7.2   | Cắt ảnh theo khung elip |       [0, 100]%       |                 |
        |    8    | Hàm main                |       [0, 100]%       |                 |
        |    9    | Phóng to/Thu nhỏ 2x     |       [0, 100]%       |                 |

    - Báo cáo cần phải căn lề, có số trang, và tài liệu tham khảo
    
    <ins>Lưu ý:</ins> Viết báo cáo sơ sài/thiếu các yêu cầu trên sẽ nhận điểm trừ tương ứng.

* Ví dụ minh họa cây thư mục bài nộp sau khi giải nén tập tin `MSSV.zip` như sau:
    ```
    MSSV
    ├── MSSV.pdf
    └── MSSV.ipynb
    ```
### Quy định chấm bài <a class="anchor" id="c23"></a>
Đây là đồ án chiếm 10%.

Những trường hợp sau đây sẽ bị 0 điểm toàn bộ đồ án:

- Sử dụng các thư viện và các hàm xử lý ảnh có sẵn mà không được cho phép
- Nộp sai quy định
- Không có báo cáo
- Thực thi mã nguồn báo lỗi

<font style="color:red">**LƯU Ý: SAO CHÉP BÀI LÀM CỦA NHAU SẼ BỊ 0 ĐIỂM TOÀN BỘ PHẦN THỰC HÀNH**</font>
