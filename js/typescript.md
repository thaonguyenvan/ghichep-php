# Ghi chép cơ bản về typescript

## Mục lục

1. TypeScript là gì? TypeScript và Javascript
2. Cài đặt TypeScript
3. TypeScript Basic Types
4. Khai báo biến trong TypeScript
5. Lệnh If Else và Switch Case trong TypeScript
6. Vòng lặp trong TypeScript

## 1. TypeScript là gì? TypeScript và Javascript

### 1. TypeScript là gì?
TypeScript là một dự án mã nguồn mở được phát triển bởi Microsoft, nó có thể được coi là một phiên bản nâng cao của Javascript bởi việc bổ sung tùy chọn kiểu tĩnh và lớp hướng đối tượng mà điều này không có ở Javascript. TypeScript có thể sử dụng để phát triển các ứng dụng chạy ở client-side (Angular2) và server-side (NodeJS).

### 2. Tại sao nên sử dụng TypeScript

Để hiểu tại sao nên sử dụng TypeScript thì có lẽ chúng ta nên tìm hiểu sơ lược về các ưu điểm mà TypeScritpt mang lại.

- Dễ phát triển dự án lớn: Với việc sử dụng các kỹ thuật mới nhất và lập trình hướng đối tượng nên TypeScript giúp chúng ta phát triển các dự án lớn một cách dễ dàng.

- Nhiều Framework lựa chọn: Hiện nay các Javascript Framework đã dần khuyến khích nên sử dụng TypeScript để phát triển, ví dụ như AngularJS 2.0 và Ionic 2.0.

- Hô trợ các tính năng của Javascript phiên bản mới nhất: TypeScript luôn đảm bảo việc sử dụng đầy đủ các kỹ thuật mới nhất của Javascript, ví dụ như version hiện tại là ECMAScript 2015 (ES6).

- Là mã nguồn mở: TypeScript là một mã nguồn mở nên bạn hoàn toàn có thể sử dụng mà không mất phí, bên cạnh đó còn được cộng đồng hỗ trợ.

- TypeScript là Javscript: Bản chất của TypeScript là biên dịch tạo ra các đoạn mã javascript nên ban có thê chạy bất kì ở đâu miễn ở đó có hỗ trợ biên dịch Javascript. Ngoài ra bạn có thể sử dụng trộn lẫn cú pháp của Javascript vào bên trong TypeScript, điều này giúp các lập trình viên tiếp cận TypeScript dễ dàng hơn.

### 3. TypeScript và Javascript

Như vậy ta có thể coi TypeScript là cha của Javascript bởi kết quả sau khi biên dịch TypeScript là xuất ra các đoạn mã Javascript

Code TypeScript

``` ts
class Customer {
    Name : string;
    constructor (firstName: string, lastName: string)
    {
            this.Name = firstName + "  " + lastName;
    }
    GetName()
    {
            return "Hello, " + this.Name;
    }
}
```

Biên dịch thành Javascript

``` js
var Customer = (function () {
    function Customer(firstName, lastName) {
        this.Name = firstName + "  " + lastName;
    }
    Customer.prototype.GetName = function () {
        return "Hello, " + this.Name;
    };
    return Customer;
}());
```

## 2. Cài đặt TypeScript

Updating ...

## 3. TypeScript Basic Types

### 1. Khai báo biến trong TypeScript

Cũng như Javascript chúng ta có thể sử dụng từ khóa var hoặc let để khai báo biến, riêng từ khóa let thường được sư dụng trong ES6 nên nó chỉ chạy ở các trình duyệt phiên bản mới.

``` js
var domain = 'freetuts.net';
let email = 'thehalfheart@gmail.com';
```

Nếu ta muốn xác định kiểu dữ liệu cho biến thì sử dụng cú pháp sau:

`var domain : string = 'freetuts.net';`

Kết quả Javascript :

`var domain = 'freetuts.net';`

### 2. Các kiểu dữ liệu trong TypeScript

**Kiểu Boolean**

Kiểu boolean có hai giá trị là true hoặc false và cả Javascript lẫn TypeScript đều gọi là boolean

TypeScript:

`let isDone: boolean = false;`

Kết quả Javascript:

`var isDone = false;`

**Kiểu Number**

Cũng tương tự như trong Javascript thì trong TypeScript chỉ tồn tại một kiểu Number, còn việc phân chia các kiểu nhỏ hơn như số nguyên, só thực sẽ phụ thuộc vào giá trị mà bạn gán cho nó.

TypeScript:
```js
var decimal: number = 12;
var hex: number = 0xf00d;
var binary: number = 0b1010;
var octal: number = 0o744;
```

Kết quả Javascript:

```js
var decimal = 12;
var hex = 0xf00d;
var binary = 10;
var octal = 484;
```

**Kiểu String**

Kiểu string đơn giản là một chuỗi (một đoạn text) được bao bọc bởi cặp ký tự ' hoặc ".

TypeScript:

`let username: string = 'thehalfheart';`

Kết quả Javascript:

`var username = 'thehalfheart';`

**Kiểu array**

Để khai báo kiểu Array trong TypeScript thì chúng ta có hai cách, cách thứ nhất chúng ta sử dụng cặp dấu [] đặt ở đằng sau kiểu dữ liệu.

`let students: string[] = ['Cuong', 'Kinh', 'Chinh'];`

Cách thứ hai chúng ta sử dụng từ khóa Array<type> để khai báo.

`let students: Array<string> = ['Cuong', 'Kinh', 'Chinh'];`

**Kiểu Tuple**

