# require_once関数
- ファイルを呼び出す
- 関数を定義したファイルを呼び出して、関数を使うのが一般的なよう。


# 例

```db.php

<?php
  // DBに接続
	function db_connect(){
		$dsn = 'mysql:host=localhost;dbname=nokyo;charset=utf8';
  	$user = 'root';
  	$password = '';

	  try {
	  	$db = new PDO($dsn,$user,$password);
			$db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
	  } catch(PDOException $Exception) {
	    die('エラー :' . $Exception->getMessage());
	  }
	}
?>

```


```

<?php
	require_once('db.php');
	db_connect();
?>


```