# スクロールに合わせてthead固定
- [参考]https://accelboon.com/tn/jquery-%E3%82%B9%E3%82%AF%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%A7table%E3%81%AE%E3%83%98%E3%83%83%E3%83%80%E3%82%92%E5%9B%BA%E5%AE%9A%E3%81%99%E3%82%8B%EF%BC%88%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3/
- 標準のtheadとスクロール用のtheadの２つを準備する（theadの内容は一緒だが、classが異なる）
- htmlのhead内でjQueryの読み込みと、関数の記述
- テーブルにclassを付けて適用
- box-sizing: border-box;にすることで、微妙なずれが生じなくなる

# 例

```

<head>
<meta charset ="UTF-8">
<title>店舗情報</title>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script>
  jQuery(function($){
      var tableSheet = $('table.sheet');
      var offset = tableSheet.offset();
      $('.fixheader').width(tableSheet.width());

      $(window).scroll(function () {
          if($(window).scrollTop() > tableSheet.offset().top
          && $(window).scrollTop() < (tableSheet.offset().top + tableSheet.height() ) ) {
              var fixheaderTop = $(window).scrollTop();
              $('.fixheader').show();
          } else {
              $('.fixheader').hide();
          }
      });

      $(window).resize(function() {
          $('.fixheader').width(tableSheet.width());
      });
  });
</script>
</head>
<body>
  <table class="fixheader" border="1" width="500px" style="display: none; position: fixed; top: 0; background-color: white; box-sizing: border-box;">
  <thead>
      <tr>
        <th width="100px">名前</th>
        <th colspan="7" width="400px">
        <?php echo $user['name'] ?>
        </th>
      </tr>
      <tr>
        <th>住所</th>
        <th colspan="7">
        <?php echo $user['address'] ?>
        </th>
      </tr>
      <tr>
        <th height="100px">営業時間</th>
        <th colspan="7">
        <?php echo $user['working'] ?>
        </th>
      </tr>
      <tr>
        <th>定休日</th>
        <th colspan="7">
        <?php echo $user['holiday'] ?>
        </th>
      </tr>
      <tr>
        <th>備考</th>
        <th colspan="7"></th>
      </tr>
      <tr>
        <th>営業日</th>
        <th>月</th>
        <th>火</th>
        <th>水</th>
        <th>木</th>
        <th>金</th>
        <th>土</th>
        <th>日</th>
      </tr>
    </thead>
  </table>
  <table class="sheet" border="1" width="500px" style="box-sizing: border-box;">
    <thead>
      <tr>
        <th width="100px">名前</th>
        <th colspan="7" width="400px">
        <?php echo $user['name'] ?>
        </th>
      </tr>
      <tr>
        <th>住所</th>
        <th colspan="7">
        <?php echo $user['address'] ?>
        </th>
      </tr>
      <tr>
        <th height="100px">営業時間</th>
        <th colspan="7">
        <?php echo $user['working'] ?>
        </th>
      </tr>
      <tr>
        <th>定休日</th>
        <th colspan="7">
        <?php echo $user['holiday'] ?>
        </th>
      </tr>
      <tr>
        <th>備考</th>
        <th colspan="7"></th>
      </tr>
      <tr>
        <th>営業日</th>
        <th>月</th>
        <th>火</th>
        <th>水</th>
        <th>木</th>
        <th>金</th>
        <th>土</th>
        <th>日</th>
      </tr>
    </thead>


```
