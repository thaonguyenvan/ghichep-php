# Ghi chép nâng cao

## Đối tượng number

Trong Javascript có một đối tượng thường được dùng để xử lý kiểu dữ liệu number đó là đối tượng Number, đối tượng này thường có hai dạng đó là số có dấu chấm động và số không có dấu chấm động.

Không giống với các ngôn ngữ lập trình khác, trong Javascript các số luôn luôn là 64 bít và kiểu float, vì vậy bạn không thể định nghĩa các kiểu dữ liệu như integer, short, long, ... hay nói cach khác trong Javascript khi làm việc với các chữ số thì chỉ có khái niệm Number.

## Xử lý Number

### Chuyển Number sang String

Để chuyển một biến đang ở kiểu Number sang kiểu String thì ta sử dụng phương thức `number.toString(type)`, hàm này có một tham số truyền vào là `type` và đây chính là kiểu dữ liệu mà ban muốn chuyển về, mặc định sẽ là hệ thập phân (10).

Sau đây là danh sách các hệ cơ số thông dụng:

- Hệ nhị phân (2)
- Hệ bát phân (8)
- Hệ thập phân (10)
- Hệ thập lục phân (8)

### Số Infinity

Infinity cũng là một kiểu dữ liệu Number và khi một biến có giá trị là Infinity thì tức là nó đã vượt mức lưu trữ cho phép nên theo mặc định nó sẽ chuyển về dạng đó. Vì nó cũng là một giá trị nên bạn có thể so sánh bình thường.

### NaN - Not a Number

Nếu bạn thực hiện một phép toán nào đó liên quan đến Number nhưng vi phạm quy tắc tính toán thì kết quả sẽ trả về một giá trị gọi là `NaN` (Not a Number). Ví dụ khi bạn thực hiện phép chia hai số nếu bạn cho mẫu số là một chuỗi String thì kết quả sẽ là `NaN`

Để kiểm tra một biến nào đó có phải là NaN hay không thì chúng ta sử dụng hàm `isNaN()`

### Numbers - Objects

Ngoài cách tạo một biến Number thông thường đó là gán giá trị trực tiếp thì còn một cách khác đó là sử dụng đối tượng Number. Tuy nhiên hai cách tạo này sẽ có kiểu dữ liệu khác nhau.

``` js
var x = 123; // number
var y = new Number(123); // object
```

## Hàm xử lý Number

### Hàm xử lý Number toàn cục

#### Number()

Dùng để chuyển đổi một biến hoặc một giá trị nào đó sang kiểu number, nó chuyển tất cả các định dạng như Boolean, Date, String. Nếu trường hợp giá trị cần chuyển đổi không thể chuyển sang Number được thì nó sẽ chuyển sang giá trị mặc định là NaN.

#### parseInt()

Hàm này có tác dụng giống như hàm Number(), tuy nhiên có một số điểm khác biệt như sau:

- Nếu chuỗi có các ký tự đầu tiên là các con số và ở đằng sau là chữ cái thì nó sẽ lấy các số đầu tiên đó và chuyển thành kiểu number. Trường hợp này nếu dùng hàm Number() thì nó sẽ chuyển thành NaN.
- Nếu dữ liệu ở các định dạng khác string thì nó sẽ chuyển thành NaN

#### parseFloat()

Hàm này chuyển dữ liệu sang định dạng float, về cách sử dụng nó giống với hàm parseInt().

### Hàm xử lý Number cục bộ

Những hàm cục bộ phải gắn liền với đối tượng Number cụ thể, ví dụ khi bạn khởi tạo một biến var x = 12 thì lúc này x có tất cả các hàm cục bộ đó. Ngoài ra bạn có thể sử dụng cặp mở đóng ()  để bao quanh một biểu thức  hoặc một giá trị thì vẫn sử dụng bình thường.

#### toString()

Hàm toString() có tác dụng chuyển đổi Number sang kiểu String.

#### toFixed(n)

Hàm này có tác dụng chuyển một số sang một số có n số lẻ ở sau nó và có làm tròn

#### toPrecision(n)

