# jQuery 생활 코딩 동영상 학습 
# jQuery란? 
* 라이브러리란 ? 자주 사용하는 코드들을 재사용할 수 있는 형태로 가공해서 프로그래밍 효율을 높여주는 코드들 
* jQuery 
  - 엘리먼트를 선택하는 강력한 방법
  - 선택된 엘리먼트들을 효율적으로 제어할 수 있는 다양한 수단을 제공하는 
  - 자바스크립트 라이브러리 
* jQuery 쓰는 방법 
  - 직접 서비스 하는 경우: http://jquery.org 에서 jQuery 소스코드 다운로드 
  - 구글의 자바스크립트 라이브러리를 사용하는 경우 : http://code.google.com/intl/ko-KR/apis/libraries/devguide.html#jquery
  
* jQuery 문법 
* **$(제어대상).method1().method2();**
* *-----주어---- ---------서술어--------*
// 메소드가 리턴될 때, 메소드가 제어했던 대상을 리턴해준다 -> 꼬리에 꼬리를 물며 메소드를 붙일 수 있게 됨 <체인: jQuery의 중요한 특성>


# javascript vs jQuery
W3C DOM 
IE DOM 

# wrapper 
* jQuery(엘리먼트 오브젝트 | 'CSS스타일 선택자') : js 에서 jQuery라는 함수를 호출한다는 의미, e.o 나 선택자를 인자로 넘겨준다 
새로운 라이브러리가 들어왔을 때 충돌할 수도 있다. 그러한 충돌을 회피하기위해 제이쿼리의 중요한 장점이 다음고 같이 있다
* 랩퍼의 안전한 사용
1. $ 대신 jQuery를 사용 
2. $를 함수의 지역변수로 선언해서 외부에 있을지 모르는 타 라이브러리의 $와의 충돌 예방 
```
(function($){
    $('body').html('hello world');
})(jQuery)
```
* 제어 대상을 지정하는 방법
  * jQuery( selector, [context] )
  * jQuery( element )
  
# 선택자
* 래퍼 안의 인자 두개 중에서 'CSS선택자' 가 더 효과적으로 엘리먼트를 선택 할 수 있다. 
* 기본 선택자
  - #은 id selector
  - .은 class selector
  - li와 같은 엘리먼트 태그명은 element selector
  - #jquery, #MYSQL 이런 형태는 다중 선택자 
  
> jQuery API에 들어가면 더 다양한 선택자들에 관한 내용이 들어있음. 

* Filter : 본인이 필요한 것을 찾기 위한 필터링
  - eq
  - gt (greater than)
  - lt (less than)
  - even : 홀수
  - odd : 짝수
  - first
  - last 
 * 속성 : [(속성이름)(기호) = **"속성값"**] 으로 표현
   - *는 포함되는 엘리먼트 찾아냄 
   - =는 일치하는 엘리먼트 찾아냄
   - !=는 일치하지 않는 
   - ^는 처음 등장하는
   - $는 마지막으로 등장하는 
   - [(속성이름)] 만 쓰면 속성이 존재하는 엘리먼트를 찾아냄
   - [(속성이름)][id]를 쓰면 속성들이 존재하는 엘리먼트를 찾아냄
   
# chain 
* jQuery의 메소드들은 반환값으로 자기 자신을 반환해야 한다는 규칙이 있음
* 이를 이용하면 한번 선택한 대상에 대해서 연속적인 제어가 가능 
```
// 예제 1) jQuery를 이용해서 코딩하는 경우 ** 랩퍼를 따로 계속 선언해주지 않아도 된다는 장점!  
<html>
    <body>
        <a id="tutorial" href="http://jquery.com" target="_self">jQuery</a>
        <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
        <script type="text/javascript">
            jQuery('#tutorial').attr('href', 'http://jquery.org').attr('target', '_blank').css('color', 'red'); //
        </script>
    </body>
</html>

// 예제 2) javascript의 DOM을 이용해서 코딩하는 경우
<html>
     <body>
         <a id="tutorial" href="http://jquery.com" target="_self">jQuery</a>
         <script type="text/javascript">
             var tutorial = document.getElementById('tutorial'); 
             tutorial.setAttribute('href', 'http://jquery.org'); // setAttribute : 속성값을 변경시켜주는. (속성의 이름, 속성의 값) -> jQuery에서 attr과 같은 역할 
             tutorial.setAttribute('target', '_blank');
             tutorial.style.color = 'red';
         </script>
     </body>
 </html>
```
* chain의 장점 
  - 코드가 간결해진다 
  - 인간의 언어와 유사해서 사고의 자연스러운 과정과 일치함 
  
* 탐색(traversing)
  - chain의 대상을 바꿔서 체인을 계속 연장시킬 수 있는 방법
  - http://api.jquery.com/category/traversing/
  - http://www.taeyo.pe.kr/Columns/View.aspx?SEQ=375&PSEQ=29 강좌
  - 너무 복잡한 chain은 코드의 가독성을 떨어 뜨릴 수 있음

* end() : chain 컨텍스트를 유지하다가 이 메소드를 만나게 되면, 마지막으로 사용한 트레버스 취소 (탐색중지)
- 하나의 컨텍스트에서 제어하고 싶은 항목 변경 가능
- 경제적, 사고의 흐름도 연속적

# event 
  - 시스템에서 일어나는 사건
  - js 나 jQuery에게 이벤트란, 브라우저에서 일어나는 사건 (클릭, 마우스 이동, 타이핑, 페이지 로딩 등) 
  - 이벤트가 발생했을 때 작동할 로직을 시스템에게 알려두면 이벤트가 발생했을 때 시스템이 그 로직을 호출 
   
  - 이벤트에 대한 기본적인 내용 js 이벤트편 참고: http://http//opentutorials.org/course/49%E2%80%8B
  
