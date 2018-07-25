## Nội dung

Outline về khoá VDI của VMWare, bao gồm các nội dung như:
- Horizon
- App Volume
- Identity manager
- ThinApp
- vSAN

## Lý thuyết

Cần nắm được BYOD là gì? xu hướng áp dụng ở các doanh nghiệp

BYOD là cách sử dụng máy tính cá nhân để làm việc ở cty.

JMP - Just-in-Time-Management Platform: Tăng tốc độ trong quá trình tạo desktop

Action khi người dùng tạo và thoát ra

Để triển khai, cần thực hiện khảo sát để biết được nhu cầu của doanh nghiệp. 

Từng pool sẽ tương ứng với một nhóm đối tượng, hoặc một kiểu cách. Thường dùng pool cho một phòng ban, hoặc nhóm người có tính chất sử dụng công việc

![pool](/images/pool.png)

Virtualized Desktop Provisioning Type: 
- Manual Desktop Pool: Cài máy bằng tay. blade, vm. Các máy không thay đổi, mỗi máy tương ứng 1 người.
- Full clone desktop pool: triển khai nhanh.  optimize một máy, sau đó để làm tương tự cho các máy còn lại.
- on-demand desktop pool: dùng công nghệ của horizon 7. kết nối app volume. map app volume kết nối tới một desktop. một app volume đã được cài sẵn các app cần thiết

Một desktop có 3 vùng: OS, app volume, applicate.

![asign_user](/images/asign_user.png)

Virtualized desktop assignment types
- Floating user: mỗi user khi login vào desktop sẽ tạo một user data file cho user trên desktop đó. khi user thoát thì sẽ bị mất dữ liệu user data trên desktop đó.
- dedicated user: desktop có một persitent disk lưu user data file. đây là ổ đĩa của user, tồn tại mãi mãi. đây là loại thường sử dụng. dedicate được gắn cố định vào máy để dùng.
khi gán disk này sang máy khác thì vẫn xài bthuong như máy trước vì user data file không đổi.

![map_user_pools](/images/map_user_pools.png)

- Tương ứng với từng trường hợp sử dụng sẽ có mapping user type với pool type phù hợp.
- Một số trường hợp cơ bản như:
	- call center user: on-demand + floating
	- IT administrator: full clone + dedicate
	- executive user: full clone + dedicate
	- vendor: on-demand + floating
	- developer: full clone + dedicate

![app_delivery](/images/app_delivery.png)

Trong quá trình triển khai, có 2 cách để thiết lập (cài đặt) ứng dụng trên desktop là:
- app volume: tự map app volume vào os, tốc độ rất nhanh. volume cài sẵn ứng dụng.
- thin app: đóng gói ứng dụng, scan hệ thống trước khi cài và sau khi cài để đóng gói ứng dụng. ví dụ có 100 máy, muốn cài 1 ứng dụng cho 100 máy thì sử dụng thinapp. 
có thể dùng stream app trên một máy khác mà không cần cài đặt

![use-case-app-delivery](/images/use-case-app-delivery.png)

- app volume sẽ cài sẵn ứng dụng trước khi clone ra và sử dụng cho nhiều máy

![display_protocol](/images/display_protocol.png)




















































## Tham khảo
