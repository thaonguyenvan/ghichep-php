# Ghi chép JS cơ bản

### Khai báo biến

- Tên biến bắt đầu bằng chữ và dấu gạch dưới

```
// Đúng
var username;

// Đúng
var _username;

// Đúng
var __username;

// Đúng
var username90;

// SAI
var 90thehalfheart;
```

- In giá trị của biến ra trình duyệt sử dụng `document.write();`

```
<html>
    <head>
        <title></title>
    </head>
    <body>
        <script language="javascript">
            var website = 'hanu.vn';
            document.write(website);
        </script>
    </body>
</html>
```


### Hàm alert() - confirm() - prompt()

- Hàm alert() trong javascript
Hàm alert() có nhiệm vụ in một thông báo popup, nó có một tham số truyền vào và tham số này chính là nội dung ta muốn thông báo với người dùng.

```
<html>
  <head>
  </head>
  <body>
    <input type="button" onclick="alert('Xin chào các bạn')" value="Click Me"/>
  </body>
</html>
```

- Hàm confirm() cũng sẽ xuất hiện một thông báo popup nhưng nó có thêm hai sự lựa chọn là Yes và No, nếu người dùng chọn Yes thì nó trả về TRUE và ngược lại nếu chọn NO thì nó sẽ trả về FALSE. Nó cũng có một tham số truyền vào và tham số này chính là nội dung thông báo.

```
<html>
    <head>
        <title></title>
        <script language="javascript">
            confirm("Hello");
        </script>
    </head>
    <body>

    </body>
</html>
```

- Hàm prompt() trong javascript
Hàm prompt() dùng  để lấy thông tin từ người dùng, gồm có hai tham số truyền vào là nội dung thông báo và giá trị ban đầu. Nếu người dùng không nhập vào thì giá trị nó sẽ trả về là NULL

```
<html>
    <head>
        <title></title>
        <script language="javascript">
            var t = prompt("Nhập tên của bạn", '');
            alert(t);
        </script>
    </head>
    <body>

    </body>
</html>
```

### Lệnh kiểm tra điều kiện if else

- Cú pháp lênh if

``` js
if (condition){
    // statment
}
```

- Trong đó condition là mệnh đề điều kiện và luôn luôn phải có một trong hai giá trị là true/false hoặc giá trị tương đương như:

    - NULL => False
    - Rỗng => False
    - Số khác 0 => TRUE
    - Số 0 => FALSE

- Kết hợp nhiều lệnh if else

``` js
if (condition1){
    // Code cho lệnh if 1
}
else if (condition2){
    // Code cho lệnh if 2
}
else{
    // Code cho lệnh else
}
```

### Lệnh switch case

- Cú pháp

``` js
switch (variable)
{
    case value_1 : {
        // do some thing
        break;
    }
    case value_2 : {
        // do some thing
        break;
    }
    default : {
        // do something
    }
}
```

### Hàm và tạo hàm (function)

- Cú pháp

```
function name_of_function(var1, var2, var3, ...)
{
    // Some code
}
```

### Biến toàn cục và biến cục bộ

- Một biến được gọi là cục bộ khi bạn khai báo nó nằm bên trong một hàm cụ thể nào đó, lúc này biến đó sẽ không sử dụng được ở bên ngoài hàm.

- Biến toàn cục là biến mà bạn khai báo bên ngoài và không nằm bên trong một hàm cụ thể nào cả.

- Nếu trong hàm có sử dụng từ khóa var và để tạo một biến và tên của biến đó đã tồn tại ở bên ngoài (toàn cục) thì lúc này bên trong hàm sẽ hiểu là đang sử dụng biến cục bộ nên không ảnh hưởng gì biến bên ngoài cả.

- Nếu bạn không sử dụng từ khóa var để tạo tên biến trong hàm thì nó sẽ sử dụng biến toàn cục nên mọi thay đổi giá trị của biến đó trong hàm sẽ bị ảnh hưởng ra ngoài hàm.

### Lệnh console.log

Lệnh `console.log()` có cú pháp `console.log(value)`, trong đó `value` là biến hoặc giá trị mà bạn muốn in ra.

