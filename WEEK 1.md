# PROPTIT - JAVA - THEORY - #1

Câu hỏi kỳ này:
- Syntax cơ bản: Nhập xuất; Biến, toán tử; If-else; Vòng lặp; Arrays; Wrapper class, String classes, Math class.
- Regex.
- Class & Object: Encapsulation; Inheritance; Polymorphism; Common Modifiers; Modifier static; Interfaces; Abstract Classes.
- 
# TABLE OF CONTENTS
1. [CÚ PHÁP CƠ BẢN](#i-cú-pháp-cơ-bản)
2. [REGEX](#ii-regex)
3. [CLASS & OBJECT (OOP)](#iii-class--object-oop)

# I. CÚ PHÁP CƠ BẢN
Một hàm main cơ bản, các thủ tục cơ bản, ta viết bên trong này.
```Java
public class Test {
    public static void main(String[] args) {
        // .....
    }
}
```
## 1. Nhập xuất:
### a. Nhập:
Trước tiên, ta cần import gói dữ liệu cần sử dụng.
``` Java
import java.util.Scanner;
```

``` Java
Scanner scan = new Scanner(System.in)
```
Trong đó:
- Scanner: là lớp giúp chúng ta lấy dữ liệu đầu vào, nằm trong gói `java.util`.
- scan: là tên đối tượng từ lớp Scanner, khi nhập, ta sẽ làm việc với đối tượng này.
- Trong ngoặc () là nguồn vào: có thể là hệ thống, người dùng hoặc tệp. Như ở đây là đầu vào hệ thống.

> Cú pháp: 
>> (data-type) (variable-name) = scan.next...();

Ta cần thay trong dấu "..." bằng phương thức ta muốn:

| Phương thức	| Mô tả |                     
|:-------|:------|
| nextByte()	| Đọc một số nguyên kiểu byte |
| nextShort()	| Đọc một số nguyên kiểu short | 
| nextInt()	| Đọc một số nguyên kiểu int | 
| nextLong()	| Đọc một số nguyên kiểu long |
| nextFloat()	| Đọc một số kiểu float |
| nextDouble()	| Đọc một số kiểu double |
| next()	| Đọc một string kết thức trước một ký tự trắng |
| nextLine()	| Đọc một line of text (kết thúc bằng phím Enter) |

> Ví dụ: Nhập một string.
``` Java
Scanner scan = new Scanner(System.in);
String test = scan.nextLine();
```

Trong Java cũng gặp tình trạng bị trôi lệnh khi nhập 1 string ngay sau khi nhập 1 số. Cách sử lý là dùng thêm 1 lần nhập `scan.nextLine()` trước khi nhập string.
``` Java
int num = scan.nextInt();

scan.nextLine();
String st = scan.nextLine();
```

### b. Xuất:
- Sử dụng `System.out.printfln();`
   - Xuất kết quả ra màn hình đồng thời con trỏ chuột nhảy xuống dòng tiếp theo
- Sử dụng `System.out.print();`
   - Xuất kết quả ra màn hình nhưng con trỏ chuột không xuống dòng.
- Sử dụng `System.out.printf();`
   - Xuất ra màn hình kết quả đồng thời có thể định dạng được kết quả đó nhờ vào các đối số thích hợp.
   - Giống trong C và CPP.

> Trong netbean hoặc eclipse có thể sử dụng `sout + tab` để thao tác nhanh.

## 2. Biến và Toán tử

### a. Biến
- Khai báo: **Data-type Variable-name;**

``` Java
int Num;
String st;
float f;
```

- Lưu ý đặt tên biến:
    - Chỉ được bắt đầu bằng chữ, dấu gạch dưới (_) hoặc dấu dollar ($).
    - Tên biến phải là một chuỗi liên tục.
    - Không trùng với các từ khóa mặc định, có phân biệt hoa và thường.

- Khởi tạo biến:
``` Java
int Num = 10;
String st = "ABC";
float f = scan.nextFloat();
```

- Java có biến toàn cục, biến cục bộ và biến static tương tự như C và CPP.
    - Biến static không thể nằm trong main.
    - Gọi tới biến static của một class bằng `ClassName.StaticVarName`
``` Java
public static int BienStatic;
```

### b. Kiểu dữ liệu & Toán tử 
- Tương tự C và CPP, cũng có ép kiểu.
- Không có kiểu dữ liệu `long long`.
- Muốn nhập kiểu `char`. Ta nhập vào string và trỏ tới vị trí đầu tiên.

``` Java
char c = scan.next().charAt(0);
```
- Toán tử $==$ dùng để so sánh, nhưng khi muốn so sánh 2 string với nhau, ta cần dùng phương thức `equals()`, giá trị trả về là true/false.
``` Java
String a = "ABC";
String b = "ABC";
System.out.println(a.equals(b)); // true
```
## 3. Câu lệnh rẽ nhánh & Vòng lặp

### a. Câu lệnh rẽ nhánh:
- Trong Java cũng có toán tử 3 ngôi `a?b:c` và `Switch Case`.
- if else tương tự trong C và CPP, cũng có các dạng if else liên tục và lồng nhau.

``` Java
if(n > 3)
{
    System.out.println("A");
} 
else if(n > 0) 
{
    System.out.println("b");
}
else
{
    System.out.println("C");
}
```

### b. Vòng lặp:
- Tương tự C và CPP:
``` Java
// Vòng lặp for
for(int i = 0; i < n; i++)
{
    // Câu lệnh
}
//----------------------------------
// Vòng lặp while
while(n > 3)
{
    // câu lệnh
}
//----------------------------------
// Vòng lặp do while
do
{
    // Câu lệnh
}
while(n > 3)
//----------------------------------
// Vòng lặp for each
for(int i : arr)
{
    // Câu lệnh
}
```
- Lưu ý: không sử dụng được từ khóa `auto`.
- Các từ khóa `Break`, `Continue` tương tự như C và CPP. Có thể thêm Label trong code và các từ khóa sẽ tương tác với Label.

``` Java
labelTest: for(int i = 0; i < n; i++)
{
    for(int j = 0; j < n; j++)
    {
        if(j > 10) break labelTest;
    }
}
```

## 4. Mảng
Cần import gói dữ liệu `java.util.Arrays` khi làm việc với các phương thức với mảng.
### a. Khai báo mảng:
> Cú pháp: **Data-type Array-name**
``` Java
// Mảng 1 chiều
int arr[];
float []arr;


// Mảng 2 chiều
double arr2[][];
int [][]arr2;
```

### b. Khởi tạo mảng:
``` Java
// Mảng 1 chiều
int[] c = {1, 2, 3, 4, 5};

int[] b = new int[10];

String[] name = new String[] { "ABC", "DEF"};


// Mảng 2 chiều
int[][] c = {{1, 2}, { 3, 4}, { 3, 4}, { 3, 4}};

int[][] b = new int[4][2];
for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 2; j++) {
        b[i][j] = i;
    }
}
```
### c. Sắp xếp mảng
``` Java
int[] arr = {4, 3, 2, 8 , 6};
Arrays.sort(arr);
```

>Lưu ý: Mảng 2 chiều trong Java, các hàng có thể khác nhau về số cột.

### 5. Hàm - Phương thức
``` Java
/*
modifier returnType nameOfMethod (Parameter List) {
   // method body
}
*/

public static int tongHaiSo(int a, int b) {
  return a + b;
}
```

Có phương thức static:
``` Java
public static void nameOfMethod()
{
	// method body
}
```
Có thể tùy biến hàm - phương thức giống như C và CPP.

## 6. Wrapper class, String classes, Math class.
### a. Wrapper class:
- Lớp `Wrapper` sẽ giúp chúng ta chuyển đổi qua lại giữa một kiểu dữ liệu nguyên thủy sang kiểu dữ liệu đối tượng và ngược lại.

| Kiểu nguyên thủy	| Kiểu Wrapper | 
| :------| :------ |
| boolean	| Boolean | 
| char	| Character | 
| byte	| Byte | 
| short	| Short | 
| int	| Integer | 
| long	| Long | 
| float	| Float | 
| double	| Double | 

- Chuyển đổi một kiểu nguyên thủy sang kiểu `Wrapper` của nó người ta gọi là `Boxing`. Ngược lại, khi bạn chuyển từ một kiểu `Wrapper` sang kiểu nguyên thủy của nó người ta gọi là `Unboxing`.
- Một số cấu trúc khác bên trong ngôn ngữ `Java`, như `ArrayList` hay `Vector` đều chứa đựng các tập hợp kiểu dữ liệu đối tượng thay vì kiểu nguyên thủy, nên việc biết và vận dụng các lớp `Wrapper` là một bắt buộc.
- Ngoài ra thì kiểu dữ liệu đối tượng sẽ thích hợp hơn trong việc thực thi đa luồng (`multithreading`) và đồng bộ hóa (`synchronization`).

- Các phương thức với Wrapper class:
    - ...Value(): giúp chuyển đổi một giá trị của lớp Wrapper nào đó về kiểu dữ liệu nguyên thủy (unboxing).
    - parse...(""): Tham số truyền vào cho phương thức là một chuỗi, kết quả nhận được là một giá trị nguyên thủy tương ứng với chuỗi truyền vào.
    - toString(): chuyển đổi từ liểu dữ liệu Wrapper thành string.
``` Java
// ... Value
Double d = 50.5;
int i = d.intValue();

// parse...
int i = Integer.parseInt("10");

// toString
String sI = Integer.toString(10);

// Boxing
int a = 500;
Integer i = new Integer(a);
Float f = new Float(4.5);
Double d = 5d;
Boolean b = true;

// Unboxing
Integer j = 500; 
int j2 = j.intValue(); 
```

> Lưu ý: `String` không phải là kiểu dữ liệu nguyên thủy.

### b. String classes:
- String trong Java không phải là một kiểu dữ liệu nguyên thủy mà là một đối tượng của lớp class String.

``` Java
String st = “Hello World” ;
String st = new String(“Hello World”);
```

- Các phương thức với String Class:
    - length(): trả về chiều dài của chuỗi - là số ký tự của một chuỗi.
    - charAt(i): trả lại giá trị ký tự tại một vị trí i của một chuỗi. 
    - trim ():  trả về Chuỗi mới sau khi loại bỏ khoảng trắng ở cả hai đầu.

### c. Math Classes:
- Cần import gói dữ liệu `java.util.Math` để sử dụng.
- Tương tụ các hàm bên C và CPP.

# II. REGEX
- Regex hay Regular Expressions, là một biểu thức chính quy. Hỗ trợ việc thực hiện các hoạt động khác nhau trên Chuỗi / văn bản như tìm kiếm, xử lý, chỉnh sửa, đối sánh mẫu, thao tác, xác thực email và mật khẩu,...
- Để sử dụng cần import gói `java.util.regex`, nó sẽ cung cấp 3 `Class` và 1 `Interface` để áp dụng các biểu thức chính quy.
    - Interface MatchResult.
    - Pattern Class.
    - Matcher Class.
    - PatternSyntaxException Class.
## 1. Tìm hiểu chung
### a. Pattern Class:
- Đây là phiên bản biên dịch của một biểu thức chính quy. Nó được sử dụng để xác định một khuôn mẫu cho các biểu thức chính quy.
- Lớp này có phương thức `Compile()`, ta sẽ truyền `Xâu cần so khớp` vào trong phương thức này, và nó sẽ trả về 1 đối tượng Pattern.

| No.	| Phương thức	| Mô tả
| :----|:-----|:-----|
| 1	| static Pattern compile(String regex)	| biên dịch regex đã cho và trả về thể hiện của Pattern.
| 2	| Matcher matcher(CharSequence input)	| tạo một matcher khớp với đầu vào đã cho với mẫu.
| 3	| static boolean matches(String regex, CharSequence input)	| Nó biên dịch biểu thức chính quy và tìm kiếm các chuỗi con từ chuỗi input phù hợp với mẫu regex.
| 4	| String[] split(CharSequence input)	| chia chuỗi input đã cho thành mảng các kết quả trùng khớp với mẫu đã cho.
| 5	| String pattern()	| trả về mẫu regex.
### b. Matcher Class:
- Lớp Matcher thực thi interface MatchResult. Nó được sử dụng để thực hiện các hoạt động so khớp trên một chuỗi ký tự.
- Thực hiện chức năng `So khớp` chính.
- Ta sẽ có được 1 đối tượng `Matcher` khi gọi tới phương thức `matcher()` trên một đối tượng `Pattern`.
- Ta truyền Xâu đầu vào - Xâu cần so khớp vào `matcher()` và xem xem nó có chứa mẫu mong muốn xuất hiện.


| No.	| Phương thức	| Mô tả
| :----|:-----|:-----|
| 1	| boolean matches()	| kiểm tra xem biểu thức chính quy có khớp với mẫu hay không.
| 2	| boolean find()	| tìm biểu thức tiếp theo khớp với mẫu.
| 3	| boolean find(int start)	| tìm biểu thức tiếp theo khớp với mẫu từ số bắt đầu đã cho.
| 4	| String group()	| trả về chuỗi con phù hợp.
| 5	| int start()	| trả về vị trí bắt đầu của chuỗi con phù hợp.
| 6	| int end()	| trả về vị trí kết thúc của chuỗi con phù hợp.
| 7	| int groupCount()	| trả về tổng số các chuỗi con phù hợp.
### c. PatternSyntaxException:
- `PatternSyntaxException` sẽ xảy ra khi mà có lỗi cú pháp trong mẫu Regular Expression.

## 2. Cú pháp Regex
| No.	| Biểu thức chính quy	| Mô tả
| :----|:-----|:-----|
| 1	| .	| Khớp (match) với bất kỳ ký tự nào
| 2	| ^regex	| Biểu thức chính quy phải  khớp tại điểm bắt đầu
| 3	| regex$	| Biểu thức chính quy phải khớp ở cuối dòng.
| 4	| [abc]	| Thiết lập định nghĩa, có thể khớp với a hoặc b hoặc c.
| 5	| [abc][vz]	| Thiết lập định nghĩa, có thể khớp với a hoặc b hoặc c theo sau là v hay z.
| 6	| [^abc]	| Khi dấu ^ xuất hiện như là nhân vật đầu tiên trong dấu ngoặc vuông, nó phủ nhận mô hình. Điều này có thể khớp với bất kỳ ký tự nào ngoại trừ a hoặc b hoặc c.
| 7	| [a-d1-7]	| Phạm vi: phù hợp với một chuỗi giữa a và điểm d và con số từ 1 đến 7.
| 8	| X $\|$ Z	| Tìm X hoặc Z.
| 9	| XZ	| Tìm X và theo sau là Z.
| 10	| $	| Kiểm tra kết thúc dòng.
| 11	| \d	| Số bất kỳ, viết ngắn gọn cho [0-9]
| 12	| \D	| Ký tự không phải là số, viết ngắn gon cho [^0-9]
| 13	| \s	| Ký tự khoảng trắng, viết ngắn gọn cho [ \t\n\x0b\r\f]
| 14	| \S	| Ký tự không phải khoản trắng, viết ngắn gọn cho [^\s]
| 15	| \w	| Ký tự chữ, viết ngắn gọn cho [a-zA-Z_0-9]
| 16	| \W	| Ký tự không phải chữ, viết ngắn gọn cho [^\w]
| 17	| \S+	| Một số ký tự không phải khoảng trắng (Một hoặc nhiều)
| 18	| \b	| Ký tự thuộc a-z hoặc A-Z hoặc 0-9 hoặc _, viết ngắn gọn cho [a-zA-Z0-9_].
| 19	| $*$	| Xuất hiện 0 hoặc nhiều lần, viết ngắn gọn cho {0,}
| 20	| $+$	| Xuất hiện 1 hoặc nhiều lần, viết ngắn gọn cho {1,}
| 21	| $?$	| Xuất hiện 0 hoặc 1 lần, ? viết ngắn gọn cho {0,1}.
| 22	| $ \{ X \} $	| Xuất hiện X lần, {}
| 23	| $ \{ X, Y \} $	| Xuất hiện trong khoảng X tới Y lần.
| 24	| $ *? $	| * có nghĩa là xuất hiện 0 hoặc nhiều lần, thêm ? phía sau nghĩa là tìm kiếm khớp nhỏ nhất.

## 3. Ví dụ

``` Java
import java.util.regex.*;
public class Test {
    public static void main(String[] args) {
        Pattern pattern = Pattern.compile("[HE]", Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher("hoanganh.nickken@gmail.com");
        boolean Found = matcher.find();

        if(Found) System.out.println("YES");
        else System.out.println("NO");
    }
}
```
- Mục đích đoạn code trên, là tìm kiếm chữ H trong xâu.
- Ta dùng pattern với regex là [HE]: mục đích là tìm chữ H, hoặc E trong xâu, đằng sau nó là phong cách tìm (Tìm không phân biệt hoa, thường).
- matcher chứa xâu đầu vào.
- Phương thức find() để tìm kiếm chuỗi regex có đảm bảo nằm trong matcher hay không ?


``` Java
import java.util.regex.*;
public class Test {
    public static void main(String[] args) {
        Pattern pattern = Pattern.compile("@gmail.com$", Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher("hoanganh.nickken@gmail.com");
        boolean Found = matcher.find();

        if(Found) System.out.println("YES");
        else System.out.println("NO");
    }
}
```

``` Java
import java.util.regex.*;
public class Test {
    public static void main(String[] args) {
        System.out.println("Ký tự ? ....");
        System.out.println(Pattern.matches("[amn]?", "a")); //true (a hoặc m hoặc n xuất hiện 1 lần)
        System.out.println(Pattern.matches("[amn]?", "aaa")); //false (a xuất hiện nhiều lần)
        System.out.println(Pattern.matches("[amn]?", "aammmnn")); //false (a hoặc m hoặc n xuất hiện nhiều lần)
        System.out.println(Pattern.matches("[amn]?", "aazzta")); //false (a xuất hiện nhiều lần)
        System.out.println(Pattern.matches("[amn]?", "am")); //false

        System.out.println("Ký tự + ....");
        System.out.println(Pattern.matches("[amn]+", "a")); //true (a hoặc m hoặc n xuất hiện 1 hoặc nhiều lần)
        System.out.println(Pattern.matches("[amn]+", "aaa")); //true (a xuất hiện nhiều lần)
        System.out.println(Pattern.matches("[amn]+", "aammmnn")); //true (a hoặc m hoặc n xuất hiện nhiều lần)
        System.out.println(Pattern.matches("[amn]+", "aazzta")); //false (z và t không đúng với regex)

        System.out.println("Ký tự * ....");
        System.out.println(Pattern.matches("[amn]*", "ammmna")); //true (a hoặc m hoặc n) có thể không xuất hiện hoặc xuất hiện nhiều lần
    }
}
```

# III. CLASS & OBJECT (OOP)
## 1.Encapsulation (Tính đóng gói).
- Tính đóng gói trong java là kỹ thuật ẩn giấu thông tin không liên quan và hiện thị ra thông liên quan. Mục đích chính của đóng gói trong java là giảm thiểu mức độ phức tạp phát triển phần mềm. Tức là thiết kế để các thuộc tính và phương thức thuộc về (bên trong) một lớp.
- Với các access modifier, tính đóng gói sẽ có thể giúp ngăn chặn những lớp bên ngoài truy cập, thay đổi thuộc tính và phương thức của một lớp. Từ đó, giúp cho việc che giấu dữ liệu, để bảo vệ trạng thái bên trong của một đối tượng. Hơn nữa, việc ẩn giấu các biến thì các lớp sẽ không chia sẻ thông tin với nhau được. Điều này làm giảm số lượng khớp nối có thể có trong một ứng dụng.
## 2. Inheritance (Tính kế thừa).
- Tính kế thừa trong Java là một cơ chế trong đó một đối tượng có được tất cả các thuộc tính và hành vi của một đối tượng cha.
- Khi bạn kế thừa từ một class có sẵn, bạn có thể tái sử dụng các phương thức và trường của class cha. Hơn nữa, bạn có thể thêm các phương thức và trường mới trong class hiện tại.
- Sử dụng tính kế thừa, ta có thể thực hiện Method Overriding, từ đó xuất hiện tính Đa hình trong runtime.
- Phân loại:
    - Đơn kế thừa.
    - Kế thừa nhiều cấp.
    - Kế thừa thứ bậc.

![Ảnh](https://media.techmaster.vn/api/static/c6gsfifk0cmj7hbgjgeg/EBBRcItv)
- Đa kế thừa và Kế thừa hỗn hợp không được hỗ trợ thông qua Class trong Java, nhưng vẫn được hỗ trợ thông qua Interface.

- Cú pháp: sử dụng từ khóa `extends`
``` Java
class Subclass extends Superclass 
{  
   //... 
} 
```
- Ngoài ra còn có từ khóa `super` để tham chiếu trực tiếp đến đối tượng của lớp cha gần nhất.
    - Sử dụng từ khóa `super.xxx` để gọi đến phương thức `xxx` của lớp cha gần nhất.
    - Sử dụng `super()` để gọi trực tiếp constructor (hàm tạo) của lớp cha gần nhất.
## 3. Polymorphism (Tính đa hình).
- Đa hình là ta có thể thực hiện một hành động bằng nhiều cách khác nhau.
- Có hai kiểu của đa hình trong java, đó là đa hình lúc biên dịch (compile) và đa hình lúc thực thi (runtime). Chúng ta có thể thực hiện đa hình trong java bằng cách method overriding (ghi đè phương thức) và method overloading (nạp chồng phương thức).
- Ghi đè phương thức:  method overriding - ghi đè method ở lớp cha trong lớp con, ta chỉ cần viết code thực thi khác của method đó ở trong lớp con là được.
- Nạp chồng phương thức : method overloading - Trong một class có thẻ có nhiều method cùng tên nhưng khác nhau tham số truyền vào và dữ liệu trả về, cách hoạt động khác nhau.
> Tương tự khi học OOP trong CPP
## 4. Modifiers.
- Có hai loại `Modifier` trong Java, đó là: `Access Modifier` và `Non-access Modifier`. Ta sẽ tìm hiểu kỹ về `Access Modifier`.
- Tương tự OOP trong CPP, trong Java có 4 phạm vi truy cập của Access Modifier như sau:
    - private
    - default
    - protected
    - public

| Access Modifier	| Trong lớp	| Trong package	| Ngoài package bởi lớp con	| Ngoài package
| :----|:----:|:----:|:----:|:----:|
| Private	| Y	| N	| N	| N
| Default	| Y	| Y	| N	| N
| Protected	| Y	| Y	| Y	| N
| Public	| Y	| Y	| Y	| Y

> Lưu ý:
> - Constructor cần để public để có thể thực hiện tính Kế thừa.
> - Nếu không khai báo Access Modifier, thì nó mặc định là `default`.
> - Protected access modifier được truy cập bên trong package và bên ngoài package nhưng phải kế thừa.
> - Ngoài ra có thêm final dùng để hạn chế người dùng:
>   - final variable: không thể thay đổi giá trị (hắng số)
>   - final parameter: tương tự final variable
>   - final method: không thể ghi đè
>   - final class: không thể kế thừa

## 5. Modifier static.
- Được sử dụng chính để quản lý bộ nhớ. Chúng ta có thể áp dụng từ khóa static với các biến, các phương thức, các khối, các lớp lồng nhau(nested class). Từ khóa static thuộc về lớp chứ không thuộc về instance(thể hiện) của lớp.
    - Biến static: Khi bạn khai báo một biến là static, thì biến đó được gọi là biến tĩnh, hay biến static.
    - Phương thức static: Khi bạn khai báo một phương thức là static, thì phương thức đó gọi là phương thức static.
    - Khối static: Được sử dụng để khởi tạo thành viên dữ liệu static.

- Biến Static: có thể được sử dụng để tham chiếu thuộc tính chung của tất cả đối tượng (mà không là duy nhất cho mỗi đối tượng), ví dụ như tên công ty của nhân viên, tên trường học của các sinh viên, ... Biến static lấy bộ nhớ chỉ một lần trong Class Area tại thời gian tải lớp đó.
``` Java
public class Student8 {
    int rollno;
    String name;
    static String college = "Bưu Chính Viễn Thông";
 
    Student8(int r, String n) {
        rollno = r;
        name = n;
    }
 
    void display() {
        System.out.println(rollno + " - " + name + " - " + college);
    }
 
    public static void main(String args[]) {
        Student8 s1 = new Student8(111, "Thông");
        Student8 s2 = new Student8(222, "Minh");
 
        s1.display();
        s2.display();
    }
}
```
- Phương thức static:
    - Một phương thức static thuộc lớp chứ không phải đối tượng của lớp.
    - Một phương thức static gọi mà không cần tạo một instance của một lớp.
    - Phương thức static có thể truy cập biến static và có thể thay đổi giá trị của nó.
    - Phương thức static không thể sử dụng biến non-static hoặc gọi trực tiếp phương thức non-static.
    - Từ khóa this và super không thể được sử dụng trong ngữ cảnh static.
- Khối static:
    - Được sử dụng để khởi tạo thành viên dữ liệu static.
    -  Nó được thực thi trước phương thức main tại lúc tải lớp.
``` Java
public class A2 {
    static {
        System.out.println("Khối static: hello !");
    }
 
    public static void main(String args[]) {
        System.out.println("Main: hello !");
    }
}
```

## 6. Abstract Classes (Lớp trừu tượng).
- Một phương thức được khai báo là `abstract` và không có code thực thi thì đó là phương thức trừu tượng, (giống virtual trong CPP), được khai báo với từ khóa `abstract` ở trước.
``` Java
abstract void printStatus();
```
- Lớp `abstract` là lớp có các `abstract method`: 
``` Java
abstract class Bike{  
  abstract void run();  
}

class Honda4 extends Bike{  
    void run() {
        System.out.println("running safely..");
    }
 
    public static void main(String args[]) {  
        Bike obj = new Honda4();  
        obj.run();  
    }  
}  
```

- Lớp trừu tượng thường được dùng để kế thừa. Và lớp trừu tượng không thể tạo ra instance.

## 7. Interfaces.
- Là một bản thiết kế của một lớp. Nó chỉ có các phương thức trừu tượng. Interface là một kỹ thuật để thu được tính trừu tượng hoàn toàn và đa kế thừa trong Java. Nó không thể được khởi tạo giống như lớp trừu tượng.

- Cú pháp:
``` Java
interface InterfaceName {
    // Khai báo các thành phần bên trong interface
}
```
- Sử dụng từ khóa `implements`.
``` Java
public class Casio580 implements MayTinhBoTui {

}
```
- Ta có thể dùng `interface` để sử dụng đa kế thừa:

``` Java
interface Printable {  
    void print();  
}  
interface Showable{  
    void show();  
}  
class A7 implements Printable,Showable {  
   
    public void print() {
        System.out.println("Hello");
    }  
    public void show() {
        System.out.println("Welcome");
    }  
    public static void main(String args[]){  
        A7 obj = new A7();  
        obj.print();  
        obj.show();  
    }  
}  
```
- Một interface khác với một class ở một số điểm sau đây:
    - Bạn không thể khởi tạo một `interface`, cho nên một `interface` không chứa bất cứ hàm `Contructor` nào.
    - Tất cả các phương thức của `interface` đều là `abstract`.
    - Một `interface` không thể chứa một trường nào trừ các trường vừa `static` và `final`.
    - Một `interface` không thể kế thừa từ lớp, nó được triển khai bởi một lớp, nhưng một `interface` có thể kế thừa từ nhiều `interface` khác.

``` Java
// Kế thừa của interface
interface A {};
interface B extends A {};
```
