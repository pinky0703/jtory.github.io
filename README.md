# jQuery 생활 코딩 동영상 학습 

> 인용
* 리스트 

1. 번호리스트


``` 코딩 표시 ```
# jQuery란? 
# javascript vs jQuery
# wrapper 
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
        </script> ``` 
