# http_build_query関数
- URLエンコードされたクエリ文字列を生成

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
?>


```

