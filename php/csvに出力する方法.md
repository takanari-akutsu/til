# CSVとは
- Comma Separated Valueの略
- カンマ区切りファイルともいう

# EXCELとの違い
- セルの色付けやフォントの変更などをしたあとCSVファイルで保存すると、書式変更は保存されない

# CSVで出力するには

```

<?php
$dsn = 'mysql:host=localhost;dbname=任意のDB;charset=utf8';
$user = 'root';
$password = '';


$file_path = "○○.csv";
$export_csv_title = ["id", "shop_id", "area", "name", "kana", "address"];
$export_sql = "SELECT * FROM ○○";


try{
    $db = new PDO($dsn,$user,$password);
    $db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
}catch(PDOException $e){
    echo $e->getMessage();
    exit;
}


foreach( $export_csv_title as $key => $val ){
$export_header[] = mb_convert_encoding($val, 'SJIS', 'UTF-8');
}


if(touch($file_path)){
$file = new SplFileObject($file_path, "w");


$file->fputcsv($export_header);


$stmt = $db->query($export_sql);


while($row = $stmt->fetch(PDO::FETCH_ASSOC)){
  mb_convert_variables('SJIS','UTF8',$row);
  $file->fputcsv($row);

}


$db = null;
}

```