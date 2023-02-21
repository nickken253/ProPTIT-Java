# PROPTIT - JAVA - THEORY - #4
Câu hỏi kỳ này:
- Package trong Java
- Xử lý Exception: từ khóa try, catch, finally, throw
- Tự custom Exception class

# I. PACKAGE TRONG JAVA
- Một `Package` (gói) trong Java là một nhóm các class, interface và các package con tương tự, liên quan đến nhau. Chúng ta có thể coi package giống như là một folder.
- Các package trong Java được sử dụng để tránh việc xung đột trong khi đặt tên, để kiểm soát truy cập, giúp bạn tìm kiếm và sử dụng các class, interface… một các dễ dàng hơn.
## 1. Phân loại
### a. Các package có sẵn trong Java API:
- `java.lang`: Chứa các lớp hỗ trợ ngôn ngữ (ví dụ: lớp được định nghĩa các kiểu dữ liệu nguyên thủy, các phép toán). Package này được import tự động.
- `java.io`: Chứa lớp để hỗ trợ input / output (I/O)
- `java.util`: Chứa các lớp tiện ích thực hiện các cấu trúc dữ liệu như danh sách liên kết, dictionary và hỗ trợ cho các hoạt động date / time.
- `java.applet`: Chứa các lớp để tạo Applet.
- `java.awt`: Chứa các class để triển khai các thành phần cho giao diện người dùng đồ họa (ví dụ như button, menu,…).
- `java.net`: Chứa các lớp để hỗ trợ các thao tác trong mạng (network).
### b. Package do người dùng tự định nghĩa:

## 2. Tại sao lại xử dụng package:
- Tìm kiếm và sử dụng các class, interface,… một các dễ dàng hơn.
- Package cung cấp bảo vệ truy cập
- Package ngăn chặn được xung đột khi đặt tên. Ví dụ: Có thể có 2 class People (tên class giống hệt nhau) trong 2 package khác nhau.
- Các package có thể được coi là đóng gói dữ liệu (hoặc ẩn dữ liệu).
## 3. Cách cài đặt và sử dụng Package
### a. Quy tắc đặt tên.
- Nếu tên package là `college.staff.cse`, khi đó có 3 thư mục là: `college`, `staff` và `cse` sao cho cse nằm trong staff và staff nằm trong college.
- Tên packages nên được viết thường hết tất cả các chữ cái.
- Với các dự án nhỏ chỉ có một vài package, bạn chỉ cần đặt cho chúng những cái tên đơn giản nhưng có ý nghĩa.
- Nhưng trong các công ty phần mềm và các dự án lớn, nơi các package có thể được nhập vào các package khác, các tên thường sẽ được chia nhỏ.
### b. Tạo package
- Từ khóa package được sử dụng để tạo một package trong java
``` Java
package mypack;  

public class Simple {  
    public static void main(String args[]) {
        System.out.println("Learn java package");
    }
} 
```
- Truy cập bằng cách
```Java
mypack.Simple
// hoặc
import package.*
```

