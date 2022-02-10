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

 + Câu 1.2
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


# 2.1
# Triển khai Additional Domain Controller trên Windows Server
trên ADC, bạn cài đặt Server Roles Active Directory Domain Service.

![Screenshot (39)](https://user-images.githubusercontent.com/95524638/153218321-3b4bf8ff-6c74-41b4-a279-d1d20e88f4e0.png)
Sau khi cài đặt xong, bạn tiến hành nâng cấp lên domain cho ADC.
![Screenshot (40)](https://user-images.githubusercontent.com/95524638/153218801-53a4a764-6041-4cc3-83b0-52b617d73610.png)
Trong mục Domain Controller Option, bạn giữ như mặc định
![Screenshot (41)](https://user-images.githubusercontent.com/95524638/153218913-1f6cef2b-1664-4adb-b51e-b6e169fb6a66.png)
Sau khi hoàn tất việc nâng cấp domain cho ADC, bạn có thể trỏ địa chỉ IP DNS server của ADC về chính nó.

# Câu 2.2 : Triển Khai Dịch Vụ DHCP server
 + cài đặt DHCP Role trong Windows Server
 Bước 1 - Chuyển đến Server Manager → Manage → Add Roles and Features.
  + Từ Roles lists, hãy chọn DHCP Server role → nhấp vào Add Features trên cửa sổ hiện ra như được hiển thị trong các ảnh chụp màn hình sau đây.
  
![Screenshot (42)](https://user-images.githubusercontent.com/95524638/153224647-802beee5-b7f6-47f5-b0a3-462fcf9b2318.png)
![Screenshot (43)](https://user-images.githubusercontent.com/95524638/153224682-16fa16d3-2c1d-47da-9ea7-40cf51ea70ce.png)


Cấu hình sau triển khai
Trong phần này, chúng ta sẽ xem cách thực hiện cấu hình sau triển khai của DHCP. Vui lòng làm theo các bước dưới đây.

Bước 1 - Nhấp vào biểu tượng cảnh báo và sau đó nhấp vào "Complete DHCP Configuration".
![Screenshot (44)](https://user-images.githubusercontent.com/95524638/153225205-13e9386c-9941-44b7-accf-46fb8e604772.png)
Chọn một tài khoản domain user có quyền tạo đối tượng trong vùng chứa Net Services trong thư mục hoạt động hoặc tài khoản quản trị domain → bấm Next.

triển khai DHCP
 + Tìm màn hình Server Manager screen → Tools → DHCP.
 + ![Screenshot (45)](https://user-images.githubusercontent.com/95524638/153226408-a06d502e-9fba-4310-a5d9-4ba57d1336e3.png)

Nhấp chuột phải vào DHCP Server → sau đó nhấp vào “Add/Remove Bindings…”


![Screenshot (46)](https://user-images.githubusercontent.com/95524638/153226600-59fa0e6b-e6e7-43e6-9958-e1fc21fde507.png)
Đảm bảo địa chỉ IP tĩnh của máy chủ sẽ xuất hiện như được hiển thị trong ảnh chụp màn hình sau.

![Screenshot (47)](https://user-images.githubusercontent.com/95524638/153226704-661bad17-ffd4-4e70-895a-63504454899b.png)

Nhấp chuột phải vào IPv4 → Chọn “New Scope”
Nhập địa chỉ IP Start và End, Subnet mask, để Length mặc định “24” cho mạng con lớp C → bấm Next.
![Screenshot (48)](https://user-images.githubusercontent.com/95524638/153227392-bcae8ac9-9b7f-4a7e-8dce-2361040148c9.png)
Chọn tùy chọn “Yes, I want to activate this scope now" để kích hoạt phạm vi ngay lập tức → chọn Next.
![Screenshot (50)](https://user-images.githubusercontent.com/95524638/153227570-82fe9723-9747-40c4-b4df-8a3e17bb4245.png)

# 3 Join domain vào máy clien
 + ![Screenshot (52)](https://user-images.githubusercontent.com/95524638/153227930-695ecff8-ced9-4461-b3b1-a503259d1523.png)
# 3.1test clien device
![Screenshot (53)](https://user-images.githubusercontent.com/95524638/153228207-1fea2a2e-6239-4abd-8c78-ceac27c0109c.png)


# Câu 4.1

![Screenshot (68)](https://user-images.githubusercontent.com/95524638/153429192-b83a2fe9-c753-43f5-988c-fa75d1af2840.png)


# Câu 4.2
 + Cài đặt Hyper-V
  + Chạy Server Manager và nhấp vào Add roles and features.



![Screenshot (61)](https://user-images.githubusercontent.com/95524638/153417950-8d3cc65c-75a3-4821-9239-f98cf1f88a1f.png)


![Screenshot (62)](https://user-images.githubusercontent.com/95524638/153417975-43450d29-1a0f-4c5b-8680-7ef183add1e7.png)

+ Sau khi cài đặt xong feature Failover Clustering, chúng ta sẽ cấu hình như sau:

 
![Screenshot (63)](https://user-images.githubusercontent.com/95524638/153418709-9e34c27b-ec19-4f79-a1d0-16fb2a052a56.png)
+ Để tiến hành quản lý, và cấu hình bạn sẽ cần truy cập vào Failover Cluster Manager:
+ 

  
![Screenshot (54)](https://user-images.githubusercontent.com/95524638/153410612-fd249434-254b-4cfa-b7f9-ee215aa04767.png)


Tiếp theo, trong giao diện Failover Cluster Manager, bạn tiến hành Validate Configuration… cho các node sẽ được add vào cluster.

![Screenshot (65)](https://user-images.githubusercontent.com/95524638/153420629-0e90493c-8e29-49c8-8a2f-f04a2ba288a4.png)
Ờ mạn hình giới thiệu của Validate Configuration wizard, bạn chọn Next:
![image](https://user-images.githubusercontent.com/95524638/153420749-9bf76691-a883-4d07-9982-2a386d5b6039.png)
Tiếp theo, bạn chọn các node đã được cài feature Failover Clustering





 + Tạo máy ảo
  + Chạy Server Manager và mở Tools > Hyper-V Manager.
  ![Screenshot (55)](https://user-images.githubusercontent.com/95524638/153412668-66497ab7-b673-4546-a3df-b8937dff0f17.png)
  Chọn Hostname ở bên trái và nhấp chuột phải vào nó để mở menu, sau đó chọn New > Virtual Machine.
  
![Screenshot (56)](https://user-images.githubusercontent.com/95524638/153412794-4eb0cd66-8515-4447-87fd-ccecd54b2d9e.png)
+ Chọn file iso để tiến hành khởi động
![Screenshot (58)](https://user-images.githubusercontent.com/95524638/153413312-2315bf55-65ee-471a-8e7f-7377391c7b56.png)


![Screenshot (59)](https://user-images.githubusercontent.com/95524638/153413430-3b649e98-1fd1-4560-b76a-3e85c4270e1d.png)



![Screenshot (60)](https://user-images.githubusercontent.com/95524638/153415695-e91b6c88-c7ea-4986-98b3-bcec4dab7139.png)



![Screenshot (67)](https://user-images.githubusercontent.com/95524638/153421918-a8258eea-f4fb-4791-a180-c5f59e7abdef.png)

4.3



