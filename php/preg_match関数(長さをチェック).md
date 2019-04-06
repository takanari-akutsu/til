# preg_match関数
- 文字列の長さをチェックできる
- [参考]http://phpspot.net/php/pg%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%8F%BE%EF%BC%9A%E9%95%B7%E3%81%95%E3%82%92%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%81%99%E3%82%8B%28n%E6%96%87%E5%AD%97%E4%BB%A5%E4%B8%8Am%E6%96%87%E5%AD%97%E4%BB%A5%E4%B8%8B%29.html

# 例

```

if(isset($_POST['password'])){$password = $_POST['password'];}


// パスワードの入力ルール
if(!preg_match("/^.{4,12}$/",$password)){
  $rule_password=true;
} else {
  $rule_password=false;
};


```
