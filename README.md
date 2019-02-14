# Jquery

- Nesne seçmek -> $("p, a, div.sinif, #id")
- Method kullanımı -> $("p, a, .sinif, #id").hide().show()
- css -> $("p").css('color','red');
- Nitelik atama -> var link = $('a').attr('href');
- Nitelik silme -> var link = $('a').removeAttr('href);
- Fonksiyon kullanımı -> 
```
$(document).ready(function(){

    $.Selamet={
        gonder:function(){
            alert("İşlem başarılı");
        },
        onayla:function(isim){
            alert('onaylandı '+isim)
        }
    }
});

...

<input type="submit" onclick="$.Selamet.gonder()">
<input type="submit" onclick="$.Selamet.onayla('selamet')">
```

- click() methodu ->
```
$(document).ready(function(){

    $(".selamet li").click(function(){
        var indis = $(this).index()
       // alert(indis);
       $("#Selamet").hide(100);
    });
});

  <div class="selamet">Bana Tıkla</div>
    <ul class="selamet">
        <li>1.Li</li>
        <li>2.Li</li>
        <li>3.Li</li>
        <li>4.Li</li>
    </ul>
    <div id="Selamet"> Burası birazdan kaldırılacaktır.</div>
```
 