Tuple là kiểu dữ liệu đặc biệt có thể chứa nhiều giá trị với nhiều kiểu dữ liệu con khác nhau. Thực ra Tuple là một mảng nhưng đã xác định được số phần tử và kiểu dữ liệu cho mỗi phần tử đó. Ví dụ mình khai báo biên student gồm hai thông tin đó là tên và tuổi thì lúc này tên sẽ là kiểu string còn tuổi sẽ là kiểu number.

TypeScript

`let student: [string, number] = ['Cuong', 27];`

Kết quả Javascript

`var student = ['Cuong', 27];`

**Kiểu Enum**

Tương tự như trong C#, Enum là kiểu dữ liệu đặc biệt dùng để tạo một nhóm tên tương ứng với các giá trị là những con số mà ta thiết lập cho nó, cách này sẽ giúp ta dễ dàng nhớ tên hơn.

TypeScript

```js
enum Fruits {Orange, Banana, Mango, Apple};  
let a: Fruits = Fruits.Orange;
alert(a);
```

Kết quả Javascript

```js
var Fruits;
(function (Fruits) {
    Fruits[Fruits["Orange"] = 0] = "Orange";
    Fruits[Fruits["Banana"] = 1] = "Banana";
    Fruits[Fruits["Mango"] = 2] = "Mango";
    Fruits[Fruits["Apple"] = 3] = "Apple";
})(Fruits || (Fruits = {}));
;
var a = Fruits.Orange;
alert(a);
```

Khi chạy chương trình này kết quả sẽ thông báo lên trình duyệt số 0 => như vậy nếu ta không thiết lập giá trị cho chúng thì nó sẽ tính theo thứ tự và bắt đầu bằng 0.

Bây giờ bạn đổi lại đoạn code TypeScript như sau:

```js
enum Fruits {Orange = 12, Banana, Mango, Apple};
let a: Fruits = Fruits.Orange;
alert(a);
```

Nhìn vào đoạn code biên dịch bạn dễ dàng đoán được số thứ tự sẽ bắt đầu từ 12.

**Kiểu any**

Đây là kiểu dữ liệu thoải mái nhất bởi nó cho phép bạn gán giá trị với kiểu dữ liệu bất kì, điều này giúp giải quyết rắc rối ở một số trường hợp, ví dụ ta cần lấy dữ liệu từ người dùng hoặc một thư viện khác thì ta không biết giá trị trả về sẽ ở kiểu dữ liệu nào nên ta sẽ sử dụng kiểu Any để tránh lỗi. Sau đây là một ví dụ từ trang chủ của nó.

```js
let notSure: any = 4; // kiểu number
notSure = "Thay thế bằng kiểu string";
notSure = false; // bây giờ lại là kiểu boolean
```

**Kiểu Void**

Trong C# thì khi muốn khai báo một hàm không có giá trị trả về thì ta sẽ sử dụng hàm void, tuy ta hay gọi là hàm void nhưng thực ra nó là một kiểu dữ liệu với giá trị là null, trong TypeScript thì có thêm giá trị undefined.

``` js
function showMessage(): void {
    alert("Success!");
}

let unusable: void = undefined;
```

**Kiểu Null và Undefined**

Cả hai kiểu này đều là giá trị của kiểu void, và cũng tương tự thì hai kiểu này rất ít sử dụng trong quá trình xây dựng dự án.

### 4. Khai báo biến trong TypeScript

#### 1. Khai báo biến với từ khoa var

#### 2. Khai báo biến với từ khóa let

Từ khóa let được giới thiệu ở phiên bản ECMAScript 6 (ES6). Khi sử dụng từ khóa let để khai báo biến thì biến đó chỉ hoạt động trong phạm vi khối của nó (block-scoped)

#### 3. Khai báo biến với từ khóa const

Sử dụng từ khóa const để khai báo một biến và biến đó sẽ không thể nào thay đổi giá trị lại, trong các ngôn ngữ lập trình khác thì đây cũng có thể hiểu là khai báo hằng. Khác với các ngôn ngữ khác là khi khai báo hằng thì thường ta chỉ gán được kiểu giá trị là kiểu chuỗi hoặc kiểu số, tuy nhiên trong Javascript nói chung và trong TypeScript nói riêng thì bạn có thể gán cho nó mọi kiểu dữ liệu.

Giống như let, phạm vi hoạt động của biến const cũng bị hạn chế bởi block-scorped.

### 5. Lệnh If Else và Switch Case

TypeScript kế thừa tất cả cú pháp của Javascript, vì vậy bạn có thể lồng JS vào TypeScript rất dễ dàng mà không sợ bị lỗi. Điều này cũng có nghĩa là cấu trúc của lệnh if else và switch case trong TypeScript giống hoàn toàn trong Javascript.

### 6. Vòng lặp

#### 1. Vòng lặp for in

Vòng lặp for in ta còn gọi là iterates, tức là sau mỗi lần lặp nó sẽ nhớ là đang lặp tới phần tử nào để lần lặp tiếp theo nó tự động lấy phần tử tiếp theo. Giá trị của mỗi lần lặp là index chứ không phải là value.

``` js
for (variable in object)   
{  
    //block to execute   
}
```

Ví dụ:

``` js
var obj = {a: 1, b: 2, c: 3};
for (var prop in obj) {
    this.val += prop + " = " + obj[prop] + "\n";
}
```

#### 2. Vòng lặp for of

Về bản chất vòng lặp for of giống vòng lặp for in, tuy nhiên điểm khác biệt duy nhất là vòng lặp for of sẽ trả về value chú không phải là index.

``` js
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
var s = "";
var o = 0;
for (let num in numbers) {
    s = s + "\n Array Value is - " + num;
}
alert(s);
```
