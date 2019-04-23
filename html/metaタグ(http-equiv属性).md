# metaタグ(http-equiv属性)
- [参考]https://reference.hyper-text.org/html5/attribute/http-equiv/
- Content-Type:文字コードの指定のために使用
- refresh:自動更新やリダイレクトの指定のために使用


# 例

```

<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  //２秒後に、記述のURLへ遷移する
	<meta http-equiv="refresh" content="2;URL=download_csv.php">
</head>

```
