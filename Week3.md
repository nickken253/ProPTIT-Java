# PROPTIT - JAVA - THEORY - #3
Câu hỏi tuần này:
- Tìm hiểu về MVC
- Tìm hiểu về đọc ghi file
# I. MVC (MODEL - VIEW - CONTROLLER)
- MVC là một design pattern phổ biến và thường được áp dụng cho thiết kế web.
- MVC được viết tắt bởi 3 từ: `Model` – `View` – `Controller`, là một mẫu thiết kế nhằm mục tiêu chia tách phần giao diện và code để dễ quản lý, phát triển và bảo trì.
    - `Model`: quản lý, xử lý dữ liệu.
    - `View`: giao diện, hiển thị dữ liệu cho người dùng.
    - `Controller`: điều khiển sự tương tác giữa Model và View.
## 1. Model
- Có nhiệm vụ quản lý dữ liệu của ứng dụng.
- Chứa tất cả các nghiệp vụ logic, đối tượng mô tả dữ liệu.
- Thông báo cho view để hiện thị lại kết quả cho người dùng.
## 2. View
- Chứa giao diện, tương tác với người dùng, sử dụng Model để hiển thị kết quả cho người dùng.
- Đưa ra kết quả từ tầng Controller.
- Thu nhận các hoạt động, yêu cầu của người dùng và chuyển cho tầng Controller xử lý.
## 3. Controller
- Định nghĩa các hoạt động, xử lý của hệ thống
- Đối chiếu các hành động của người dùng từ View. Đồng thời tương tác Model để gọi View và hiển thị thông tin tương ứng cho người dùng.
> Tóm lại:
>
> Ưu điểm của mô hình MVC là ứng dụng của bạn sẽ dễ nâng cấp và bảo trì do code của bạn được chia thành các thành phần độc lập.
>
> Tuy nhiên đối với những dự án nhỏ thì việc áp dụng mô hình MVC sẽ gây cồng kềnh, tốn thời gian trong quá trình phát triển.

``` Java
// Model
public class LoginModel {
   private String user;
   private String pass;

   public LoginModel() {}

   public LoginModel(String _user, String _pass) {
      this.user = _user;
      this.pass = _pass;
   }

   public String getUser() {
      return user;
   }

   public void setUser(String _user) {
      this.user = _user;
   }

   public String getPass() {
      return pass;
   }

   public void setPass(String _pass) {
      this.pass = _pass;
   }
}
```

```Java
// View
import java.util.Scanner;

public class LoginView {
   public static Scanner scanner = new Scanner(System.in);

   public void showMessage(String msg) {
      System.out.println(msg);
   }

   public LoginModel getInfo() {
      System.out.println("_____LOGIN_____");
      System.out.println();

      LoginModel user = new LoginModel();
      System.out.print("Username: ");
      user.setUser(scanner.next());
      System.out.print("Password: ");
      user.setPass(scanner.next());
      return user;
   }
}
```

```Java
// Controller
public class LoginController {
   private LoginView view;

   public LoginController(LoginView view) {
      this.view = view;
   }

   private boolean check(LoginModel user) {
      if ((user.getUser().equals("admin")) 
      && (user.getPass().equals("123"))) {
         return true;
      }
      return false;
   }

   public void login() {
      while (true) {
         LoginModel user = view.getInfo();
         if (check(user)) {
            view.showMessage("Login successfully");
            break;
            } else {
            view.showMessage("Wrong username or password");
         }
      }
   }
}
```

# II. ĐỌC GHI FILE
- Lưu ý về đọc ghi file:
    - `IOException` còn được gọi là `checked exception`. Chúng được trình biên dịch kiểm tra tại thời điểm biên dịch và lập trình viên được yêu cầu xử lý các ngoại lệ này.

    - Một số `IOException` phổ biến là:
        - `FileNotFoundException` lỗi mở một file không tồn tại.
        - Lỗi đọc các dòng không có trong file.
        - `IOException` là các exception liên quan tới đọc ghi.
- Ta sẽ tìm hiểu thêm về sử lý ngoại lệ ở phần sau.
## 1. Đọc ghi file sử dụng Byte Stream
- Có rất nhiều class Byte Stream, để hình dung Byte Stream hoạt động như thế nào, chúng ta sẽ tập trung vào `FileInputStream` và `FileOutputStream`.
```Java
public class CopyFileByte {
    public static void main(String [] args) throws IOException {
      FileInputStream inputStream = null;
      FileOutputStream outputStream = null;
 
      try {
         inputStream = new FileInputStream("inStream.txt");
         outputStream = new FileOutputStream("outStream.txt");
          
         int c;
         while ((c = inputStream.read()) != -1) {
            outputStream.write(c);           
         }
      } finally {
         if (inputStream != null) {
            inputStream.close();
         }
         if (outputStream != null) {
            outputStream.close();
         }
      }         
    }
}
```