Hàm này có tác dụng chuyển một số thành số có chiều dài là n, hàm  này khác với hàm toFixed() ở chỗ hàm toFixed() chuyển thành số có n số lẻ ở đằng sau. Có một điều lưu ý là tham số n phải luôn luôn lớn hơn 0 và nếu bạn không truyền tham số vào thì mặc định nó lấy luôn chiều dài ban đầu.

## Đối tượng Date

Cu pháp khởi tạo

``` js
// Thời gian hiện tại
new Date();

// Tham số truyền vào là mili giây
new Date(milliseconds);

// Tham số truyền vào là chuỗi ngày tháng
new Date(dateString);

// Tham số truyền vào gồm
//  - year:         năm
//  - month:        tháng
//  - day:          ngày
//  - hours:        giờ
//  - minutes:      phút
//  - seconds:      giây
//  - milliseconds: mini giây
new Date(year, month, day, hours, minutes, seconds, milliseconds);
```

### Định dạng (format) Date

Có ba định dạng chính đó là:

- ISO
- Long
- Short

#### Định dạng ISO

Định dạng chuẩn của ISO 8601 là (YYYY-MM-DD) hoặc (YYYY-MM) hoặc (YYYY).

Có một lưu ý nếu bạn truyền vào không đủ (ngày - tháng - năm - giờ - phút - giây) thì mặc định các tham số khác sẽ lấy thời gian nhỏ nhất.

#### Định dạng Long

Định dạng Long tức là bạn truyền vào với tên của tháng là ba chữ cái đầu tiên ghi bằng tiếng Anh, lúc này bạn có thể đặt vị trí của nó thế nào cũng được vì đối tượng Date tự nhận diện và chuyển đổi

``` js
var LONG_1 = new Date("Mar 25 2015");
var LONG_2 = new Date("2015 Mar 25");
var LONG_3 = new Date("25 2015 Mar");
```

#### Định dạng Short

Định dạng Short được lưu trữ dưới dạng `MM/DD/YYYY` hoặc `YYYY/MM/DD` hoặc `MM-DD-YYYY` hoặc `YYYY-MM-DD/`

``` js
var SHORT_1 = new Date("03-25-2015");
var SHORT_2 = new Date("03/25/2015");
var SHORT_3 = new Date("2015/03/25");
var SHORT_4 = new Date("2015-03-25");
```

#### Định dạng đầy đủ

Trên là những định dạng ghi tắt, nếu truyền đầy đủ thì bạn phải truyền đẩy đủ (ngày - tháng - năm - giờ - phút - giây - timezone):

`var d = new Date("Wed Mar 25 2015 09:56:24 GMT+0100 (W. Europe Standard Time)");`

## Hàm xử lý ngày tháng (Date)

### Các hàm nhóm Date Get

Trong Javascript tổng cộng có 10 hàm thiết lập thời gian thông dụng:

- getDate() lấy ngày (1 - 31)
- getDay() lấy ngày trong tuần (0-6)
- getFullYear() lấy năm đầy đủ (YYYY)
- getYear() lấy năm 2 số cuối (YY)
- getHours() lấy số giờ (0 - 23)
- getMiliSeconds() lấy số mili giây (0 - 999)
- getMinutes() lấy số phút (0 - 59)
- getMonth() lấy tháng (0 - 11)
- getSeconds() lấy số giây (0 - 59)
- getTime() thời gian đã được convert sang dạng miliseconds.

``` js
// Đối tượng thời gian hiện tại
var d = new Date();

d.getDate();
d.getDay();
d.getFullYear();
d.getYear();
d.getHours();
d.getMilliseconds();
d.getMinutes();
d.getMonth();
d.getSeconds();
d.getTime();
```

### Các nhàm nhóm Date Set

Tương ứng với mỗi hàm Date Get thì sẽ có một hàm Date Set (trừ hàm getDay()).

- setDate() thiết lập ngày (1 - 31)
- setFullYear() thiết lập năm đầy đủ (YYYY)
- setYear() thiết lậpnăm 2 số cuối (YY)
- setHours() thiết lập số giờ (0 - 23)
- setMiliSeconds() thiết lập số mili giây (0 - 999)
- setMinutes() thiết lập số phút (0 - 59)
- setMonth() thiết lập tháng (0 - 11)
- setSeconds() thiết lập số giây (0 - 59)
- setTime() thiết lập thời gian đã được convert sang dạng miliseconds.

