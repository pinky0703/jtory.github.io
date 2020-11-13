# jQuery 선택자 
  - $('#email') : 아이디 선택자
  - $('.class') : 클래스 선택자
  - $('h1') : 엘리먼트 선택자
  - $('*') : 전체 선택
  - $('h1,p') : 다중 선택자 

# jQuery 함수 

# jQuery Bootstrap
* bootstrap button 
  - 'btn-primary'
  - 'btn-default'
  - 'btn-success'
  - 'btn-info'
  - 'btn-danger'
  - 'btn-warning'
  - 'btn-link'
  
* bootstrap grid 시스템
  - 기본적으로 12컬럼으로 구성.
  

# jQuery 클래스? 


# jQuery Serialize() 

# 예제 실습 
* resource에다가 jquery.min.js 추가하기
* 링크 추가 : 부트스트랩? 
``` // html 코드
<html>
<head>
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
</head>
<body>
  <div class="col-md-6">
    <div class="heading">
      <h2 class="title">Login</h2>
      <p>If you have an account with us, please log in.</p>
    </div><!— End .heading —>

    <form action="#">
      <input type="text" name="email" class="form-control" id="email" placeholder="Email Address">
      <input type="text" name="password" class="form-control" id="pwd" placeholder="Password">

      <div class="form-footer">
      <span id="errMsg"></span>
        <button type="button" class="btn btn-primary">LOGIN</button>
        <p><input type="checkbox" /> remember</p>
        <a href="#" class="forget-pass"> Forgot your password?</a>
      </div><!— End .form-footer —>
    </form>
  </div><!— End .col-md-6 —>
</body>
</html>

// jQuery Code
 
/* $('.btn-primary').click(function(e){
  alert('ok');
}); */

 /*  if(email=='' || pwd==''){
    
    alert('fail');
  } else{
    alert('ok');
  } */
  
// 1. email 값을 입력하지 않았을 경우 email input box에 $('…').focus(); 
  // 2. email 은 @ 문자가 있어야 하고, 길이가 4~20 이어야 한다.
  // 3. password는 email과 같으면 안되고, 길이가 4~20 이어야 한다.
  // 3-1.	password와 email이 같으면 password 값을 지운다.
	// 4. 모두 만족할 경우 alert('ok')
function commonClick(e){
	let email = $('#email').val();
	let pwd = $('#pwd').val();
  
  if(email==''){
		  $('#email').focus(); 
  		
  }
  if(email.indexOf('@')== -1){
  	$('#errMsg').text('@를 입력하쇼').addClass('text-warning'); //. 붙이는건 셀렉터고 이런건 안붙여두돼
  	return;
  }
  if( 4 < pwd.length || pwd.length < 20){
  	
  	$('#errMsg').text('비밀번호는 4~20사이여야함').removeClass('text-danger').addClass('text-warning');
    return;
  }
  if(email==pwd){
  	$('pwd').val('');
    return;
  }
  alert('ok');

  
  // 1. email 값을 입력하지 않았을 경우 email input box에 $('…').focus(); 
  // 2. email 은 @ 문자가 있어야 하고, 길이가 4~20 이어야 한다.
  // 3. password는 email과 같으면 안되고, 길이가 4~20 이어야 한다.
  // 3-1.	password와 email이 같으면 password 값을 지운다.
	// 4. 모두 만족할 경우 alert('ok')
  JSON.stringfy($('form').serialize());
 
} // 함수는 세미콜론 안찍어도돼 
 
var commonClick2 = e => {
	alert('ok');
}; // 안찍어도 되는데 변수니까 찍어주자 

$('.btn-primary').click(commonClick); // 공통함수 
$('#email').keyup(function(e)){
	$('#errMsg').text($(this).val());
});

/* $('.btn-primary').click()(e) => {
  alert('ok');
}); // 파라미터가 하나면 생략가능? 한줄이면 괄호 안써도 되고.

$('.btn-primary').click(e => alert('ok')); // 요즘 방식  */


```