Thường được dùng để debug, ví dụ show kết quả trả về từ ajax.

### setTimeout() và setInterval()

Hàm setTimeout() dùng để thiết lập một khoảng thời gian nào đó sẽ thực hiện một nhiệm vụ nào đó và nó chỉ thực hiện đúng một lần.

``` js
setTimeout(function, time)
```

Trong đó:

- function: là nội dung cần thực hiện, đây là một hàm
- time: là khoảng thời gian bao nhiêu (tính bằng mili giây) thì function đó sẽ thực hiện

- Ví dụ: Sau 3 giây thì xuất hiện câu chào lên màn hình

``` js
setTimeout(function(){
    alert("Chào mừng bạn đến với blog của tôi");
}, 3000);
```

Giả sử bạn xây dựng chức năng sau 3 giây thì sẽ xuất hiện thông báo, tuy nhiên sau 2 giây chương trình muốn hủy bỏ thì phải làm thế nào? Lúc này bạn phải sử dụng hàm `clearTimeout()`.

Tham số truyền vào hàm `clearTimeout()` là đối tượng `setTimeout()` nên lúc này ban phải đặt hàm `setTimeout()` vào một biến cụ thể.

``` js
// hành động
var action = setTimeout(function(){
    // something
}, 3000);

// hủy hành động
clearTimeout(action);
```

- Hàm `setInterval()` có cú pháp và chức năng giống như hàm setTimeout(), tuy nhiên với hàm `setInterval()` thì số lần thực hiện lã mãi mãi.

- Tương tự như hàm `clearTimeout()`, hàm `clearInterval()` sẽ xóa đi nhiệm vụ mà ta đã thiết lập trong hàm `setInterval()`, và ta cũng phải đặt `setInterval()` trong một biến thì mới clear được.

### Vòng lặp for

``` js
var i = 0;
for (i = 0; i < 100; i++){
    // Dòng lệnh xử lý vòng lặp
}
```

- var i = 0; là khai báo biến điều khiển vòng lặp i
- (i = 0) là điểm bắt đầu lặp (lặp từ 0)
- (i < 100) là điều kiện dừng vòng lặp, nghĩa là lặp nếu i < 100. Bạn có thể dùng một điều kiện bất kì thông qua các toán tử  miễn là nó trả về true hoặc false như (i <= 100, i == 100)
- (i++) là tăng bước nhảy, bạn có thể dùng công thức khác như i+=2, i-=2, i--, ...

### Vòng lặp while - do while

- Vòng lặp while

``` js
while (condition){
    // do something
}
```

Trong đó condition là điều kiện dừng vòng lặp, nếu condition đúng thì vòng lặp sẽ được thực thi cho tới khi condition có giá trị sai. Chính vì vậy nếu condition luôn luôn đúng thì vòng lặp sẽ dẫn tới lặp vô hạn.

- Vòng lặp do while

vòng lặp do while sẽ thực hiện đoạn code bên trong lệnh do mới kiểm tra điều kiện. Ví dụ khi bạn chơi trò chơi bốc thăm, lần đầu tiên bạn sẽ bốc nếu cây thăm may mắn thì bốc tiếp và ai được nhiều cây thăm may mắn thì thắng, như vậy có nghĩa là bạn sẽ được bốc 1 lần rồi mới kiểm tra điều kiện cho lần bốc kế tiếp. Từ đó suy ra trong vòng lặp do while sẽ luôn luôn thực thi lặp ít nhất 1 lần.

``` js
do {
    // some thing
}
while (condition);
```

### Lệnh break - continue

- Lệnh break có tác dụng dừng vòng lặp cho dù điều kiện của vòng lặp vẫn đang đúng, hay nói cách khác là nó thoát khỏi vòng lặp một cách đột xuất và không quan tâm đến điều kiện lặp.

``` js
for (var i = 1; i <= 10; i++)
{
    document.write(i + " - ");
    if (i == 5) {
        document.write("Vòng lặp bị dừng");
        break;
    }
}
```

