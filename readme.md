# Jquery
웹사이트에 자바스크립트를 쉽게 활용할 수 있도록 도와주는 오픈소스 기반의 자바스크립트 라이브러리로서 2006년 미국의 소프트웨어 개발자 존 레식(John Resig)이 발표한 것으로서 웹 문서에서 자바스크립트를 활용하면, 문장이 길어지고, 복잡해지지만, jQuery를 활용하면, 문장이 간결해지고, DOM 요소의 접근과 제어하는데 개발시간을 단축시킬 수 있으나 2015년 이후 점차 쇄락해나가고 있으나, 대한민국에서는 아직도 복잡한 구문을 간결하게 해주거나 Ajax와 같은 처리를 할 경우에 많이 활용되고 있는 것이 사실이다. 차세대 대체 라이브러리인 Lodash나 Moment의 근간이 되므로 jQuery를 활용할 줄 안다면, 이 또한 활용할 수 있을 거라 생각되며, 현재 까지 개발된 3.x 버전의 단점을 보완하며, 뒤를 이어 차기 버전인 4.x 의 발표로 그 동안 빼앗겨 오던 위상을 되찾을 수 있을 거라 내다본다.


<br><hr><br>

## jQuery의 연결
```html
<!-- CDN 연결 방식 -->
<script src="https://code.jquery.com/jquery-latest.js"><script>
<!-- 다운로드 받아 연결하는 방식 -->
<script src="./js/jquery-1.12.4.js"></script>    
```

<br><hr><br>

## jQuery의 적용
```html
<script src="./js/jquery-1.12.4.js"></script>  
<script>
    //제어할 요소의 위에 스크립팅하는 경우
    //$("선택자").메소드();
    $(document).ready(function(){
        $("span").text("Before Hello jQuery");
    });
</script>
<div></div>
<span></span>
<script>
    //제어할 요소의 아래에 스크립팅하는 경우
    $(function(){
        $("div").text("After Hello jQuery");
    });
</script>
```

<br><hr><br>

## jQuery 선택자(Selector)
- 문서를 동적으로 제어할 요소를 선택해야 하는데 이러한 경우 해당 요소를 선택하기 위한 문자열을 말하며, 이 때 선택되는 요소를 DOM 구조상 엘리먼트라고 부르기도 한다.

| 선택자 | 설명 |
|------------------|--------------------------------------|
| $("*") | 페이지 내의 모든 엘리먼트를 선택 |
| $("태그명") | 페이지 내의 해당 태그의 엘리먼트를 선택 |
| $("#아이디") | 페이지 내의 해당 id를 가진 엘리먼트를 선택 |
| $(".클래스명") | 페이지 내의 해당 class를 가진 여러 엘리먼트를 선택 |
| $("부모 > 자식") | 부모 요소의 자식 요소에 해당하는 엘리먼트를 선택 |
| $("조상 후손") | 조상 요소 안에 있는 자식 요소를 포함한 모든 하위 요소에 속하는 엘리먼트를 선택 |
| $("형 + 아우") | 형 요소의 바로 다음에 있는 하나의 아우에 해당하는 엘리먼트를 선택 |
| $("형 ~ 아우들") | 형 요소의 다음에 있는 아우들에 해당하는 엘리먼트를 선택 |
| $("요소:odd") | 페이지 전체에서 해당 요소의 인덱스가 홀수 번째인 요소를 선택 |
| $("요소:even") | 페이지 전체에서 해당 요소의 인덱스가 짝수 번째인 요소를 선택 |
| $("요소:eq(idx)") | 페이지 전체에서 해당 요소의 인덱스가 idx 번째인 요소를 선택 |
| $("요소:gt(idx)") | 페이지 전체에서 해당 요소의 인덱스가 idx 보다 큰 요소를 선택 |
| $("요소:lt(idx)") | 페이지 전체에서 해당 요소의 인덱스가 idx 보다 작은 요소를 선택 |
| $("not(상태선택자)") | 현재 상태에 속하지 않는 요소를 선택 |
| $("요소:first") | 페이지 전체에서 해당 요소의 첫 번째인 요소를 선택 |
| $("요소:last") | 페이지 전체에서 해당 요소의 마지막 번째인 요소를 선택 |
| $("요소:first-child") | 각 그룹에서 해당 요소의 첫 번째인 요소를 선택 |
| $("요소:last-child") | 각 그룹에서 해당 요소의 마지막 번째인 요소를 선택 |
| $("요소:nth-child(n)") | 각 그룹에서 해당 요소의 n 번째인 요소를 선택 |
| $("요소:nth-child(odd)") | 각 그룹에서 해당 요소의 홀수 번째인 요소를 선택 |
| $("요소:nth-child(even)") | 각 그룹에서 해당 요소의 짝수 번째인 요소를 선택 |
| $("요소:empty") | 각 그룹에서 텍스트나 하위 요소가 없는 요소를 선택 |
| $("요소:contains(문자열)") | 지정한 요소 중에서 해당 문자열이 있는 요소를 선택 |
| $("요소:has(하위요소)") | 지정한 요소 중에서 해당 하위 요소가 있는 요소를 선택 |
| $("[속성]") | 해당하는 태그의 속성이 존재하는 요소를 선택 |
| $("[속성='값']") | 해당하는 태그의 속성의 값이 일치하는 요소를 선택 |
| $("[속성^='값']") | 태그의 속성이 지정한 값으로 시작하는 요소를 선택 = 접두사 |
| $("[속성&#x24;='값']") | 태그의 속성이 지정한 값으로 끝나는 요소를 선택 = 접미사 |
| $("[속성*='값']") | 태그의 속성이 지정한 조건이 포함되는 요소를 선택 = 포함하는 문자열 |
| $(":button") | 폼 컨트롤 input의 type이 button인 요소를 선택 |
| $(":checkbox") | 폼 컨트롤 input의 type이 checkbox인 요소를 선택 |
| $(":file") | 폼 컨트롤 input의 type이 file인 요소를 선택 |
| $(":image") | 폼 컨트롤 input의 type이 image인 요소를 선택 |
| $(":password") | 폼 컨트롤 input의 type이 password인 요소를 선택 |
| $(":radio") | 폼 컨트롤 input의 type이 radio인 요소를 선택 |
| $(":reset") | 폼 컨트롤 input의 type이 reset인 요소를 선택 |
| $(":submit") | 폼 컨트롤 input의 type이 submit인 요소를 선택 |
| $(":text") | 폼 컨트롤 input의 type이 text인 요소를 선택 |
| $(":checked") | 폼 컨트롤중 type이 radio이거나 checkbox인 요소를 선택 |
| $(":selected") | 폼 컨트롤중 option 요소 중 selected된 요소를 선택 |
| $(":enabled") | 폼 컨트롤중 활성화된 요소를 선택 |
| $(":disabled") | 폼 컨트롤중 비활성화된 요소를 선택 |
| $(":focus") | 폼 컨트롤중 커서가 있는 요소를 선택 |
| $(":animated") | 현재 애니메이션중인 요소를 선택 |

### jQuery 기본 선택자
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 선택자</title>
    <script src="jquery-1.12.4.js"></script>
    <style>
    .highlight { font-weight:900; }
    </style>
</head>
<body>
    <div id="con">
        <ul class="lst">
            <li><a href="https://jquery.com">텍스트1</a></li>
            <li><a href="index.html">텍스트2</a></li>
            <li><a>텍스트3</a></li>
        </ul>
    </div>
    <br>
    <button type="button" id="btn1">버튼1</button>
    <br>
    <script>
    $(function(){
        //jQuery 선택자 연습
        $("*").css("margin","0px").css("padding","0px");    //전체 선택자
        $("a").css("text-decoration", "none").css("color","deeppink").addClass("highlight");    //태그 선택자
        $("#con").css({"margin-top":"30px", "padding":"20px"}); //아이디 선택자
        $(".lst").css("list-style", "none");    //클래스 선택자
        $("a[href]").css("background-color", "deepskyblue");    //속성 존재유무 선택자
        $("a[href*='https'").css("padding","15px"); //속성 포함하는 선택자
        $("a[href$='.html'").css("background","orange");    

        //속성 선택자
        //속성 일치 [속성='값']
        //속성 불일치 [속성!='값']
        //포함하는 문자열 : [속성*='문자열'] 
        //속성 접미사 : [속성$='접미사'] [속성~='접미사']
        //속성 접두사 : [속성|='접두사'], [속성^='접두사']

        //순서 위치 선택자
        //첫 번째 요소 : :first-child, :first-of-type, :eq(0), :nth-child(1), :nth-of-type(1), :first
        //특정 번째 요소  :nth-child(n번째), :nth-of-type(n번째), :eq(인덱스)
        //마지막 요소   :last-chlid, :last-of-type, :last
        //:even  짝수 번째 요소
        //:odd  홀수 번째 요소 
        //:empty  내용이 없는 요소 선택
        //only-of-type  내부 요소가 혼자인 경우 선택
        //범위 요소   :lt(인덱스), :gt(인덱스)

        //가상 요소 선택자
        //:before : 특정 요소의 앞 부분 선택
        //:after : 특정 요소의 뒤 부분 선택
        //:checked : 체크박스나 라디오 버튼이 체크된 경우 선택
        //:animated : 애니메이션이 동작 중인 요소 선택
        //:focus : 현재 커서가 위치한 요소 선택
        //:enabled : 사용 가능한 폼 요소 선택
        //:disabled : 사용이 불가능한 요소 선택
        //:selected : 셀렉트 된 요소 선택
        //:readonly : 읽기 전용이 적용된 요소 선택
        //:required : 필수 요소로 적용된 요소 선택
        //:visible : 화면에 보여지는 요소 선택

        // 폼 요소(type) 선택자
        //:button : 버튼 요소 선택  
        //:text : 텍스트 요소 선택
        //:password : 패스워드 요소 선택
        //:checkbox : 체크 박스 요소 선택
        //:radio : 라디오 버튼 요소 선택
        //:file  : 파일 요소 선택
        //:hidden : 히든 요소 선택
        //:submit : 서브밋 요소 선택
        //:reset : 리셋 요소 선택
        //:input : 입력 요소 선택

        $("#btn1").click(function(){
            var cnt = $(".lst li").length + 1;  //후손 선택자
            //var cnt = $(".lst > li").length + 1;  - 자식 선택자
            $(".lst").append("<li><a href=''>텍스트"+cnt+"</a></li>")
        });
        
    });    
    </script>
</body>
</html>
```

### jQuery 복수 요소의 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jquery 03 - 복수 요소 선택</title>
    <script src="./jquery-1.12.4.js"></script>
    <script>
    $(document).ready(function(){
        var $dt = $("span, .simpletext1, p");       //선택자 변수
        $(".container").append("<div class='res'>요소의 개수 : "+$dt.length+"</div>");
    });    
    </script>
</head>
<body>
    <h1>복수 요소의 선택</h1>
    <div class="container">
        <span>Simple</span>
        <div class="simpletext1">jQuery</div>
        <div>basic</div>
        <p>example</p>
        <p>easyJquery</p>
    </div>
    <div class="container"></div><div class="container"></div>
</body>
</html>
```

### jQuery 자식과 후손 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 04 - 후손 요소와 자식 요소</title>
    <script src="./jquery-1.12.4.js"></script>
</head>
<body>
    <section class="container">
        <h1>후손과 자식 요소 선택</h1>
        <div>
            <em>Hello!</em>   <em>jQuery</em>   <p><em>plugin</em></p> <em>forever</em>
         </div><br><hr><br>
         <span>
            <em>Good Bye!</em>   <em>javascript</em> <p><em>plugin</em></p>
         </span> 
    </section>
    <script>
    $(function(){
        $("div > em").css("color", "red");  //div 자식 em 요소 선택
        $("div em").css("backgroundColor", "yellow");   //div 후손 em 요소 선택
        //span 자식 em요소에 글자색을 흰색(white)로 할 것
        $("span > em").css("color", "white"); 
        //span 후손 em요소에 배경색을 딥핑크(deeppink)로 할 것
        $("span em").css("background-color", "deeppink"); 
    });    
    </script>
</body>
</html>
```

### jQuery 자식과 후손 노드에 대한 접근
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 05 - 후손 요소와 자식 요소2</title>
    <script src="./jquery-1.12.4.js"></script>  
</head>
<body>
    <section class="container">
        <h1>후손과 자식 요소의 접근 제어</h1>
        <p>
            <em> one  </em>      <em> two  </em>   <span> <em> three </em> </span>
         </p>
        <div>
            <em> <ins>four</ins> </em>      <span> <em> <ins>five</ins>  </em> </span>       <em><ins>six</ins></em> 
        </div>
    </section><br><hr><br>
    <div>    
        <span> ancestor descendant로 검색된 엘리먼트 : </span><span class="result1"></span>
     </div>
     <div>    
        <span> parent &gt; child로 검색된 엘리먼트 : </span><span class="result2"></span>
     </div>
     <script>
     $(function(){
        //클래스가 result1인 곳에 p의 후손 요소인 em의 text를 출력하시오.
        var res1 = "";
        $("p em").each(function(){
            res1 += $(this).text();
        });
        $(".result1").text(res1);
        //클래스가 result2인 곳에 div의 자식 요소인 em의 text를 출력하시오.
        var res2 = "";
        $("div > em").each(function(){
            res2 += $(this).text();     //res2 += $(this).html();
        });
        $(".result2").text(res2);   //$(".result2").html(res2);
     });   
     </script>
</body>
</html>
```

### jQuery의 동생(next) 요소의 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 06 : prev + next, prev ~ nextall</title>
    <script src="./jquery-1.12.4.js"></script>  
</head>
<body>
    <section class="container">
        <h1>인접 요소 선택</h1>
        <p>
            <em> one  </em>   <a> two  </a>   <a> three  </a>   <b> four </b>   <a> five </a>   <em> six </em>
            <a> seven </a>
        </p>
    </section><br><hr><br>
    <div>
        <span> prev + next로 검색된 엘리먼트 : </span>
        <span class="result1"></span>
     </div>
     <div id="result2">
        <span> prev ~ nextall로 검색된 엘리먼트 : </span>
     </div> 
     <script>
     $(function(){
        //em의 바로 다음에 나오는 a요소의 텍스트를 찾아 클래스가 result1인 곳에 출력
        var $t = $("em + a");
        $t.each(function(){
            $(".result1").append($(this).text());
        });
        $(".result1").append(", <span>요소의 수 : "+$t.length+"</span>");
        //em의 동생들 요소중에서 a요소의 텍스트를 찾아 아이디가 result2인 곳에 출력
        var len = 0;
        $.each($("em ~ a"), function(index, value) {
            len++;
            $("#result2").append(value);
        });
        $("#result2").append(", <span>요소의 수 : "+len+"</span>");
     });   
     </script> 
</body>
</html>
```

### jQuery 첫 요소(first)와 마지막 요소(last)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 07 : 첫 요소와 마지막 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
   table { table-layout:auto;   width: 75%;}
   td { color: blue;   font-weight: bold; }
   .selectedstyle {color: red;  font-size: 20pt;   background-color: pink;  }
    </style>
</head>
<body>
    <script>
    $(document).ready(function(){
    //td의 첫 요소와 마지막 요소를 선택하여 해당 요소에 selectedstyle 클래스를 부여하고, 첫 요소의 텍스트는 클래스 result1에 마지막 요소의 텍스트는 클래스 result2에 출력
        $("td:first, td:last").addClass("selectedstyle");
        $(".result1").text("첫 요소 : "+$("td:first").text());
        $(".result2").text("마지막 요소 : "+$("td:last").text());
    });    
    </script>
    <section class="container">
        <h1>첫 요소(:first)와 마지막 요소(:last)</h1>
        <table>
            <tr><td>one</td></tr>       <tr><td>two</td></tr>       <tr><td>three</td></tr>
            <tr><td>four</td></tr>       <tr><td>five</td></tr>
         </table>
    </section><br><hr><br>
    <div class="result1"></div><div class="result2"></div>
</body>
</html>
```

### jQuery의 짝수(even) 번째 요소와 홀수(odd) 번째 요소
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 08 : 짝수 번째 요소와 홀수 번째 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>  table {   table-layout:auto;   width: 75%;} </style>
</head>
<body>
    <script>
    $(document).ready(function(){
        //td의 인덱스가 짝수 번째는 글자색을 빨강, 글자 크기를 30px로 변경 - 메서드 체이닝
        $("td:even").css("color", "#ff0000").css("font-size", "30px");
        //td의 인덱스 홀수 번째는 배경색을 빨강, 글자 크기를 30pt로 변경 - 속성 열거법
        $("td:odd").css({"background-color":"red", "font-size":"30pt"});
    });    
    </script>
    <section class="container">
        <h1>짝수 번째 요소(:even)와 홀수 번째 요소(:odd)</h1>
        <table>
            <tr><td>zero</td></tr><tr><td>one</td></tr>
            <tr><td>two</td></tr><tr><td>three</td></tr>
            <tr><td>four</td></tr><tr><td>five</td></tr>
         </table>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 인덱스를 활용한 특정(n) 번째 요소 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 09 : 특정 번째 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>  table {   table-layout:auto;   width: 75%;} </style>
</head>
<body>
    <section class="container">
        <h1>특정 번째 요소 - eq(index), nth-child(n)</h1>
        <table>
            <tr><td>zero</td><td>one</td><td>two</td></tr><tr><td>three</td><td>four</td><td>five</td></tr>
         </table>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //td의 3의 배수 번째는 글자색을 빨강, 글자 두께를 900으로 변경 - nth-child(n)
        $("td:nth-child(3n)").css({"color":"red", "font-weight":"900"});
        //td의 네 번째 요소에 배경색을 핑크색, 글자색을 빨강으로 변경 - eq(index)
        $("td:eq(3)").css("background-color", "pink").css("color", "red");
    });    
    </script>
</body>
</html>
```

### jQuery 전(less then) 후(great then) 요소로 범위 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 10 : 후 혹은 전에 위치한 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>  
    table {   table-layout:auto;   width: 75%;} 
    .textstyle { color: blue;   font-weight: bold; background-color: pink}  
    </style>
</head>
<body>
    <section class="container">
        <h1>후(:gt()) 혹은 전(:lt())에 위치한 요소</h1>
        <table>
            <tr><td>zero</td></tr><tr><td>one</td></tr><tr><td>two</td></tr>
            <tr><td>three</td></tr><tr><td>four</td></tr><tr><td>five</td></tr>
         </table>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //eq(index), lt(index), gt(index)
        //td의 세 번째 후 요소에 글자색을 빨강으로 변경
        $("td:gt(2)").css("color", "red");
        //td의 다섯 번째 전 요소에 textstyle 클래스를 부여
        $("td:lt(4)").addClass("textstyle");
    });    
    </script>
</body>
</html>
```
### jQuery 첫 번째 자식(first child)와 마지막 자식(last child) 요소 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 11 : 첫 번째 자식 요소와 마지막 자식 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
</head>
<body>
    <section class="container">
        <h1>첫 번째 자식 요소(:first-child)와 마지막 자식 요소(:last-child)</h1>
        <div> 
            <span>one,</span><span>two,</span><span>three,</span><span>four</span>
        </div> 
        <div>      
            <span>five,</span><span>six,</span><span>seven,</span><span>eight</span>
        </div>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //span의 첫 번째 자식 요소와 마지막 자식 요소에 배경색을 딥핑크로 설정
        $("span:first-child, span:last-child").css("background", "deeppink");
    });    
    </script>
