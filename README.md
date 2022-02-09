# Windows Server Practical Exam
![download](https://user-images.githubusercontent.com/95524638/153192740-9a214352-5a55-44f4-a0d7-64f17914d7ec.png)


### 1. Nâng cấp Domain controller cho server
* Thực hiện theo trình tự
  + Vào sever manager để tiến hành add thêm các tính năng.
  
  * Làm theo các bước trên con trỏ chuột

![Screenshot (3)](https://user-images.githubusercontent.com/95524638/153203036-0e2f79b3-584d-448d-abaf-ab1050dde43c.png)

![Screenshot (4)](https://user-images.githubusercontent.com/95524638/153203047-dbd671de-f0dc-442b-804c-1ed6a761c299.png)

![Screenshot (5)](https://user-images.githubusercontent.com/95524638/153203057-c672d7b3-efb5-4887-9761-36fa4a1323c7.png)

![Screenshot (6)](https://user-images.githubusercontent.com/95524638/153203142-d5454b17-9f17-4bb8-a2d6-35e386ca1f06.png)

![Screenshot (8)](https://user-images.githubusercontent.com/95524638/153204039-a8a27cc7-fd29-44ec-8355-f2a2d759f2a9.png)


![Screenshot (6)](https://user-images.githubusercontent.com/95524638/153203198-a2921064-4742-473e-bb47-3eea229d4cb0.png)![Screenshot (15)](https://user-images.githubusercontent.com/95524638/153205963-1573723e-0c47-4241-b2c9-98f9e96f1150.png)

![Screenshot (13)](https://user-images.githubusercontent.com/95524638/153204243-f4841753-3ef4-4ba0-8584-ff1d3a2f5225.png)


![Screenshot (10)](https://user-images.githubusercontent.com/95524638/153204053-7b783320-0ffa-4b4b-b773-0f7465427379.png)
* Quá Trinh CÀi đặt hoàn tất


* Chờ đợi máy tính khởi động lại
![Screenshot (14)](https://user-images.githubusercontent.com/95524638/153204279-f1524690-2e40-4ec6-93c5-37ae13d8d19e.png)

* Sau khi máy tính đã join domain




![Screenshot (15)](https://user-images.githubusercontent.com/95524638/153206293-6c7d8f21-d044-4a38-971f-e3d6170ae1a3.png)
![Screenshot (16)](https://user-images.githubusercontent.com/95524638/153206321-181fcaa9-1ff8-4120-a073-314262614421.png)

*  Cài đặt iSCSI Target Server:
*  Để triển khai dịch vụ, chúng ta tiến hành cài đặt Server roles iSCSI Target Server. Tại Server Roles mở rộng File and Storage Services -> File and iSCSI  Services và chọn iSCSI Target Server.


![Screenshot (17)](https://user-images.githubusercontent.com/95524638/153207191-4e4ac353-3872-42f0-959b-5f2d0d94f1bc.png)


![Screenshot (18)](https://user-images.githubusercontent.com/95524638/153207210-9cc8231a-df4c-4f70-87c0-2a141a3b55ad.png)
Bước 2: Lấy thông tin IQN (iSCSI Qualified Name) từ iSCSI Initiator (Client):
Truy cập iSCSI Initiator trên Windows 10  và Windows Server từ menu Windows:

* Mặc định dịch vụ iSCSI Initiator chưa được bật, sau khi chọn mở dịch vụ lần đầu trên hợp thoại Micrsoft iSCSI chọn Yes để start dịch vụ.
* 
![Screenshot (20)](https://user-images.githubusercontent.com/95524638/153207657-8faa28da-941d-4381-a173-7e4ddd4e60ff.png)
* Trong iSCSI Initiator Properties chọn tab Configurations, copy Initiator name và lưu lại để sử dụng khi tạo iSCSI Virtual Disk.

![Screenshot (21)](https://user-images.githubusercontent.com/95524638/153208003-b2329b5f-79ff-4bac-abbd-dddcbc900e7b.png)
* Bước 3: Tạo New iSCSI Virtual Disk…
 * Trong Server Manager, chọn lên File and Storage Services, chọn iSCSI. Trong iSCSI Virtual Disks, chọn Tasks -> New iSCSI Virtaul Disk…
 ![Screenshot (22)](https://user-images.githubusercontent.com/95524638/153208255-a4f840b7-0735-4a43-a7b0-748cf395d31b.png)
 *Tiếp theo, chọn nơi lưu trữ cho iSCSI Virtual Disk
 
![Screenshot (23)](https://user-images.githubusercontent.com/95524638/153208421-395da9b8-3d06-453f-aa5b-7235e93f7c78.png)

 * Đặt tên cho iSCSI Virtual Disk
  
![Screenshot (24)](https://user-images.githubusercontent.com/95524638/153208599-88774196-824c-4adc-bacb-821726da733e.png)

* Tiếp theo, chọn size cho iSCSI Virtual Disk. Ở đây, nếu chọn Dynamically expanding thì dung lượng của fiile ổ cứng iSCSI Virtual Disk sẽ tăng theo dung lượng mà chúng ta sử dụng và cao nhất là bằng với số dung lượng mà bạn đã chọn ở mục Size. Dynamically expanding cho phép tiết kiệm dung lượng của phân vùng chưa file iSCSI Virtual Disk khi file này chưa sử dụng đến dung lượng mà bạn khai báo ở Size.
![Screenshot (25)](https://user-images.githubusercontent.com/95524638/153208746-6282c105-86ad-4ced-bd0c-d8ac4173eb6a.png)
 * Tiếp theo, tạo New iSCSI target
 
![Screenshot (26)](https://user-images.githubusercontent.com/95524638/153208834-a8d60785-672c-4674-bb7f-049a4a522f20.png)
Đặt tên cho iSCSI target
![Screenshot (27)](https://user-images.githubusercontent.com/95524638/153208949-1689efdb-6147-4753-8da9-8e9c2f4611f7.png)
* Tiếp theo, mục Access Server chúng ta sẽ tiến hành khai báo iSCSI initiator, chọn Add.
 + Tiếp theo, bạn điền IQN của iSCSI Initiator đã lấy ở Bước 2 từ phía client.

![Screenshot (29)](https://user-images.githubusercontent.com/95524638/153209553-91fe7075-f3cb-4957-b75c-b2eaae258b9c.png)
Màn hình Confirmation, cho phép bạn có cái nhìn tổng thể về những cấu hình mà bạn đã chọn. Bạn click Create để tiến hành tạo iSCSI Virtual Disk.
![Screenshot (29)](https://user-images.githubusercontent.com/95524638/153209689-8e8d6774-5c99-4bfc-972a-cbd9d546abd1.png)![Screenshot (30)](https://user-images.githubusercontent.com/95524638/153209812-eb7c2576-7fab-491d-b500-436333fdaf18.png)

Sau khi tạo xong, bạn chọn Cloes để đóng của sổ New iSCSI Virtual Disk Wizard.
![Screenshot (31)](https://user-images.githubusercontent.com/95524638/153209791-1764a2ea-4360-4dfe-aac1-dc536f3c11ed.png)

* Sau khi tạo xong iSCSI Virtual Disk, bạn sẽ thấy  ổ đỉa ảo này trong thư iSCSI của Server Manager.
*

 + ![Screenshot (32)](https://user-images.githubusercontent.com/95524638/153209942-6a76e72b-bcc6-4ed9-971b-39d2cead8a38.png)
 Bạn có thể thấy file ổ cứng ảo iSCSI Virtual Disk được lưu trữ trong iSCSIVirtualDisks. File này chỉ có dung lượng khoản 4MB thay vì 10 GB do phía trên, khi khởi tạo, bạn đã chọn Dynamically expanding
 ![Screenshot (33)](https://user-images.githubusercontent.com/95524638/153210520-5f41d363-9cf8-4f42-a6ee-02441eb99f77.png)
Bước 4: Kết nối iSCSI Virtual Disk cho iSCSI Initiator phía client:
Truy cập vào iSCSI Initiator như đã nói ở Bước 2. Trong cửa sổ iSCSI Initiator Properties chọn tab Discovery, chọn Discover Portal…, điền vào thông tin IP hoặc DNS name của máy đang chạy iSCSI target server.
![Screenshot (34)](https://user-images.githubusercontent.com/95524638/153211267-e2bc4be6-f218-4d23-a9c5-c520e86deb67.png)
![Screenshot (35)](https://user-images.githubusercontent.com/95524638/153211282-58aefa01-df72-4515-9c5e-22439146d972.png)
Sau khi chỉ dịnh xong iSCSI target server, tiếp tục chuyển qua tab Targets của iSCSI Initiator Properties
![Screenshot (35)](https://user-images.githubusercontent.com/95524638/153214232-4084f57c-ae25-42fb-bd3d-0165c6b26261.png)


![Screenshot (36)](https://user-images.githubusercontent.com/95524638/153214189-2ff392fd-fe41-4dcb-bbfc-90464ced504f.png)
Ở tab Target, bạn chọn lên Target name muốn kết nối đến, chọn Conect.

![Screenshot (36)](https://user-images.githubusercontent.com/95524638/153214336-d607bda2-ca45-46fc-926b-9b564f1a434c.png)
Sau khi kết nối thành công đến target, bạn truy cập vào Disk Management của Windows sẽ thấy ổ đĩa iSCSI Virtual Disk. Bạn tiến hành khởi tạo đỉa mới và tạo phân vùng là có thể sử dụng.

![Screenshot (37)](https://user-images.githubusercontent.com/95524638/153214460-50a9d606-7b07-4bc5-9170-5759db2a069d.png)

