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
   ```
   const interval = window.setInterval(()=> {
     console.log('현재시각은', new Date());
   },1000/60);

   window.clearInterval(interval);
   ```
   + 정해진 시간에 함수가 호출된다고 보장할 수 없음
   + 일반적으로 애니메이션 구현에 잘 이용되지 않음
#### setTimeout
   ```
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
   ```
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
```
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

<br>

---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
