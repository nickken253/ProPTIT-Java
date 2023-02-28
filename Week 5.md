# PROPTIT - JAVA - THEORY - #5
Câu hỏi kỳ này:
- JFrame.
- JTextField.
- JButton.
- JPanel.
- JMenu.
- JLabel.
- JComboBox.
# TABLE OF CONTENTS
- [JAVA SWING LÀ GÌ ? NÓ ĐƯỢC SỬ DỤNG LÀM GÌ ?](#i-java-swing-là-gì--nó-được-sử-dụng-làm-gì)
    - [Khái niệm chung](#1-khái-niệm-chung)
    - [Ứng dụng của Java Swing](#2-ứng-dụng-của-java-swing)
- [SỰ KHÁC NHAU GIỮA AWT VÀ SWING](#ii-sự-khác-nhau-giữa-awt-và-swing)
- [HỆ THỐNG PHÂN CẤP CÁC LỚP TRONG JAVA SWING](#iii-hệ-thống-phân-cấp-các-lớp-trong-java-swing)
- [CÁC PHƯƠNG THỨC HAY DÙNG Ở COMPONENT CLASS](#iv-các-phương-thức-hay-dùng-ở-component-class)
- [SỬ DỤNG SWING CƠ BẢN](#v-sử-dụng-swing-cơ-bản)
    - [JButton Class](#1-jbutton-class)
    - [JTextField Class](#2-jtextfield-class)
    - [JScrollBar Class](#3-jscrollbar-class)
    - [JPanel Class](#4-jpanel-class)
    - [JMenu Class](#5-jmenu-class)
    - [JList Class](#6-jlist-class)
    - [JLabel Class](#7-jlabel-class)
    - [JComboBox Class](#8-jcombobox-class)

# I. JAVA SWING LÀ GÌ ? NÓ ĐƯỢC SỬ DỤNG LÀM GÌ ?
## 1. Khái niệm chung
- Swing trong Java  là một bộ công cụ Giao diện Người dùng Đồ họa (GUI) bao gồm các thành phần GUI. Swing cung cấp một bộ widget và gói phong phú để tạo ra các thành phần GUI tinh vi cho các ứng dụng Java. Swing là một phần của Java Foundation Classes (JFC), là một API để lập trình Java GUI cung cấp GUI.
- Thư viện Java Swing được xây dựng dựa trên Bộ công cụ tiện ích con trừu tượng Java ( AWT ), một bộ công cụ GUI phụ thuộc vào nền tảng cũ hơn. Bạn có thể sử dụng các thành phần lập trình GUI đơn giản của Java như nút, hộp văn bản, v.v., từ thư viện và không phải tạo các thành phần từ đầu. Tuy nhiên, nó lại khác với AWT ở chỗ bộ công cụ này thuộc loại nền tảng độc lập, bao gồm các thành phần nhẹ và phức tạp hơn AWT.
- Gói javax.swing cung cấp các lớp cho java swing API như JButton, JTextField, JTextArea, JRadioButton, JCheckbox, JMenu, JColorChooser, etc..
## 2. Ứng dụng của Java Swing
- Java Swing được dùng để hỗ trợ tạo giao diện đồ hoạ người dùng (với Java).
- Bộ công cụ này cung cấp các bộ điều khiển nâng cao như thanh trượt, colorpicker, Tree, TabbedPane và bảng điều khiển,..
- Swing có những đặc điểm:
    - Độc lập với thiết bị.
    - Có thể tuỳ chỉnh, mở rộng.
    - Khá nhẹ.
    - Có thể cấu hình.
# II. SỰ KHÁC NHAU GIỮA AWT VÀ SWING

| No   | Java AWT | Java Swing
|:----:|:----:|:----:|
| 1	| Phụ thuộc nền tảng (Platform Dependent)	| Độc lập với nền tảng (Platform Independent)|
| 2	| Thành phần của AWT nặng	| Thành phần của Swing khá nhẹ|
| 3|	AWT không hỗ trợ pluggable look and feel.	|Swing hỗ trợ pluggable look and feel.|
| 4|	AWT có ít thành phần hơn Swing	|Swing cung cấp nhiều thành phần và các thành phần cũng mạnh mẽ hơn AWT như: bảng, danh sách, cuộn màn hình, trình chọn màu,..|
| 5|	AWT không tuân theo cấu trúc MVC (Model View Controller)	|Swing theo cấu trúc MVC|
# III. HỆ THỐNG PHÂN CẤP CÁC LỚP TRONG JAVA SWING
![Ảnh](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/java-swing-la-gi.jpg)
> Chú thích: Tất cả các thành phần trong swing được kế thừa từ lớp Jcomponent như JButton, JComboBox, JList, JLabel đều có thể được thêm vào lớp Container.
>
> Container là các window như Frame và Dialog. Các container này chỉ có thể thêm một thành phần vào chính nó.
# IV. CÁC PHƯƠNG THỨC HAY DÙNG Ở COMPONENT CLASS
| Phương thức	| Mục đích| 
| :----|:-----|
| public void add(Component c)	| Bổ sung một thành phần trên một phần khác
| public void setSize(int width,int height)	| Để cài đặt và tùy chỉnh kích cỡ của thành phần (chiều rộng, chiều cao)
| public void setLayout(LayoutManager m)	| Để cài đặt Layout Manager cho thành phần
| public void setVisible(boolean b)	| Để cài đặt tính nhìn thấy được (visible) của thành phần. Theo mặc định là false.
# V. SỬ DỤNG SWING CƠ BẢN
- Một số ví dụ đơn giản để tạo GUI bằng Swing trong Java:
## 1. JButton Class
- Nó được dùng để tạo ra một nút (button) có tên.
- Việc sử dụng ActionListener sẽ dẫn đến một số hành động khi nút được nhấn.
- Nó kế thừa lớp AbstractButton và độc lập với nền tảng.
``` Java
import javax.swing.*;
public class Main {
    public static void main(String args[]) {
        JFrame a = new JFrame("example");
        JButton b = new JButton("click me");
        b.setBounds(40,90,85,20);
        a.add(b);
        a.setSize(300,300);
        a.setLayout(null);
        a.setVisible(true);
    }
}
```
> Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/lap-trinh-java-swing.jpg)
## 2. JTextField Class
- Nó kế thừa lớp JTextComponent và dùng để cho phép chỉnh sửa dòng đơn.
``` Java
import javax.swing.*;
public class Main {
    public static void main(String args[]) {
        JFrame a = new JFrame("example");
        JTextField b = new JTextField("edureka");
        b.setBounds(40,90,85,20);
        a.add(b);
        a.setSize(300,300);
        a.setLayout(null);
        a.setVisible(true);
    }
}
```
> Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/swing-trong-java.jpg)
## 3. JScrollBar Class
- Dùng để thêm thanh cuộn
``` Java
import javax.swing.*;
public class Main {
    public static void main(String args[]) {
        JFrame a = new JFrame("example");
        JScrollBar b = new JScrollBar();
        b.setBounds(40,90,85,250);
        a.add(b);
        a.setSize(300,300);
        a.setLayout(null);
        a.setVisible(true);
    }
}
```
> Kết quả

![a](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/java-swing-co-ban.jpg)
## 4. JPanel Class
- Kế thừa lớp JComponent, cung cấp không gian cho một ứng dụng (có thể đính kèm bất kỳ thành phần nào khác).
``` Java
import javax.swing.*;
public class Main{
    Main(){
        JFrame a = new JFrame("example");
        JPanel p = new JPanel();
        p.setBounds(40,70,200,200);
        JButton b = new JButton("click me");
        b.setBounds(60,50,80,40);
        p.add(b);
        a.add(p);
        a.setSize(400,400);
        a.setLayout(null);
        a.setVisible(true);
    }
    public static void main(String args[])
    {
        new Main();
    }
}
```
> Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/swing-java.jpg)
## 5. JMenu Class
- Kế thừa lớp JMenuItem, là một thành phần menu kéo xuống (hiển thị từ thanh menu).
``` Java
import javax.swing.*;
public class Main{
    JMenu menu;
    JMenuItem a1,a2;
    Main(){
        JFrame a = new JFrame("Example");
        menu = new JMenu("options");
        JMenuBar m1 = new JMenuBar();
        a1 = new JMenuItem("example");
        a2 = new JMenuItem("example1");
        menu.add(a1);
        menu.add(a2);
        m1.add(menu);
        a.setJMenuBar(m1);
        a.setSize(400,400);
        a.setLayout(null);
        a.setVisible(true);
    }
    public static void main(String args[])
    {
        new Main();
    }

}
```
>Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/swing-java-la-gi.jpg)
## 6. JList Class
- Kế thừa lớp JComponent, đối tượng của lớp Jlist đại diện cho danh sách các mục văn bản.
``` Java
import javax.swing.*;
public class Main{
    Main(){
        JFrame a = new JFrame("example");
        DefaultListModel<String> l = new DefaultListModel< >();
        l.addElement("first item");
        l.addElement("second item");
        JList<String> b = new JList< >(l);
        b.setBounds(100,100,75,75);
        a.add(b);
        a.setSize(400,400);
        a.setVisible(true);
        a.setLayout(null);
    }
    public static void main(String args[])
    {
        new Main();
    }

}
```
![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/code-swing.jpg)
## 7. JLabel Class
- Được dùng để đặt văn bản trong vùng chứa, lớp JLabel cũng kế thừa lớp JComponent.
``` Java
import javax.swing.*;
public class Main{
    Main(){
        JFrame a = new JFrame("example");
        JLabel b1;
        b1 = new JLabel("edureka");
        b1.setBounds(40,40,90,20);
        a.add(b1);
        a.setSize(400,400);
        a.setLayout(null);
        a.setVisible(true);
    }
    public static void main(String args[])
    {
        new Main();
    }
}
```
> Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/swing-code.jpg)
## 8. JComboBox Class
- Kế thừa lớp JComponent, dùng để hiển thị menu lựa chọn bật lên.
``` Java
import javax.swing.*;
public class Main{
    JFrame a;
    Main(){
        a = new JFrame("example");
        String courses[] = { "core java","advance java", "java servlet"};
        JComboBox c = new JComboBox(courses);
        c.setBounds(40,40,90,20);
        a.add(c);
        a.setSize(400,400);
        a.setLayout(null);
        a.setVisible(true);
    }
    public static void main(String args[])
    {
        new Main();
    }
}
```
> Kết quả

![A](https://ironhackvietnam.edu.vn/wp-content/uploads/2021/03/java-swing-code.jpg)