- Khác hoàn toàn với lệnh break, lệnh continue trong javascript có tác dụng bỏ qua một bước lặp nào đó, nghĩa là lúc gặp lệnh continue thì tất cả những đoạn code nằm bên dưới sẽ không được thực hiện mà nó sẽ nhảy qua vòng lặp mới luôn.

Ví dụ bỏ qua giá trị 5

``` js
for (var i = 1; i <= 10; i++)
{
  if (i == 5) {
      continue;
  }
  document.write(i + " - ");
}
```

### Sự kiện trong js


Bảng các sự kiện thông dụng trong javascript.

| STT | Event | Mô tả |
|-----|-------|-------|
|1|onclick|Xảy ra khi click vào thẻ HTML|
|2|ondbclick|Xảy ra khi double click vào thẻ HTML|
|3|onchange|Xảy ra khi giá trị (value) của thẻ HTML đổi. Thường dùng trong các đối thẻ form input|
|4|onmouseover|Xảy ra khi con trỏ chuột bắt đầu đi vào thẻ HTML|
|5|onmouseout|Xảy ra khi con trỏ chuột bắt đầu rời khỏi thẻ HTML|
|6|onmouseenter|Tương tự như onmouseover|
|7|onmouseleave|Tương tự như onmouseout|
|8|onmousemove|Xảy ra khi con chuột di chuyển bên trong thẻ HTML|
|9|onkeydown|Xảy ra khi gõ một phím bất kì vào ô input|
|10|onload|Sảy ra khi thẻ HTML bắt đầu chạy, nó giống như hàm khởi tạo trong lập trình hướng đối tượng vậy đó.|
|11|onkeyup|Xảy ra khi bạn gõ phím nhưng lúc bạn nhã phím ra sẽ được kích hoạt|
|12|onkeypress|Xảy ra khi bạn nhấn môt phím vào ô input|
|13|onblur|Xảy ra khi con trỏ chuột rời khỏi ô input|
|14|oncopy|Xảy ra khi bạn copy nội dung của thẻ|
|15|oncut|Xảy ra khi bạn cắt nội dung của thẻ|
|16|onpaste|Xảy ra khi bạn dán nội dung vào thẻ|

- Ví dụ: chương trình gồm một ô input và một thẻ div dùng để hiển thị nội dung (giá trị của ô input) khi người dùng gõ vào ô input

``` js
<html>
  <body>
    <script language="javascript">
      // Hàm show kết quả
      function show_result()
      {
        // Lấy hai thẻ HTML
        var input = document.getElementById("message");
        var div = document.getElementById("result");

        // Gán nội dung ô input vào thẻ div
        div.innerHTML = input.value;
      }
    </script>
    <input type="text" id="message" value="" onkeyup="show_result()"/>
    <div id="result"></div>
  </body>
</html>
```

Nếu như bài này bạn sử dụng sự kiện `onkeypress` hoặc `onkeydown` thì sẽ có kết quả sai, lý do là những sự kiện này xảy ra khi bạn nhấn phím xuống nên nó sẽ lấy giá trị chưa được cập nhật. Còn sự kiện `onkeyup` xảy ra khi bạn nhả phím ra nên nó sẽ lấy được giá trị mới.

### Thêm sự kiện (Event)

Để thêm sự kiện bằng Javascript thì bạn sẽ sử dụng cú pháp như sau:


```js
elementObject.eventName  = function(){
    // do something
};
```

Trong đó:

- elementObject là đối tượng HTML mà chúng ta sử dụng DOM để lấy.
- eventName là tên của event như onclick, onchange, ...

Lưu ý nếu chúng ta sử dụng phương thức `document.getElementById()`, kết quả nó sẽ trả về chỉ là một đối tượng nên có thể gán trược tiếp `button.onclick = function(){}`. Nhưng nếu bạn sử dụng truy vấn DOM theo selector thì kết quả nó sẽ trả về một mảng các đối tượng, lúc này ban phải sử dụng vòng lặp để thiết lập sự kiện.

