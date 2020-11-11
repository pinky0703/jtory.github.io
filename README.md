# jQuery 생활 코딩 동영상 학습 

> 인용
* 리스트 

1. 번호리스트


``` 코딩 표시 ```

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
* jQuery(엘리먼트 오브젝트 | 'CSS스타일 선택자') : js 에서 jQuery라는 함수를 호출한다는 의미 
# 선택자

# chain 

# event 


# 엘리먼트 제어 


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

  
  
