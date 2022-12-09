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

