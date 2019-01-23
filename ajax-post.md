# Phương thức POST trong jQuery Ajax

## Sử dụng Ajax để thực hiện gửi thông tin người dùng nhập vào form để xử lí mà không cần tải lại trang

`index.php`

```
<!DOCTYPE html>
<html>
    <head>
        <title></title>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <script language="javascript" src="http://code.jquery.com/jquery-2.0.0.min.js"></script>
        <script language="javascript">
            function load_ajax(){
                $.ajax({
                    url : "result.php",
                    type : "post",
                    dataType:"text",
                    data : {
                         number : $('#number').val()
                    },
                    success : function (result){
                        $('#result').html(result);
                    }
                });
            }
        </script>
    </head>
    <body>
        <div id="result">
            Nội dung ajax sẽ được load ở đây
        </div>
        <br/>
        <input type="text" value="" id="number"/>
        <input type="button" name="clickme" id="clickme" onclick="load_ajax()" value="Click Me"/>
    </body>
</html>
```

`result.php`

```
// Nhập giá trị number bằng phương thức post
$number = isset($_POST['number']) ? (int)$_POST['number'] : false;

// Kiểm tra number có lớn hơn không hay không
if (!$number){
    die ('<h1>Vui lòng nhập một số lớn hơn không (0)</h1>');
}

// Lặp từ 1 tới number để in ra màn hình
for ($i = 1; $i <= $number; $i++){
    echo '<li>Số: '.$i.'</li>';
}
```

Trong file index.php này tôi có tạo một button, một textbox#number và tôi đã thêm vào sự kiện khi click vào button sẽ gọi đến hàm load_ajax(). Nội dung của hàm load_ajax() gồm các thông số được giải thích như bên dưới:

```
function load_ajax(){
    $.ajax({
        url : "result.php", // gửi ajax đến file result.php
        type : "post", // chọn phương thức gửi là post
        dataType:"text", // dữ liệu trả về dạng text
        data : { // Danh sách các thuộc tính sẽ gửi đi
             number : $('#number').val()
        },
        success : function (result){
            // Sau khi gửi và kết quả trả về thành công thì gán nội dung trả về
            // đó vào thẻ div có id = result
            $('#result').html(result);
        }
    });
}
```

Trong những thuộc tính trên các bạn chú ý thuộc tính data,  đây là một Object trong Javascript gồm 2 đối số key:value. Trong đó key chính là tên mà bên file result.php sẽ nhận dạng (chính là number). Còn value chính là giá trị của textbox#number.

Có thể một số bạn chưa biết điều này, tham số Ajax thực chất là một đối tượng Object bình thường trong javascript, nghĩa là bạn hoàn toàn có thể viết lại như thế này:

```
function load_ajax()
{
    // Khai báo object
    var agrs = {
        url : "result.php", // gửi ajax đến file result.php
        type : "post", // chọn phương thức gửi là post
        dataType:"text", // dữ liệu trả về dạng text
        data : { // Danh sách các thuộc tính sẽ gửi đi
             number : $('#number').val()
        },
        success : function (result){
            // Sau khi gửi và kết quả trả về thành công thì gán nội dung trả về
            // đó vào thẻ div có id = result
            $('#result').html(result);
        }
    };

    // Truyền object vào để gọi ajax
    $.ajax(agrs);
}
```

`$.post` có tác dụng lấy dữ liệu từ server bằng phương thức `HTTP POST REQUEST`, vì thế chúng ta có thể sử dụng cách này hoặc cách trên để viết Ajax.

Với cách này thì sẽ có các tham số truyền vào như sau:

`jQuery.post( url [, data ] [, success ] [, dataType ] )`

Trong đó:

- url: đường dẫn đến file cần lấy thông tin
- data: là một đối tượng object gồm các key : value sẽ gửi lên server
- success: là function sẽ xử lý khi thực hiện thành công
- dataType: là dạng dữ liệu trả về. (text, json, script, xml)

Ví dụ: Bạn thay đổi hàm load_ajax() trong file index.php với nội dung như sau:

```
function load_ajax()
{
    $.post(
            'result.php', // URL
            {number : $('#number').val()},  // Data
            function(result){ // Success
                $('#result').html(result);
            },
            'text' // dataTyppe
    );
}
```


**Nguồn:** 

https://freetuts.net/phuong-thuc-post-trong-jquery-ajax-94.html
