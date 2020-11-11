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
 