Lưu ý:

- Vì đây là hàm set nên bạn phải truyền tham số vào.
- Các hàm có ảnh hưởng lẫn nhau nhé các bạn, ví dụ bạn thiết lập ngày giờ không đúng thì nó sẽ lấy ngày giờ mặc định.
- Nếu bạn dùng hàm setTime() để thiết lập thì nó ảnh hưởng tới tất cả các giá trị còn lại bởi vì setTime() là hàm thiết lập thời gian đầy đủ đã chuyển sang dạng miniseconds.

## BOM là gì? BOM trong javascript

### BOM là gì?

- window
- screen
- location
- history
- navigator
- popup
- timing
- cookies

Trong các đối tượng BOM trên có phân cấp lẫn nhau và trong đó window là cấp cao nhất vì nó đại diện cho browser.
Ví dụ khi bạn muốn truy cập tới document thì bạn sẽ viêt là window.document, tuy nhiên vẫn có cách ghi tắt là document, muốn truy cập tới cookie thì ta viết window.document.cookie (viết tắt document.cookie), ...

### BOM - Window

#### Xác định kích thước của trình duyệt

Để lấy kích thước chiều cao và chiều rộng của trình duyệt thì chúng ta sử dụng đối tượng window, tuy nhiên với mỗi trình duyệt thì có những cách lấy khác nhau.

- Đối với Internet Explorer, Chrome, Firefox, Opera, và Safari thì cú pháp như sau:

```js
// lấy chiều cao
var heightBrowser = window.innerHeight;

// lấy chiều rộng
var widthBrowser = window.innerWidth;
```

- Đối với Internet Explorer các version 5,6,7,8 thì cú pháp như sau:

```js
// Lấy chiều cao
var height = document.documentElement.clientHeight;
// hoặc
var height = document.body.clientHeight;

// Lấy chiều rộng
var width = document.documentElement.clientWidth;
// hoặc
var width = document.body.clientWidth;
```

#### Thao tác với một cửa sổ window

**Mở một cưa sổ với lệnh window.open()**

Cú pháp: `window.open(url, name, options)`

Trong đó:

- url : là đường dẫn website bạn muốn mở
- name: là tên bạn đặt cho cửa sổ này
- options: là một chuỗi các thông số được cách nhau bởi dấu phẩy, sau đây là các thông số thông dụng:
  - height=pixels : chiều cao của cửa sổ
  - width=pixels: chiều rộng của cửa sổ
  - top=pixels: vị trí hiển thị cửa sổ so với lề trên
  - left=pixels: vị trí hiển thị cửa sổ so với lề trái
  - menubar=yes|no|1|0: có hiển thị thanh menu hay không?
  - resizable=yes|no|1|0: có hiển thị biểu tượng resize cửa sổ hay không?
  - scrollbars=yes|no|1|0: có hiển thị thanh cuộn hay không?
  - status=yes|no|1|0: có hiển thị thanh trạng thái hay không?
  - titlebar=yes|no|1|0: có hiển thị titlebar hay không?
  - toolbar=yes|no|1|0: có hiển thị toolbar hay không?
  - fullscreen=yes|no|1|0: có hiển thị biểu tượng fullscreen hay không?

```js
<html>
    <body>
      <script language="javascript">

        var windowChild = null;

        function openWindow()
        {
          windowChild = window.open('https://facebook.com', "windowChild", "width=500, height=500");
            return false;
        }

      </script>
      <a href="#" onclick="return openWindow()">Open</a>
    </body>
</html>
</script>
```

**Đóng một cửa số với lệnh window.close()**

Sau khi mở cửa sổ thì để đóng cửa sổ đó chúng ta sử dụng lệnh `windowObj.close()`, trong đó `windowObj` là cửa sổ mà ta sử dụng lệnh `window.open()` tạo ra.