</body>
</html>
```

### jQuery 특정(n) 번째 자식 요소 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 12 : 특정 번째 자식 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
</head>
<body>
    <section class="container">
        <h1>특정 번째 자식 요소(:nth-child(n))</h1>
        <div>
            <ul><li>사과</li><li>바나나</li><li>복숭아</li></ul>
         </div>
         <div><ul><li>소나타</li></ul></div>
         <div>
            <ul><li>코끼리</li><li>뱀</li><li>토끼</li><li>말</li></ul>
         </div>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //li중에서 홀수 번째 자식 요소마다 글자색을 파랑으로 함.
        $("li:nth-child(odd)").css("color","blue");
        //$("li:nth-child(2n+1)").css("color","blue");
        //li중에서 짝수 번째 자식 요소마다 글자색을 빨강으로 함.
        $("li:nth-child(even)").css("color","red");
        //$("li:nth-child(2n)").css("color","red");
        //li중에서 2번 째 요소마다 배경색을 하늘색으로 하며, 2nd~! 텍스트를 추가
        $("li:nth-child(2)").css("background-color","skyblue").append(" - 2nd~!");
    });    
    </script>
</body>
</html>
```

### jQuery 체크박스(checkbox)의 선택
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 13 - :checkbox, :checked, not(:checked)</title>
    <script src="./jquery-1.12.4.js"></script> 
</head>
<body>
    <section class="container">
        <h1>체크박스(:checkbox), 체크된 상태(:checked), 체크되지 않은 상태(not(:checked))</h1>
        <div>
            <h2>좋아하는 과일은 ?</h2>
        </div>
        <div>
            <input type="checkbox" name="fruit" /> <span>샤인머스킷</span>
        </div>
        <div>
            <input type="checkbox" name="fruit" /> <span>망고</span>
        </div>
        <div>
            <input type="checkbox" name="fruit" checked="checked" /><span>두리안</span>
        </div>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //체크박스의 다음 요소 span에 배경색을 빨강으로 설정
        $("input:checkbox + span").css("background","red");
        //$("input[type=checkbox]").css("background","red");

        $("input[type=checkbox]:checked + span").css("color", "green");
        $("input[type=checkbox]:not(:checked) + span").css("color", "white");

        $("input:checkbox").click(function(){
            //체크박스가 체크되면, 그 다음 요소 span의 글자색을 그린으로 변경
            $("input[type=checkbox]:checked + span").css("color", "green");
            //체크박스가 체크 해제되면, 그 다음 요소 span의 글자색을 흰색으로 변경
            $("input[type=checkbox]:not(:checked) + span").css("color", "white");
        });
        //이벤트트리거 : 이벤트를 자동으로 강제 발생  
        //$(선택자).이벤트메서드(function(){ 이벤트내용; }).이벤트메서드()
    });    
    </script>
</body>
</html>
```

### jQuery의 속성 선택자
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 14 : 속성 선택자</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .spotlight {   background-color: #ff0;}
    .redtext {   color: #f00;}
    .bluetext {   color: #00f;}
    .largetext {   font-size: 30pt;}
    .italictext {   font-style: italic;}
    .box {   border: 3px solid #f00;}
    </style>
</head>
<body>
    <section class="container">
        <h1>속성 선택자</h1>
        <div> 
            <span data="simpletext1">simple</span>
            <span class="simpletext2">jQuery</span>
            <span data="complextext1">basic</span>
            <span data="complextext2">example</span>
            <span data="complex">book</span>
        </div> 
    </section><br><hr><br>
    <script>
    $(function(){
        //data 속성이 있는 요소에 대하여 spotlight 클래스 추가
        $("[data]").addClass("spotlight");
        //data 속성이 comple 로 시작하는 요소에 대하여 redtext 클래스를 추가
        $("[data^='comple']").addClass("redtext");
        //$("[data|='comple']").addClass("redtext");
        //data 속성이 text1로 끝나는 요소에 대하여 box 클래스를 추가
        $("[data$='text1']").addClass("box");
        //data 속성이 text가 포함된 요소에 대하여 largetext 클래스를 추가
        $("[data*='text']").addClass("largetext");
        //$("[data~='text']").addClass("largetext");
    });    
    </script>
</body>
</html>
```

### jQuery 속성(attribute) 선택자의 응용
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 15 : 속성 선택자2</title>
    <script src="./jquery-1.12.4.js"></script> 
</head>
<body>
    <section class="container">
        <h1>속성 선택자 응용</h1>
        <div id="imgList">
            <img src="a.jpg" alt=""><img src="b.png" alt=""><img src="c.gif" alt="">
        </div>
        <nav id="gnb">
            <ul>
                <li><a href="company.jsp">회사소개</a></li>
                <li><a href="proList.do">제품</a></li>
                <li><a href="serList.jsp?serno=1">서비스</a></li>
                <li><a href="boardList.do">커뮤니티</a></li>
                <li><a href="consulList.do?sid=kim">온라인 상담</a></li>
            </ul>
        </nav>
        <nav id="quick"><ul class="menu"></ul></nav>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //아이디가 imgList인 내부 요소 img의 너비를 200px, 높이를 300px로 변경
        $("#imgList img").width(200).height(300);
        //아이디가 imgList인 내부 요소 img의 src속성이 jpg인 경우 5px 빨간색 테두리
        $("#imgList img[src$='.jpg']").css("border","5px solid red");
        //아이디가 imgList인 내부 요소 img의 src속성이 png인 경우 5px 초록색 테두리
        $("#imgList img[src$='.png']").css("border","5px solid green");
        //아이디가 imgList인 내부 요소 img의 src속성이 gif인 경우 5px 파란색 테두리
        $("#imgList img[src$='.gif']").css("border","5px solid blue");
        //아이디가 gnb인 내부 요소인 a 요소의 href속성에 .do가 포함되어 있는 요소만 
        //아이디가 quick안의 클래스 menu의 내부 요소로 추가
        $("#gnb a[href*='.do']").each(function(){
            $("#quick .menu").append("<li><a href='"+$(this).attr("href")+"'>"+$(this).text()+"</a></li>");
        });
    });    
    </script>
</body>
</html>
```

### jQuery 폼 컨트롤 요소의 선택자
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 16 : 폼 컨트롤 선택자</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
    div { clear:both; }
    label { display:inline-block; width:100px; }  
    </style>
</head>
<body>
    <section class="container">
        <h1>폼 컨트롤 선택자</h1>
        <article id="joinFrm">
            <div class="item"> 
                <label for="userId"> 아이디 * </label> 
                <input id="userId" type="text">
            </div>
            <div class="item"> 
                <label for="userName"> 이름   * </label> 
                <input id="userName" type="text" value="성명을 입력">
            </div>
            <div class="item"> 
                <label for="pwd"> 암호   * </label> 
                <input id="pwd" type="password">
            </div>
            <div class="item"> 
                <label for="pwdConfirm"> 암호 확인  * </label> 
                <input id="pwdConfirm" type="password">
            </div>
            <input type="button" id="regBtn" value="회원가입">      
        </article>
    </section><br><hr><br>
    <div id="msg"></div>
    <script>
    $(document).ready(function(){
   //아이디, 이름, 암호, 암호확인을 입력하고, #regBtn을 누르면
   //데이터의 유효성을 검사하도록 하고, 그 데이터를 ajaxJoin.do로
   //비동기방식으로 보내도록 하시오.
        $("#userName").click(function(){
            $(this).val("");
        });
        var pass = "no";
        var source;
        $(":button").click(function(){
            $(":text, :password").each(function(){
                if($(this).val()==""){
                    alert("입력 데이터가 비어 있습니다.");
                    return false;
                } else {
                    pass = "yes";
                }
            });
        });
        if(pass=="yes"){
            source = { "id":$("#usetId").val(), "pw":$("#pwd").val(), "name":$("#userName").val() };
            $.ajax({
                url:"ajaxJoin.do?member="+source,  
                type:"get",
                dataType:"json",
                success:function(res){
                    $("#msg").text(res);
                },
                error:function(res, status, err){
                    alert(res+"가 "+err+"로 인해서 정상적으로 처리되지 못했습니다.");
                }
            });
        }
    });    
    </script>
</body>
</html>
```

<br><hr><br>

## jQuery 기본(Basic) 메소드
jQuery에 주로 많이 사용하는 기본적인 메소드로 스타일이나 클래스, 태그의 속성, 해당 요소의 값을 설정하거나 설정된 값을 가져올 때 활용된다.

| 메소드 | 설명 |
|------------------|--------------------------------------|
| attr("태그속성", [태그속성값]) | 선택한 요소에 지정한 태그 속성을 가져오거나 설정 |
| removeAttr("태그속성") | 선택한 요소에 지정한 태그 속성을 제거 |
| prop("태그속성", [태그속성값]) | 선택한 요소에 지정한 태그 속성을 가져오거나 설정 |
| removeProp() | 선택한 요소에 지정한 태그 속성을 제거 |
| css("스타일속성", [스타일속성값]) | 선택한 요소에 지정한 태그 속성을 가져오거나 설정 |
| addClass("클래스명") | 선택한 요소에 지정한 클래스를 추가 |
| hasClass("클래스명") | 선택한 요소에 지정한 클래스의 존재 여부를 확인 |
| removeClass("클래스명") | 선택한 요소에서 지정한 클래스를 제거 |
| toggleClass("클래스명") | 선택한 요소에서 지정한 클래스를 교대로 추가/제거 |
| html(["태그포함텍스트"]) | 선택한 요소에서 태그를 포함한 내용을 가져오거나 설정 |
| text(["텍스트"]) | 선택한 요소에서 텍스트 내용을 가져오거나 설정 |
| val(["값"]) | 선택한 폼 콘트롤 요소에서 값을 가져오거나 설정 |
※ []는 생략가능한 값으로 생략시에는 getter의 역할을 수행하며, 지정시에는 setter의 역할을 한다.

### jQuery 태그 속성 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 17 : attribute 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
    div { clear:both; }
    label { display:inline-block; width:100px; }  
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - attr()</h1>
        <article class="data">
            <img data-value="미인 이미지"/>
            <div class="comment"><strong>어트리뷰트 연습 : </strong></div>
            <div class="res"></div>
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //img 첫 요소에 src 속성을 임의 이미지로 연결하고, title 속성을 "아름다운 사람들"로 지정
        $("img:eq(0)").attr({"src":"blackpink.jpg", "title":"아름다운 사람들"});
        $("img:eq(0)").attr("alt", $("img:eq(0)").attr("data-value"));
        //img 첫 요소에 지정된 title 값을 클래스가 comment인 곳에 요소로 추가
        $(".comment").append($("img:eq(0)").attr("title"));
        //img 첫 요소에 지정된 data-value 값을 클래스가 res인 곳에 텍스트로 추가
        $(".res").text($("img:eq(0)").attr("data-value"));
    });    
    </script>
</body>
</html>
```

### jQuery 태그 속성 제거 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 18 : attribute 제거 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
    .imgFrame { width:90px; margin:60px auto; border-bottom:3px dashed #333;
     border-top:3px dashed #333; padding-top:10px; }
    .imgFrame button { border:0; outline:0; background:#333;
        color:#fff; width:90px; height:40px; margin-bottom:40px; } 
    .imgFrame img { width:200px; }
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - removeAttr()</h1>
        <article class="data">
            <div class="imgFrame">
                <button> 어트리뷰트 값 제거하기 </button> 
                <img src="yourPhoto1.jpg" title="당신의 애인사진1" alt="Lover picture">
           </div>     
           <div class="imgFrame">
                <button> 어트리뷰트 값 제거하기 </button> 
                <img src="yourPhoto2.jpg" title="당신의 애인사진2" alt="Lover picture"> 
           </div>
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //버튼을 클릭하면, 그 버튼의 다음 요소인 img 요소의 src 속성을 제거하시오.
        $("button").click(function(){
            $(this).next().removeAttr("src");
        });
    });    
    </script>
</body>
</html>
```

### jQuery 스타일 클래스 추가 및 제거 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 19 : class 추가 및 제거 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
	.gbor {   border:10px solid green;     }
    .data img { width: 200px; transition-duration:0.8s;}
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - addClass(), removeClass()</h1>
        <article class="data">
            <button> 선색 변경 </button>
            <img src="jinkyoung1.jpg" title="당신의 애인사진1" alt="Lover picture" class="img1">
            <img src="jinkyoung2.jpg" title="당신의 애인사진2" alt="Lover picture" class="img1">
            <img src="blackpink.jpg" title="당신의 애인사진2" alt="Lover picture" class="img2">
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        var sw = true;
        //버튼을 클릭하면, img1 클래스의 img 요소에 .gbor을 교대로 적용(스위치 개념)
        $("button").click(function(){
            if(sw) {
                $(".img1").addClass("gbor");
            } else {
                $(".img1").removeClass("gbor");
            }
            sw = !sw;
        });
    });    
    </script>
</body>
</html>
```

### jQuery 스타일 클래스의 On/Off
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 20 : class On/Off 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
	.gbor {   border:10px solid green;  transition-duration:0.8s;   }
    .data img { width: 200px; transition-duration:0.8s;}
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - toggleClass()</h1>
        <article class="data">
            <button> 선색 변경 </button>
            <img src="jinkyoung1.jpg" title="당신의 애인사진1" alt="Lover picture" class="img1">
            <img src="jinkyoung2.jpg" title="당신의 애인사진2" alt="Lover picture" class="img1">
            <img src="blackpink.jpg" title="당신의 애인사진2" alt="Lover picture" class="img2">
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //버튼을 클릭하면, img1 클래스의 img 요소에 .gbor을 교대로 적용
        $("button").click(function(){
            $(".img1").toggleClass("gbor");
        });
    });    
    </script>
</body>
</html>
```

### jQuery 스타일 클래스의 존재 여부 확인 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 21 : class 존재 여부 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
	.gbor {   border:10px solid green;  transition-duration:0.8s;   }
	.bbor {   border:10px solid blue;  transition-duration:0.8s;   }
    .rbor {   border:10px solid red;   transition-duration:0.8s;  }
    .data img { width: 200px; transition-duration:0.8s;}
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - hasClass()</h1>
        <article class="data">
            <button> 선색 변경 </button>
            <img src="jinkyoung1.jpg" title="당신의 애인사진1" alt="Lover picture" class="img1 gbor">
            <img src="jinkyoung2.jpg" title="당신의 애인사진2" alt="Lover picture" class="img1 bbor">
            <img src="blackpink.jpg" title="당신의 애인사진2" alt="Lover picture" class="img1 rbor">
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //버튼을 클릭하면, img1 클래스의 img 요소에 .gbor, .bbor, .rbor 을 교대로 적용
        $("button").click(function(){
            $(".img1").each(function(){
                if($(this).hasClass("gbor")){
                $(this).removeClass("gbor").addClass("bbor");
                } else if($(this).hasClass("bbor")) {
                    $(this).removeClass("bbor").addClass("rbor");
                } else {
                    $(this).removeClass("rbor").addClass("gbor");
                }
            });
        });
    });    
    </script>
</body>
</html>
```

### jQuery 텍스트 및 html의 get과 set 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 22 : 텍스트 및 태그 get/set 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
    p {   margin: 14px;    cursor: pointer;}
    b {   text-decoration: underline;}
    button {   cursor: pointer;}
    #console{    font-size: 20px;    color: blue;  font-weight: bold;}
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - text(), html()</h1>
        <article class="data">
            <p><b> 난 너에게 </b> 내 친구를 <span id="tag"> 소개시켜 줬고 </span></p>
            <p>그런 <span id="text"> 만남이 </span> 있은 후 부터</p>
            <p>넌 내게 <button name="oktbtn">조금씩</button> 멀어지는 것을 느끼며</p>
            <div id="console"></div>
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        var sw = true;
        //p 요소를 클릭하면, 클릭된 요소의 태그를 포함하여 아이디가 console인 곳에 텍스트 형태로 출력
        $("p").click(function(){
            $("#console").text($(this).html());
        });
    });    
    </script>
</body>
</html>
```

### jQuery 폼 컨트롤 요소의 값 get과 set
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 23 : 폼 요소의 get/set 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; }  
	.gbor {   border:10px solid green;     }
    .data img { width: 200px; transition-duration:0.8s;}
    </style>
</head>
<body>
    <section class="container">
        <h1>기본 메소드 - val()</h1>
        <article class="data">
            <button id="submit">값 전송</button>
            <button id="reset">초기화</button>
            <input type="text" size="30" title="id입력" placeholder="id" id="m_id">
            <div id="console"></div>
        </article>
    </section><br><hr><br>
    <script>
    $(document).ready(function(){
        //아이디가 reset 인 버튼을 클릭하면, 아이디가 m_id 인 요소의 입력값을 비우고,
        $("#reset").click(function(){
            $("#m_id").val("");
        });
        //아이디가 submit 인 버튼을 클릭하면, 값이 비어 있는지 검증을 하고, 값이 있는 경우 그 값을 아이디가 console 인 곳에 텍스트로 출력
        $("#submit").click(function(){
            var data = $("#m_id").val();
            if(data==""){
                alert("값을 입력해 주세요");
            } else {
                $("#console").text(data);
                //report(data);
            }
        });
        function report(msg){
            $("#console").text(msg);
        }
    });    

    </script>
