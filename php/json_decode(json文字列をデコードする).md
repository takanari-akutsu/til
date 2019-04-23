# json_decodey関数
- json文字列をデコードする
- 第２引数を指定することで、受け取る型を指定できる（trueはobject型、falseはarray型、省略するとobject型）

# 例（ぐるなびのAPI）

```

<?php
  // $data = array(
// キーID
//   'keyid' => '○○',
// 店舗ID
//   'name' => '正宗屋',
// 住所
//   'address' => '大阪府',
// );

$url = "https://api.gnavi.co.jp/RestSearchAPI/v3/?" . http_build_query($data);

$json = json_decode(file_get_contents($url));
var_dump($json->rest[0]);
?>


```