``` js
<html>
    <body>
      <script language="javascript">

        var windowChild = null;

        function openWindow()
        {
            windowChild = window.open('https://freetuts.net', "windowChild", "width=500, height=500");
            return false;
        }

        function closeWindow()
        {
            windowChild.close()
            return false;
        }
      </script>
      <a href="#" onclick="return openWindow()">Open</a>
      <a href="#" onclick="return closeWindow()">Close</a>
    </body>
</html
```

**Di chuyển cửa sổ với lệnh window.moveTo()**

Sau khi mở một cửa sổ nếu muốn di chuyển nó thì ta dùng lệnh `windowObj.moveTo(top, left)`, trong đó:

- top: là số pixels so với lề trên
- left: là số pixels so với lề trái

**Resize cửa sổ với lệnh window.resizeTo()**

Lúc mở cửa sổ bạn sẽ thiết lập height và with cho window, tuy nhiên nếu sau khi mở bạn muốn thay đổi thì sử dụng hàm `windowObj.resizeTo(width, height)`, trong đó:

- width: chiều rộng của cửa sổ
- height: chiều cao của cửa sổ

### BOM - Location điều hướng và xử lý URL

Location là một thuộc tính của đối tượng window nên khi sử dụng nó bạn phải thông qua đối tượng window và đối tượng window luôn tồn tại trong các trình duyệt hiện nay nên bạn hoàn toàn yên tâm khi sử dụng mà không cần phải khai báo.

#### Các phương thức của Location

**window.location.reload(url) - tải lại trang web**

Thông thường để tại lại trang web bạn sẽ nhấn phím F5 hoặc là clich chuột phải và chọn Refresh page, tuy nhiên nếu bạn refresh bằng Javascript thì vẫn được bằng cách sử dụng phương thức reload().

**window.location.replace(urr) - ghi đè trang web**

Phương thức này ít khi sử dụng mà thay vào đó họ sử dụng cú pháp `window.location.href="url"`. Tuy nhiên hai cách này vẫn có sự khác biệt:

- Đối với replace() thì trình duyệt sẽ KHÔNG đưa vào lịch sử.
- Đối với location.href thì trình duyệt sẽ CÓ đưa vào lịch sử

**window.location.assign(url) - load một trang mới**

Về công dụng vẫn không có gì khác với hai cách trên, tuy nhiên cách này nó có đặc điểm giống với location.href

#### Các thuộc tính của Location

Ngoài các phương thức trên thì bạn có thể sử dụng Location để xử lý các thành phần liên quan đến URL như lấy phần hash, lấy phần search.

Và đây là danh sách các thuộc tính đầy đủ cho đối tượng location này:

- hash: thiết lập hoặc lấy phần sau dấu # của URL
- host: thiết lập hoặc lấy hostname và port number của URL
- hostname: thiết lập hoặc lấy hostname
- href: thiết lập hoặc lấy URL
- origin: trả về protocal, hostname và port number của URL
- pathname: thiết lập hoặc lấy path name của URL
- port: thiết lập hoặc lấy port của URL
- search: lấy phần query string của URL

### BOM - History

Khi bạn lướt web thì trình duyệt sẽ lưu lại lịch sử lướt web của bạn và dựa vào lịch sử đó chúng ta có thể xem lại những ngày trước đã xem gì, và vấn đề này trình duyệt đã hỗ trợ cho chúng ta rồi (back, forward, clear history). Nhưng nếu bạn có nhu cầu cần sử dụng Javascript để xử lý thì vẫn có một số phương thức và thuộc tính nằm trong đối tượng History có thể giúp giải quyết vấn đề này.

**Đếm tổng số trang đã lưu trong history**

`var totalPage = window.history.length;`

**Đi tới một trang nào đó trong history**

Chúng ta có ba phương thức thường dùng để đến một trang trong history:

- history.back() : trở lại trang trước
- history.forward() : đi tới trang kế tiếp
- history.go(number): đi tới một trang:
  - nếu number âm thì tính từ trang hiện tại trừ đi number
  - nếu number dương thì tính từ trang hiện tại cộng với number

### BOM - Cookie