</body>
</html>
```

<br><hr><br>

## jQuery 탐색(Traversing) 메소드
jQuery에 선택자로 원하는 요소를 선택하지 못하는 경우 선택자를 보좌하여 원하는 요소를 쉽게 선택할 수 있도록 도와주는 메소드로 원래 선택자만 가지고는 상위 요소나 this 요소에 속한 요소를 선택할 수 없지만 탐색 메소드를 활용하면, 쉽게 선택할 수 있다.

| 메소드 | 설명 |
|------------------|--------------------------------------|
| add("선택자") | 해당 요소를 선택자로 더 추가할 경우 사용 |
| addBack() | 다단계로 DOM 탐색을 수행 후 원래 선택했던 선택자로 다시 복귀할 경우 사용 |
| children() | 앞서 선택한 요소의 자식 요소를 선택할 경우 사용 |
| each() | 선택되는 요소가 여러 개일 경우 하나씩 순환하여 선택할 경우 사용 |
| eq(인덱스) | 앞서 선택한 요소 중에서 지정한 인덱스에 속한 요소를 선택할 경우 사용 |
| filter("선택자") | 앞서 선택한 요소 중에서 선택자로 지정한 요소를 선택할 때 사용 |
| find("선택자") | 앞서 선택한 요소 내부에서 지정한 선택자에 해당하는 요소를 선택 |
| first() | 앞서 선택한 요소 중에서 맨 처음 요소만 선택 |
| has("선택자") | 선택한 요소에서 지정한 선택자에 해당하는 자식요소가 존재하는 경우 선택 |
| is("선택자") | 선택한 요소 자신이 지정한 선택자에 해당하는 경우 선택 |
| last() | 앞서 선택한 요소 중에서 맨 마지막 요소만 선택 |
| map() | 앞서 선택한 요소를 순회하여 반복요소나 배열과 같은 복합체를 순회할 경우 사용 |
| next() | 앞서 선택한 요소의 바로 다음 요소 하나를 선택 |
| nextAll(["선택자"]) | 앞서 선택한 요소의 다음 요소들중에서 지정한 선택자에 해당하는 요소를 선택 |
| nextUntil(제한점, ["선택자"]) | 앞서 선택한 요소의 다음 요소들중에서 지정한 선택자중 제한점 전까지의 요소를 선택 |
| not("선택자") | 앞서 선택한 요소들 중에서 지정한 선택자에 해당하지 않은 요소만 선택 |
| odd() | 앞서 선택한 요소들 중에서 홀수 번째에 해당하는 요소만 선택 |
| even() | 앞서 선택한 요소들 중에서 짝수 번째에 해당하는 요소만 선택 |
| parent() | 앞서 선택한 요소의 부모 요소를 선택 |
| parents(["선택자"]) | 앞서 선택한 요소의 조상 요소를 선택 |
| parentsUntil(제한점, ["선택자"]) | 앞서 선택한 요소의 지정한 범위에 속하는 조상 요소를 선택 |
| prev() | 앞서 선택한 요소의 바로 이전 요소 하나를 선택 |
| prevAll(["선택자"]) | 앞서 선택한 요소의 이전 요소들중에서 지정한 선택자에 해당하는 요소를 선택 |
| prevUntil(제한점, ["선택자"]) | 앞서 선택한 요소의 이전 요소들중에서 지정한 선택자중 제한점 전까지의 요소를 선택 |
| siblings(["선택자"]) | 앞서 선택한 요소의 형제(이전이후모두) 요소를 모두 선택 |


### jQuery 선택자 추가 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 24 : 선택자의 추가</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { width:1000px; margin:20px auto; } 
    div { width: 60px;   height: 60px;   margin: 10px;   float: left;}
    p { clear:both;}
    .rB { border: 2px solid red; }
    .yB { background: yellow; } 
    </style>
    <script>
    $(function(){
        //버튼을 누르면 눌려진 버튼의 글자크기를 20px로 적용하고, div 요소를 추가 선택하여 둘 다 "이벤트 적용" 텍스트가 입력될 수 있도록 한다.
        //버튼을 누르면 div 요소에 .rB를 적용하고, p요소를 선택자를 추가하여 .yB를 적용
        $("button").on("click", function(){
            $(this).css("font-size","20px").add("div").text("이벤트 적용");
            $("div").addClass("rB").add("p").addClass("yB");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 추가 메소드 - add()</h1>
        <article class="data">
            <button class="btn"> 클릭 </button>
            <div></div>   <div></div>    <div></div>
            <p> rB 클래스의 적용은 받지 못하고 yB 클래스의 적용 받음</p>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 필터 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 25 : 선택자의 필터</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div { width: 60px; height: 60px; margin: 5px; float: left; border: 2px white solid; }
    </style>
    <script>
    $(function(){
        //버튼을 누르면 div 요소에 배경색을 노랑으로 하고, 선택했던 요소들 중에서 mid 클래스가 존재하는 요소에 대하여는 테두리색을 빨강색으로 변경적용
        $("button").on("click", function(){
            $("div").css("background", "yellow").filter(".mid").css("border-color", "red");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 필터 메소드 - filter()</h1>
        <article class="data">
            <button style="clear:both;" id="btn1">버튼</button>
            <div id="first"></div>	
            <div id="second" class="mid"></div>
            <div id="third"  class="mid"></div>
            <div id="fourth"  class="mid"></div>
            <div id="fifth"  class="mid"></div>
            <div id="sixth"></div>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 부정필터 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 26 : 선택자의 부정 필터</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div { width: 60px; height: 60px; margin: 5px; float: left; border: 2px white solid; }
    </style>
    <script>
    $(function(){
        //버튼을 누르면 div 요소에 배경색을 노랑으로 하고, 선택했던 요소들 중에서 mid 클래스가 존재하지 않은 요소에 대하여는 테두리색을 빨강색으로 변경적용
        $("button").on("click", function(){
            $("div").css("background", "yellow").not(".mid").css("border-color","red");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 부정필터 메소드 - not()</h1>
        <article class="data">
            <button style="clear:both;" id="btn1">버튼</button>
            <div id="first"></div>	
            <div id="second" class="mid"></div>
            <div id="third"  class="mid"></div>
            <div id="fourth"  class="mid"></div>
            <div id="fifth"  class="mid"></div>
            <div id="sixth"></div>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 범위적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 27 : 선택자의 범위</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div { width: 60px; height: 60px; margin: 5px; float: left; border: 2px black solid; }
    </style>
    <script>
    $(function(){
        //버튼을 누르면
        //div 엘리먼트 중에서 2 이상 4미만, 인덱스가 0부터 시작하기에 세번째, 네번째 엘리먼트만 배경색 빨강
        //인덱스가 5이후인 요소는 배경색 초록으로 적용 - slice(begin, end) : begin포함, end미포함 - end 값은 생략가능
        $("button").click(function(){
            var div = $(".data > div");
            div.slice(2, 4).css("background", "red");
            div.slice(5).css("background","green");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 범위 메소드 - slice()</h1>
        <article class="data">
            <div></div>	<div></div>	<div></div>	<div></div>
            <div></div>	<div></div>	<div></div>	<div></div>	
            <button>색 입히기</button>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 next/prev 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 28 : 선택자의 다음/이전 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div, span { display:block; width: 60px; height: 60px; margin: 5px; float: left; border: 2px black solid; }
    .after { background: pink; } 
    .sel {border: 5px blue solid;}
    </style>
    <script>
    $(function(){
        //버튼을 누르면
        //눌려진 버튼의 다음에 위치한 div 엘리먼트에 배경색을 노랑으로 
        //눌려진 버튼의 이전에 위치한 div 엘리먼트에 배경색을 빨강으로 설정
        //div의 다음 요소에 after 클래스를 적용
        //div의 다음 요소들 중에서 middle 클래스가 있는 요소에 클래스 sel을 적용
        //div의 이전 요소가 span이면, 글자색을 오렌지색으로 설정
        //div의 이전 요소들 모두를 안여백(padding)값 25px로 설정
        $("button").click(function(){
            $(this).next("div").css("background", "yellow");
            $(this).prev("div").css("background","red");
            $("div").next().addClass("after");
            $("div").nextAll(".middle").addClass("sel");
            $("div").prev("span").css("color", "orange");
            $("div").prevAll().css("padding","25px");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 다음/이전 요소 선택 메소드 - next(), prev()</h1>
        <article class="data">
            <button> 바로 아래 형제 엘리먼트에 스타일 입히기1</button>
            <div id="first">first</div>	
            <span id="second" class="middle">
                sibling1		<div id="child">child</div>
            </span>
            <div id="third"  class="middle">sibling2</div>
            <span id="fourth"  class="middle">sibling3</span>
            <span id="fifth"  class="middle">sibling4</span>
            <div id="sixth">last</div>  
            <button> 바로 위 형제 엘리먼트에 스타일 입히기1</button>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 자식 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 29 : 선택자의 자식 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div, span { display:block; width: 60px; height: 60px; margin: 5px; float: left; border: 2px black solid; }
    .after { background: pink; } 
    .sel {border: 5px blue solid;}
    </style>
    <script>
    $(function(){
        //아이디가 btn1인 버튼을 누르면
        //div 요소에 아래 테두리선 3px solid red를 적용하고, 그 자식요소 중에서 span 요소의 글자크기를 3배 크게 적용
        //div 요소에 배경색 핑크로 하고, 그 자식요소 중에서 .sel 인 요소의 글자색을 빨강색으로 설정
        //아이디가 btn2인 버튼을 누르면 div의 내용 중에서 span 요소를 제거
        $("#btn1").click(function(){
            $("div").css("border-bottom", "3px solid red").children("span").css("font-size", "3em");
            $("div").css("background-color", "pink").children(".sel").css("color", "red");
        });
        $("#btn2").click(function(){
            $("div").contents().remove("span");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 자식 요소 선택 메소드 - children(), contents()</h1>
        <article class="data">
            <button id="btn1"> 엘리먼트에 스타일 입히기</button>
            <button id="btn2"> 엘리먼트에 제거하기</button>
            <p> 이곳은 문장입니다. </p>
            <div><span class="sel"> 이곳은 div의 차일드 span 이다.</span></div>
            <p>그리고 <span> 여기는 또 다른 </span> 문장<span>입니</span>이다.</p>
            <div> 그리고 마지막으로 
               <span> 이곳은  div의 차일드 span 이고</span>이곳은 div이다. 
            </div>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 형제 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 28 : 선택자의 다음/이전 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    ul { float:left; margin:5px; font-size:16px; font-weight:bold; } 
    p { color:blue; margin:10px 20px; font-size:16px; padding:5px;    font-weight:bolder; } 
   .yw { background:yellow; }
    </style>
    <script>
    $(document).ready(function(){
        //클래스가 yw인 요소의 글자색을 짙은 하늘색으로 설정하고, 그 형제들의 글자색은 빨강으로 하며, 그 형제들의 개수를 구하여 p요소의 내부 요소인 u 요소의 텍스트로 출력하라.
        var len = $(".yw").css("color","deepskyblue").siblings().css("color","red").length;
        $("p u").text(len);
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 형제 요소 선택 메소드 - siblings()</h1>
        <article class="data">
            <ul>
                <li>One</li>    <li>Two</li>    <li class="yw">Three</li> 
                   <li>Four</li>
            </ul>
            <ul>
                <li>Five</li>    <li>Six</li>    <li>Seven</li>
            </ul>
            <ul>
                <li>Eight</li>    <li class="yw">Nine</li>    <li>Ten</li>  
                <li>Eleven</li>
            </ul>
            <p>    찾은 형제 엘리먼트의 개수: <u></u>개  </p>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 선택자 부모/조상 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 29 : 선택자의 부모/조상 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    </style>
    <script>
    $(document).ready(function(){
        //문서가 로딩되면, b 요소의 조상에 해당하는 요소의 태그들을 모두 배열로 저장한 후 b 요소의 자식요소로 추가하여 설정
        var res1 = new Array();
        $("b").parents().each(function(i){
            res1[i] = this.tagName;
        });
        $("b").append(res1.reverse().join(", "));
        //문서가 로딩되면, u 요소의 부모에 해당하는 요소에 글자색을 빨강으로 하고, 부모에 해당하는 태그를 u 요소의 자식요소로 추가하시오.
        var res2 = new Array();
        $("u").parent().css("color", "red").each(function(i){
            res2[i] = this.tagName;
        });
        $("u").append(res2.join(", "));
    });    
    </script>
</head>
<body>
    <header id="hd">헤더구역</header>
    <section class="container">
        <h1>선택자 부모/조상 선택 메소드 - parent(), parents()</h1>
        <article class="data">
            <p>
                <span> 여기는 <b> 부모/조상 엘리먼트 모두 검색 : </b> </span>
            </p>
            <div>
                <span> 여기는 <u> 부모 엘리먼트만 검색 : </u> </span>
            </div>
        </article>
    </section><br><hr><br>
    <footer id="ft">푸터 구역</footer>
</body>
</html>
```

