# $.ajax() 기본 구문
 ```
 $.ajax({
    url:'/study/tmp/test.php', //request 보낼 서버의 경로 
    type: 'post', // 메소드
    data: {'id':'admin'}, // 보낼 데이터
    success : function(data){
      // 서버로부터 정상적으로 응답이 왔을 때 실행 
    },
    error : function(err){
        // 서버로부터 응답이 정상적으로 처리되지 못했을 때 실행 
    }
 });
 ```
 # 예제 - 회원목록 추가하기 
 - 페이지 전체 새로 호출
 - Ajax를 통해 호출하는 방식
 