Cookie là dữ liệu được lưu trữ trong một file text và nằm trong máy tính nên việc lưu trữ Cookie sẽ là vĩnh viễn hoặc là một thời gian cụ thể do bạn thiết lập. Tuy nhiên mỗi domain sẽ có một dung lượng Cookie tối đa có thể lưu trữ được nên hãy lưu ý trường hợp dữ liệu quá lớn.

Khi trình duyệt gửi thông tin lên Server thì cookies sẽ được load và gửi kèm theo trong request, chính vì vậy trong ngôn ngữ server (PHP, JSP, ..) cũng sẽ nhận được thông tin đó. Đây cũng là thông tin để trả lời cho câu hỏi tạo sao Cookie được lưu trữ ở Client mà trên Server vẫn đọc được, và ta cũng hay sử dụng Cookie để xây dựng chức năng Remember Me khi Login.

#### Các thao tác với Cookie

Javascript có thể đọc, thêm và xóa Cookie thông qua đối tượng BOM `document.cookie`.

**Tạo Cookie**

Ở phần Cookie là gì bạn đã biết Cookie được lưu trữ ở dạng name=value nên để tạo Cookie thì ta sử dụng chuỗi dữ liệu giống như vậy.

`document.cookie = 'website=freetuts.net';`

Để thiết lập thời gian sống cho Cookie thì ta sử dụng từ khóa expires cấu trúc của chuỗi này là thời gian ở dạng UTC.

`document.cookie="website=freetuts.net; expires=Thu, 0 Dec 2015 12:00:00 UTC";`

**Lấy giá trị Cookie**

Để lấy danh sách các Cookie thì ta sử dụng cú pháp như sau:

`var giatri = document.cookie;`

**Đổi giá trị cho Cookie**

Để thay đổi giá trị cho Cookie thì bạn chỉ việc gán lại giá trị cho cookie.

**Xóa Cookie**

Trong Javascript không có hàm xóa Cookie mà bạn phải sử dụng từ khóa expires để thiết lập thời gian sống cho Cookie là khoảng thời gian đã qua. Ví dụ hôm nay là ngày 8/11/2015 thì bạn chỉ việc gán expires là 7/8/2015 là đã xóa được Cookie đó.

#### Viết hàm xử lý Cookie

Vì Cookie được lưu trữ ở dạng chuỗi các key=value và các chuỗi giá trị cách nhau bởi dấu chấm phẩy ; nên để lấy một giá nào đó bạn phải xử lý chuỗi rất phức tạp, vì vậy thông thường chúng ta viết hàm tạo và lấy Cookie để sử dụng được nhiều lần.

``` js
// Hàm thiết lập Cookie
function setCookie(cname, cvalue, exdays) {
    var d = new Date();
    d.setTime(d.getTime() + (exdays*24*60*60*1000));
    var expires = "expires="+d.toUTCString();
    document.cookie = cname + "=" + cvalue + "; " + expires;
}

// Hàm lấy Cookie
function getCookie(cname) {
    var name = cname + "=";
    var ca = document.cookie.split(';');
    for(var i=0; i<ca.length; i++) {
        var c = ca[i];
        while (c.charAt(0)==' ') c = c.substring(1);
        if (c.indexOf(name) == 0) return c.substring(name.length, c.length);
    }
    return "";
}
```

### BOM - Window Navigator

Đối tượng Window Navigator trong Javascript được dùng để kiểm tra các thông tin về người dùng như trình duyệt đang sư dụng là gì? hệ điều hành đang sử dụng là gì? Trình duyệt có bật Cookie hay không? hay thậm chí có thể kiểm tra được tên và version của Browser

**Kiểm tra Cookie có được bật không?**

Để kiểm tra trình duyệt có bật Cookie hay không thì ta sử dụng thuộc tính `navigator.cookieEnabled`

```js
if (window.cookieEnabled){
    alert("Có bật Cookie - freetuts.net");
}
else{
    alert("Cookie đã bị tắt");
}
```

**Kiểm tra tên trình duyệt đang sử dụng**

Để kiểm tra tên trình duyệt thì ta dùng thuộc tính `navigator.appName` và thuộc tính `navigator.appCodeName` dùng để kiểm tra tên mã code của trình duyệt