* jQuery의 이벤트
  - 크로스브라우징의 문제를 해결해줌
  - bind로 **이벤트 핸들러를 설치**하고, unbind로 **제거** (예제1)
    - unbind할 경우에는 어떤 이벤트 핸들러인지 명확하게 명시한다 !
  - trigger로 이벤트 핸들러를 강제로 실행 (예제2)
    - 
  - click, ready와 같이 다양한 이벤트 헬퍼(helper)를 제공함
  - live를 이용하면 현재 존재 하지 않는 엘리먼트에 이벤트 핸들러를 설치할 수 있음
  - 익명함수 : 이벤트를 위한 함수가 대부분 재활용이 되지 않기 때문에 
  - 이벤트 헬퍼 
  ```
  $(document).ready(function(){ // 여기서 ready가 이벤트 헬퍼 : 이벤트헬퍼는 보다 더 경제적인 기능을 하기 위함 
                 $('#click_me').click(clickHandler);
                 $('#remove_event').click(function(e){
                     $('#click_me').unbind('click', clickHandler);
                 });
                 $('#trigger_event').click(function(e){
                     $('#click_me').trigger('click');
                 });
             })
  ```
  - live로도 이벤트 설치가 가능하다 
# 엘리먼트 제어 
* jQuery는 엘리먼트를 제어하는 일관되고 풍부한 기능들을 제공한다
* http://api.jquery.com/category/manipulation/
* 자식으로 삽입 
  - append()
  - appendTo()
  - html()
  - prepend()
  - prependTo()
  - text()
* 형제로 삽입
  - after()
  - before()
  - insertAfter()
  - insertBefore()
* 부모로 감싸기
  - unwrap()
  - wrap()
  - wrapAll()
  - wrapInner()
* 삭제
  - detach()
  - empty()
  - remove()
  - unwrap()
* 치환
  - replaceAll()
  - replaceWith()
* 클래스
  - addClass(), hasClass(), removeClass(), toggleClass()
* 속성제어
  - attr(), prop(), removeAttr(), removeProp(), val()


# 폼
* 서버로 데이터를 전송하기 위한 수단
* Query는 폼을 제어하는데 필요한 이벤트와 메소드 제공 

$
 focus(), .blur(), .change(), .select()
 
 wrapper를 통해서 change context 유지 가능 
 
 ``` 
 <form action="javascript:alert('success!');">
            <div>
                <input type="text" /> // input 엘리먼트 
                <input type="submit" />
            </div>
        </form>
        <span></span>
        <script>
            $("form").submit( function() { // form 이라는 엘리먼트의 래퍼를 만들었고, submit() : 이벤트 타입에 대한 헬퍼 
                if ($("input:first").val() == "correct") { // val : 엘리먼트의 value 값 리턴 
                    $("span").text("Validated...").show();
                    return true; //리턴하는 값이 true 이면 action 속성으로 정상적인 작동! 
                }
                $("span").text("Not valid!").show().fadeOut(1000);
                return false;
            });
        </script> 
```

# 탐색 
* 체인 컨텍스트를 유지하면서 제어의 대상이 되는 엘리먼트를 변경하는 기법 
* Traversing 
- end() : 이전 컨텍스트로 돌아간다 
- filter() : 현재 엘리먼트 셋 안에서 가져오는거고
- find()는 현재 선택된 엘리먼트 셋들의 자식엘리먼트 안에서 가져오는 것 
 (filter보다 범주가 크다)
- siblings() : 각각의 엘리먼트에 대한 다음 형제 엘리먼트 전부를 선택한다 
 
# 애니메이션 
- fade out
- fade in
- hide 
- show
- slide down 
- slide up 
- mix 

- **animate** : 수치들을 이용해서 현재 엘리먼트가 가진 디자인을 바꿔주는 것 
``` 
$("#go").click( function() {
                $("#block").animate({ // #은 호출인가 ? 
                    width: "300px",
                    opacity: 0.4,
                    marginLeft: "50px",
                    fontSize: "30px",
                    borderWidth: "10px"
                }, 3000); // animation 효과가 3초안에 끝난다 
``` 
fail click to do again 
# Ajax
* Asynchronous JavaScript and XML 의 약자
* 자바스크립트를 이용해서 비동기식으로 서버와 통신하는 방식. 이 때 XML을 이용한다.
* 꼭 XML을 이용할 필요는 없고, 최근에는 **json을 더 많이 이용**한다.
* **비동기식**이란 여러가지 일이 동시적으로 발생한다는 뜻으로, 서버와 통신하는 동안 다른 작업을 할 수 있다는 의미.

ajax가 있기전까지는 web은 문서에 불과했다 -> 등장하면서 서버와 통신할 수 있게 됨
* 선행 지식 : 폼, 서버와 클라이언트의 관계 

* $.ajax(settings) : settings라는 인자(객체)로 전달됨
- jQuery를 이용한 ajax통신의 가장 기본적인 API
- 주요 속성 (settings안에 들어감)
  - data : 서버에 전송할 데이터, key/value 형식의 객체
  - dataType : 서버가 리턴하는 데이터 타입 (xml, json, script, html)
  - type : 서버로 전송하는 데이터의 타입 (POST, GET)
  - url : 데이터를 전송할 URL
  - success : ajax통신에 성공했을 때 호출될 이벤트 핸들러
  
JS에서 중괄호는 객체를 의미 { (이름):(값) } -> 객체의 속성이 만들어짐 

  
  