``` js
// Lấy đối tượng html, bạn có thể sử dụng các DOM Element khác để lấy
var elementObjs = document.getElementsByTagName('element');

// Lặp qua từng phần tử trong kết quả và gán sự kiện
for (var i = 0; i < elementObjs.length; i++)
{
    elementObjs[i].eventName = function()
    {
      // Do simething
    };
}
```

### Sự kiện onload

Cũng như các ngôn ngữ lập trình khác, Javascript sẽ chạy biên dịch từ trên xuống dưới và từ trái qua phải. Chính vì vậy khi bạn sử dụng một hàm mà phía trên nó không tồn tại hàm đó thì sẽ bị bái lỗi undefined ngay. Và để giải quyết vấn đề này thì ta sẽ dùng sự kiện onload trong javascript.

Sự kiện onload có ý nghĩa rằng khi trình duyệt đã load xong mọi thứ (image, js, css) thì những đoạn code nằm bên trong đó mới được chạy. Có một lưu ý rằng nếu bạn sử dụng onload cho một thẻ HTML nào đó thì nó sẽ có tác dụng với thẻ HTML đó thôi nhưng nếu bạn dùng cho window thì nó sẽ có tác dụng cho toàn trang.

Hay nói cách khác những đoạn code nằm bên trong sự kiện onload sẽ được chạy sau cùng khi mà trình JS đã được biên dịch 1 lần. Chính vì vậy nếu trong sự kiện onload bạn gọi tới một hàm nào đó thì dù bạn đặt hàm đó phía trên hay phía dưới thì đều đúng, lý do là trình biên dịch đã thực hiện dịch 1 lần rồi nên hàm đó đã tồn tại.

``` js
window.onload = function()
{
    do_validate();
};

function do_validate()
{
    alert(1);
}
```

### Hàm addEventListener()

Ta có cú pháp để thêm event như sau

``` js
elementObject.eventName  = function(){
    // do something
};
```

Tuy nhiên nếu bạn sử dụng hàm addEventListener() thì cú pháp sẽ như sau:

``` js
elementObject.addEventListener('eventName', function(e){
    // do something
});
```

Trong đó:

- `eventName` là tên của sự kiện bỏ đi chữ `on`, ví dụ `click`, `change`, ...
- function ở tham số thứ hai chính là hàm sẽ được chạy khi sự kiện `eventName` được kích hoạt

``` js
<html>
    <body>
        <input type="text" id="txt-val" value="" />
        <div id="result"></div>
        <script language="javascript">
            // Lấy đối tượng
            var input = document.getElementById("txt-val");

            // Thêm sự kiện cho đối tượng
            input.addEventListener('keyup', function(){
                // Gán giá trị vào div
                document.getElementById('result').innerHTML = input.value;
            });
        </script>
    </body>
</html>
```

- Nếu bạn muốn truyền tham số vào thì bắt buộc bạn phải tạo một hàm khác rồi gọi nó từ hàm addEventListener().

``` js
// Lấy đối tượng
var button = document.getElementById("btn");

// Thêm sự kiện cho đối tượng
button.addEventListener('click', function(){
    do_something(2, 3);
});

function do_something(a, b)
{
  alert( a + b);
}
```

### Hàm removeEventListener()

- Ví dụ bạn gán hành động validate form cho sự kiện submit của form, sau đó bạn không muốn validate nữa thì bạn sẽ có hai giải pháp. Một là bạn sẽ phải xóa đi đoạn code validate đó và hai là bạn chỉ cần sử dụng hàm removeEventListener() để xóa hành động validate.

``` js
object.removeEventListener("click", some_action);
```

### DOM trong js

DOM là viết tắt của chữ Document Object Model, dịch tạm ra là mô hình các đối tượng trong tài liệu HTML.

Như các bạn biết trong mỗi thẻ HTML sẽ có những thuộc tính (Properties) và có phân cấp cha - con với các thẻ HTML khác. Sự phân cấp và các thuộc tính của thẻ HTML này ta gọi là selector và trong DOM sẽ có nhiệm vụ xử lý các vấn đề như đổi thuộc tính của thẻ, đổi cấu trúc HTML của thẻ, ...

Các thể loại DOM trong Javascript