``` js
document.write("App Name: " + window.navigator.appName + "<br/>");
document.write("Code Name: " + window.navigator.appCodeName);
```

**Kiểm tra Engine của trình duyệt**

Để kiểm tra Engine của trình duyệt ta sử dụng thuộc tính `navigator.product`.

**Kiểm tra Vesion của trình duyệt**

Để kiểm tra Version của trình duyệt ta sử dụng thuộc tính `navigator.appVersion` hoặc `navigator.userAgent`.

**Kiểm tra hệ điều hành của Client**

Javascript cũng có thể xem hệ điều hành mà người dùng đang sử dụng bằng cách sử dụng thuộc tính `navigator.platform`.

**Kiểm tra ngôn ngữ của trình duyệt**

Mỗi trình duyệt có thể lựa chọn ngôn ngữ khác nhau và ta có thể kiểm tra bằng phương thức `navigator.language`

### BOM - Screen

**Lấy width và height của màn hình**

Chúng ta sử dụng thuộc tính `screen.width` để lấy chiều rộng và `screen.height` để lấy chiều cao của màn hình, kết quả sẽ trả về định dạng Pixels.

``` js
document.write("With screen: " + screen.width + "<br/>");
document.write("Height screen: " + screen.height);
```

Ngoài ra để lấy chiều rộng và chiều cao mà không tính các tools tính năng của trình duyệt thì bạn sử dụng `screen.availWidth` và `screen.availHeight`.

**lấy Color Depth của screen**

Để lấy color depth của screen thì ta sử dụng thuộc tính `screen.colorDepth`.

**Lấy số Pixel depth của screen**

Để lấy Pixel depth của màn hình thì ta sử dụng thuộc tính `screen.pixelDepth`.

## Đối tượng (object)

Trong Javascript đối tượng là một khái niệm trừu tượng thể hiện cho một đối tượng cụ thể và nó có sẵn một số đối tượng như Date, Number. Ngoài các đối tượng này thì lập trình viên có thể tự tạo một đối tượng theo ý của mình dựa vào yêu cầu của ứng dụng. Ví dụ mình cần tạo ra một đối tượng chuyên xử lý vấn đề về bình luận cho trang tin tức thì mình sẽ tạo một đối tượng Comment.

### Khởi tạo đối tượng

Đấy là về mặt lý thuyết, còn về mặt thực hành thì để tạo một đối tượng bạn sẽ có hai cách sau.

Cách 1: Sử dụng từ khóa `new Object()`

`var Comment = new Object();`

Cách 2: Sử dụng từ khóa {}

`var Comment = {};`

### Thuộc tính và phương thức đối tượng

**Thuộc tính**

Thuộc tính là những đặc điểm (có thể hiểu là biến) cần lưu trữ trong đối tượng. Ví dụ với đối tượng Comment thì mình cần các thuộc tính sau.

- title
- content
- fullname
- email

Cách 1: Sử dụng từ khóa new Object()

``` js
// Khởi tạo
var Comment = new Object();

// Thêm thuộc tính
Comment.title = '';
Comment.content = '';
Comment.fullname = '';
Comment.email = '';
```

Cách 2: Sử dụng từ khóa {} và thêm thuộc tính ngay lúc khai báo

``` js
// Khởi tạo
var Comment = {
    title : "",
    content : "",
    fullname : "",
    email : ""
};
```

Cách 3: Sử dụng từ khóa {} và thêm thuộc tính sau đó

``` js
// Khởi tạo
var Comment = {};

// Thêm thuộc tính
Comment.title = '';
Comment.content = '';
Comment.fullname = '';
Comment.email = '';
```

**Phương thức**

Phương thức là những hành động (có thể hiểu là hàm) của đối tượng. Ví dụ trong đối tượng Comment thì mình cần hai phương thức là:

``` js
addComment()
validateComment()
```

Lúc này ta sẽ có ba cách khai báo tương tự như cách khai báo thuộc tính.

Cách 1: Sử dụng từ khóa new Object()

``` js
// Khởi tạo
var Comment = new Object();

// Thêm phương thức
Comment.addComment = function(){
    // do some thing
};

Comment.validateComment = function(){
    // do some thing
};
```