## 2. Đọc ghi file sử dụng Character Stream
- Có rất nhiều class Character Stream, để hình dung Character Stream hoạt động như thế nào, chúng ta sẽ tập trung vào `FileReader` và `FileWriter`.
```Java
public class CopyFileCharacter {
    public static void main(String [] args) throws IOException {
      FileReader in = null;
      FileWriter out = null;
 
      try {
         in = new FileReader("input.txt");
         out = new FileWriter("output.txt");
          
         int c;
         while ((c = in.read()) != -1) {
            out.write(c);           
         }
      }finally {
         if (in != null) {
            in.close();
         }
         if (out != null) {
            out.close();
         }
      }         
    }    
}
```

## 3. Sử dụng Buffered Streams
- Các ví dụ trên không sử dụng `Buffered Streams`, điều này có nghĩa là việc đọc và xuất dữ liệu được thực hiện trực tiếp dưới quyền điều khiển của hệ điều hành, gây lãng phí thời gian và tài nguyên. Để giảm thiểu những trên, `Buffered Streams` đã được sinh ra. 
- `Buffered Streams` được sử dụng để tăng tốc độ hoạt động I/O, bằng cách đơn giản là tạo ra một khoảng nhớ đệm với kích thước cụ thể nào đó. Vì vậy chúng ta không cần phải truy cập vào ổ đĩa cứng khi thực hiện I/O. Một chương trình có thể chuyển đổi từ không sử dụng `buffered stream` (Byte Stream và Chracter Stream sang sử dụng buffered stream bằng việc sử dụng ý tưởng `Wrapping`. 
- Ta bổ sung thêm
```Java
bufferIn = new BufferedInputStream(inputStream);
bufferOut = new BufferedOutputStream(outputStream); 
```

## 4. Sử dụng Scanner
```Java
Scanner sc = new Scanner(new File("myNumbers.txt"));
while (sc.hasNextLong()) {
    long aLong = sc.nextLong();
}
```

# III. XỬ LÝ NGOẠI LỆ
- Ở ví dụ nhập xuất file bên trên, nếu vào trường hợp nhập file ko tồn tại sẽ sinh ra lỗi thực thi. Chính vì thế, ta phải xử lí ngoại lệ.
## 1. Có 2 kiểu ngoại lệ trong Java
- `Checked Exceptions`: Các ngoại lệ này thường là bị buộc phải bắt hoặc khai báo. Nếu quy tắc này không được tuân theo thì trình biên dịch sẽ không thực thi chương trình.
    - `IOException`: Ngoại lệ liên quan đến file input / output
    - `SQLException`: Ngoại lệ liên quan đến cú pháp SQL
    - `DataAccessException`: Ngoại lệ liên quan đến việc truy cập CSDL
    - `ClassNotFoundException`: Bị ném khi JVM không thể tìm thấy một lớp mà nó cần, do lỗi dòng lệnh, sự cố đường dẫn hoặc tệp, class bị thiếu...
    - `InstantiationException`: Ngoại lệ khi cố gắng tạo đối tượng của một abstract class hoặc interface
 - `Unchecked Exceptions`: Ngoại lệ này thường là do viết code sai, truyền đối null hoặc tham số không chính xác...
    - `NullPointerException`: Ngoại lệ bị ném ra khi cố gắng truy cập một đối tượng có biến tham chiếu có giá trị hiện tại là null
    - `ArrayIndexOutOfBound`: Ngoại lệ khi cố gắng truy cập một phần tử vượt quá độ dài của mảng
    - `IllegalArgumentException`: Ngoại lệ bị ném ra khi một phương thức nhận được một đối số được định dạng khác với phương thức mong đợi.
    - `IllegalStateException`: Ngoại lệ bị ném ra khi trạng thái của môi trường không phù hợp với hoạt động cố gắng thực hiện, ví dụ: Sử dụng Scanner đã bị đóng.
    - `NumberFormatException`: Ngoại lệ bị ném khi một phương thức chuyển đổi một Chuỗi thành số nhưng không thể chuyển đổi.
    - `ArithmeticException`: Lỗi số học, chẳng hạn như chia cho 0.

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