- DOM document: có nhiệm vụ lưu trữ toàn bộ các thành phần trong tài liệu của website
- DOM element: có nhiệm vụ truy xuất tới thẻ HTML nào đó thông qua các thuộc tính như tên class, id, name của thẻ HTML
- DOM HTML: có nhiệm vụ thay đổi giá trị nội dung và giá trị thuộc tính của các thẻ HTML
- DOM CSS: có nhiệm vụ thay đổi các định dạng CSS của thẻ HTML
- DOM Event: có nhiệm vụ gán các sự kiện như onclick(), onload() vào các thẻ HTML
- DOM Listener: có nhiệm vụ lắng nghe các sự kiện tác động lên thẻ HTML đó
- DOM Navigation dùng để quản lý, thao tác với các thẻ HTML, thể hiện mối quan hệ cha - con của các thẻ HTML
- DOM Node, Nodelist: có nhiệm vụ thao tác với HTML thông qua đối tượng (Object)

### DOM Element

DOM Element được dùng để truy xuất tới 1 thẻ html thông qua các thuộc tính như class, id, name ...

- Tìm thẻ HTML theo ID

`var element = document.getElementById('idname');`

-  Tìm thẻ HTML theo tên của thẻ HTML

`var element = document.getElementsByTagName('tagname');`

- Tìm thẻ HTML theo tên class

`var element = document.getElementsByClassName('input');`

- Tìm thẻ HTML theo cú pháp của Selector CSS

`var element = document.querySelectorAll("selector.css");`

### DOM HTML

- Thay đổi và lấy nội dung bên trong thẻ HTML

Để lấy nội dung bên trong một thẻ HTML thì chúng ta sử dụng cú pháp như sau:

`var html = document.getElementById("content").innerHTML`

Và để thay đổi nội dung cho một thẻ HTML thì ta dùng cú pháp sau:

`var html = document.getElementById("content").innerHTML = "<h1>Nội dung</h1>"`

- Thay đổi và lấy giá trị thuộc tính thẻ HTML

Để thay đổi giá trị của một thuộc tính HTML bất kì thì ta sử dụng cú pháp sau:

`document.getElementById("element").attributeName = "new value";`

Để lấy giá trị của một thuộc tính HTML ta sử dụng cú pháp sau:

`var value = document.getElementById("element").attributeName;`

### DOM CSS

- Thay đổi CSS

Cú pháp thiết lập CSS bằng Javascript:

`document.getElementById("object").style.cssName = 'something';`

Cú pháp lấy giá trị CSS bằng Javascript:

`var value = document.getElementById("object").style.cssName;`

Trường hợp thuộc tính có dấu gạch ngang như: font-size, line-height, margin-bottom thì thuộc tính đó trong style sẽ có tên là fontSize, lineHeight, marginBottom ,nghĩa là sẽ bỏ đi dấu gạch ngang và viết hoa ký tự đầu tiên của chữ thứ hai.

``` js
document.getElementById("object").style.fontSize = 'something';
document.getElementById("object").style.lineHeight = 'something';
document.getElementById("object").style.marginBottom = 'something';<br />
<br />
```

Lưu ý rằng có những thuộc tính nếu bạn chưa thiết lập CSS cho nó thì khi bạn lấy giá trị sẽ là một giá trị rỗng.

### DOM Nodes

- DOM Node - document.createElement()

Khi bạn sử dụng DOM Element để truy vấn tới một đối tượng HTML nào đó thì kết quả nó sẽ trả về một object và object đó ta gọi là DOM Nodes.

`var node = document.getElementById("some-id");`

Với cách này bắt buộc phải tồn tại một đối tượng HTML đang hiển thị trên website thì mới khởi tạo thành công. Giả sử nếu bạn muốn tạo một Node mới hoàn toàn v không liên quan tới những thẻ HTML đang hiển thị trên website thì làm thế nào? Rất đơn giản chúng ta sẽ sử dụng phương thức document.createElement() với tham số truyền vào là tên của thẻ HTML cần tạo.

`var p = document.createElement("p");`

Sau khi khởi tạo xong bạn hoàn toàn có thể sử dụng các phương thức, thuộc tính của DOM HTML, DOM CSS.