# II. XỬ LÝ EXCEPTION
- `Exception` (ngoại lệ) là một tình trạng bất thường. Trong java, ngoại lệ là một sự kiện làm gián đoạn luồng bình thường của chương trình. Nó là một đối tượng được ném ra tại runtime.
![Ảnh](https://viettuts.vn/images/java/exception-handling/exception-handling-trong-java.png)
## 1. Có 2 kiểu ngoại lệ trong Java
- `Checked Exceptions`: Các ngoại lệ này thường là bị buộc phải bắt hoặc khai báo. Nếu quy tắc này không được tuân theo thì trình biên dịch sẽ không thực thi chương trình. Các lớp extends từ lớp Throwable ngoại trừ RuntimeException và Error được gọi là checked exception, ví dụ như Exception, SQLException vv. Các checked exception được kiểm tra tại compile-time.
    - `IOException`: Ngoại lệ liên quan đến file input / output
    - `SQLException`: Ngoại lệ liên quan đến cú pháp SQL
    - `DataAccessException`: Ngoại lệ liên quan đến việc truy cập CSDL
    - `ClassNotFoundException`: Bị ném khi JVM không thể tìm thấy một lớp mà nó cần, do lỗi dòng lệnh, sự cố đường dẫn hoặc tệp, class bị thiếu...
    - `InstantiationException`: Ngoại lệ khi cố gắng tạo đối tượng của một abstract class hoặc interface
 - `Unchecked Exceptions`: Ngoại lệ này thường là do viết code sai, truyền đối null hoặc tham số không chính xác... Các lớp extends từ RuntimeException được gọi là unchecked exception, ví dụ: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException,... Các ngoại lệ unchecked không được kiểm tra tại compile-time mà chúng được kiểm tra tại runtime.
    - `NullPointerException`: Ngoại lệ bị ném ra khi cố gắng truy cập một đối tượng có biến tham chiếu có giá trị hiện tại là null
    - `ArrayIndexOutOfBound`: Ngoại lệ khi cố gắng truy cập một phần tử vượt quá độ dài của mảng
    - `IllegalArgumentException`: Ngoại lệ bị ném ra khi một phương thức nhận được một đối số được định dạng khác với phương thức mong đợi.
    - `IllegalStateException`: Ngoại lệ bị ném ra khi trạng thái của môi trường không phù hợp với hoạt động cố gắng thực hiện, ví dụ: Sử dụng Scanner đã bị đóng.
    - `NumberFormatException`: Ngoại lệ bị ném khi một phương thức chuyển đổi một Chuỗi thành số nhưng không thể chuyển đổi.
    - `ArithmeticException`: Lỗi số học, chẳng hạn như chia cho 0.

## 2. Các từ khóa xử lý ngoại lệ trong java
Có 5 từ khóa được sử dụng để xử lý ngoại lệ trong java, đó là: `try`, `catch`, `finally`, `throw`, `throws`
### a. Khối lệnh try-catch:
```Java
try {  
    // code có thể ném ra ngoại lệ
} catch(Exception_class_Name ref) {
    // code xử lý ngoại lệ
}
```
### b. Khối lệnh try-finally:
```Java
try {  
    // code có thể ném ra ngoại lệ
} finally {
    // code trong khối này luôn được thực thi
} 
```

### c. Đa khối lệnh catch:
- Nếu bạn phải thực hiện các tác vụ khác nhau mà ở đó có thể xảy ra các ngoại lệ khác nhau, hãy sử dụng đa khối lệnh catch trong java.
```Java
try {
    // code có thể ném ra ngoại lệ
} catch(Exception_class_Name_1 ex) {
    // code xử lý ngoại lệ 1
} catch(Exception_class_Name_2 ex) {
    // code xử lý ngoại lệ 2
} catch(Exception_class_Name_n ex) {
    // code xử lý ngoại lệ n
} finally {
    // code trong khối này luôn được thực thi
}
```
### d. Khối lệnh try lồng nhau:
- Đôi khi một tình huống có thể phát sinh khi một phần của một khối lệnh có thể xảy ra một lỗi và toàn bộ khối lệnh chính nó có thể xảy ra một lỗi khác.
```Java
try {  
    statement 1;  
    statement 2;  
    try {  
        statement 1;  
        statement 2;  
    }  
    catch(Exception e) {
         
    }  
}  
catch(Exception e) {
     
}
```
### e. Khối lệnh finally:
![Ảnh](https://viettuts.vn/images/java/exception-handling/flow-cua-khoi-lenh-finally-trong-java.png)
- Khối finally có thể được sử dụng để chèn lệnh "cleanup" vào chương trình như việc đóng file, đóng các kết nối,...
## 3. Ví dụ
```Java
public class TestTryCatch1 {
    public static void main(String args[]) {
        int data = 50 / 0;  // ném ra ngoại lê ở đây
        System.out.println("rest of the code...");
    }
}
```
- Ta sẽ xử lý bằng try-catch như sau:
```Java
public class TestTryCatch2 {
    public static void main(String args[]) {
        try {
            int data = 50 / 0;
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("rest of the code...");
    }
}
```