Cách 2: Sử dụng từ khóa {} và thêm phương thức ngay lúc khai báo

``` js
// Khởi tạo
var Comment = {
    addComment : function(){
        // do some thing
    },
    validateComment : function(){
        // do some thing
    }
};
```

Cách 3: Sử dụng từ khóa {} và thêm phương thức sau đó

``` js
// Khởi tạo
var Comment = {};

// Thêm phương thức
Comment.addComment = function(){
    // do some thing
};

Comment.validateComment = function(){
    // do some thing
};
```

**Thao tác với thuộc tính và phương thức**

- Gán giá trị cho thuộc tính

Để gán giá trị cho thuộc tính chúng ta chỉ việc thực hiện bằng cách sử dụng toán tử = giống như cách gán giá trị cho biến

`Comment.title = "Tiêu đề bình luận";`

- Lấy giá trị của thuộc tính

Để lấy giá trị thuộc tính thì ta làm tương tự như thao tác với biến.

`var title = Comment.title;`

- Gọi phương thức

Tương tự như thuộc tính chúng ta gọi bình thường.

`comment.addComment();`

### Mảng chứa đôi tượng - đối tượng chứa đối tượng

- Đối tượng chứa đối tượng

``` js
var Comment = {
    info : {
        title : "",
        content : "",
        email : "",
        fullname : ""
    }
};
```

Lúc này để truy xuất tới các thuộc tính và phương thức này ta chỉ việc sử dụng dấu chấm và bổ sung thêm một cấp nữa.

``` js
Comment.info.title = "Comment tại freetuts.net";
Comment.func.addComment();
```

- Mảng chứa đối tượng

Để gán giá trị là một đối tượng vào mảng cũng tương tự như gán các giá trị bình thường khác (xem mảng trong Javascript).

``` js
// Đối tượng Comment
var Comment = {
    title   : "",
    content : "",
    email   : "",
    fullname : ""
};

// Khởi tạo mảng
var Comments = [];

// Gán giá trị cho phần tử mảng
Comments[0] = Comment;

// Gọi tới thuộc tính
Comments[0].title = "Tiêu đề bình luận";
alert(Comments[0].title);

// Hoặc

// Khởi tạo mảng
var Comment = [{
    title   : "",
    content : "",
    email   : "",
    fullname : ""
}];

// Sử dụng
Comment[0].title = "Tiêu đề bình luận";
alert(Comment[0].title);
```

### Use Strict là gì? Strict Mode trong javascript

Khi bạn download những file JS trên mạng về hoặc download những Plugin jQuery thì bạn sẽ thấy phía trên cùng của file người ta có đặt dòng chữ `"use strict";`. Vậy câu hỏi được đặt ra là từ khóa use strict là gì và mục đích người ta đặt nó ở đầu file để làm gì?. Để trả lời câu hỏi trên thì ta phải tìm sự thoải mái trong việc phát triển của Javascript và sự ra đời của Strict Mode.

#### Chế độ Strict Mode là gì ?
Khi bạn làm việc với Javascript thì bạn có thể sử dụng biến mà chưa cần định nghĩa (hoisting), bạn có thể quên đặt dấu chấm phẩy ở cuối mỗi đoạn code và bạn có thể sử dụng tên những từ khóa để tạo tên biến. Điều này làm cho các lập trình viên có thói quen làm việc quá dễ dãi và dẫn đến chương trình thiếu tính an toàn. Chính vì vậy Javascript kể từ phiên bản 1.8.5 trở đi đã bổ sung một khái niệm gọi Strict Mode nhằm giải quyết tính thiếu an toàn này.

Và bây giờ câu hỏi đặt ra là làm thế nào để khai báo sử dụng chế độ Strict Mode? Để trả lời câu hỏi này thì ta qua phần tiếp theo.