`p.innerHTML = "Học DOM Nodes"`

Để thêm Node này vào trang web thì chúng ta sử dụng phương thức appendChild

`document.getElementsByTagName('body')[0].appendChild(p);`

- DOM Node - document.createTextNode()

Text node là một node đặc biệt, nó không phải là một thẻ HTML thông thường mà chỉ là một chuỗi (string) nên thông thường chúng ta sử dụng nó để thay thế cách gán thông thường node.innerHTML.

- Phương thức appendChild()

Dùng để thêm (bổ sung) vào vị trí cuối cùng của đối tượng một thẻ HTML nào đó

- Phương thức insertBefore()

Được dùng để thêm một Node vào đằng trước một node con nào đó. Phương thức này có hai tham số truyền vào `insertBefore(node_insert, node_child)`, trong đó:

  - node_insert là node bạn muốn thêm vào
  - node_child là node con mà bạn muốn thêm vào đằng trước nó.

- Phương thức removeChild()

Được dùng để xóa một node con ra khỏi node hiện tại.

``` js
<html>
    <body>
        <div id="content">
            <h5>chúc vui vẻ khi học bài</h5>
        </div>

        <input type="button" value="Remove" id="btn-remove"/>

        <script language="javascript">
          // Lấy button
          var button = document.getElementById("btn-remove");

          // Thêm sự kiện click cho button
          button.addEventListener("click", function(){

            // Lấy thẻ cần remove
            var need_remove = document.getElementsByTagName("h5")[0];

            // Remove
            document.getElementById("content").removeChild(need_remove);
          });
        </script>
    </body>
</html>
```

- Phương thức replaceChild()

Dùng để replace (thay thế) một node con nào đó bằng một node khác mới hoàn toàn.

### Đối tượng this

Đối tượng this chính là đối tượng hiện tại đang được sử dụng hoặc đang truy cập tới. Ví dụ khi bạn viết một hành động cho sự kiện click thì nếu trong hành động đó có sử dụng this lúc này this chính là thẻ HTML mà ta click.

Ví dụ:

``` js
// Lấy đối tượng
var button = document.getElementById('btn');

// Gán sự kiện
button.addEventListener("click", function(){
// Lấy thuộc tính type của đối tượng đang xử lý
// chính là button có id="btn"
    alert(this.type);
});
```

Như vậy trong ví dụ này this chính là thẻ HTML mà chúng ta đang xử lý và đó chính là thẻ HTML có id="btn", vì vậy bạn có thể sử dụng DOM để lấy các giá trị thuộc tính hoặc gán thêm sự kiện khác vẫn được

### Chuỗi

Trường hợp trong chuỗi cũng có xuất hiện dấu nháy đơn hoặc nháy đôi thì bắt buộc bạn phải thêm ký tự \ đằng trước dấu nháy đó nếu không sẽ bị lỗi cũ pháp.

Ngoài ra còn nhiều ký hiệu kết hợp với dấu \ nữa như trong bảng dưới đây:

<img src="https://i.imgur.com/mxDOIFd.png">

- Nối chuỗi

Để nối chuỗi chúng ta sử dụng dấu + để gép hai chuỗi (hoặc biến) lại với nhau.

``` js
var message = "chào mừng bạn" + "đến với freetuts.net";

// Hoặc

var message1 = "chào mừng bạn";
var message2 = "đến với freetuts.net";

// Nối hai chuỗi
var message = message1 + message2;
```

Lưu ý khi xuống hàng của chuỗi trong Javascript

Khi bạn muốn Enter xuống hàng một chuỗi trong Javascript thì bắt buộc phải sử dụng dấu + để nối chuỗi nếu không sẽ bị lỗi cú pháp.

``` js
// Đúng
var message = "Chào mừng bạn đến với"
              + "freetuts.net";

// Sai
var message = "Chào mừng bạn đến với
               freetuts.net";
```

Nếu bạn muốn viết gọn hơn thì sử dụng dấu \ để báo cho trình duyệt biết là có xuống hàng.

