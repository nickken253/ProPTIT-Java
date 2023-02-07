# PROPTIT - JAVA - THEORY - #2
Câu hỏi kỳ này
- Tìm hiểu về Collection và Collections.
- Sự khác nhau giữa Collection và Collections.
- Tập trung tìm hiểu các Collection phổ biến sau: List, ArrayList, Map. Các Collection còn lại chỉ đọc qua các lưu trữ và cách thao tác.
- Phân biệt List và ArrayList. Lúc nào cần dùng List lúc nào dùng ArrayList
- Một số method thường dùng trong Collections (đặc biệt là sort).
# TABLE OF CONTENTS
1. [COLLECTION & COLLECTIONS](#i-collection--collections)
    * [Collection](#1-collection)
    * [Collections](#2-collections)
    * [Kết luận](#3-kết-luận)
2. [CÁC COLLECTION THƯỜNG GẶP](#ii-các-collection-thường-gặp)
    * [List](#1-list)
    * [ArrayList](#2-arraylist)
    * [Map](#3-map)
        - [Tổng quan](#a-tổng-quan)
        - [Map.Entry](#b-mapentry-interface)
    * [Phân biệt List và ArrayList](#4-phân-biệt-list-và-arraylist)
3. [MỘT SỐ METHOD CỦA COLLECTION THƯỜNG DÙNG](#iii-một-số-method-của-collection-thường-dùng)
         
# I. COLLECTION & COLLECTIONS
- Java Collection cung cấp nhiều interface (`Set`, `List`, `Queue`, `Deque`, etc.) và các lớp (`ArrayList`, `Vector`, `LinkedList`, `PriorityQueue`, `HashSet`, `LinkedHashSet`, `TreeSet`, ect.).
## 1. Collection
- Là một `root interface` trong hệ thống cấp bậc `Collection`. 
- Gói `java.util` chứa tất cả các lớp và interface của Collection.
- Collection là một interface, cung cấp các chức năng về cấu trức dữ liệu cho List, Set, Queue.
- Một số interface trong Collection:
    - `List`: Các phần tử trong List interface được sắp xếp có thứ tự và có thể có giá trị giống nhau.
    - `Map`: Lưu trữ các cặp key/value, key của các phần tử này là duy nhất.
    - `Set`: Các phần tử trong Set là duy nhất, không chứa các phần tử chùng lặp.
    - `SortedSet`: Là một dạng riêng của Set interface, trong đó các giá trị của các phần tử mặc định được sắp xếp tăng dần.
    - `SortedMap`: Là một dạng riêng của Map interface, trong đó key được sắp xếp theo thứ tự tăng dần.
- Một số method của Interface Collection. Các method này sẽ được các Interface con kế thừa lại:

| Phương thức	| Mô tả
| :---- | :---- |
| boolean `add(Object element)`	| Được sử dụng để chèn một phần tử vào collection.
| boolean `addAll(Collection c)`	| Được sử dụng để chèn các phần tử collection được chỉ định vào collection gọi phương thức này.
| boolean `remove(Object element)`	| Được sử dụng để xóa phần tử từ collection.
| boolean `removeAll(Collection c)`	| Được sử dụng để xóa tất cả các phần tử của collection được chỉ định từ collection gọi phương thức này.
| boolean `retainAll(Collection c)`	| Được sử dụng để xóa tất cả các thành phần từ collection gọi phương thức này ngoại trừ collection được chỉ định.
| int `size()`	| Trả lại tổng số các phần tử trong collection.
| void `clear()`	| Loại bỏ tổng số của phần tử khỏi collection.
| boolean `contains(Object element)`	| Được sử dụng để tìm kiếm phần tử.
| boolean `containsAll(Collection c)`	| Được sử dụng để tìm kiếm collection được chỉ định trong collection.
| Iterator `iterator()`	| Trả về một iterator.
| Object[] `toArray()`	| Chuyển đổi collection thành mảng (array).
| boolean `isEmpty()`	| Kiểm tra nếu collection trống.
| boolean `equals(Object element)`	| So sanh 2 collection.
| int `hashCode()`	| Trả về số hashcode của collection.
- Ngoài ra, ta còn có thể làm việc với Collection thông qua `Iterator Interface`.

| Phương thức	| Mô tả
| :---- | :---- |
| public boolean hasNext()	| Nó trả về true nếu iterator còn phần tử kế tiếp phần tử đang duyệt.
| public object next()	| Nó trả về phần tử hiện tại và di chuyển con trỏ trỏ tới phần tử tiếp theo.
| public void remove()	| Nó loại bỏ phần tử cuối được trả về bởi Iterator. Nó hiếm khi được sử dụng.
## 2. Collections
- Collections là một lớp. Nhưng lớp Collections là để sắp xếp và đồng bộ các phần tử Collection.
- Một số loại trong Collection:
    - `ArrayList`: Là kiểu danh sách sử dụng cấu trúc mảng để lưu trữ phần tử. Thứ tự các phần tử dựa theo thứ tự lúc thêm vào và giá trị của các phần tử này có thể trùng nhau.
    - `AbstractCollection`: Triển khai hầu hết collection interface.
    - `AbstractList`: kế thừa từ AbstractCollection và implements hầu hết List interface.
    - `AbstractSequentialList`: Extends AbstractList, được sử dụng để triển khai một list không thể sửa đổi, truy cập tuần tự.
    - `LinkedList`: Là 1 cấu trúc dữ liệu lưu trữ các phần tử dưới dạng danh sách. Các phần tử trong `LinkedList` được sắp xếp có thứ tự và có thể có giá trị giống nhau.
    - `AbstractSet`: extends AbstractCollection và implements hầu hết Set interface.
    - `HashSet`: Extends AbstractSet để sử dụng với bảng băm.
    - `AbstractSet`: Extends HashSet cho phép lặp lại thứ tự chèn.
    - `TreeSet`: Implements một tập hợp được lưu trữ bởi tree. Extends AbstractSet.
    - `AbstractMap`: Implements hầu hết Map interfaces.
    - `HashMap`: Extends AbstractMap để sử dụng bảng băm.
    - `TreeMap`: Extends AbstractMap để sử dụng tree.
    - `WeakHashMap`: Extends AbstractMap để sử dụng bảng băm với các khóa yếu.
    - `LinkedHashMap`: Extends HashMap, cho phép lặp lại thứ tự chèn.
    - `IdentityHashMap`: Extends AbstractMap.
- Collections chỉ chứa static method. Một số method của collections:

| Phương thức	| Mô tả
| :---- | :---- |
| void `sort()` | sắp xếp collections
| `min()`, `max()`| trả về phần tử nhỏ nhất /lớn nhất trong Collection
| int `binarySearch()`| tìm kiếm nhị phân một giá trị
| void `reverse()`| đảo ngược collections
| void `copy()`| Sao chép tất cả các phần tử từ một danh sách này sang một danh sách khác.
| int `frequency()`	| Trả về số lượng các phần tử có trong bộ sưu tập được chỉ định bằng đối tượng được chỉ định.
| int `indexOfSubList()` | Trả về vị trí bắt đầu của lần xuất hiện đầu tiên của danh sách mục tiêu được chỉ định trong danh sách nguồn quy định, hoặc -1 nếu không tìm thấy đối tượng chỉ định.
> Xem thêm tại [Tìm hiểu về Collection's Method](https://gpcoder.com/2783-lop-collections-trong-java-collections-utility-class/).
## 3. Kết luận
- `Collection` là một interface, trong khi `Collections` là một lớp. Collecion interface cung cấp các chức năng về cấu trức dữ liệu cho List, Set, Queue. Nhưng lớp `Collections` là để sắp xếp và đồng bộ các phần tử `Collection`.

![Ảnh](https://viettuts.vn/images/java/java-collection/he-thong-cap-bac-colection-trong-java.png)

# II. CÁC COLLECTION THƯỜNG GẶP
- Có một số collection sau: `List`, `ArrayList`, `Map`.
## 1. List
- Là một `Interface`. Các phần tử trong `List` được sắp xếp có thứ tự và có thể có giá trị giống nhau. Nó chứa các phương thức để chèn và xóa các phần tử dựa trên chỉ số index.
- Định nghĩa các phương thức để tương tác với list cũng như các phần tử bên trong list. Tương tự như Set Interface, List Interface cũng được kế thừa và có đầy đủ các phương thức của Collection Interface.
- Một số class thực thi List Interface thường sử dụng:

    - `ArrayList`: là 1 class dạng list được implement dựa trên mảng có kích thước thay đổi được.
    - `LinkedList`: là một class dạng list hoạt động trên cơ sở của cấu trúc dữ liệu danh sách liên kết đôi (double-linked list)
    - `Vector`: là 1 class thực thi giao diện List Interface, có cách thực lưu trữ như mảng tuy nhiên có kích thước thay đổi được, khá là tương tự với ArrayList, tuy nhiên điểm khác biệt là Vector là synchronized, hay là đồng bộ, có thể hoạt động đa luồng mà không cần gọi synchronize một cách tường minh. Cho nên, nó chậm hơn ArrayList.
    - `Stack`: cũng là 1 class dạng list, Stack có cách hoạt động dựa trên cơ sở của cấu trúc dữ liệu ngăn xếp (stack) với kiểu vào ra LIFO (last-in-first-out hay vào sau ra trước) nổi tiếng.
- Khi khởi tạo một List chúng ta có thể gán nó bằng ArrayList, LinkedList, Stack hay Vector.
- Lưu ý: chúng ta cần sử dụng kiểu dữ liệu đối tượng.
- Khai báo:
``` Java
List<Integer> listName = new ArrayList<Integer>();
List<String> listName = new Stack<String>();
```
- Các method của List thường dùng:

| Phương thức	| Mô tả
| :---- | :---- |
| void `add(int index, Object element)`	| Nó được sử dụng để chèn các phần tử vào list tại chỉ số index.
| boolean `addAll(int index, Collection c)`	| Nó được sử dụng để chèn tất cả các yếu tố của c vào danh sách tại chỉ số index.
| object `get(int index)`	| Nó được sử dụng để trả về đối tượng được lưu trữ tại chỉ số index trong list.
| object `set(int index, Object element)`	| Nó được sử dụng để gán phần tử cho vị trí được chỉ định index trong list.
| object `remove(int index)`	| Nó được sử dụng để xóa các phần tử tại vị trí có chỉ số index và trả về phần tử đã xóa.
| ListIterator `listIterator()`	| Nó được sử dụng để trả về một Iterator mà bắt đầu từ phần tử đầu tiên của list.
| ListIterator `listIterator(int index)`	| Nó được sử dụng để trả về một Iterator mà phần tử bắt đầu từ chỉ số index chỉ định.
## 2. ArrayList
- Lớp `ArrayList` trong java là một lớp kế thừa lớp `AbstractList` và triển khai của `List Interface` trong Collections Framework nên nó sẽ có một vài đặc điểm và phương thức tương đồng với List. ArrayList được sử dụng như một mảng động để lưu trữ các phần tử.
- Lớp `ArrayList` cho phép truy cập ngẫu nhiên vì nó lưu dữ liệu theo chỉ mục.
- Khai báo:
``` Java
ArrayList<String> list = new ArrayList<String>();
```

- Khởi tạo:
``` Java
ArrayList();
ArrayList(Collection c); // Khởi tạo theo phần tử của Collection c
ArrayList(int capacity); // Khởi tạo số lượng phần tử
```
- Các method của ArrayList thường dùng:

| Phương thức	| Mô tả
| :---- | :---- |
| boolean `add(Object o)`	| Nó được sử dụng để nối thêm phần tử được chỉ định vào cuối một danh sách.
| void `add(int index, Object element)`	| Nó được sử dụng để chèn phần tử element tại vị trí index vào danh sách.
| boolean `addAll(Collection c)`	| Nó được sử dụng để nối tất cả các phần tử trong collection c vào cuối của danh sách, theo thứ tự chúng được trả về bởi bộ lặp iterator.
| boolean `addAll(int index, Collection c)`	| Nó được sử dụng để chèn tất cả các phần tử trong collection c vào danh sách, bắt đầu từ vị trí index.
| void `retainAll(Collection c)`	| Nó được sử dụng để xóa những phần tử không thuộc collection c ra khỏi danh sách.
| void `removeAll(Collection c)`	| Nó được sử dụng để xóa những phần tử thuộc collection c ra khỏi danh sách.
| int `indexOf(Object o)`	| Nó được sử dụng để trả về chỉ mục trong danh sách với sự xuất hiện đầu tiên của phần tử được chỉ định, hoặc -1 nếu danh sách không chứa phần tử này.
| int `lastIndexOf(Object o)`	| Nó được sử dụng để trả về chỉ mục trong danh sách với sự xuất hiện cuối cùng của phần tử được chỉ định, hoặc -1 nếu danh sách không chứa phần tử này.
| Object[] `toArray()`	| Nó được sử dụng để trả về một mảng chứa tất cả các phần tử trong danh sách này theo đúng thứ tự.
| Object[] `toArray(Object[] a)`	| Nó được sử dụng để trả về một mảng chứa tất cả các phần tử trong danh sách này theo đúng thứ tự.
| Object `clone()`	| Nó được sử dụng để trả về một bản sao của ArrayList.
| void `clear()`	| Nó được sử dụng để xóa tất cả các phần tử từ danh sách này.
| void `trimToSize()`	| Nó được sử dụng để cắt dung lượng của thể hiện ArrayList này là kích thước danh sách hiện tại.
| boolean `contains(element)`	| Kết quả trả về là true nếu tìm thấy element trong danh sách, ngược lại trả về false.

- Như tìm hiểu bên trên, ta thấy `ArrayList` và `Vector` gần giống nhau. Tuy nhiên, ta có thể so sánh một vài sự khác biệt như sau:

| ArrayList	| Vector
| :---- | :---- |
| ArrayList là non-synchronized.	| Vector là synchronized.
| ArrayList là nhanh hơn vì nó là non-synchronized.	| Vector là chậm hơn ví nó là synchronized. Tức là, trong môi trường đa luồng, các thread giữ nó ở trong trạng thái runnable hoặc non-runnable cho đến khi thread hiện tại giải phóng đối tượng đó.
| ArrayList được duyệt bởi Iterator.	| Vector được duyệt bởi Enumeration và Iterator.
## 3. Map
### a. Tổng quan
- Giống như trong CPP, trong java, map được sử dụng để lưu trữ và truy xuất dữ liệu theo cặp key và value. Mỗi cặp key và value được gọi là mục nhập (entry). Map trong java chỉ chứa các giá trị key duy nhất. Map rất hữu ích nếu bạn phải tìm kiếm, cập nhật hoặc xóa các phần tử trên dựa vào các key.
- Các method của Map thường dùng:

| Phương thức	| Mô tả
| :---- | :---- |
| Object `put(Object key, Object value)`	| Nó được sử dụng để chèn một mục nhập trong map hiện tại.
| void `putAll(Map map)`	| Nó được sử dụng để chèn map chỉ định vào map hiện tại.
| Object `remove(Object key)`	| Nó được sử dụng để xóa một mục nhập của key được chỉ định.
| Object `get(Object key)`	| Nó được sử dụng để trả lại giá trị cho khoá được chỉ định.
| boolean `containsKey(Object key)`	| Nó được sử dụng để tìm kiếm key được chỉ định từ map hiện tại.
| Set `keySet()`	| Nó được sử dụng để trả đối tượng Set có chứa tất cả các keys.
| Set `entrySet()`	| Nó được sử dụng để trả lại đối tượng Set có chứa tất cả các keys và values.
### b. Map.Entry Interface
- Entry là một interface con của Map. Vì vậy, chúng ta được truy cập nó bằng tên Map.Entry. Nó cung cấp các phương pháp để truy xuất các key và value.
- Các method của Map.Entry:

| Phương thức	| Mô tả
| :---- | :---- |
| Object `getKey()`	| Nó được dùng để lấy key.
| Object `getValue()`	| Nó được sử dụng để lấy value.
## 4. Phân biệt List và ArrayList
- Ta có bảng sau:

| List | ArrayList
| :----: | :----: |
| Interface | Class
| extends Collection | implements List
| Không thể khởi tạo bằng new List<>() | Có thể khởi tạo bằng new ArrayList<>()
| Dùng để ghi nhớ các index của Object trong List | Dùng để tạo mảng động lưu trức các Object
- Ta xét đến 2 cách khai báo như sau:
``` Java
List<Student> listOfStudents = new ArrayList<>(); // (1)

ArrayList<Student> listOfStudents = new ArrayList<>(); // (2)
```
- Về mặt lý thuyết khai báo như cách (1) hay cách (2) thì nó đều tạo một đối tượng mà ta khai báo sau toán tử new chỉ khác nhau là ở cái kiểu biến ta tham chiếu đến đối tượng đó.
- Khai báo theo cách (1) sẽ tận dụng được tính đa hình trong lập trình hướng đối tượng và làm cho chương trình của chúng ta linh hoạt hơn, dễ mở rộng hơn sau này.

# III. MỘT SỐ METHOD CỦA COLLECTION THƯỜNG DÙNG
## 1. Sort()
``` Java
ArrayList<String> al = new ArrayList<String>();
al.add("Peter");
al.add("John");
al.add("Marry");
al.add("Andrew");

// Sort sử dụng Collections
Collections.sort(al);
```

- Ngoài ra, để sắp xếp kiểu dữ liệu tự định nghĩa, ta sử dụng `Comparable interface`. Inetrface này chỉ chứa 1 method là `compareTo()`.

```Java
class Employee implements Comparable<Employee> { // Cần implement Interface
	int id;
	String name;
	int age;

	Employee(int id, String name, int age) {
		this.id = id;
		this.name = name;
		this.age = age;
	}

	public int compareTo(Employee employee) { // viết method so sánh
		if (age == employee.age)
			return 0;
		else if (age > employee.age)
			return 1;
		else
			return -1;
	}
}
```
``` Java
import java.util.*;

class TestSort3 {
	public static void main(String args[]) {
		ArrayList<Employee> al = new ArrayList<Employee>();
		al.add(new Employee(101, "Peter", 23));
		al.add(new Employee(106, "Marry", 29));
		al.add(new Employee(105, "John", 21));

		//Sắp xếp list employee
		Collections.sort(al);
		for (Employee st : al) {
			System.out.println(st.id + " " + st.name + " " + st.age);
		}
	}
}
```

- Ta còn có thể sử dụng `Comparator interface`. Inetrface này chứa method là `compare()` và `equals()`.

``` Java

class Employee {
	int id;
	String name;
	int age;

	Employee(int id, String name, int age) {
		this.id = id;
		this.name = name;
		this.age = age;
	}
}
```
``` Java
import java.util.*;

class AgeComparator implements Comparator<Employee> {
	public int compare(Employee s1, Employee s2) {
		if (s1.age == s2.age)
			return 0;
		else if (s1.age > s2.age)
			return 1;
		else
			return -1;
	}
}
```
``` Java
import java.util.*;

class NameComparator implements Comparator<Employee> {
	public int compare(Employee s1, Employee s2) {
		return s1.name.compareTo(s2.name);
	}
}
```
``` Java
import java.util.*;

class TestSort4 {
	public static void main(String args[]) {

		ArrayList<Employee> al = new ArrayList<Employee>();
		al.add(new Employee(101, "Peter", 23));
		al.add(new Employee(106, "Marry", 27));
		al.add(new Employee(105, "John", 21));

		System.out.println("Sorting by Name...");

		Collections.sort(al, new NameComparator());
		for (Employee st : al) {
			System.out.println(st.id + " " + st.name + " " + st.age);
		}

		System.out.println("sorting by age...");

		Collections.sort(al, new AgeComparator());
		for (Employee st : al) {
			System.out.println(st.id + " " + st.name + " " + st.age);
		}

	}
}
```

- Hoặc ta có thể viết ngắn gọn lại bằng:
``` Java

// Sử dụng Comparator - cmp: sắp xếp theo điều kiện tùy chọn
Comparator<Employee> cmpName = (t1, t2) -> t1.name.compareTo(t2.name);
Comparator<Employee> cmpAge = (t1, t2) -> {
    return (int) t1.age - t2.age;
}
al.sort(cmpName);
al.sort(cmpAge);

```

## 2. binarySearch
- Collections.binarySearch(tên list, giá trị cần tìm): Trả về chỉ số của phần tử trong mảng;
