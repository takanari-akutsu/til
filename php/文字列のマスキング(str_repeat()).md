# 文字列をマスキングする方法
- str_repeat()を用いる


# 例

```

<?php 
	$string = "abcde";
	echo str_repeat('*', strlen($string));
?>

```
- 実行結果：*****
