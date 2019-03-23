# cssの適用方法
1.外部ファイルで指定(htmlファイルにて、linkタグを使う)

```
<head>
	<link rel="stylesheet" type="text/css" href="css/sample.css">
</head>

```

※type属性は、MIMEタイプのこと。MIMEタイプとは、ファイルでいうところの拡張子のことで、データ形式を表す

2.htmlファイル内で指定(styleタグを使用する)

```
<head>
	<style type="text/css">
		p{
			color:red;
		}
	</style>
</head>

```


3.htmlファイル内で指定(style属性を使用する)

```
<p style="color:red;">サンプル</p>

```