``` js

var message = "Chào mừng bạn đến với \
                       freetuts.net";<br />
```

- Ép sang kiểu chuỗi

Nếu bạn muốn ép một giá trị nào đó sang kiểu chuỗi thì có thể sử dụng cú pháp `string.toString()`.

``` js
// Trước khi chuyển đổi
var number = 12;
alert(typeof number);

// Sau khi chuyển đổi
number = number.toString();
alert(typeof number);
```

### Các hàm xử lý chuỗi

#### Tìm kiếm chuỗi con

Chúng ta có ba hàm thường dùng để tìm kiếm chuỗi con trong Javascript như sau:

  - indexOf()
  - lastIndexOf()
  - search()

**Hàm indexOf()**

Để tìm kiếm chuỗi con thì ta sử dụng hàm `String.indexOf(str)`, trong đó `str` là chuỗi con và `String` là chuỗi cha. Hàm này sẽ trả kết quả về kết quả là vị trí xuât hiện đầu tiên của chuỗi (bắt đầu là vị trí 0), nếu không tìm thấy chuỗi con thì nó sẽ trả về -1.

**Hàm lastIndexOf()**

Trường hợp nếu chuỗi con xuất hiện nhiều lần trong chuỗi cha thì kết quả cũng trả về vị trí xuất hiện của chuỗi con đầu tiên. Vậy làm thế nào để lấy vị trí của chuỗi con cuối cùng trong chuỗi cha? Ta sẽ sử dụng hàm `String.lastIndexOf(str)`, hàm này sẽ trả về vị trí xuất hiện của chuỗi con cuối cùng và trả về -1 nếu không tìm thấy.

**Hàm search()**

Ngoài hai hàm trên bạn có thể sử dụng hàm `string.search(str)` để tìm kiếm, tác dụng của nó cũng giống như hàm `string.indexOf(str)`.

#### Cắt chuỗi con

Nếu ban muốn cắt một chuỗi con từ chuỗi cha thì bạn có thể sử dụng ba hàm sau:

- slice(start, end)
- substring(start, end)
- substr(start, length)

**Hàm slice()**

Hàm slide có hai tham số truyền vào:

- start: vị trí bắt đầu
- end: vị trí kết thúc

Nếu tham số truyền vào là số âm thì nó sẽ tính ngược lại, nghĩa là nó sẽ đếm từ cuối lên.

Nếu bạn chỉ truyền một tham số đầu tiên thì nó sẽ tự hiểu vị trí end là vị trí cuối cùng.

**Hàm substring()**

Hàm `substring()` có cách sử dụng giống với hàm `slice()`, tuy nhiên tham số truyền vào hàm `substring()` phải luôn luôn lớn hơn 0.

**Hàm substr()**

Hàm `substr()` có hai tham số là `start` và `length`, trong đó `start` là vị trí bắt đầu và `length` là số ký tự muốn lấy bắt đầu từ vị trí `start`. Nếu bạn truyền tham số `start` là số âm thì nó sẽ tính từ cuối trở lên, còn tham số `length` phải luôn luôn là số dương.

#### Tìm kiếm và lặp chuỗi

Để tìm kiếm và lặp một chuỗi con nào đó thì bạn sử dụng hàm `replace(str_find, str_replace)`, trong đó `str_find` là chuỗi cần tìm và `str_replace` là chuỗi sẽ được thay thế chuỗi `str_find`.

#### Chuyển thành chữ hoa và chữ thường

Để chuyển chuỗi thành chữ hoa ta dùng hàm `toUpperCase()` và chuyển thành chữ thường ta dùng hàm `toLowerCase()`.

#### Nối thêm chuỗi

Để nối thêm chuỗi thông thường ta dùng toán tử +, ngoài ra bạn có thể dùng hàm `concat()` để thực hiện nối chuỗi.

#### Chuyển đổi chuỗi sang mảng

Để chuyển một chuỗi sang mảng thì ta sử dụng hàm `split()` với tham số truyền vào là ký tự ngăn cách giữa các phần tử.

``` js
document.write(string.split(" ").length);
```

### Thao tác với mảng

- Khai báo mảng

