# Jquery

- Nesne seçmek -> $("p, a, div.sinif, #id")
- Method kullanımı -> $("p, a, .sinif, #id").hide().show()
- css -> $("p").css('color','red');
- Nitelik atama -> var link = $('a').attr('href');
- Nitelik silme -> var link = $('a').removeAttr('href);
- Fonksiyon kullanımı -> 
```javascript
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
```javascript
$(document).ready(function(){

    $(".selamet li").click(function(){
        var indis = $(this).index()
       // alert(indis);
       $("#Selamet").hide(100);
    });
});
...
  <div class="selamet">Bana Tıkla</div>
    <ul class="selamet">
        <li>1.Li</li>
        <li>2.Li</li>
        <li>3.Li</li>
        <li>4.Li</li>
    </ul>
    <div id="Selamet"> Burası birazdan kaldırılacaktır.</div>
```
 
 trim() methodu -> 
 ````javascript
$("button").click(function(){
    var deger = $("input[name=deger]").val();
    deger = $.trim();
    if(!deger){
        alert("Boş bırakmayın");
    }
})

...
<input type="text" name="Değer">
<button>sonucu al</button>
````

- on() methodu -> 
````javascript
$("body").on("click","button",function(){
    $(this).after('<button>Banada Tıkla</button>')
    });
    $("p").on({
        click:function(){
            $(this).after('<p>Burayada tıkla</p>');
        }
    });
...
<button>Buraya tıkla</button>
    <p>Burayada tıkla</p>
````

- append() methodu -> seçtiğimiz divin sonuna ekleme yapar.

````javascript
    $("a").on({
        click:function(){
            $("#selamet").append("<div> Bu yeni div </div>");
        }
    });
    ...
    <a href="#">Tıkla</a>
    <div id="selamet"></div>
````

- last Filtresi() -> son elemanı seçecer
```javascript
    $("#Selamet li:last a").css("color","red");

    $("#Selamet li").each(function(index,element){
        $(element).text("li - "+index)
    })
    ...
    <ul id="Selamet">
        <li><a href="#">1. Tab</a></li>
        <li><a href="#">2. Tab</a></li>
        <li><a href="#">3. Tab</a></li>
    </ul>
```

- hover() ->

```javascript
    $("#gel_buraya").hover(function(){
        $("#Selamet li").hide();
    },function(){
        $("#Selamet li").show();
    })
    ...
    <div>
        <p id="gel_buraya">gel buraya</p>
    <ul id="Selamet">
        <li><a href="#">1. Tab</a></li>
        <li><a href="#">2. Tab</a></li>
        <li><a href="#">3. Tab</a></li>
    </ul>
```

- eq() -> seçim yaparken kullanılır

```javascript
    $("ul li").eq(4).css("background-color","lightgreen");
    ...
    ul id="Selamet">
        <li><a href="#">1. Tab</a></li>
        <li><a href="#">2. Tab</a></li>
        <li><a href="#">3. Tab</a></li>
        <li><a href="#">4. Tab</a></li>
        <li><a href="#">5. Tab</a></li>
        <li><a href="#">6. Tab</a></li>
    </ul>
```

- parent() -> bir üst divi seçer.


```javascript
$("button").click(function(){
        $(this).parent().parent().remove();
    })
...
<ul id="Selamet">
    <li><a href="#">1. Tab<button>Kapat</button></a></li>
    <li><a href="#">2. Tab<button>Kapat</button></a></li>
    <li><a href="#">3. Tab<button>Kapat</button></a></li>
    <li><a href="#">4. Tab<button>Kapat</button></a></li>
    <li><a href="#">5. Tab<button>Kapat</button></a></li>
    <li><a href="#">6. Tab<button>Kapat</button></a></li>
</ul>
```

- serialize() methodu -> formdaki tüm verileri seçmeye yarar.

```javascript
$("button").click(function(e){
    var deger = $("#form1").serialize();
    alert(deger);
    })
...
<table>
        <tr>
            <td>Kullanıcı adı:</td>
            <td><input type="text" name="kadi"></td>
        </tr>
        <tr>
            <td>E-Posta:</td>
            <td><input type="text" name="kadi"></td>
        </tr>
</table>

```
-  change() -> değişiklik varsa tetiklenir.

```javascript
$("#change").change(function(e){
        var deger = $(this).val();
        alert(deger)
    })
...
<select name="Sehir" id="change">
    <option value="rize">rize</option>
    <option value="erzurum">erzurum</option>
</select>     
```
- html() -> html kodu ile birlikte değeri alır, değer atama işlemi görür
- text() -> yazılan değeri alır

```javascript

var deger =$('#div').html();
alert(deger);
$("#div2").html(deger);
...
<div id="div" class="selamet"> <strong> bir</strong> Deneme</div>
<div id="div2"></div>
<input type="text" name deger1>
<button class="class ">İşlem yap</button>
```

- val() -> form elemanlarını alıp üzerinde işlem gerçekleştirir

```javascript
$('button').click(function(e){
    $('input').val("yeni değer")
});
...
<input type="text" name deger1>
```

- toggleClass() -> toggle mantığı ile sınıf değiştirir
- addClass()-> sınıf atama
- removeClass()-> sınıf silme

```javascript
$("#div").click(function(e){
        $(this).toggleClass("selamet2")
});
...
<style type="text/css">
    .selamet1 {background: lightblue;border: 5px solid #ddd;padding: 10px}
    .selamet2 {background: green;border: 5px solid #ddd;padding: 10px}
</style>
...
<div id="div" class="selamet1">  bir Deneme</div>

```

- clone() ->

```javascript
var clone=$("#div").clone();
$("#div").after(clone);
...
<div class="selamet1" id="div">Bu bir normal div</div>
```

- wrap() -> seçilen nesneyi classın içerisine dahil eder

```javascript
$(".deneme").wrap('<div class="selamet1"></div>')
...
<div class="deneme">Bu bir deneme dividir</div>
```

- next() -> seçili olan class veya id den sonrası üzerinde işlem gerçekleştirir.

```javascript
$("#input").next().hide();
...
<input type="text" name=deger1 id=input value="ara">
```

- error() ->

```javascript
$("img").error(function(){
        $(this).attr("src","eklenecek url")
});
```

- one() -> Tek bir kez çalışır

```javascript
$("button").one("click",function(){
        $("span").toggle();
});    
...
<button>Göster/gizle</button>
<span>deneme</span>
```

- submit() -> formlarda post işlemi gerçekleştiri

```javascript
$(".deneme").click(function(){
        $("form").submit(function(){
            var deger = $("input[name=deneme]").val();
            alert(deger);
            if(deger == ''){
                alert("boş")
                return false;
            }
            return true;
        }).submit();
    });
...
<div class="deneme">Formu post et</div>
<form method="POST">
    <input type="text" name=deneme/>
</form>
```