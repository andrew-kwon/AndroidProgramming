<style> 
div.polaroid {
  	width: 200px;
  	box-shadow: 0 10px 30px 0 rgba(0, 0, 0, 0.2), 0 16px 30px 0 rgba(0, 0, 0, 0.19);
  	text-align: center;
	margin-bottom: 0.5cm;
}
</style>

#Activity-Navigation 실습

##1. 액티비티 라이프사이클 실습
###실습 내용


* FirstActivity에서 버튼 눌러서 SecondActivity를 생성한 후 백(Back) 버튼을 누른다. 이 때 표시된 로그를 Android Monitor에서 확인한다.

	Log.i(“tag string”, “message”);

```java
	protected void onCreate(Bundle savedInstanceState) {
    }
* 로그에 대한 한글 블로그: http://m.blog.naver.com/eominsuk55/220229760263

### 참고 소스:
[https://github.com/kwanulee/Android/tree/master/examples/ActivityIntent](https://github.com/kwanulee/Android/tree/master/examples/ActivityIntent)

## 2. 액티비티간 정보 교환하기 실습
### 실습 내용
* ThirdActivity 를 만든다.
* SecondActivity에 버튼을 하나 만들고 버튼을 누르면 ThirdActivity를 시작한다.
* 이때 SecondActivity는 intent에 putExtra를 이용하여 문자열을 추가
* ThirdActivity는 onCreate에서 getIntent()로 전달 받은 인텐트를 가져온다.
* 받은 인텐트에서 getStringExtra를 이용하여 문자열을 받아 EditText에 표시한다.
* ThirdActivity의 onBackPressed에서 인텐트를 만들어서 setResult 호출
* 이때 인텐트에 putExtra를 이용하여 EditText에 입력된 문자열을 포함시킨다.
* SecondActivity의 onActivityResult에서 전달 받은 인텐트에 포함된 문자열을 Log.i 로 보인다.

### 실습 확인
* Android Monitor에 출력된 로그값을 확인하여 ThirdActivity에서 전달한 문자열을 확인한다. 

### 참고 소스:
[https://github.com/kwanulee/Android/tree/master/examples/ActivityIntent](https://github.com/kwanulee/Android/tree/master/examples/ActivityIntent)

## 3. 액션바 실습
### 실습 내용
* 앞에서 만든 SecondActivity에 위로 가기 버튼과 옵션 메뉴를 정의한다.
* 옵선 메뉴의 아이템에는 ThirdActivity가 있다.

### 실습 확인
* FirstActivity에서 버튼을 눌러 SecondActivity로 전환 -> SecondActivity에서 옵션메뉴인 ThirdActivity를 선택 -> ThridActivity 전환 -> 백버튼을 눌러 다시 SecondActivity로 전환 -> 액션바의 Up 버튼을 눌러 FirstActivity로 전환

### 참고 소스:
[https://github.com/kwanulee/Android/tree/master/examples/NavigationUI](https://github.com/kwanulee/Android/tree/master/examples/NavigationUI)