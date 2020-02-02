# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 4. Web Animation - FE

### Animation
- 반복적인 움직임의 처리
- 간단한 애니메이션은 CSS3의 transition과 transform으로 대부분 구현 가능
- Javascript보다 CSS3가 더 빠름

### FPS(Frame per Second)
- 1초에 화면에 표현할 수 있는 정지화면의 수
- 일반적으로 매끄러운 애니메이션은 60fps

### Javascript으로 Animation 구현
- setInterval
- setTimeout
- [requestAnimationframe](https://developer.mozilla.org/ko/docs/Web/API/Window/requestAnimationFrame)
- Animation API
#### setInterval
   ```javascript
   const interval = window.setInterval(()=> {
     console.log('현재시각은', new Date());
   },1000/60);

   window.clearInterval(interval);
   ```
   + 정해진 시간에 함수가 호출된다고 보장할 수 없음
   + 일반적으로 애니메이션 구현에 잘 이용되지 않음
#### setTimeout
   ```javascript
   let count = 0;

   function animate() {   
     setTimeout(() => {
       if(count >= 20) return;
       console.log('현재시각은', new Date());
       count++;
       animate();
     },500);
   }
   animate();
   ```
   + 지정된 시간 이후에 한 번만 호출
   + 재귀를 통해 애니메이션 구현 가능
   + 제때 콜백함수가 실행되지 않을 수 있음
#### requestAnimationframe
   ```javascript
   var count = 0;
   var el=document.querySelector(".outside");
   el.style.left = "0px";

   function run() {
      if(count > 70) return;
      count = count + 1;
      el.style.left =  parseInt(el.style.left) + count + "px";
      requestAnimationFrame(run);
   }

   requestAnimationFrame(run);
   ```
   + 특정조건을 만족할 때 까지 함수 호출
   + 브라우저가 실행
   + canvas, svg를 사용한 그래픽 작업에서 복잡한 애니메이션을 구현할 때 유용

### CSS3로 Animation구현
- transition
- transform
```javascript
<style>
   .animation {
      position: relative;
      left: 100px;
      transform: scale(1);
      transition: all 1s ease-in-out;
   }
</style>

<script>
   var target = document.querySelector(".animation");
   var btn = document.querySelector("button");

   btn.addEventListener("click", function() {
      target.style.transform = "scale(4)";

      var pre = parseInt(target.style.left);    // inline으로 속성을 줘야 적용
      target.style.left = pre + 100 + "px";
   });
</script>
```
#### [GPU가속을 이용하는 CSS 애니메이션 속성](https://d2.naver.com/helloworld/2061385)
애니메이션 처리 속도가 빠름
- transform : translateXX();
- transform : scale();
- trnasform : rotate();
- opacity

### (참고) [Javascript Arrow Function](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions/%EC%95%A0%EB%A1%9C%EC%9A%B0_%ED%8E%91%EC%85%98)
- 자신의 this, arguments, super, new.target을 바인딩하지 않음
- 항상 익명
- 메소드 함수가 아닌 곳에 적합
- 생성자로 사용 불가

### (참고) vendor prefix
```javascript
<style>
    .button {
        background: red;          <!-- gradient 속성을 지원하지 않는 모든 브라우저를 위한 코드 -->
        background: -webkit-linear-gradient(red, yellow); <!-- 크롬과 사파리 4.0 이상을 위한 코드 -->
        background: -moz-linear-gradient(red, yellow);    <!-- 파이어폭스 3.6 이상을 위한 코드 -->
        background: -ms-linear-gradient(red, yellow);     <!-- 익스플로러 10.0 이상을 위한 코드 -->
        background: -o-linear-gradient(red, yellow);      <!-- 오페라 10.0 이상을 위한 코드 -->
        background: linear-gradient(red, yellow);         <!-- CSS 표준 문법 코드 -->
    }
</style>
```
- 주요 웹 브라우저 공급자가 새로운 실험적인 기능을 제공할 깨 이전 버전의 웹 브라우저에 그 사실을 알리기 위해 사용하는 접두사
- 해당 기능이 포함되지 않은 이전 버전의 웹 브라우저에서 그 기능을 사용할 수 있게 함
- CSS 표준 문법 코드는 벤더 프리픽스로 작성된 코드가 모두 나오고 난 후에 나와야함



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