Chúng ta có hai cách thông thường để khai báo mảng đó là sử dụng từ khóa `new Array()` và sử dụng cặp dấu ngoặc vuông ([]).

``` js
var name_array = new Array();
// Hoặc
var name_array = new Array(1,2,3);

// Hoặc

var name_array = [];
// Hoặc
var name_array = [1,2,3];
```

- Truy xuất các phần tử trong mảng

Để truy xuất đến phần tử của một mảng chúng ta dùng cú pháp tenmang[vitri]. Ví dụ:

``` js
var t = new Array(1,2,3);
alert(t[0]); // kết quả là 1
alert(t[1]); // kết quả là 2
alert(t[2]); // kết quả là 3
```

- In mảng ra trình duyệt và console

**Hàm array.join()**

Để hiển thị các phần tử ra ngoài trình duyệt chúng ta sẽ sử dụng hàm array.join(). Ví dụ:

``` js
var t = new Array(1,2,3);
document.write(t.join()); // kết quả 1,2,3
document.write(t.join('-')); // kết quả 1-2-3
```

Như vậy hàm join này được tích hợp vào đối tượng mảng trong javascript và nó có một tham số truyền vào, nếu ta không truyền gì vào thì mặc định nó lấy dấu phẩy để ngăn giữa các giá trị khi in lên trình duyệt.

**Hàm console.log():**

#### Sử dụng vòng lặp để lặp mảng

- Lặp mảng với vòng lặp for

``` js
var name_array = [1,2,3];
for (var i = 0; i < name_array.length; i++){
    document.write(name_array[i]);
}
```

- Lặp mảng với vòng lặp while

``` js
var name_array = [1,2,3];
var index = 0;
while (index < name_array.length){
    document.write(name_array[index]);
    index++;
}
```

Riêng đối với vòng lặp do while thì không khuyến khích sử dụng để lặp mảng, lý do nó vòng lặp do while luôn luôn lặp ít nhất một lần nên trong trường hợp mảng cần lặp rỗng thì sẽ bị báo lỗi ngay.

### Các hàm xử lý mảng

**Hàm array.valueOf()**

Hàm này có tác dụng tương tự như hàm array.join() mà ta đã học ở bài trước, có nghĩa là nó sẽ nối các phần tử với nhau vào một chuỗi cách nhau bởi dấu phẩy.

**Hàm array.push()**

Hàm thêm một phần tử vào cuối mảng.

**Hàm array.pop()**

Ngược với hàm array.push(), hàm này có tác dụng xóa đi phần tử cuối cùng trong mảng.

**Hàm array.shift()**

Hàm xóa phần tử đầu tiên của mảng, sau đó dồn các phần tử phía sau xuống một bậc.

**Hàm array.unshift()**

Thêm một phần tử vào vị trí đầu tiên của mảng, đồng thời đẩy các phẩn từ phía sau lên một bậc.

**Hàm array.splice()**

Hàm splice() có ba tham số truyền vào như sau: `splice(position_add, num_element_remove, value1, value2, ...)`.

Trong đó:

- `position_add` là vị trí sẽ thêm (vị trí đầu tiên là 0)
- `num_element_remove` là số phần tử sẽ xóa (bắt đầu từ position_add)
- `value1, value2, ..` là danh sách các phần tử sẽ được thêm vào sau khi tại vị trí position_add và sau khi remove num_element_remove phần tử.

**Hàm array.sort()**

Hàm này dùng để sắp xếp các phần tử trong mảng theo thứ tự chữ cái alpha.

**Hàm array.reverse()**

Hàm đảo ngược các phẩn tử lại. Vị trí đầu sẽ được chuyển xuống cuối mảng và vị trí cuối mảng sẽ được chuyển lên đầu mảng.

**Hàm array.concat()**

Hàm dùng để nối hai mảng với nhau và trả về một mảng gồm tổng số phần tử của hai mảng đó.

**Hàm array.slice()**

Hàm dùng để lấy một số phần tử con trong mảng. Có hai tham số truyền vào như sau: slice(start, end).


**Cre:**

https://freetuts.net/
