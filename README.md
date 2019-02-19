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