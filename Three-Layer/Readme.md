# 3 Layer 
## **Một số ưu điểm khi sử dụng mô hình 3 lớp:**
- Phân tách rõ ràng chức năng của các phần 
- Ứng dụng có thể truy suất từ bên ngoài
**Một số lưu ý khi xây dựng mô hình:**
- Cần 3 project khác nhau để làm nên 3 lớp, tên Project đặt như sau:
- Lớp GUI: (VD: QuanLy_GUI)
- Lớp Business: (VD: QuanLy_BUS)
- Lớp Data Access: (VD: QuanLy_DAL)
- Lớp DTO: (VD: QuanLy_DTO)
Vậy GUI,BUS,DAL là gì ??
- 1.Presentation Layer (GUI): Đây sẽ là tầng giao diện , giao tiếp với người dùng
- 2.Business Logic Layer (BLL): Tiếp nhận thông tin từ GUI , giải quyết vấn đề trước khi chuyển xuống cho DAL 
- 3.Data Access Layer (DAL) : Thao tác trực tiếp với cơ sở dữ liệu (CURD , thao tác hoặc truy vấn)
**Tách nhỏ hơn nữa**
Thực thế trong dự án 3 cục kia chỉ là 3 cục chính , ta có thể phân tách nhỏ hơn nữa như sau
1.GUI
    _ Ta có thể chia GUI là 2 thành phần nhỏ hơn là UI Components và UI Process Components
        _ UI Components :nhiệm vụ thu nhận  dữ liệu như textbox , input v..v
        _ UI Process Components : nhiệm vụ chuyển đổi giữa các UI. Vd :Find Id , list customer contact v...vv
2.BLL
    _ Ta có thể chia BLL là 4 thành phần nhỏ hơn là Service Interface , Bussiness Workflows ,Bussiness Components,Bussiness Entities
        _ Service Interface: là phần dịch vụ mà nó cung cấp cho mới GUI sử dụng 
        _ Bussiness Workflows : chịu trách nhiệm xác định và điều phối các quy trình nghiệp 
        vụ gồm nhiều bước và kéo dài. Những quy trình này phải được sắp xếp và thực hiện 
        theo một thứ tự chính xác.
        _ Bussiness Components : chịu trách nhiệm kiểm tra các quy tắc nghiệp vụ, ràng buộc logic và thực hiện các công việc
        _ Bussiness Entities :hường được sử dụng như Data Transfer Objects ( DTO ) . Bạn có thể sử dụng để truyền dữ liệu giữa 
        các lớp (Presentation và Data Layer). 
3.DAL
    _ chịu trách nhiệm chính lưu trữ và truy xuất dữ liệu từ các nguồn dữ liệu (Data Sources) 

## **Một số khái niệm:**
- Lớp DTO, chứa những dữ liệu được xây dựng dưới dạng lớp đối tượng
- Lớp BUS (hay là BLL) gồm các nghiệp vụ insert, update, delete,...
- Lớp DAO ( hay là DAL ). Truy vấn đến cơ sở dữ liệu