### jQuery 선택자 후손 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 28 : 선택자의 후손 요소</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    </style>
    <script>
    $(document).ready(function(){
        //p 요소를 클릭하면, 클릭된 요소 후손 중에서 em 요소에 대한 글자색을 빨강으로 하고, 배경색은 핑크색으로 설정
        $("p").click(function(){
            $(this).find("em").css({"color":"red", "background-color":"pink"});
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>선택자 후손 요소 선택 메소드 - find()</h1>
        <article class="data">
            <div> p 엘리먼트 중에서 <em> 이태릭 단어의 </em>  </div> 
            <p> 글자 <b> <em>색</em> </b> 을 <em> 빨간색으로 </em>변경한다.</p> 
            <p> 글자 <strong> <em>색</em> </strong> 을 <em> 빨간색으로 </em>변경한다.</p>
        </article>
    </section><br><hr><br>
</body>
</html>
```


<br><hr><br>

## jQuery 조작(Manipulation) 메소드
선택자 또는 탐색 메소드로 해당 요소를 선택한 후 DOM 구조의 변화를 일으키는 조작을 해야하는 경우 사용하는 것으로 자식 요소, 형제 요소, 부모 요소 등의 증가, 제거, 변환, 크기 조작 등을 시행할 수 있다.

| 메소드 | 설명 |
|------------------|--------------------------------------|
| $("선택자").after("요소") | 선택자로 선택한 요소의 지정한 동생 요소로 추가 |
| $("요소").insertAfter($("선택자")) | 선택자로 선택한 요소의 지정한 동생 요소로 추가 |
| $("선택자").before("요소") | 선택자로 선택한 요소의 지정한 형 요소로 추가 |
| $("요소").insertBefore($("선택자")) | 선택자로 선택한 요소의 지정한 형 요소로 추가 |
| $("선택자").append("요소") | 선택자로 선택한 요소의 지정한 자식 요소로 추가 |
| $("요소").appendTo($("선택자")) | 선택자로 선택한 요소의 지정한 자식 요소로 추가 |
| $("선택자").wrap("요소") | 선택자로 선택한 요소의 지정한 부모 요소로 각 각 추가 |
| $("선택자").wrapAll("요소") | 선택자로 선택한 요소들을 하나의 지정한 부모 요소로 추가 |
| $("선택자").replaceAll("요소") | 선택자로 선택한 요소를 지정한 요소로 변경 |
| $("선택자").clone() | 선택자로 선택한 요소를 복사하기 |
| $("선택자").empty() | 선택자로 선택한 요소의 내부 텍스트 및 요소를 모두 비우기 |
| $("선택자").remove() | 선택자로 선택한 요소를 제거하기 |
| $("선택자").unwrap() | 선택자로 선택한 요소의 부모를 제거하기 |
| $("선택자").width(숫자값) | 선택자로 선택한 요소의 너비를 지정하거나 가져옴 |
| $("선택자").height(숫자값) | 선택자로 선택한 요소의 높이를 지정하거나 가져옴 |
| $("선택자").outerWidth(true) | 선택자로 선택한 요소의 마진을 포함한 너비를 가져옴 |
| $("선택자").outerHeight(true) | 선택자로 선택한 요소의 마진을 포함한 높이를 가져옴 |
| $("선택자").offset() | 선택자로 선택한 요소의 top과 left에 해당하는 위치를 가져옴 |
| $("선택자").position() | 선택자로 선택한 요소의 top과 left에 해당하는 위치를 가져옴 |
| $("선택자").scrollLeft() | 선택자로 선택한 요소의 가로 방향으로 스크롤된양을 가져옴 |
| $("선택자").scrollTop() | 선택자로 선택한 요소의 세로 방향으로 스크롤된양을 가져옴 |


### jQuery 자식 요소 추가하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 33 : 자식 엘리먼트 추가하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    div { float:left; width:50%; }
    </style>
    <script>
    $(document).ready(function(){
        //추가할 도시명
        var cities = ["파주","고양","김포","의정부","화성","안산","세종"]
        //추가할 카드명
        var cards = ["뮤츠","리자몽","레쿠쟈","아르세우스","펄기아","디아루가"]
        //문서가 로딩되면, 내가 살고 싶은 도시를 아이디가 cities_list에 추가 될 수 있도록 함
        $(cities).each(function(index, value){
            //$("#cities_list").append("<li>"+value+"</li>");
            $("<li>"+value+"</li>").appendTo($("#cities_list"));
        });
        //$("#cities_list").append($("#data1"));
        //문서가 로딩되면, 내가 갖고 싶은 카드를 아이디가 card_list에 추가 될 수 있도로 함
        $.each(cards, function(index, value){
            //$("#card_list").prepend("<li>"+value+"</li>");
            $("<li>"+value+"</li>").prependTo($("#card_list"));
        });
        //$("#card_list").prepend($("#data1"));
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>자식 추가 메소드 - append(), appendTo(), prepend(), prependTo()</h1>
        <article class="data">
            <div>  <b> 내가 살고 싶은 도시 </b>  <ul id="cities_list"></ul> </div> 
            <div>  <b> 내가 갖고 싶은 카드  </b>  <ul id="card_list"></ul> </div> 
        </article>
    </section><br><hr><br>
    <article id="data1">데이터1</article>
</body>
</html>
```

### jQuery 형제 요소 추가하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 34 : 형제 엘리먼트 추가하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    </style>
    <script>
    $(document).ready(function(){
        //문서가 로딩되면, <div class="container">니가 좋아하는 사람 : 김○태</div> 요소를 header의 이후(동생=next) 요소로 추가
        //$("header").after("<div class='container'>니가 좋아하는 사람 : 김○태</div>");
        $("<div class='container'>니가 좋아하는 사람 : 김○태</div>").insertAfter($("header"));
        //$("header").after($("#data1"));
        //문서가 로딩되면, <div class="container">니가 좋아하는 사람 : 김기○</div> 요소를 footer의 이전(형=prev) 요소로 추가
        //$("footer").before("<div class='container'>니가 좋아하는 사람 : 김기○</div>");
        $("<div class='container'>니가 좋아하는 사람 : 김기○</div>").insertBefore($("footer"));
    });    
    </script>
</head>
<body>
    <header> <h1> 오늘은 불금~! 함께 공부할 </h1></header>
    <section class="container">
        <h1>형제 추가 메소드 - before(), insertBefore(), after(), insertAfter()</h1>
    </section><br><hr><br>
    <article id="data1">데이터1</article>
    <footer> <h3> <em> copyright kkt </em> </h3> </footer>
</body>
</html>
```

### jQuery 부모 요소 추가하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 35 : 부모 엘리먼트 추가하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .border { border: 2px solid red; margin:10px; padding:0px 30px;
	float :left; width: 60px; }
    </style>
    <script>
    $(document).ready(function(){
        //p요소를 클릭하면, <div class='border'>불금 퐈이팅~!</div> 을 각 각의 p요소의 부모요소로 추가
        $("p").click(function(){
            $("p").wrap("<div class='border'>불금 퐈이팅~!</div>");
            //$("p").wrapAll("<div class='border'>불금 퐈이팅~!</div>");
        });        //$("p").wrap($(".indata1"));
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>부모 요소 추가 메소드 - wrap(), wrapAll()</h1>
        <article class="data">
            <h2>jQuery After Third part -> 312</h2>
            <p>React -> 37</p>
            <div>		<p>VUE.js -> 1</p>	</div>
            <p>angular -> 54</p>
            <p>polymer -> 3</p>
        </article>
    </section><br><hr><br>
    <div class="indata1">데이터1</div>
</body>
</html>
```

### jQuery 엘리먼트 변경하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 36 : 엘리먼트 변경하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .bd { border: 2px solid red;  }
    .box { border:2px dashed blue; }
    </style>
    <script>
    $(document).ready(function(){
        //.box요소를 클릭하면, 클릭된 요소를 "<h1 class='bd'>Replace Text1</h1>"로 변경
        $(".box").click(function(){
            $(this).replaceWith("<h1 class='bd'>Replace Text1</h1>");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>엘리먼트 변경 메소드 - replaceWith()</h1>
        <article class="data">
            <div class="box one">Youngeun's</div>
            <div class="box two">jQuery</div>
            <div class="box three">Mobile</div>
            <div class="box four">Story</div>
        </article>
    </section><br><hr><br>
    <div class="indata1">데이터1</div>
</body>
</html>
```

### jQuery 엘리먼트 비우기 및 제거하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 37 : 엘리먼트 비우기 및 제거하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .bd { border: 2px solid red;  }
    .box { border:2px dashed blue; }
    </style>
    <script>
    $(document).ready(function(){
        //아이디가 btn1인 요소를 클릭하면, p요소의 내용을 비운다.
        $("#btn1").click(function(){
            $("p").empty();
        });
        //아이디가 btn2인 요소를 클릭하면, li요소 중에서 비어 있는 요소를 제거한다.
        $("#btn2").click(function(){
            $("li:empty").remove();
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>엘리먼트 비우기 및 제거 메소드 - empty(), remove()</h1>
        <article class="data">
            <button id="btn1"> 엘리먼트 비우기 </button> 
            <button id="btn2"> 엘리먼트 지우기 </button> 
            <div>	
                <p>Kitea's</p>	jQuery
            </div>
            <p> <span> Mobile </span> </p>
            <p>Story</p>
            <ul>
                <li>데이터1</li><li></li><li>데이터3</li><li>데이터4</li>
            </ul>
        </article>
    </section><br><hr><br>
    <div class="indata1">데이터1</div>
</body>
</html>
```

### jQuery 엘리먼트 복제하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 38 : 엘리먼트 복제하기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    </style>
    <script>
    $(document).ready(function(){
        //button 요소를 클릭하면, strong요소를 span 요소에 자식으로 추가하고,
        //em 요소를 복제하여 span 요소에 자식으로 추가
        $("button").click(function(){
            $("strong").appendTo($("span"));
            $("em").clone().appendTo($("span"));
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>엘리먼트 복제 메소드 - clone()</h1>
        <article class="data">
            <button>복제</button>   
            <strong> 김 </strong>
            <em> 기태 </em>
            <span> 세상에서 제일 좋아하는 사람 : </span>
            <span> 세상에서 제일 미워할 수 없는 사람 : </span>
        </article>
    </section><br><hr><br>
    <div class="indata1">데이터1</div>
</body>
</html>
```

### jQuery 엘리먼트 크기 구하기 및 설정
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 39 : 엘리먼트 크기 구하기 및 설정과 위치</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; position:relative; }
    .data:after { content:""; display:block; clear:both; }
    div.abs { width: 150px; height: 60px; position: absolute;
     left:220px; top:35px; background-color: green; 
     cursor: pointer; }
    </style>
    <script>
    $(document).ready(function(){
        //.abs 요소를 클릭하면, 클릭된 요소의 가로 위치, 세로 위치, 폭, 높이를 
        //아이디가 result인 곳에 출력
        $(".abs").click(function(){
            var $obj = $(this).offset();    //left, top
            $("#result").text(this.tagName + "  coords("+$obj.left+", "+$obj.top+"), width:"+$(this).width()+", height:"+$(this).height());
        });
        $(".indata1").click(function(){
            $("#result").empty();
            $(".abs").width($(".abs").width()*2);
            $(".abs").height($(".abs").height()*2);
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>엘리먼트 위치 및 크기 메소드 - offset(), width(), height()</h1>
        <article class="data">
            <div id="result"></div>  <div class="abs"></div>
        </article>
    </section><br><hr><br><div class="indata1">초기화</div>
</body>
</html>
```

### jQuery 엘리먼트 마진을 포함한 크기 설정
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 40 : 엘리먼트 마진을 포함한 크기</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    p { width:200px; height:60px;  margin:20px; text-align:center;
   background:red; cursor:pointer; color:#fff; line-height:60px; } 
    </style>
    <script>
    $(document).ready(function(){
        //문서가 로딩되면, 첫 p요소의 너비와 마진을 포함한 너비를 구하여 아이디가 res1인 곳에 출력하고, 높이와 마진을 포함한 높이를 구하여 아이디가 res2인 곳에 출력
        var p = $("p:first");
        $("#res1").text("width Size : "+p.outerWidth()+", Margin Include Size : "+p.outerWidth(true));
        $("#res2").text("height Size : "+p.outerHeight()+", Margin Include Size : "+p.outerHeight(true));
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>엘리먼트의 마진을 포함한 크기 - outerWidth(), outerHeight()</h1>
        <article class="data">
            <p>Hello~! KimGiTae</p>
            <div id="res1"></div>  <div id="res2"></div>
        </article>
    </section><br><hr><br>
</body>
</html>
```

<br><hr><br>

## jQuery 이벤트(Event) 메소드와 이벤트 객체
사용자가 해당 DOM 요소에 영향을 미치는 행위를 할 경우 그 행위종류(이벤트명)마다 다르게 변화점을 적용시킬 수 있으며, 이는 사용자와 브라우저에 대한 행위종류마다 상호작용(interaction)을 다르게 적용시킬 수 있도록 해주는 메소드를 의미한다.
종합 이벤트 메소드와 독립 이벤트 메소드로 구분하며, 종합 이벤트 메소드는 독립 이벤트 메소드처럼 특정 이벤트에서만 적용이 되는 것이 아니라, 원하는 모든 이벤트 메소드를 적용할 수 있다.

| 메소드 | 이벤트종류 | 설명 |
|------------------|-----------------|----------------------------------------------|
| bind("이벤트명") | 종합 이벤트 | 앞서 선택한 요소에 대하여 여러 이벤트를 적용시킬수 있다. |
| on("이벤트명") | 종합 이벤트 | 앞서 선택한 요소에 대하여 여러 이벤트를 적용시킬수 있다. |
| unbind("이벤트명") | 종합 이벤트 | 앞서 선택한 요소에 대하여 bind가 되지 않도록 여러 이벤트를 해제시킬수 있다. |
| off("이벤트명") | 종합 이벤트 | 앞서 선택한 요소에 대하여 on이 되지 않도록 여러 이벤트를 해제시킬수 있다. |
| one("이벤트명") | 종합 이벤트 | 앞서 선택한 요소에 대하여 한 번만 이벤트를 발생시킬 경우 사용 |
| blur() | 폼 이벤트 | 앞서 선택한 폼 컨트롤 요소중 입력가능한 컨트롤 요소에서 커서가 다른 곳으로 이동할 경우 발생 |
| change() | 폼 이벤트 | 앞서 선택한 폼 컨트롤 요소중 select 요소에서 해당 값을 선택하거나 변경할 경우 발생 |
| click() | 마우스 이벤트 | 선택한 요소를 마우스로 클릭할 경우 발생 |
| contextmenu() | 마우스 이벤트 | 선택한 요소에서 마우스 오른쪽 버튼을 누를 경우 발생 |
| dblclick() | 마우스 이벤트 | 선택한 요소에서 마우스로 더블클릭할 경우 발생 |
| focus() | 폼 이벤트 | 선택한 폼 컨트롤 요소중 입력가능한 컨트롤 요소에서 커서를 취득할 경우 발생 |
| focusIn() | 폼 이벤트 | 선택한 폼 컨트롤 요소중 입력가능한 컨트롤 요소에서 커서를 들어올 경우 발생 |
| focusOut() | 폼 이벤트 | 선택한 폼 컨트롤 요소중 입력가능한 컨트롤 요소에서 커서를 잃어버릴 경우 발생 |
| hover() | 마우스 이벤트 | 선택한 요소 위에 마우스 포인터가 위치할 경우 발생 |
| keydown() | 키보드 이벤트 | 선택한 폼 컨트롤 요소에 커서가 있을 때 키보드가 아래로 누르는 시점에서 발생 |
| keyup() | 키보드 이벤트 | 선택한 폼 컨트롤 요소에 커서가 있을 때 키보드가 위로 올라올 시점에서 발생 |
| keypress() | 키보드 이벤트 | 선택한 폼 컨트롤 요소에 커서가 있을 때 키보드를 누르고 있을 경우 발생 |
| mousedown() | 마우스 이벤트 | 선택한 요소에서 마우스 버튼을 누르고 있는 경우 발생 |
| mouseup() | 마우스 이벤트 | 선택한 요소에서 마우스 버튼에서 손가락을 뗄 경우 발생 |
| mouseenter() | 마우스 이벤트 | 선택한 요소로 마우스 포인터가 진입할 경우 발생 |
| mouseleave() | 마우스 이벤트 | 선택한 요소로 마우스 포인터가 떠날 경우 발생 |
| mousemove() | 마우스 이벤트 | 선택한 요소에서 마우스 포인터가 움직일 경우 발생 |
| mouseover() | 마우스 이벤트 | 선택한 요소 위에 마우스 포인터가 올라올 경우 발생 |
| mouseout() | 마우스 이벤트 | 선택한 요소 위에 마우스 포인터가 떠날 경우 발생 |
| ready() | 창/문서 이벤트 | 해당 문서 또는 요소가 메모리에 로딩이 되면 발생 |
| resize() | 창/문서 이벤트 | 해당 창의 크기가 변경되면 발생 |
| scorll() | 창/문서 이벤트 | 해당 창에서 화면 스크롤시 발생 |
| select() | 폼 이벤트 | 선택한 폼 컨트롤 요소에서 해당 옵션이 선택되면 발생 |
| submit() | 폼 이벤트 | 선택한 폼의 데이터가 전송되면 발생 |


| 객체명 | 설명 |
|------------------|----------------------------------------------|
| event.target | 이벤트를 받는 객체로서 this와 같다 |
| event.pageX | 이벤트를 받는 객체의 한 페이지 내에서의 가로 위치 |
| event.pageY | 이벤트를 받는 객체의 한 페이지 내에서의 세로 위치 |
| event.screenX | 이벤트를 받는 객체의 모니터 화면 기준에서의 가로 위치 |
| event.screenY | 이벤트를 받는 객체의 모니터 화면 기준에서의 세로 위치 |
| event.clientX | 이벤트를 받는 객체의 브라우저 기준의 가로 위치 |
| event.clientY | 이벤트를 받는 객체의 브라우저 기준의 세로 위치 |
| event.which | 이벤트를 일으키는 요소나 그 위치를 반환할 때 활용 |
| event.type | 이벤트의 종류를 반환할 때 활용 |
| event.result | 이벤트의 결과를 반환할 때 활용 |
| event.preventDefault() | 모든 이벤트 발생을 방지할 경우 활용 |


### jQuery 범용(종합) 이벤트 적용 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 41 : 범용 이벤트 적용 메소드</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:500px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        //a 태그에 마우스 포인터를 올리면, img 요소에 해당 이미지를 보이도록 하시오. 
        $("a").on("mouseover", function(){
            $("img").attr("src", $(this).attr("data-val")).css("display", "none");
            $("img").delay(500).fadeIn(800);
        });
        //on()이나 bind()과 같은 여러 이벤트를 적용할 수 있는 메소드를 범용 이벤트 메소드라고 한다.
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>범용 이벤트 적용 메소드 - bind(), on()</h1>
        <article class="data">
            <ul>	
                <li> <a href="" data-val="img1.jpg"> 사진1 </a> </li>
                <li> <a href="" data-val="img2.jpg"> 사진2 </a> </li>
            </ul><img />
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 범용(종합) 이벤트 적용 메소드2
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 42 : 범용 이벤트 메소드를 활용한 여러 이벤트 적용</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:500px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        //img 요소에 마우스 포인터를 올리면, dy1.jpg를 적용하고,
        //마우스 포인터가 내려가면, dy2.jpg를 적용하며,
        //클릭시에는 주의 메시지를 출력하도록 하시오.
        $("img").bind({
            mouseover:function(){ $(this).attr("src", "dy1.jpg"); },
            mouseout:function(){ $(this).attr("src", "dy2.jpg"); },
            click:function() { alert("우리 위키미키 도연이 괴롭히지 마세요~!"); }
        });
        //개별 이벤트 메소드를 적용할 경우
        /* $("img").mouseover(function(){
            $(this).attr("src", "dy1.jpg");
        });
        $("img").mouseout(function(){
            $(this).attr("src", "dy2.jpg");
        });
        $("img").click(function(){
            alert("우리 위키미키 도연이 괴롭히지 마세요~!");
        }); */
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>범용 이벤트 적용 메소드 - bind(), on()</h1>
        <article class="data">
            <img src="dy1.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 이벤트 타겟 활용
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 43 : 범용 이벤트 타겟 활용</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:50px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        //img 요소를 더블클릭할 때마다 이벤트 타켓을 활용하여 callback처리로 이미지를
        //1.5배씩 커지게 하시오.
        $("img").bind("dblclick", function(event){
            var $t = $(event.target);
            $t.width($t.width()*1.5);
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>범용 이벤트 적용 메소드 - bind(), on()</h1>
        <article class="data">
            <img src="dy1.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 일회성 이벤트 적용
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 44 : 일회용 범용 이벤트 타겟 활용</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:100px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        //img 요소를 클릭하면, 클릭된 이미지를 2배로 커지게 하시오.(이벤트 작동은 한 번만)
        $("img").one("click", function(event){
            var $t = $(this);
            $t.width($t.width()*2);
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>일회용 범용 이벤트 적용 메소드 - one()</h1>
        <article class="data">
            <img src="dy1.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 이벤트의 제거
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 45 : 범용 이벤트 제거</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:100px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        var cnt = 0;
        //img 요소를 클릭하면, 클릭된 이미지를 2배로 커지게 하시오.(이벤트 작동은 세 번만)
        $("img").bind("click", function(event){
            var $t = $(event.target);
            $t.width($t.width()*2);
            cnt++;
            if(cnt >= 3){
                $t.unbind();
            }
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>범용 이벤트 제거 메소드 - unbind(), off()</h1>
        <article class="data">
            <img src="dy1.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 46 : 범용 이벤트 제거</title>
    <script src="./jquery-1.12.4.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:100px; height:auto; }
    </style>
    <script>
    $(document).ready(function(){
        var cnt = 0;
        //img 요소를 클릭하면, 클릭된 이미지를 2배로 커지게 하시오.(이벤트 작동은 세 번만)
        $("img").on("click", function(event){
            var $t = $(event.target);
            $t.width($t.width()*2);
            cnt++;
            if(cnt >= 3){
                $t.off();
            }
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>범용 이벤트 제거 메소드 - unbind(), off()</h1>
        <article class="data">
            <img src="dy1.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 이벤트의 교대 수행
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 47 : 범용 이벤트의 교대 수행</title>
    <script src="https://code.jquery.com/jquery-1.8.0.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { display:block; width:100px; height:auto; }
    div { width:200px;	height:100px; line-height:100px; color:#fff; background:black; transition-duration:0.8s; text-align:center; }
    </style>
    <script>
    $(document).ready(function(){
        //div 요소를 클릭하면, 클릭된 DIV 요소에 배경색을 딥핑크, 딥스카이블루, 그린, 검정으로 교대로 바뀔 수 있도록 하시오.
        $("div").toggle(
            function(evnet) { $(evnet.target).css("background","deeppink").width(400); },
            function(evnet) { $(evnet.target).css("background","deepskyblue").width(100); },
            function(evnet) { $(evnet.target).css("background","green").width(300); },
            function(evnet) { $(evnet.target).css("background","black").width(200); }
        );
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>이벤트 교대 수행 메소드 - toggle()</h1>
        <p>jQuery version 1.9 미만에서만 작동됨</p>
        <article class="data">
            <img src="dy2.jpg">
	        <div>DIV</div>
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 이벤트의 위임(상속)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 48 : 이벤트의 위임(상속)</title>
    <script src="https://code.jquery.com/jquery-1.8.0.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    $(document).ready(function(){
        //p 요소를 클릭하면, 클릭된 p요소의 다음(동생) 요소로 "<p>Another paragraph!</p>" 이 추가되도록 하시오.(단, 새로 추가된 p요소에도 이벤트가 상속되어야 함)
        $("p").live("click", function(){
            $(this).after("<p>Another paragraph!</p>");
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>이벤트 위임(상속) 메소드 - live()</h1>
        <div>jQuery version 1.9 미만에서만 작동됨</div>
        <article class="data">
            <p>Click me!</p> 
        </article>
    </section><br><hr><br>
</body>
</html>
```

### jQuery 마우스 개별 이벤트
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 49 : 마우스 개별 이벤트</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { width: 300px; height:auto; border-width:10px; border-style:solid; 
    border-color:black; transition-duration:0.6s; }
    </style>
    <script>
    $(document).ready(function(){
        //img 요소에서 마우스 왼쪽 버튼을 누르면, 테두리 색이 파랑,
        //img 요소에서 마우스 왼쪽 버튼을 떼면, 테두리 색이 골드,
        //img 요소에서 마우스 포인터가 내려 오면, 테두리 색이 검정,
        //img 요소에서 마우스 포인터가 올라 가면, 테두리 색이 빨강,
        //img 요소를 클릭하면, 이미지는 1.5배로 커짐
        //img 요소를 더블클릭하면, 이미지는 1.5배로 작아짐
        $("img").mousedown(function(){
            $(this).css("border-color","blue");
        });
        $("img").mouseup(function(){
            $(this).css("border-color","gold");
        });
        $("img").mouseout(function(){
            $(this).css("border-color","black");
        });
        $("img").mouseover(function(){
            $(this).css("border-color","red");
        });
        $("img").click(function(){
            $(this).width($(this).width()*1.5);
        });
        $("img").dblclick(function(){
            $(this).width($(this).width()/1.5);
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>마우스 개별 이벤트 메소드</h1>
        <p>click, dblclick, mouseover, mouseout, mousedown, mouseup
            mouseenter, mouseleave, hover, mousemove, contextmenu, wheel 등 이 있다.</p>
        <article class="data">
            <img src="dy2.jpg" id="pic1">
        </article>
    </section><br><hr><br>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 50 : 마우스 개별 이벤트2</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    img { width: 500px; height:auto; border-width:10px; border-style:solid; 
    border-color:black; transition-duration:0.6s; }
    </style>
    <script>
    $(document).ready(function(){
        //img 요소에서 마우스 포인터를 움직이면,
        //브라우저를 기준으로 마우스 포인터의 위치를 x, y 좌표값으로 첫 번째 p요소에 출력
        //화면을 기준으로 마우스 포인터의 위치를 x, y 좌표값으로 .middle이 적용된 p요소에 출력
        //페이지를 기준으로 마우스 포인터의 위치를 x, y 좌표값으로 마지막 p요소에 출력
        $("img").mousemove(function(event){
            $("p:first").html(event.clientX + ", " + event.clientY);
            $("p.middle").html(event.screenX + ", " + event.screenY);
            $("p:last").html(event.pageX + ", " + event.pageY);
        });
    });    
    </script>
</head>
<body>
    <section class="container">
        <h1>마우스 개별 이벤트 메소드2</h1>
        <div>click, dblclick, mouseover, mouseout, mousedown, mouseup
            mouseenter, mouseleave, hover, mousemove, contextmenu, wheel 등 이 있다.</div>
        <article class="data">
            <div><img src="dy2.jpg" id="pic1"></div>
            <p></p>   <p class="middle"></p>   <p></p>
        </article>
    </section><br><hr><br>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 51 : 마우스 개별 이벤트3</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin:0; padding:0; }
    body, html { width:100%; height:100%; }
    ul { list-style: none; }
    a { text-decoration:none; }
    .container, .page { width:100%; height:100%; }
    .page { background-repeat:no-repeat; background-size:cover; 
    background-position: center center; }
    #page1 { background-image: url("black1.jpg"); }
    #page2 { background-image: url("black2.jpg");
     background-attachment:fixed;  }
    #page3 { background-image: url("black3.jpg"); }
    #page4 { background-image: url("black4.jpg"); }
    .boxFrame { width:1000px; margin:0px auto;  padding-top:100px;
    display:none; }
    .col { width:300px; float:left; margin:10px; }
    #gnb { position:fixed; top:0; left:0; z-index:20; width:100%;
    height:80px; background:rgba(0,0,0,0.8); display:none; }
    #gnb li { float:left; padding:20px; float:left; }
    #gnb a { color:#fff; font-weight:bold; }
    .title1 { color:#fff; text-shadow:1px 1px 10px #222;
        text-align:center; line-height:250px; font-size:60px; }
    .comment { position:fixed; left:50%; width:500px; margin-left:-250px; 
        bottom:150px; z-index:999; box-shadow:0px 0px 10px #fff; color:deepskyblue; }    
    </style>
    <script>
        $(document).ready(function(){
            var Ht = $(window).height(); //페이지 높이 계산
            var pageCnt = $(".page").length; //페이지 수 계산
            $(window).scroll(function(){ //스크롤이 되었을 때
                var scTop = $(window).scrollTop(); //스크롤된 양 계산
                //console.log(scTop);
                if(scTop >= Ht*2){
                    $(".boxFrame").fadeIn(1500);
                } else {
                    $(".boxFrame").fadeOut(1500);
                }
                if(scTop >= 100) {
                    $("#gnb").slideDown(800);
                } else {
                    $("#gnb").slideUp(800);
                }
            });
        });
        </script>
</head>
<body>
    <section class="comment">
        <h1>마우스 개별 이벤트 메소드2</h1>
        <div>click, dblclick, mouseover, mouseout, mousedown, mouseup
            mouseenter, mouseleave, hover, mousemove, contextmenu, wheel 등 이 있다.</div>
        <article class="data">
            
        </article>
    </section>
    <nav id="gnb">
        <ul>
            <li><a href="">회사소개</a></li>
            <li><a href="">제품소개</a></li>
            <li><a href="">서비스</a></li>
            <li><a href="">고객센터</a></li>
        </ul>
    </nav>
    <div class="container">
        <section class="page" id="page1">
            <h1 class="title1">제목1</h1>
        </section>
        <section class="page" id="page2">
            <h1 class="title1">제목2</h1>
        </section>
        <section class="page" id="page3">
            <div class="boxFrame">
                <div class="col">
                    <img src="https://placeimg.com/300/200/any/grayscale" alt="">
                </div>
                <div class="col">
                    <img src="https://placeimg.com/300/200/any/grayscale" alt="">
                </div>
                <div class="col">
                    <img src="https://placeimg.com/300/200/any/grayscale" alt="">
                </div>
            </div>
        </section>
        <section class="page" id="page4"></section>
    </div>
</body>
</html>
```

### jQuery 폼 관련 이벤트 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 52 : 폼 관련 이벤트 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    input { display:block; width:900px; height:48px; line-height: 48px; 
    font-size:30px; }
    </style>
    <script>
    $(document).ready(function(){
        //문서가 로딩되면, input 요소에 "아이디를 입력하세요"라는 값이 파란색 글자로 입력되도록 하시오.
        $("input").val("아이디를 입력하세요").css("color","blue");
        //input 요소가 포커스(커서)를 획득하면, 해당 요소의 값을 비우고 글자색을 검정색으로 하시오.
        $("input").focus(function(){
            $(this).val("").css("color", "black");
        });
        //input 요소에서 포커스를 잃으면, 해당 요소의 입력된 값을 비교하여, 입력된 값이 없는 경우 "아이디가 입력되지 않았습니다~!"를 빨간색으로 표시하시오.
        $("input").blur(function(){
            if($(this).val()=="") {
                $(this).val("아이디가 입력되지 않았습니다~!").css("color","red");
            }
        });

        //아이디가 sel인 요소에서 해당 값을 선택하면, 선택된 사이트의 주소로 새로운 창에 띄우기하시오.
        $("#sel").change(function(){
            var hrefUrl = $(this).val();
            if($(this).val()!="") {
                window.open(hrefUrl, "new Window");
            }
        });
    });
    </script>
</head>
<body>
    <section class="comment">
        <h1>폼 관련 이벤트 메소드 - focus(), blur(), change()</h1>
        <article class="data">
            <input type="text" id="id">
        </article>
        <article class="data">
            사이트 선택:
            <select id="sel">
                <option value="" selected>선택안함</option>
                <option value="http://www.naver.com">네이버</option>
                <option value="http://www.daum.net">다음</option>
                <option value="http://www.google.com">구글</option>
            </select>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 윈도우 관련 이벤트 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 53 : 창 관련 이벤트 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    input { display:block; width:900px; height:48px; line-height: 48px; 
    font-size:30px; }
    </style>
    <script>
    $(document).ready(function(){
        //데스크탑(960이상)일 경우 제목, 설명 등의 글자색은 파랑, 글자크기는 제목 : 48px, 설명 : 20px, 이미지는 dy1.jpg로
        //태블릿(768~959)일 경우 제목, 설명 등의 글자색은 초록, 글자크기는 제목 : 36px, 설명 : 18px, 이미지는 dy2.jpg로
        //모바일(~767)일 경우 제목, 설명 등의 글자색은 빨강, 글자크기는 제목 : 24px, 설명 : 14px, 이미지는 dy3.jpg로
        var wd0 = screen.width;
        $(window).resize(function(){
            var wd = $(window).width();
            if(wd>=960 || wd==wd0){
                $(".title").css("color", "blue").css("font-size","48px");
                $(".comment").css("color", "blue").css("font-size","20px");
                $("img").attr("src","dy1.jpg").width(500);
            } else if(wd>=768) {
                $(".title").css("color", "green").css("font-size","36px");
                $(".comment").css("color", "green").css("font-size","18px");
                $("img").attr("src","dy2.jpg").width(400);
            } else {
                $(".title").css("color", "red").css("font-size","24px");
                $(".comment").css("color", "red").css("font-size","14px");
                $("img").attr("src","dy3.jpg").width(200);
            }
        }).resize();
    });
    </script>
</head>
<body>
    <section class="comment">
        <h1>창 관련 이벤트 메소드 - resize()</h1>
        <article class="data">
            <h2 class="title">제목</h2>
            <p class="comment">설명</p>
            <h3>이미지 이름 :</h3>
            <img src="dy1.jpg" alt="위키미키 도연">
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 키보드 관련 이벤트 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 54 : 키보드 관련 이벤트 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    input { display:block; width:900px; height:48px; line-height: 48px; 
    font-size:30px; }
    </style>
    <script>
    $(document).ready(function(){
        //아이디가 msgBox인 요소에 글자를 입력하면, 입력된 글자수를 카운트하여 80글자를 기준으로 입력가능한(남은) 글자수를 h2요소에 출력하고, 만약, 초과하여 입력하면, msgBox의 글자색은 빨강으로 하고 비활성화되도록 하고, 초과하지 않으면, 파랑으로 글자색을 표시하며, 아이디가 btn1인 요소를 클릭하면, msgBox를 초기화하도록 하시오.
        $("#msgBox").keyup(function(){
            var inLength = $(this).val().length;
            var remain = 80 - inLength;
            $("h2").html(remain);
            if(remain >= 0) {
                $("h2").css("color","blue");
            } else {
                $("h2").css("color","red");
                $(this).css("color","red");
                $(this).attr("disabled", "true");
                $("#status").text(Math.abs(remain)+"글자를 초과하였습니다.");
            }
        });
        $("#btn1").click(function(){
            $("#msgBox").remove();
            $("h2").after("<textarea id='msgBox' cols='40' rows='8'></textarea>");
            $("h2").text("80").css("color","black");
        });
    });
    </script>
</head>
<body>
    <section class="comment">
        <h1>키보드 관련 이벤트 메소드 - keyup(), keydown(), keypress()</h1>
        <article class="data">
            <div>
                남은 글자수
                <h2>80</h2>
                <textarea id="msgBox" cols="40" rows="8"></textarea>
            </div>
            <div id="status"></div><button id="btn1">초기화</button>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 54 : 키보드 관련 이벤트 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    input { display:block; width:900px; height:48px; line-height: 48px; 
    font-size:30px; }
    #imgTarget { transition-duration:0.6s; width:200px; }
    #msgBox { opacity:0; }
    </style>
    <script>
    $(document).ready(function(){
        //+를 누르면 이미지(#imgTarget)를 두 배 확대, -를 누르면 두 배 축소
        $("#msgBox").keypress(function (event) {
			var ht = $("#imgTarget").height();
			var wd = $("#imgTarget").width();
			$("#result").text("눌려진 키는 " 
			+ String.fromCharCode(event.which) + " 이며, 키 값은 " 
			+ event.which + " 입니다.");
			if(event.which == 43) {
				$("#imgTarget").width($("#imgTarget").width()*2);
			} else if(event.which == 45) {
				$("#imgTarget").width($("#imgTarget").width()/2);
			}
		});
    });
    </script>
</head>
<body>
    <section class="comment">
        <h1>키보드 관련 이벤트 메소드 - keyup(), keydown(), keypress()</h1>
        <article class="data">
            <div>
                <h2>눌려진 키는?</h2>
                <input id="msgBox" autofocus />
            </div>
            <h3 id="result"></h3>
            <img src="dy3.jpg" alt="도연" id="imgTarget">
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```
<br><hr><br>


## jQuery 효과(Effect) 메소드
| 메소드 문법 | 설명 |
|--------------------------------------|------------------------------|
| animate() | animate("적용할내용", 실행시간, [function(){}]) | 적용할 내용을 주어진 실행시간 동안 애니메이션하는 메소드로 <br>만약, function 이 추가되면, 애니메이션 후에 그 내용이 추가로 진행된다. |
| clearQueue() | 현재 진행중이거나 진행할 애니메이션이 제거됨 |
| delay(지연시간) | 현재 진행할 애니메이션의 동작 지연시간을 지정 |
| finish() | 애니메이션을 종료하면서 원래 적용되는 애니메이션의 최종상태로 곧바로 변경됨  |
| stop([true|false], [true|false]) | 첫 번째 옵션은 현재 작동 중인 애니메이션이며, <br>두 번째 옵션은 큐에 저장되어 미래에 작동할 애니메이션을 말하며,<br>true이면, 정지기능이 활성화되고, false이면, 정지기능이 비활성화됨 |
| queue([function(){}]) | 앞으로 진행할 애니메이션의 내용을 큐에 저장 |
| dequeue([function(){}]) | 앞으로 진행할 애니메이션의 내용을 큐에서 제거 |
| show(실행시간, [function(){}]) | 가로 세로 크기가 커지면서 나타나는 애니메이션 적용 |
| hide(실행시간, [function(){}]) | 가로 세로 크기가 작아지면서 사라지는 애니메이션 적용 |
| toggle(실행시간, [function(){}]) | show와 hide 애니메이션을 교대로 수행하는 애니메이션 적용 |
| fadeIn(실행시간, [function(){}]) | 페이드 효과를 진행하면서 서서히 나타나는 애니메이션 적용 |
| fadeOut(실행시간, [function(){}]) | 페이드 효과를 진행하면서 서서히 사라지는 애니메이션 적용 |
| fadeToggle(실행시간, [function(){}]) | 페이드 인 과 페이드 아웃 효과를 교대로 작동하는 애니메이션 적용 |
| fadeTo(실행시간, 불투명도, [function(){}]) | 불투명도 애니메이션을 적용하는 메소드로 점 점 흐려지거나 점 점 선명하게 나타내는 애니메이션에 적용 |
| slideDown(실행시간, [function(){}]) | 아래로 펼쳐지면서 나타나는 애니메이션 적용 |
| slideUp(실행시간, [function(){}]) | 위로 접히면서 사라지는 애니메이션 적용 |
| slideToggle(실행시간, [function(){}]) | slideDown과 slideUp 애니메이션을 교대로 적용 |

※ effect 관련 메소드의 실행시간은 fast, slow와 같은 키워드로도 가능하지만, 보통 ms단위의 숫자만 기재하는 것이 보통임.
※ effect 관련 메소드의 실행시간이 있는 메소드는 easing 속성을 지정할 수 있으며, easing는 가속 또는 감속 효과를 나타냄


### jQuery 기본 효과 메소드 show/hide/toggle
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 56 : 보이기/숨기기 효과 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin: 0; padding:0; }
    body, html { width: 100%; height: 100%; }
    ul { list-style:none; }
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    .lst, .btnFrame { margin: 30px auto; width:600px;  clear:both; }
    .lst li { float:left; margin-left:10px; display:none; }
    .txt { clear:both; text-align:center; }
    h1 { text-align: center; margin-top:1.8rem; }
    p { line-height:1.8; padding-top:2rem; padding-bottom:3rem; }
    button { display:block; float:left; margin:24px; padding:18px; background-color: #2c4d5f; color:#fff; outline:0; border:0; border-radius:14px; cursor: pointer;
     }
    </style>
    <script>
    $(document).ready(function(){
        //아이디가 btn1인 버튼을 클릭하면, .lst 내부의 li 요소를 보이게 하는 효과를 적용
        $("#btn1").click(function(){ //duration : fast, normal(생략), slow, ms단위 숫자 
            $(".lst li").show(2000, function(){
                $(".txt").text("리스트 박스가 보여지고 있습니다.");
            });
        });
        //아이디가 btn2인 버튼을 클릭하면, .lst 내부의 li 요소를 숨기게 하는 효과를 적용
        $("#btn2").click(function(){
            $(".lst li").hide("slow", function(){
                $(".txt").text("리스트 박스가 숨겨지고 있습니다.");
            });
        });

        //아이디가 btn3인 버튼을 클릭하면, .lst 내부의 li 요소를 교대로 보이고, 숨기게 하는 효과를 적용
        $("#btn3").click(function(){
            $(".lst li").toggle("slow", function(){
                var status = $(".lst li").css("display");
                if(status=="none"){
                    $(".txt").text("리스트 박스가 숨겨지고 있습니다.");
                } else {
                    $(".txt").text("리스트 박스가 보여지고 있습니다.");
                }
            });
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>보이기/숨기기 효과 메소드 - show(), hide(), toggle()</h1>
        <p>가로 방향과 세로 방향으로 커지면서 보여지거나 작아지면서 숨겨지는 효과</p>
        <article class="data">
            <div class="btnFrame">
                <button id="btn1">보이기 버튼</button>
                <button id="btn2">숨기기 버튼</button>
                <button id="btn3">토글 버튼</button>
            </div>
            <ul class="lst">
                <li><img src="item1.png" alt=""></li>
                <li><img src="item2.png" alt=""></li>
                <li><img src="item3.png" alt=""></li>
            </ul>
            <div class="txt">버튼을 누르면, 효과가 실행됩니다.</div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 기본 효과 메소드 slideDown/slideUp/slideToggle 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 57 : 펼쳐지기/접히기 효과 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin: 0; padding:0; }
    body, html { width: 100%; height: 100%; }
    ul { list-style:none; }
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    .lst, .btnFrame { margin: 30px auto; width:600px;  clear:both; }
    .lst li { float:left; margin-left:10px; display:none; }
    .txt { clear:both; text-align:center; }
    h1 { text-align: center; margin-top:1.8rem; }
    p { line-height:1.8; padding-top:2rem; padding-bottom:3rem; }
    button { display:block; float:left; margin:24px; padding:18px; background-color: #2c4d5f; color:#fff; outline:0; border:0; border-radius:14px; cursor: pointer;
     }
    </style>
    <script>
    $(document).ready(function(){
        $(".lst li").each(function(index){
            $(this).delay(index*500).slideDown(600);
        });
        //아이디가 btn1인 버튼을 클릭하면, .lst 내부의 li 요소를 펼쳐지면서 보여지는 효과를 적용
        $("#btn1").click(function(){ 
            //duration : fast, normal(생략), slow, ms단위 숫자 
            $(".lst li").slideDown(2000, function(){
                $(".txt").text("리스트 박스가 펼쳐지고 있습니다.");
            });
        });
        //아이디가 btn2인 버튼을 클릭하면, .lst 내부의 li 요소를 접히면서 숨겨지는 효과를 적용
        $("#btn2").click(function(){
            $(".lst li").slideUp("slow", function(){
                $(".txt").text("리스트 박스가 접히고 있습니다.");
            });
        });

        //아이디가 btn3인 버튼을 클릭하면, .lst 내부의 li 요소를 교대로 펼쳐져 보이고, 접히며 숨겨지는 효과를 적용
        $("#btn3").click(function(){
            $(".lst li").stop().slideToggle(3000, function(){ //stop(true, true)
                var status = $(".lst li").css("display");
                if(status=="none"){
                    $(".txt").text("리스트 박스가 접히고 있습니다.");
                } else {
                    $(".txt").text("리스트 박스가 펼쳐지고 있습니다.");
                }
            });
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>보이기/숨기기 효과 메소드 - slideDown(), sildeUp(), slideToggle()</h1>
        <p>세로 방향으로 펼쳐지면서 보여지거나 접히면서 숨겨지는 효과</p>
        <h1>지연 메소드 - delay(), 정지 메소드 - stop()</h1>
        <article class="data">
            <div class="btnFrame">
                <button id="btn1">보이기 버튼</button>
                <button id="btn2">숨기기 버튼</button>
                <button id="btn3">토글 버튼</button>
            </div>
            <ul class="lst">
                <li><img src="item1.png" alt=""></li>
                <li><img src="item2.png" alt=""></li>
                <li><img src="item3.png" alt=""></li>
            </ul>
            <div class="txt">버튼을 누르면, 효과가 실행됩니다.</div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 기본 효과 메소드 fadeIn/fadeOut/fadeToggle
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 58 : 페이드 효과 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin: 0; padding:0; }
    body, html { width: 100%; height: 100%; }
    ul { list-style:none; }
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    .lst, .btnFrame { margin: 30px auto; width:600px;  clear:both; }
    .lst li { float:left; margin-left:10px; display:none; }
    .txt { clear:both; text-align:center; }
    h1 { text-align: center; margin-top:1.8rem; }
    p { line-height:1.8; padding-top:2rem; padding-bottom:3rem; }
    button { display:block; float:left; margin:24px; padding:18px; background-color: #2c4d5f; color:#fff; outline:0; border:0; border-radius:14px; cursor: pointer;
     }
    </style>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-easing/1.4.1/jquery.easing.min.js"></script>
    <script>
    $(document).ready(function(){
        //가속 감속 효과 모음 : linear swing easeInQuad easeOutQuad easeInOutQuad easeInCubic easeOutCubic easeInOutCubic easeInQuart easeOutQuart easeInOutQuart easeInQuint easeOutQuint easeInOutQuint easeInSine easeOutSine easeInOutSine easeInExpo easeOutExpo easeInOutExpo easeInCirc easeOutCirc easeInOutCirc easeInElastic easeOutElastic easeInOutElastic easeInBack easeOutBack easeInOutBack easeInBounce easeOutBounce easeInOutBounce
        $(".lst li").each(function(index){
            $(this).delay(index*500).fadeIn(600, "easeInOutBounce");
        });
        //아이디가 btn1인 버튼을 클릭하면, .lst 내부의 li 요소를 서서히 보여지는 효과를 적용
        $("#btn1").click(function(){ 
            //duration : fast, normal(생략), slow, ms단위 숫자 
            $(".lst li").each(function(index){ 
                $(this).delay(index*500).fadeIn(2000, "easeOutElastic");
                $(".txt").text("리스트 박스가 서서히 나타나고 있습니다.");    
            });
        });
        //아이디가 btn2인 버튼을 클릭하면, .lst 내부의 li 요소를 서서히 사라지는 효과를 적용
        $("#btn2").click(function(){
            $(".lst li").fadeOut("slow", "easeOutCubic", function(){
                $(".txt").text("리스트 박스가 서서히 사라지고 있습니다.");
            });
        });

        //아이디가 btn3인 버튼을 클릭하면, .lst 내부의 li 요소를 교대로 서서히 보이고, 서서히 사라지는 효과를 적용
        $("#btn3").click(function(){
            $(".lst li").stop().fadeToggle(3000, "easeOutExpo", function(){ //stop(true, true)
                var status = $(".lst li").css("display");
                if(status=="none"){
                    $(".txt").text("리스트 박스가 서서히 사라지고 있습니다.");
                } else {
                    $(".txt").text("리스트 박스가 서서히 나타나고 있습니다.");
                }
            });
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>서서히 보이기 서서히 사라지는 효과 메소드 - fadeIn(), fadeOut(), fadeToggle()</h1>
        <p>서서히 보여지거나 서서히 사라지는 효과</p>
        <h1>가속 감속 효과 적용시 jquery.easing.js 활용</h1>
        <article class="data">
            <div class="btnFrame">
                <button id="btn1">보이기 버튼</button>
                <button id="btn2">숨기기 버튼</button>
                <button id="btn3">토글 버튼</button>
            </div>
            <ul class="lst">
                <li><img src="item1.png" alt=""></li>
                <li><img src="item2.png" alt=""></li>
                <li><img src="item3.png" alt=""></li>
            </ul>
            <div class="txt">버튼을 누르면, 효과가 실행됩니다.</div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 기본 효과 메소드 fadeTo
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 59 : 흐림도(불투명도) 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin: 0; padding:0; }
    body, html { width: 100%; height: 100%; }
    ul { list-style:none; }
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    .lst, .btnFrame { margin: 30px auto; width:600px;  clear:both; }
    .lst li { float:left; margin-left:10px; opacity:1; }
    .txt { clear:both; text-align:center; }
    h1 { text-align: center; margin-top:1.8rem; }
    p { line-height:1.8; padding-top:2rem; padding-bottom:3rem; }
    button { display:block; float:left; margin:24px; padding:18px; background-color: #2c4d5f; color:#fff; outline:0; border:0; border-radius:14px; cursor: pointer;
     }
    </style>
    <script>
    $(document).ready(function(){
        //아이디가 btn1인 버튼을 클릭하면, .lst 내부의 li 요소를 서서히 선명해지는 효과를 적용
        var opa = parseFloat($(".lst li").css("opacity"));
        $("#btn1").click(function(){ 
            if(opa<1) {
                opa = opa + 0.1;
            }
            $(".lst li").clearQueue().fadeTo(300, opa);
        });
        //아이디가 btn2인 버튼을 클릭하면, .lst 내부의 li 요소를 서서히 흐려지는 효과를 적용
        $("#btn2").click(function(){
            if(opa>0){
                opa = opa - 0.1;
            }
            $(".lst li").clearQueue().fadeTo(300, opa);
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>흐림도(불투명도) 효과 메소드 - fadeTo()</h1>
        <p>서서히 흐려지거나 서서히 선명해지는 효과</p>
        <article class="data">
            <div class="btnFrame">
                <button id="btn1">선명하게 버튼</button>
                <button id="btn2">흐리게 버튼</button>
            </div>
            <ul class="lst">
                <li><img src="item1.png" alt=""></li>
                <li><img src="item2.png" alt=""></li>
                <li><img src="item3.png" alt=""></li>
            </ul>
            <div class="txt">버튼을 누르면, 효과가 실행됩니다.</div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### jQuery 사용자 효과 메소드 animate
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 60 : 사용자 정의 애니메이션 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    * { margin: 0; padding:0; }
    body, html { width: 100%; height: 100%; }
    ul { list-style:none; }
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    #visual { width:200px; height:200px; margin:100px auto;
	 overflow:hidden; position:relative; clear:both; margin-bottom: 10px; }
	.img_box { width:2000px; height:200px; }
	#visual a { display:block; width:200px; height:200px; float:left; 
    position: relative; }
	#visual img { display:block; width:200px; height:auto; }
	.num { display:block; color:black;	background:yellow;
	 border-radius:20px; width:40px; height:40px; position:absolute;
	  z-index:10; top:20px; left:20px;
		text-align:center;	line-height: 40px; }
	#btn_box { width:200px; height:30px; margin:0px auto; }
	#btn_box a { display:block; width:30px; height:30px; cursor:pointer; 
    position:absolute; top:280px; z-index:20; }
	#btn_box .left { left:50%; margin-left:-150px; }
	#btn_box .right { right:50%; margin-right:-150px; }
    #num_box { clear:both; width:200px; margin:2px auto; height:40px; }
    #num_box span { display:block; width:32px; margin:8px; float:left; color:#333; 
    cursor:pointer; text-align: center; line-height: 32px; font-weight: 900; }
    </style>
    <script>
    $(document).ready(function(){
       var len = $(".img_box a").length;
       var wd = $("#visual").width();
       $(".img_box a").each(function(index){
            $(this).find(".num").text(index+1);
            $("#num_box").append("<span>"+(index+1)+"</span>")
       }); 
       $("#btn_box .left").click(function(){
            var ml = parseInt($(".img_box").css("margin-left"));
            if(ml<0) {
                $(".img_box").not(":animated").animate({"margin-left":"+="+wd+"px"}, 500);
            }
       });
       $("#btn_box .right").click(function(){
            var ml = parseInt($(".img_box").css("margin-left"));
            if(ml>(len-1)*wd*-1) {
                $(".img_box").not(":animated").animate({"margin-left":"-="+wd+"px"}, 500);
            }
       });
       $("#num_box span").click(function(){
            var idx = $(this).index() * -1;
            var mlt = idx * wd;
            $(".img_box").not(":animated").animate({"margin-left":mlt+"px"}, 500);
       });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>사용자 정의 효과 메소드 - animate()</h1>
        <p>사용자가 애니메이션을 작성할 수 있도록한 메소드</p>
        <article class="data">
            <section id="visual">
                <div class="img_box">
                    <a href="">
                        <img src="dy1.jpg" alt="">
                        <span class="num"></span>
                    </a>
                    <a href="">
                        <img src="dy2.jpg" alt="">
                        <span class="num"></span>
                    </a>
                    <a href="">
                        <img src="dy3.jpg" alt="">
                        <span class="num"></span>
                    </a>
                    <a href="">
                        <img src="im0.jpg" alt="">
                        <span class="num"></span>
                    </a>
                </div>
            </section>
            <section id="btn_box">
                <a class="left">◀</a><a class="right">▶</a>
            </section>
            <div id="num_box"></div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

<br><hr><br>

## jQuery 유틸리티(Utility) 메소드
| 메소드 문법 | 설명 |
|--------------------------------------|------------------------------|
| jQuery.contains("선택자", "조상선택자") | 해당 선택된 요소가 조상선택자에 속하는지 여부 반환 |
| jQuery.data("선택자", "키", "값") | 해당 선택된 요소에 해당 키(필드)에 값을 바운딩시킴 |
| jQuery.dequeue("선택자",[큐이름]) | 해당 선택자가 큐에 있으면, 실행시킴 |
| jQuery.each("배열 또는 객체", function(){}) | 지정된 배열 또는 객체의 요소의 개수 만큼 반복실행 |
| jQuery.extends("배열 또는 객체1", "배열 또는 객체2") | 배열 또는 객체1에 배열 또는 객체2를 확장시켜 객체 합치기 |
| jQuery.grep("배열", function(){}) | 배열 요소에서 function의 비교구문에 해당하는 요소를 반환 |
| jQuery.inArray(찾을값, 배열) | 배열 요소에서 찾고자 하는 값에 해당하는 인덱스를 반환 |
| jQuery.isArray(객체명) | 지정된 객체명이 배열객체인지 여부를 반환 |
| jQuery.isEmptyObject(객체명) | 지정된 객체가 비어 있는지 여부를 반환 |
| jQuery.isFunction(메소드명) | 지정된 메소드가 존재하는지 여부를 반환 |
| jQuery.isNumeric(변수명) | 지정된 변수명이 값이 수치인지 여부를 반환 |
| jQuery.isPlainObject(객체명) | 지정된 객체가 {}의 구성원이 있는 일반객체인지 여부를 반환 |
| jQuery.isWindow(객체명) | 지정된 객체가 window 객체인지 여부를 반환 |
| jQuery.isXMLDoc(문서명) | 지정된 문서가 XML 문서인지 여부를 반환 |
| jQuery.makeArray(객체명) | 지정된 객체를 배열로 변환 |
| jQuery.map(배열객체, function(value, index){}) | 지정된 배열객체를 순회 |
| jQuery.merge(배열1,배열2) | 두 개의 배열을 합쳐 반환 |
| jQuery.noop() | 함수에 내용을 비우기 |
| jQuery.now() | 현재 날짜와 시간을 반환 |
| jQuery.parseHTML(데이터) | 해당 문자열 데이터를 태그로 파싱 |
| jQuery.parseJSON(객체) | 해당 객체를 JSON 객체로 파싱 |
| jQuery.parseXML(데이터) | 해당 데이터를 XML 형태로 파싱 |
| jQuery.trim(문자열) | 해당 문자열의 앞/뒤 공백문자를 제거 |
| jQuery.type(객체명) | 해당 객체의 타입을 반환 |
| jQuery.unique(배열명) | 해당 배열의 중복을 제거하고 반환 |
| jQuery.uniqueSort(배열명) | 해당 배열의 중복을 제거하고, 소트하여 반환 |

※ "jQuery." 으로 시작하는 메소드는 "$." 으로도 쓸 수 있음

### 배열 요소의 필터링
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 61 : 배열의 필터링 유틸리티 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    
    </style>
    <script>
    $(function(){   
        var arr = [ 1, 9, 3, 8, 6, 1, 5, 9, 4, 7, 3, 8, 6, 9, 1 ];
        //아이디가 btn1인 요소를 클릭하면,
        //1) 위 arr 배열의 요소의 데이터를 #res1에 출력
        //2) 위 arr 배열에서 3의 배수가 이고, 2의 배수가 아닌 데이터를 필터링하여 #res2의 자식 요소 li의 텍스트로 각 요소를 출력하시오.
        //3) 위 arr 배열에서 3의 배수가 아닌 데이터를 res3에 출력
        $("#btn1").click(function(){
            $("#res1").text(arr.join(", "));             //1. 요소 출력
            //2-1. 3의  배수이면서, 2의 배수가 아닌 요소를 필터링
            arr1 = jQuery.grep(arr, function(v, i){
                return (v%3==0 && v%2!=0);
            });
            for(var i=0;i<arr1.length;i++){ //2-2. 필터링된 요소 출력
                $("#res2").append("<li>"+arr1[i]+"</li>");
            }
            arr2 = jQuery.grep(arr, function(v, i){ //3-1. 3의 배수가 아닌 데이터 필터링
                return v%3!=0;
            });
            var txt = "";
            for(var i=0;i<arr2.length;i++){   //3-2. 필터링된 요소 텍스트로 출력
                txt+=arr2[i] + ", ";
            }
            $("#res3").text(txt);
        });

    //아이디가 btn2인 요소를 클릭하면, #lst1, #lst2의 자식 요소의 qr 속성이 bind인 요소만 필터링하여 #res4의 목록으로 구성하시오.
        $("#btn2").click(function(){
            var lst = $("#lst1 li, #lst2 li");
            var res = $.grep(lst, function(v, i){
                return ($(v).attr("qr")=="bind");
            });
            for(var i=0;i<res.length;i++){
                $("#res4").append(res[i]);
            }
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>배열의 필터링 유틸리티 메소드 - grep()</h1>
        <p>배열에서 특정 요소만 필터링 하여 배열로 반환하는 메소드</p>
        <article class="data">
            <div id="res1"></div>
            <ul id="res2">

            </ul>
            <div id="res3"></div>
            <button type="button" id="btn1">grep를 이용한 배열 필터링1</button>
            <div id="data1">
                <ul id="lst1">
                    <li qr="bind">javascript</li>
                    <li qr="frame">React</li>
                    <li qr="frame">Vue</li>
                    <li qr="bind">Momento</li>
                </ul>
                <ul id="lst2">
                    <li qr="frame">Node</li>
                    <li qr="bind">jQuery</li>
                    <li qr="bind">Lodash</li>
                    <li qr="frame">Angular</li>
                </ul>
            </div>
            <button type="button" id="btn2">grep를 이용한 배열 필터링2</button>
            <div id="res4"></div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 배열 요소의 가공
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 62 : 배열의 가공 유틸리티 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    var arr1 = ["kim", "lee", "park", "joeng", "han"];
    var arr2 = ["kitae", "hayoung", "pyoenghwa", "jinseok", "taiheon"];
    $(function(){
        //아이디가 btn1인 요소를 클릭하면,
        //1) 위 arr1 배열의 요소의 데이터를 대문자로 변환하여 #res1에 출력
        //2) 위 arr1과 arr2 요소를 순회하여 더한 후 #res2의 자식 요소 li의 텍스트로 각 요소를 출력하시오.
        $("#btn1").click(function(){
            var data1 = $.map(arr1, function(value, index){
                return (value.toUpperCase());
            });
            $("#res1").text(data1.join(", "));
            
            var data2 = $.map(arr1, function(value, index){
                return (value+arr2[index]);
            });
            for(var i=0; i<data2.length;i++){
                $("#res2").append("<li>"+data2[i]+"</li>");
            }
        });
        //아이디가 btn2인 요소를 클릭하면,
        //아이디가 lst1인 요소의 자식 요소를 가공하여 data-val 값이 front인 요소와 back인 요소를 두 개의 각 각의 그룹으로 분리된 ul의 목록요소 형태로 출력되도록 하시오.
        $("#btn2").click(function(){
            var data = $("#lst1 li").clone();
            $("#res3").append("<h2>FRONT END</h2><ul id='front'></ul>");
            $("#res3").append("<h2>BACK END</h2><ul id='back'></ul>");
            var front = $.map(data, function(value, index){
                if($(value).attr("data-val")=="front"){
                    return value;
                }
            });
            for(var i=0;i<front.length;i++){
                $("#front").append(front[i]);
            }
            var back = $.map(data, function(value, index){
                if($(value).attr("data-val")=="back"){
                    return value;
                }
            });
            for(var i=0;i<back.length;i++){
                $("#back").append(back[i]);
            }
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>배열의 가공 유틸리티 메소드 - map()</h1>
        <p>배열를 가공 하여 또 다른 배열로 반환하는 메소드</p>
        <article class="data">
            <div id="res1"></div>
            <ul id="res2">

            </ul>
            <button type="button" id="btn1">map를 이용한 배열 가공1</button>
            <div id="data1">
                <ul id="lst1">
                    <li data-val="front">HTML</li>
                    <li data-val="back">java</li>
                    <li data-val="front">CSS</li>
                    <li data-val="back">jsp</li>
                    <li data-val="back">servlet</li>
                    <li data-val="front">javascript</li>
                </ul>
            </div>
            <button type="button" id="btn2">map를 이용한 배열 가공2</button>
            <div id="res3">

            </div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 배열 요소의 합치기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 63 : 배열의 합치기 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    
    </style>
    <script>
    var arr1 = ["kim", "lee", "park", "joeng", "han"];
    var arr2 = ["kang", "choi", "oh", "nam"]
    $(function(){
        //아이디가 btn1인 요소를 클릭하면,
        //1) 위 arr1과 arr2 배열 요소를 합치기 하여 #res1에 출력
        $("#btn1").click(function(){
            var mg = $.merge(arr1, arr2);
            $("#res1").text(mg.join(", "));
        });
        //아이디가 btn2인 요소를 클릭하면,
        //2) 아래 아이디가 lst1인 요소의 자식 요소와 lst2인 요소를 합치기 하여 비순서형 목록 형태로 아이디가 res2인 곳에 출력
        $("#btn2").click(function(){
            $("#res2").append("<ul id='merge_data'></ul>");
            var ar1 = $("#lst1 li").clone();
            var ar2 = $("#lst2 li").clone();
            var mg = $.merge(ar1, ar2);
            $.each(mg, function(index){
                $("#merge_data").append(mg[index]);
            });
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>배열의 합치기 메소드 - merge()</h1>
        <p>배열의 요소를 합치기하여 또 다른 배열로 반환하는 메소드</p>
        <article class="data">
            <div id="res1"></div>
            <button type="button" id="btn1">merge를 이용한 배열 합치기1</button>
            <div id="data1">
                <ul id="lst1">
                    <li>javascript</li>
                    <li>jQuery</li>
                    <li>Lodash</li>
                    <li>Momento</li>
                </ul>
                <ul id="lst2">
                    <li>Node</li>
                    <li>React</li>
                    <li>Vue</li>
                    <li>Angular</li>
                </ul>
            </div>
            <button type="button" id="btn2">merge를 이용한 배열 합치기2</button>
            <div id="res2"></div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 배열 요소의 순회
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 64 : 배열(객체) 요소 또는 속성 탐색 순회 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    var arr1 = ["kim", "lee", "park", "joeng", "han"];
    var obj1 = {name:"kim", age:38, height:174};
    var arr2 = ["kang", "choi", "oh", "nam"]
    $(function(){   
    //아이디가 btn1인 요소를 클릭하면,
    //1) 위 arr1를 순회하여 해당 수 만큼 #res1에 자식 요소인 li요소와 텍스트로 출력
    $("#btn1").click(function(){
        $.each(arr1, function(index, value){
            $("#res1").append("<li>"+value+"</li>");
        });
        $.each(obj1, function(key, value){
            $("#res3").append("<li>"+key+" : "+value+"</li>");
        });
    });
    //아이디가 btn2인 요소를 클릭하면,
    //2) 아이디가 lst1인 요소의 자식 요소 중에서 data-val 속성이 back인 텍스트 데이터를 res2의 자식 요소인 li요소와 텍스트로 출력하시오.
        $("#btn2").click(function(){
            var tar = $("#lst1 li").clone();
            $.each(tar, function(index, value){
                var th = $(this).attr("data-val");
                if(th=="back"){
                    $("#res2").append(value);
                }
            });
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>배열 요소 탐색 및 순회 메소드 - each()</h1>
        <p>배열의 요소를 탐색 및 순회하는 메소드</p>
        <article class="data">
            <ul id="res1"></ul>
            <button type="button" id="btn1">each를 이용한 배열 요소 순회</button>
            <div id="data2">
                <ul id="lst1">
                    <li data-val="front">HTML</li>
                    <li data-val="back">java</li>
                    <li data-val="front">CSS</li>
                    <li data-val="back">jsp</li>
                    <li data-val="back">servlet</li>
                    <li data-val="front">javascript</li>
                </ul>
            </div>
            <ul id="res3"></ul>
            <button type="button" id="btn2">each를 이용한 배열 요소 탐색</button>
            <div id="data3">
                <ul id="res2"></ul>
            </div>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 객체의 요소 합치기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 65 : 객체 요소 합치기 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    var obj1 = { apple:0, banana:{ weight:52, price:1000 }, cherry:97};
    var obj2 = {  banana:{ price:2000 },  durian:10000 };    
    //아이디가 btn1인 요소를 클릭하면,
    //1) 위 obj1과 obj2인 객체를 합치기 하여 map과 같은 JSON 의 형태로 #res1에 출력하시오.
    $(function(){
        $("#btn1").click(function(){
            var obj = $.extend(obj1, obj2);
            $("#res1").append(JSON.stringify(obj));
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>객체 요소 합치기 메소드 - extend()</h1>
        <p>객체의 요소를 합치는 메소드</p>
        <article class="data">
            <div id="res1"></div>
            <button type="button" id="btn1">extend를 이용한 객체 요소 합치기</button>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 객체 데이터의 데이터 바인딩
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 66 : 해당 요소에 데이터 바인딩시키는 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //아이디가 btn1인 요소를 클릭하면,
    //1) 아이디가 res1인 곳의 첫 span 요소에 "취업"을 마지막 span 요소에 숫자 100을 객체로 만들어 데이터를 바인딩시키시오. 
    $(function(){
        $("#btn1").click(function(){
            var div = $("#res1");
            $.data(div, "study", {
                first:"취업",
                last:100
            });
            $("span").first().text($.data(div, "study").first);
            $("span").last().text($.data(div, "study").last);
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>특정 요소에 값 바인딩 메소드 - data()</h1>
        <p>특정 요소에 값을 바인딩 시키는 메소드</p>
        <article class="data">
            <div id="res1">
                우리는 백엔드 기능과 프론트엔드 기능을 모두 학습하여 웹 개발자로 
                <span></span>
                하기 위하여 열심히 학습을 하고 있으며, 
                <span></span>% 취업하고자 합니다.
            </div>
            <button type="button" id="btn1">data를 이용한 값 바인딩 시키기</button>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### 날짜 객체의 제어와 계산식 처리
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 67 : 날짜와 계산식 처리 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    
    </style>
    <script>
    $(function(){       
        //아이디가 btn1인 요소를 클릭하면,
        //1) #res1에 현재 시각을 출력
        //2) #res2에 아이디가 reg인 곳의 계산식을 처리하여 그 결과인 k를 출력
        $("#btn1").click(function(){
            $("#res1").text($.now());       //Date.now()
            $.globalEval($("#reg").text());
            $("#res2").text(k);
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>날짜와 문자열 계산식 처리 메소드 - now(), glovalEval()</h1>
        <article class="data">
            <div id="reg">var k = 1004;</div>
            <div id="res1"></div>
            <div id="res2"></div>
            <button type="button" id="btn1">현재 시각과 계산식의 처리</button>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

### html 파싱하기
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 68 : 외부 엘리먼트 HTML로 파싱 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    var str = "hello, <b>data binding</b> jQuery."
    //아이디가 btn1인 요소를 클릭하면,
    //1) 위 str 데이터를 #res1에 태그 형식으로 출력하시오.
    $(function(){
        $("#btn1").click(function(){
            $("#res1").append($.parseHTML(str));
        });
    });
    </script>
</head>
<body>
    <section class="container">
        <h1>외부 엘리먼트 HTML로 파싱 메소드 - parseHTML()</h1>
        <p>불러온 외부 엘리먼트를 포함한 데이터를 HTML로 파싱하는 메소드</p>
        <article class="data">
            <div id="res1"></div>
            <button type="button" id="btn1">외부 텍스트를 포함한 내용을 HTML로 파싱하기</button>
        </article>
    </section>
    <br><hr><br>
    </div>
</body>
</html>
```

## 배열 데이터와 객체 데이터를 활용하여 구글 차트 만들기

### 구글 차트 - 수직 막대 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 69 : jQuery 데이터 바인딩과 구글 차트 - 수직 막대</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 야식의 인기도를 나타내는 수직 막대 그래프를 그리시오.
    //데이터 : 피자:18, 치킨:42, 보쌈:14, 닭발:9, 기타:11
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>구글 차트 수직막대 그래프 - ColumnChart()</h2>
        <h2>구글 차트 그리기 - draw()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ["음식명", "인기도"], ["피자",18], ["치킨",42], ["보쌈",14], ["닭발",9], ["기타",11]
        ]);
        var options = {
            title : "야식의 인기도", width:600, height:400,
            bar : { groupWidth: "80%"}, legend : { position:"none" }
        };
        var chart = new google.visualization.ColumnChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 레이블 설정
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 70 : jQuery 데이터 바인딩과 구글 차트 - 수직 막대의 데이터 레이블</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 야식의 인기도를 나타내는 데이터 레이블 수직 막대 그래프를 그리시오.
    //데이터 : 피자:18, 치킨:42, 보쌈:14, 닭발:9, 기타:11
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <p>구글 수직 막대 그래프에 데이터 레이블과 값 표시</p>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ["음식명", "인기도", {role:'annotation'}, {role:'style'}], ["피자",18,"18","deeppink"], ["치킨",42,"42","red"], ["보쌈",14,"14","deepskyblue"], ["닭발",9,"9","gold"], ["기타",11,"11","green"]
        ]);
        var options = {
            title : "야식의 인기도", width:600, height:400,
            bar : { groupWidth: "80%"}, legend : { position:"none" }
        };
        var chart = new google.visualization.ColumnChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 묶은 세로 막대형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 71 : jQuery 데이터 바인딩과 구글 차트 - 묶은 세로 막대 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 묶은 세로 막대 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <p>구글 묶은 세로 막대 그래프</p>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ["색상","빨","주","노","초","파","남","보"],
            ["남자",2,3,4,5,4,3,2],
            ["여자",5,4,3,2,3,4,5]
        ]);
        var options = {
            title : "남녀의 색 선호 그래프", width:800, height:400,
            colors:["red","orange","yellow","green","blue","navy","purple"],
            bar:{groupWidth:"80%"},
            isStacked:false //true-누적형, false-기본형
        };
        var chart = new google.visualization.ColumnChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 누적 세로 막대형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 72 : jQuery 데이터 바인딩과 구글 차트 - 누적 수직 막대 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 누적 세로 막대 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <p>구글 누적 세로 막대 그래프</p>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ["년대","짜장면","붕어빵","달고나","풍선껌"],
            ['1950', 10, 20, 30, 40], // 제목과 항목수를 맞춰주어야 합니다.
            ['1960', 15, 30, 35, 20],
            ['1970', 20, 25, 40, 30],
            ['1980', 10, 30, 20, 50],
            ['1990', 5, 10, 25, 55]
        ]);
        var options = {
            title : "그 때 그 시절 그 것", width:700, height:400,
            bar:{groupWidth:"50%"},
            isStacked:true //true-누적형, false-기본형
        };
        var chart = new google.visualization.ColumnChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 꺾은 선 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 73 : jQuery 데이터 바인딩과 구글 차트 - 꺾은 선 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 꺾은 선 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>꺾은 선 그래프 - LineChart()</h2>
        <p>구글 누적 세로 막대 그래프</p>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['Year', 'Sales', 'Expenses'],
            ['2004', 1000, 400],
            ['2005', 1170, 460],
            ['2006', 660, 1120],
            ['2007', 1030, 540]
        ]);
        var options = {
            title: '꺾은선 그래프', width: 700, height: 400
        };
        var chart = new google.visualization.LineChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 원형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 74 : jQuery 데이터 바인딩과 구글 차트 - 원형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 원형 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>원형 그래프 - PieChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['Task', 'Hours per Day'],
            ['Work', 11],
            ['Eat', 2],
            ['Commute', 2],
            ['Watch TV', 2],
            ['Sleep', 7]
        ]);
        var options = {
            title: '하루 일과 원형 그래프', width: 700, height: 400
        };
        var chart = new google.visualization.PieChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 거품형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 75 : jQuery 데이터 바인딩과 구글 차트 - 거품형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 거품형 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>거품형 그래프 - BubbleChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['ID', '기대수명', '출산율', '지역', '인구'],
            ['CAN', 80.66, 1.67, 'North America', 33739900],
            ['DEU', 79.84, 1.36, 'Europe', 81902307],
            ['DNK', 78.6, 1.84, 'Europe', 5523095],
            ['EGY', 72.73, 2.78, 'Middle East', 79716203],
            ['GBR', 80.05, 2, 'Europe', 61801570],
            ['IRN', 72.49, 1.7, 'Middle East', 73137148],
            ['IRQ', 68.09, 4.77, 'Middle East', 31090763],
            ['ISR', 81.55, 2.96, 'Middle East', 7485600],
            ['RUS', 68.6, 1.54, 'Europe', 141850000],
            ['USA', 78.09, 2.05, 'North America', 307007000]
        ]);
        var options = {
            title: '버블 차트', hAxis: { title: '기대 수명' }, vAxis: { title: '출산율' }, bubble: { textStyle: { fontSize: 11 } }
        };
        var chart = new google.visualization.BubbleChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 도넛형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 76 : jQuery 데이터 바인딩과 구글 차트 - 도넛형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 도넛형 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>도넛형 그래프 - PieChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['항목', '하루당 할애시간'],
            ['일하는 시간', 11],
            ['식사 시간', 2],
            ['출퇴근 시간', 2],
            ['TV 시청 시간', 2],
            ['수면 시간', 7]
        ]);
        var options = {
            title: '도넛형 차트', pieHole: 0.4,
        };
        var chart = new google.visualization.PieChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 가로 막대 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 77 : jQuery 데이터 바인딩과 구글 차트 - 가로 막대 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 가로 막대 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>가로 막대 그래프 - BarChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ["Element", "Density", { role: "style" }],
            ["Copper", 8.94, "#b87333"],
            ["Silver", 10.49, "silver"],
            ["Gold", 19.30, "gold"],
            ["Platinum", 21.45, "color: #e5e4e2"]
        ]);
        var view = new google.visualization.DataView(data);
        view.setColumns([0, 1,
        {
            calc: "stringify",
            sourceColumn: 1,
            type: "string",
            role: "annotation"
        },
        2]);
        var options = { title: "가로막대형 그래프", width: 600, height: 400,
            bar: { groupWidth: "95%" },legend: { position: "none" },
        };
        var chart = new google.visualization.BarChart(document.getElementById("chart1"));
        chart.draw(view, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 이중 축 혼합형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 78 : jQuery 데이터 바인딩과 구글 차트 - 이중 축 혼합형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 이중 축 혼합형 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>이중 축 혼합형 그래프 - ComboChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['Month', 'Bolivia', 'Ecuador', 'Madagascar', 'Papua New Guinea', 'Rwanda', 'Average'],
            ['2004/05', 165, 938, 522, 998, 450, 614.6],
            ['2005/06', 135, 1120, 599, 1268, 288, 682],
            ['2006/07', 157, 1167, 587, 807, 397, 623],
            ['2007/08', 139, 1110, 615, 968, 215, 609.4],
            ['2008/09', 136, 691, 629, 1026, 366, 569.6]
        ]);
        var options = { 
            title: '이중축 혼합형 그래프',
            vAxis: { title: 'Cups' },
            hAxis: { title: 'Month' },
            seriesType: 'bars',
            series: { 5: { type: 'line' } }
        };
        var chart = new google.visualization.ComboChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

### 구글 차트 - 캘린더 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 78 : jQuery 데이터 바인딩과 구글 차트 - 달력형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 캘린더 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>캘린더 그래프 - Calendar()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['calendar']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = new google.visualization.DataTable();
        data.addColumn({ type: 'date', id: 'Date' });
       data.addColumn({ type: 'number', id: 'Won/Loss' });
       data.addRows([
          [ new Date(2012, 3, 13), 37032 ],
          [ new Date(2012, 3, 14), 38024 ],
          [ new Date(2012, 3, 15), 38024 ],
          [ new Date(2012, 3, 16), 38108 ],
          [ new Date(2012, 3, 17), 38229 ],
          // Many rows omitted for brevity.
          [ new Date(2013, 9, 4), 38177 ],
          [ new Date(2013, 9, 5), 38705 ],
          [ new Date(2013, 9, 12), 38210 ],
          [ new Date(2013, 9, 13), 38029 ],
          [ new Date(2013, 9, 19), 38823 ],
          [ new Date(2013, 9, 23), 38345 ],
          [ new Date(2013, 9, 24), 38436 ],
          [ new Date(2013, 9, 30), 38447 ]
        ]);
        var options = {
            title: "달력형 그래프",
            height: 350,
        };
        var chart = new google.visualization.Calendar(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```


### 구글 차트 - 원통형 그래프
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 80 : jQuery 데이터 바인딩과 구글 차트 - 원통형 그래프</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <script src="http://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
    <script src="https://www.gstatic.com/charts/loader.js" type="text/javascript"></script>
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
    <script>
    //문서가 로딩되면, 아이디가 chart1인 곳에 구글 차트를 활용하여 원통형 그래프를 그리시오.
    </script>
</head>
<body>
    <section class="container">
        <h2>구글 차트 데이터 설정 - arrayToDataTable()</h2>
        <h2>원통형 그래프 - CandlestickChart()</h2>
        <article class="data">
            <div id="chart1"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
        // 차트 패키지 로딩
        google.charts.load('current', {packages:['corechart']});
    </script>
    <script>
    google.charts.setOnLoadCallback(drawChart);
    //실제 데이터베이스에서 매핑된 데이터를 배열로 먼저 파싱한 후 접목할 것.
    function drawChart(){
        var data = google.visualization.arrayToDataTable([
            ['Mon', 20, 28, 38, 45],
            ['Tue', 31, 38, 55, 66],
            ['Wed', 50, 55, 77, 80],
            ['Thu', 77, 77, 66, 50],
            ['Fri', 68, 66, 22, 15]
        ], true);

        var options = { title:"원통형 그래프",
        legend:'none', width:1000, height:600
        };
        var chart = new google.visualization.CandlestickChart(document.getElementById("chart1"));
        chart.draw(data, options);
    }
    </script>
</body>
</html>
```

<br><hr><br>

## jQuery 비동기(Ajax) 방식
| 메소드 문법 | 설명 |
|--------------------------------------|------------------------------|
| .ajaxComplete() | Ajax 요청 완료 시 호출할 핸들러를 지정 |
| .ajaxError() | Ajax 요청이 오류와 함께 완료될 때 호출할 핸들러를 지정 |
| .ajaxSend() | Ajax 요청이 전송되기 전에 실행할 함수를 지정 |
| .ajaxStart() | 첫 번째 Ajax 요청이 시작될 때 호출할 핸들러를 지정 |
| .ajaxStop() | 모든 Ajax 요청이 완료되었을 때 호출할 핸들러를 지정 |
| .ajaxSuccess() | Ajax 요청이 성공적으로 완료될 때마다 실행할 함수를 지정 |
| jQuery.ajax() | ajax 기능을 수행 |
| jQuery.ajaxPrefilter() | ajax 기능이 수행되기 전에 처리할 내용 지정 |
| jQuery.ajaxSetup() | ajax 처리에 앞서 기본값을 설정 |
| jQuery.ajaxTransport() | ajax 처리시에 데이터를 전송할 객체를 생성 |
| jQuery.get() | GET 요청 방식으로 서버에서 데이터를 로딩 |
| jQuery.getJSON() | GET 요청 방식으로 서버에서 데이터를 받아 JSON 으로 인코딩 |
| jQuery.getScript() | GET 요청 방식으로 서버에서 데이터를 받아 Javascript 파일로 로딩 |
| jQuery.param() | URL 쿼리 스트링이나 Ajax 요청에 사용하기에 적합한 배열, 일반 객체 또는 jQuery 객체로 변환 |
| jQuery.post() | POST 요청 방식으로 서버에서 데이터를 로딩 |
| .load() | 서버에서 데이터를 로드하고 반환된 HTML을 일치하는 요소에 배치 |
| .serialize() | 폼 요소의 데이터를 그룹화하여 전송 적합한 문자열로 인코딩 |
| .serializeArray() | 폼 요소의 데이터를 전송 적합한 배열로 인코딩 |
※ "jQuery." 으로 시작하는 메소드는 "$." 으로도 쓸 수 있음

<br><hr><br>

### Ajax 이벤트 메소드
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 81 : jQuery Ajax 이벤트 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 이벤트 메소드</h2>
        <p>ajaxStart(), ajaxStop(), ajaxComplete(), ajaxSuccess(), ajaxError(), ajaxSend()</p>
        <h3>ajaxStart() : ajax 기능이 시작될 때 발생하는 이벤트</h3>
        <h3>ajaxStop() : ajax 기능이 정지될 때 발생하는 이벤트</h3>
        <h3>ajaxComplete() : ajax 기능이 완료될 때 발생하는 이벤트</h3>
        <h3>ajaxSuccess() : ajax 기능이 성공 수행되었을 때 발생하는 이벤트</h3>
        <h3>ajaxError() : ajax 기능이 실패 수행되었을 때 발생하는 이벤트</h3>
        <h3>ajaxSend() : ajax에 의해 데이터 전송 또는 수신이 이루어질 때 발생하는 이벤트</h3>
        <h2 style="color:red">이벤트 발생 순서</h2>
        <p>성공 수행시 : start -> send -> sucess -> complete -> stop</p>
        <p>실패 수행시 : start -> send -> error -> stop</p>
        <h2>데이터 로딩 메소드 - load()</h2>
        <article class="data">
            <input type="button" id="trigger1" value="success button"/>
            <input type="button" id="trigger2" value="error button"/><br>
            <div style="display:inline;">log : </div>
            <div id="log" style="display:inline;"></div><br>
            <div style="display:inline;">result : </div>
            <div id="result" style="display:inline;"></div><br>            
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#log").css("display","none");
    });    
    $(document).ajaxStart(function(event, xhr, settings){ 
        $("#log").delay(500).fadeIn(500, function() {
            $(this).text('start').delay(1000).fadeOut(500);
        });    
    })
    .ajaxStop(function(event, xhr, settings){ 
        $("#log").delay(500).fadeIn(500, function() {
            $(this).text('stop').delay(1000).fadeOut(500);
        });    
    })
    .ajaxComplete(function(event, xhr, settings){ 
        if(settings.url === "test.html") {
            $("#log").delay(500).fadeIn(500, function() {
                $(this).text('complete').delay(1000).fadeOut(500);
            }); 
        }
    })
    .ajaxSuccess(function(event, xhr, settings){ 
        $("#log").delay(500).fadeIn(600, function() {
            $(this).text('success').delay(1000).fadeOut(500);
        });  
    })
    .ajaxError(function(event, xhr, settings){ 
        $("#log").delay(500).fadeIn(600, function() {
            $(this).text('error').delay(1000).fadeOut(500);
        });  
    })
    .ajaxSend(function(event, xhr, settings){ 
        $("#log").delay(500).fadeIn(600, function() {
            $(this).text('send').delay(1000).fadeOut(600);
        });  
    });
    </script>
    <script>
    $(document).ready(function(){
	  $('#trigger1').click(function() {
        $("#log").stop();
		$('#result').load("test.html");
	  });
	  $('#trigger2').click(function() {
		$('#result').load("error.html");
	  });	  
    });
    </script>
</body>
</html>
```

### Ajax 로딩
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 82 : jQuery Ajax 문서로딩 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 문서 로딩 메소드 - load()</h2>
        <article class="data">
            <input type="button" id="trigger1" value="success button"/>
            <input type="button" id="trigger2" value="target button"/>
            <input type="button" id="trigger3" value="json button"/><br>
            <div style="display:inline;">result : </div>
            <div id="result" style="display:inline;"></div><br>            
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
	  $('#trigger1').click(function() {
		$('#result').load("test.html #projects li");
	  });
	  $('#trigger2').click(function() {
		$('#result').load("error.html", function(response, status, xhr){
            if (status == "error") {
                var msg = "문서의 내용을 불러오지 못했습니다.";
                $("#result").html( msg + xhr.status + " " + xhr.statusText );
            }
        });
	  });
	  $('#trigger3').click(function() {
		$('#result').load("data.json");
	  });
    });
    </script>
</body>
</html>
```

### Ajax 쿼리스트링의 데이터 직렬화
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 83 : jQuery Ajax 전송데이터 파라미터화 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터의 직렬화 메소드 - serialize()</h2>
        <p>Get 방식으로 전송할 데이터를 하나의 매개값으로 쿼리스트링화(직렬화)할 수 있음</p>
        <article class="data">
            <form>
                <select name="job">
                  <option>Employment</option>
                  <option>Founded</option>
                </select>
                <br>
                <select name="position" multiple="multiple">
                  <option>FRONT-END</option>
                  <option>SI</option>
                  <option selected="selected">SM</option>
                </select>
                <br>
                <input type="checkbox" name="area" value="수도권" id="ch1">
                <label for="ch1">수도권</label>
                <input type="checkbox" name="area" value="비수도권" checked="checked" id="ch2">
                <label for="ch2">지방</label>
                <br>
                <input type="radio" name="part" value="개발자" checked="checked" id="r1">
                <label for="r1">개발자</label>
                <input type="radio" name="part" value="비개발자" id="r2">
                <label for="r2">비개발자</label>
              </form> <br>
              <button type="button" id="btn1">전송할 데이터 확인</button>
              <div id="result"></div>           
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        function dataValues(){
            var str = $("form").serialize();
            $("#result").text(str);
            //$.ajax({url:"research.do?"+str})
        }
        $("#btn1").on("click", function() { dataValues(); } );
    });
    </script>
</body>
</html>
```

### Ajax 전송 데이터 매개변수의 배열화
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 84 : jQuery Ajax 전송데이터 배열화 메소드</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터의 배열화 메소드 - serializeArray()</h2>
        <article class="data">
            <form>
                <div><input type="text" name="a" value="1" id="a"></div>
                <div><input type="text" name="b" value="2" id="b"></div>
                <div><input type="hidden" name="c" value="3" id="c"></div>
                <div>
                  <textarea name="d" rows="8" cols="40">4</textarea>
                </div>
                <div><select name="e">
                  <option value="5" selected="selected">5</option>
                  <option value="6">6</option>
                  <option value="7">7</option>
                </select></div>
                <div>
                  <input type="checkbox" name="f" value="8" id="f">
                </div>
                <div>
                  <input type="submit" name="g" value="전송" id="g">
                </div>
            </form>  
            <br>
            <div id="result"></div>     
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("form").submit(function(event) {
            var data = $(this).serializeArray();
            $("#result").text(data);
            console.log(data);
            event.preventDefault();
        });
    });
    </script>
</body>
</html>
```

### Ajax 의 설정
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 85 : jQuery Ajax 전송받을 데이터 지정</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 전송받을 데이터 지정 메소드 - ajaxSetup()</h2>
        <article class="data">
            <div><h2>AJAX Setup</h2></div>
            <button type="button" id="btn1">데이터 받아오기</button>    
            <div id="result"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#btn1").click(function(){
            $.ajaxSetup({url: "test.txt", 
                success: function(result){
                    $("#result").html(result);
                }
            });
            //전송 받기 전의 해당 파일과 전송에 관한 정보를 객체에 저장하기
            var currentRequests = {};   //저장 객체 선언
            $.ajaxPrefilter(function(options, originalOptions, jqXHR ) {
                console.log(options.url);
                if (options.abortOnRetry) {
                    if (currentRequests[options.url]) {
                        currentRequests[options.url].abort();
                    }
                    currentRequests[options.url] = jqXHR;
                }
                console.log(currentRequests);
            });
            
            //전송 객체를 생성 - 이미지 객체를 생성
            $.ajaxTransport("image", function(s) {
                if ( s.type === "GET" && s.async ) {
                    var image;
                    return {
                        send: function( _ , callback ) {
                            image = new Image();
                            function done( status ) {
                                if(image) {
                                    var statusText = (status === 200) ? "success" : "error",
                                    tmp = image;
                                    image = image.onreadystatechange = image.onerror = image.onload = null;
                                    callback( status, statusText, { image: tmp } );
                                }
                            }
                            image.onreadystatechange = image.onload = function() {
                                done( 200 );
                            };
                            image.onerror = function() {
                                done( 404 );
                            };
                            image.src = s.url;
                        },
                        abort: function() {
                            if ( image ) {
                                image = image.onreadystatechange = image.onerror = image.onload = null;
                            }
                        }
                    };
                }
            });
            $.ajax();
        });
    });
    </script>
</body>
</html>
```

### Ajax의 데이터 선택적 송수신 메소드

### Ajax 객체 데이터 수신
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 86 : jQuery Ajax 데이터 송수신 처리1</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터 송수신 메소드 - ajax()</h2>
        <article class="data">
            <div><h2>AJAX Data Trans</h2></div>
            <input type="text" id="id" name="id" placeholder="id 입력" autofocus>
            <button type="button" id="btn1">데이터 전송 및 받기</button>    
            <ul id="result"></ul>
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#btn1").click(function(){
            var id = $("#id").val();
            if(id==""){
                alert("값이 비어 있습니다.");
                return false;
            }
            //ajax 메소드는 get과 post 방식을 선택할 수 있음.
            $.ajax({
                url:"getMember.do?userId="+id,     //요청 데이터를 받아 처리하는 서버측 컨트롤러 또는 페이지 주소
                //data:id,      //post 방식으로 서버로 전송할 데이터 - string 또는 object
                method:"GET",   //전송 방식 : post, get, put
                dataType:"json" //반환받을 데이터 타입 - json, xml, script, html
            }) 
            .done(function(res){ //요청 처리에 대한 성공시 처리할 문장
                $.each(res, function(key, value){
                    $("#result").append("<li>"+key+" : "+value+"</li>");
                });
            })
            .fail(function(xhr, status, errorThrown){  //요청 처리에 대한 실패시 처리할 문장
                $("#result").append("<li>"+xhr.status+","+xhr.statusText+"</li>");
            })
            .always(function(xhr, status){  //요청처리를 실패하든 성공하든 무조건 실행해야 하는 내용 기술 
                $("#result").append("<li>"+xhr.status+"</li>");
            });
        });
    });
    //컨트롤러에서
    /*
    //회원관리 목록
	@GetMapping("test3")
	public String testLoad3(Model model) throws Exception {
		return "ajax/test3";
	}
	
    //회원 상세 정보 요청
	@GetMapping("getUser.do")
	@ResponseBody
	public UserDTO getUser(@RequestParam("id") String id, Model model) throws Exception {
		UserDTO user = ajaxService.getUser(id);
		return user;
	}
    */
    </script>
</body>
</html>
```

### Ajax 리스트 데이터 수신
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 87 : jQuery Ajax 데이터 송수신 처리2 - get</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .table th { border-top:2px solid #333; }
    .table td, .table th { border-bottom:2px solid #333; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터 송수신 메소드 - ajax()</h2>
        <article class="data">
            <div><h2>AJAX Data Trans</h2></div>
            <button type="button" id="btn1">데이터 목록 받기</button>    
            <table class="table">
                <thead>
                    <tr>
                        <th>아이디</th>
                        <th>비밀번호</th>
                        <th>이름</th>
                    </tr>
                </thead>
                <tbody id="result">

                </tbody>
            </table>
            <a href="/memberList3.do">회원 목록 페이지</a><br>
            <div id="msg"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#btn1").click(function(){
            $.ajax({
                url:"memberList.do",     //요청 데이터를 받아 처리하는 서버측 컨트롤러 또는 페이지 주소
                //data:id,      //post 방식으로 서버로 전송할 데이터 - string 또는 object
                contentType:'application/json;charset=utf-8',
                method:"GET",   //전송 방식 : post, get, put
                dataType:"json" //반환받을 데이터 타입 - json, xml, script, html
            }) 
            .done(function(users){ //요청 처리에 대한 성공시 처리할 문장
                console.log(users);
                $.each(users, function(index, value){
                    var tr = "<tr>";
                    tr = tr + "<td>"+index+" : "+value['userId']+"</td>";
                    tr = tr + "<td>"+index+" : "+value['userPw']+"</td>";                    
                    tr = tr + "<td>"+index+" : "+value['userName']+"</td>";
                    tr = tr + "</tr>";
                    $("#result").append(tr);
                });
            })
            .fail(function(xhr, status, errorThrown){  //요청 처리에 대한 실패시 처리할 문장
                $("#result").append("<tr><td>error</td><td>"+xhr.status+"</td><td>"+xhr.statusText+"</td></tr>");
            })
            .always(function(xhr, status){  //요청처리를 실패하든 성공하든 무조건 실행해야 하는 내용 기술 
                $("#msg").text(xhr.status);
            });
        });
    });
    //컨트롤러에서
    /*
    회원 관리 창 
	@GetMapping("test2")
	public String testLoad2(Model model) throws Exception {
		return "ajax/test2";
	}
	
    //회원 목록 요청
	@GetMapping("userList.do")
	@ResponseBody
	public List<UserDTO> userList(Model model) throws Exception {
		List<UserDTO> userList = ajaxService.userList();
		return userList;
	}
    */
    </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 88 : jQuery Ajax 데이터 송수신 처리3 - post</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .table th { border-top:2px solid #333; }
    .table td, .table th { border-bottom:2px solid #333; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터 송수신 메소드 - ajax()</h2>
        <article class="data">
            <div><h2>AJAX Data Trans</h2></div>
            <button type="button" id="btn1">데이터 목록 받기</button>    
            <table class="table">
                <thead>
                    <tr>
                        <th>아이디</th>
                        <th>비밀번호</th>
                        <th>이름</th>
                    </tr>
                </thead>
                <tbody id="result">

                </tbody>
            </table>
            <a href="/memberList3.do">회원 목록 페이지</a><br>
            <div id="msg"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#btn1").click(function(){
            $.ajax({
                url:"memberList2.do",     //요청 데이터를 받아 처리하는 서버측 컨트롤러 또는 페이지 주소
                //data:id,      //post 방식으로 서버로 전송할 데이터 - string 또는 object
                contentType:'application/json;charset=utf-8',
                method:"POST",   //전송 방식 : post, get, put
                dataType:"json" //반환받을 데이터 타입 - json, xml, script, html
            }) 
            .done(function(users){ //요청 처리에 대한 성공시 처리할 문장
                console.log(users);
                var data = users["users"];
                $.each(data, function(index, value){
                    var tr = "<tr>";
                    tr = tr + "<td>"+index+" : "+value.userId+"</td>";
                    tr = tr + "<td>"+index+" : "+value.userPw+"</td>";                    
                    tr = tr + "<td>"+index+" : "+value.userName+"</td>";
                    tr = tr + "</tr>";
                    $("#result").append(tr);
                });
            })
            .fail(function(xhr, status, errorThrown){  //요청 처리에 대한 실패시 처리할 문장
                $("#result").append("<tr><td>error</td><td>"+xhr.status+"</td><td>"+xhr.statusText+"</td></tr>");
            })
            .always(function(xhr, status){  //요청처리를 실패하든 성공하든 무조건 실행해야 하는 내용 기술 
                $("#msg").text(xhr.status);
            });
        });
    });
    //컨트롤러에서
    /*
    회원 관리 창 
	@GetMapping("test2")
	public String testLoad2(Model model) throws Exception {
		return "ajax/test2";
	}
	
    //회원 목록 요청
	@GetMapping("userList.do")
	@ResponseBody
	public List<UserDTO> userList(Model model) throws Exception {
		List<UserDTO> userList = ajaxService.userList();
		return userList;
	}
    */
    </script>
</body>
</html>
```

### Ajax POST 방식을 이용한 폼 데이터 전송
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 88 : jQuery Ajax 데이터 송수신 처리4 - post</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .table th { border-top:2px solid #333; }
    .table td, .table th { border-bottom:2px solid #333; } 
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터 송수신 메소드 - ajax()</h2>
        <article class="data">
            <div><h2>AJAX Data Trans</h2></div>
            <form>
                <input type="text" id="id" name="id" placeholder="아이디 입력">
                <input type="hidden" id="idck" name="idck" value="no">
            </form>
            <button type="button" id="btn1">아이디 중복체크</button><br>
            <div id="msg"></div>
        </article>
    </section>
    <br><hr><br>
    <script>
    $(document).ready(function(){
        $("#btn1").click(function(){
            var id = $("#id").val();
            if(id==""){
                alert("아이디가 입력되지 않았습니다.");
            }
            $.ajax({
                url:"idCheck.do",     //요청 데이터를 받아 처리하는 서버측 컨트롤러 또는 페이지 주소
                data:id,      //post 방식으로 서버로 전송할 데이터 - string 또는 object
                contentType:'application/json;charset=utf-8',
                method:"POST",   //전송 방식 : post, get, put
                dataType:"json" //반환받을 데이터 타입 - json, xml, script, html
            }) 
            .done(function(res){ //요청 처리에 대한 성공시 처리할 문장
                console.log(res);
            })
            .fail(function(xhr, status, errorThrown){  //요청 처리에 대한 실패시 처리할 문장
                $("#msg").text("아이디 중복 체크를 진행하지 못했습니다.");
            })
            .always(function(xhr, status){  //요청처리를 실패하든 성공하든 무조건 실행해야 하는 내용 기술 

            });
        });
    });
    //컨트롤러에서
    /*
    //아이디 검색 폼
    @GetMapping("test1")
	public String testLoad(Model model) throws Exception {
		return "ajax/test1";
	}
	
	//아이디 중복 체크
	@GetMapping("idCheck.do")
	@ResponseBody
	public boolean idCheck(@RequestParam("id") String id) throws Exception {
		UserDTO user = ajaxService.getUser(id);
		if(user==null) {
			return true;
		} else {
			return false;	
		}
	}
    */
    </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="ko" xmlns="http://www.w3.org/1999/xhtml"
 xmlns:th="http://www.thymeleaf.org"
 xmlns:layout="http://www.ultraq.net.nz/thymeleaf/layout">
<head>
	<!-- templates/ajax/test5.html -->
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 90 : 회원가입</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .table th { border-top:2px solid #333; }
    .table td, .table th { border-bottom:2px solid #333; }
    #addBtn { display:block; width:100px; height:42px; line-height:42px; background:deepskyblue; cursor: pointer; margin-bottom:28px; text-align:center; color:#fff; }
	#submitBtn, #proBtn { border:none; display:block; padding:8px; background:deeppink; color: #FFF2F6; cursor:pointer; margin:18px; float:left; text-decoration:none; box-sizing:border-box; font-size:14px; line-height:16px; }    
    </style>
</head>
<body>
    <section class="container">
        <h2>회원 가입</h2>
        <article class="data">
            <div><h2>회원 등록</h2></div>	 
		    <br><hr><br>		 
		    <form th:action="@{/ajax/addUser.do}" th:object="${user}" method="post">              
                <table class="table">
                	<tbody>
                        <tr>
                        	<th><label for="id">사용자 아이디</label></th>
                            <td>
                            	<input type="text" class="form-control" id="id" th:field="*{id}" name="id" placeholder="사용자 아이디">
                            </td>
                        </tr>
                        <tr>
                        	<th><label for="name">이름</label></th>
                            <td>
                            	<input type="text" class="form-control" id="name" th:field="*{name}" name="name" placeholder="사용자 이름">
                            </td>
                        </tr>
                        <tr>
                        	<th><label for="pw">비밀번호</label></th>
                            <td>
                            	<input type="password" class="form-control" id="pw" th:field="*{pw}" name="pw" placeholder="사용자 비밀번호">
                            </td>
                        </tr>
                        <tr>
                        	<th><label for="pw2">비밀번호 확인</label></th>
                            <td>
                            	<input type="password" class="form-control" id="pw2" name="pw2" placeholder="사용자 비밀번호">
                            </td>
                        </tr>
                        <tr>
                        	<th><label for="email">이메일</label></th>
                            <td>
                            	<input type="email" class="form-control" id="email" th:field="*{email}" name="email" placeholder="이메일 입력">
                            </td>
                        </tr>
                	</tbody>
                </table>
                <div class="container" role="group">
                	<input type="submit" class="btn btn-danger inline" value="회원가입" />
                </div>
             </form>
             <script>
             //컨트롤러에서    
             /*
                //회원 가입 폼
                @GetMapping("test6")
                public String testLoad6(@ModelAttribute("user") UserDTO user, Model model) throws Exception {
                    return "ajax/test6";
                }
                
                @PostMapping("addUser.do")
                public String addUser(@ModelAttribute("user") UserDTO user, Model model) throws Exception {
                    AES256 aes256 = new AES256();
                    user.setPw(aes256.encrypt(user.getPw()));
                    ajaxService.addUser(user);
                    return "ajax/test1";
                }
             */
             </script>		
        </article>
    </section>
    <br><hr><br>
</body>
</html>
```

### Ajax 멀티파트를 이용한 이미지 업로드
```html
<!DOCTYPE html>
<html lang="ko" xmlns="http://www.w3.org/1999/xhtml"
 xmlns:th="http://www.thymeleaf.org"
 xmlns:layout="http://www.ultraq.net.nz/thymeleaf/layout">
<head>

    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery 89 : jQuery Ajax 데이터 송수신 처리5 - post</title>
    <script src="https://code.jquery.com/jquery-latest.js"></script> 
    <style>
    .container { clear:both; width:1000px; margin:20px auto; line-height:2.8; } 
    .container:after { content:""; display:block; clear:both; }
    .data { clear: both; }
    .data:after { content:""; display:block; clear:both; }
    .table th { border-top:2px solid #333; }
    .table td, .table th { border-bottom:2px solid #333; }
    #addBtn { display:block; width:100px; height:42px; line-height:42px; background:deepskyblue; cursor: pointer; margin-bottom:28px; text-align:center; color:#fff; }
	#submitBtn, #proBtn { border:none; display:block; padding:8px; background:deeppink; color: #FFF2F6; cursor:pointer; margin:18px; float:left; text-decoration:none; box-sizing:border-box; font-size:14px; line-height:16px; }    
    </style>
</head>
<body>
    <section class="container">
        <h2>jQuery Ajax 데이터 송수신 메소드 - ajax()</h2>
        <article class="data">
            <div><h2>AJAX Data Trans</h2></div>	 
		    <br><hr><br>		 
		    <form id="addForm">
		    	
		        <div>
		            <label for="img_upload" id="addBtn">이미지 추가</label>
		            <input type="file" name="img_upload" id="img_upload" onchange="previewImage(this,'View_area')" style="display: none;" multiple>
		            <span id='View_area' style='display:block; position:relative; color:black; border: 0px solid black;'></span>
		        </div>
		 
		        <div>
		            <input type="button" class="btn" id="submitBtn" onclick="dataSubmit();" value="전송하기"/>
		            <a class="btn" id="proBtn" href="">이미지 업로드 완료</a>
		        </div>
		 		<br>
		        <ul id="resultDiv">

		        </ul>
		        
		        <div id="inputData">
		        	
		        </div>
		    </form>
            <script>
			function dataSubmit() {
				var maxSize = 10 * 1024 * 1024;
				var sendData = "";
				if ($('#img_upload')[0].files.length >= 4) {
					alert("첨부 가능한 개수를 초과하였습니다. 3개 까지 첨부가 가능합니다.");
				    return false;
				}
				for(var i in $('#img_upload')[0].files){
					if ($('#img_upload')[0].files[i].size > maxSize) {
						alert("첨부된 파일 중에 용량이 초과된 파일이 있습니다.\n이미지를 더블클릭하여 삭제 후 다시 선택하여 주시기 바랍니다.");
					    return false;
					}
				}
				
				var form = $("#addForm")[0]; 
			    var data = new FormData(form);
			 
			    $.ajax({
			        url: "/ajax/url.do",
			        type: "POST",
			        enctype: 'multipart/form-data',
			        data: data,
			        processData: false,
			        contentType: false,
			        dataType:"json",
			    }).done(function (qty) {
					console.log(qty);
					$.each(qty, function(index, value){
						$("#resultDiv").append("<li>"+value+"</li>");
						$("#inputData").append("<input type='hidden' name='imgSrc"+index+"' value='"+value+"'>");
						sendData += "<input type='hidden' name='imgSrc"+index+"' value='"+value+"'>";	
					});
			    });
			}
            /*
            application.properties 에서 다음 사항 추가
            # multipart setting
            spring.servlet.multipart.enabled=true
            spring.servlet.multipart.location=/Users
            spring.servlet.multipart.max-request-size=30MB
            spring.servlet.multipart.max-file-size=10MB
            part4.upload.path=D:/kim6/pro06/myapp/src/main/resources/static/images
            part5.upload.path=D:/kim6/pro06/temp


            컨트롤러에서
            @Value("${part4.upload.path}")
            private String uploadPath;

            @Value("${part5.upload.path}")
            private String uploadPath2;
            
            @RequestMapping(value="url.do", method = {RequestMethod.GET, RequestMethod.POST})
            @ResponseBody
            public List<String> getData(Model model, MultipartHttpServletRequest req){
                
                List<MultipartFile> multipartFileList = new ArrayList<>(); 
                List<String> fileQt = new ArrayList<String>(); 
                try {
                    MultiValueMap<String, MultipartFile> files = req.getMultiFileMap();
                    for (Map.Entry<String, List<MultipartFile>> entry : files.entrySet()) {
                        List<MultipartFile> fileList = entry.getValue();
                        for (MultipartFile file : fileList) {
                            if (file.isEmpty()) continue;
                            multipartFileList.add(file);
                            String originalName = file.getOriginalFilename();
                            String fileName = originalName.substring(originalName.lastIndexOf("//")+1);
                            String folderPath = makeFolder(); //날짜 폴더 생성
                            String uuid = UUID.randomUUID().toString(); //UUID
                            String saveName = uploadPath + File.separator + folderPath +File.separator + uuid + "_" + fileName; //저장할 파일 이름 중간에 "_"를 이용하여 구분                    
                            Path savePath = Paths.get(saveName);
                            //images안의 디렉토리 경로와 파일 이름 별도로 저장하여 서비스로 전달하기 위한 이름 
                            String singleFileName = File.separator + folderPath +File.separator + uuid + "_" + fileName;
                            fileQt.add(singleFileName);
                            //Paths.get() 메서드는 특정 경로의 파일 정보를 가져옵니다.(경로 정의하기)
                            file.transferTo(savePath);
                        }
                    }
                } catch (Exception e){
                    e.printStackTrace();
                }
                return fileQt;
            }
            
            private String makeFolder(){
            String str = LocalDate.now().format(DateTimeFormatter.ofPattern("yyyy/MM/dd"));
            //LocalDate를 문자열로 포멧
            String folderPath = str.replace("/",File.separator);
            File uploadPathFoler = new File(uploadPath, folderPath);
                
            if(uploadPathFoler.exists() == false){
                    uploadPathFoler.mkdirs();
            }
            return folderPath;
            }
            */
            </script>
		    <script src="/js/imageLoad.js"></script>
        </article>
    </section>
    <br><hr><br>
</body>
</html>
```