#### Use Strict là gì ?
Use strict là từ khóa khai báo sử dụng chế độ Strict Mode, nghĩa là nếu bạn muốn sử dụng chế độ Strict Mode ở đâu thì chỉ việc đặt từ khóa "use strict" ở đó. Chế độ Strict Mode có hai phạm vi sử dụng đó là toàn cục và cục bộ. Tính toàn cục tức là khi bạn đặt từ "use strict" ở ngoài hàm và nằm phía trên cùng của file thì lúc này tất cả các đoạn code bên dưới đều bị ảnh hưởng. Tính cục bộ tức là bạn đặt "use strict" nằm trong một hàm nào đó thì phạm vi ảnh hưởng chỉ nằm trong hàm đó mà thôi.

**Phạm vi Strict Mode toàn cục**

Trong ví dụ này chương trình chạy bị sẽ bị sai vì biến domain chưa được khởi tạo. Tuy nhiên nếu ta bỏ từ khóa use strict đi thì chương trình sẽ chạy bình thường.

``` js
// Phía trên cùng của file
"use strict";

// Đoạn code này lỗi vì biến domain chưa được khởi tạo
domain = "https://freetuts.net";

// In ra màn hình
document.write(domain);
```

Bây giờ ta thử gom đoạn code trên vào một hàm thử.

``` js
// Phía trên cùng của file
"use strict";

function show_domain(){
    // Đoạn code này lỗi vì biến domain chưa được khởi tạo
    domain = "https://freetuts.net";

    // In ra màn hình
    document.write(domain);
}

show_domain();
```

Chạy lên chương trình vẫn bị lỗi vì ta đã khai báo tính toàn cục cho chế độ Strict Mode.

**Phạm vi Strict Mode cục bộ**

Sử dụng ví dụ trên nhưng ta sẽ khai báo ở trong phạm vi của hàm.

**Ví dụ Use Strict trong Javsacript**

- Sử dụng biến chưa được định nghĩa: Bạn không thể sử dụng một biến mà chưa được định nghĩa trước đó.
- Không chấp nhận delete biến: Bạn không thể delete các hàm, biến nếu chạy ở chế độ Strict Mode
- Định thuộc tính nghĩa hai lần: Nếu trong một Object bạn định nghĩa tên key bị trùng thì sẽ bị lỗi.
- Khao báo tham số bị trùng: Nếu bạn khai báo các tham số bị trùng tên thì sẽ bị lỗi
- Lỗi literals và escape với number: Bạn không được sử dụng literals và escape với kiểu number.
- Khai báo tên biến trùng với key: Bạn không thể khai báo tên của biến trùng với key của Javascript.

Ngoài ra bạn không thể sư dụng tên biến với các từ khóa sau:

- implements
- interface
- package
- private
- protected
- public
- static
- yield

### RegExp - Regular Expression

Trong Javascript thì Regular Expression là một chuỗi nhưng nó không được bao quanh bởi cặp dấu nháy đơn ' hoặc nháy kép " mà nó được bao quanh bởi cặp dấu /.

Cú pháp:

`/pattern/modifiers`

Trong đó:

- pattern là chuỗi Regular Expression
- modifiers là thông số cấu hình cho chuỗi pattern và nó có các giá trị:
  - i : so khớp không quan tâm đến chữ hoa chữ thường
  - g : so khợp toàn bộ chuỗi cần tìm
  - m : so khớp luôn cả các dữ liệu xuống dòng (multiline)

Ví dụ: Pattern kiểm tra chuỗi có tồn tại chữ "freetuts" không, không phân biệt chữ hoa chữ thường và tìm toàn bộ tài liệu.

`var pattern = /freetuts/igm;`

Trong ví dụ này thì:

- pattern là freetuts
- modifiers là igm

#### Các quy tắc Regular Expression căn bản

<img src="https://i.imgur.com/u65pKNl.png">

**hàm trong parttern dùng để kiểm tra một chuỗi - hàm test().**

  Cú pháp: pattern.test(string)

Trong đó:

- pattern là chuỗi pattern
- string là chuỗi cần kiểm tra.

Kết quả trả về: TRUE nếu khớp và FALSE nếu không khớp.

Ví dụ: Kiểm tra chuỗi có ít nhất một chữ n

``` js
if (/n+/.test("hello")) {
    document.write('Trong chuỗi có chữ n');
}
else {
    document.write('Trong chuỗi không có chữ n');
}
```
