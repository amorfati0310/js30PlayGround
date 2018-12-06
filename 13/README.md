- [그리는\_방식](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors)

* fillStyle
* strokeStyle

- [선결합방식](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin)

- 1번 round 부드럽게 연결
- 2번 bevel 짤리는 느낌
- 3번 edge있게 연결

```js

Up until now we have only seen methods of the drawing context. If we want to apply colors to a shape, there are two important properties we can use: fillStyle and strokeStyle.

ctx.fillStyle = 'orange';
ctx.fillStyle = '#FFA500';
ctx.fillStyle = 'rgb(255, 165, 0)';
ctx.fillStyle = 'rgba(255, 165, 0, 1)';


function draw() {
  var ctx = document.getElementById('canvas').getContext('2d');
  for (var i = 0; i < 6; i++) {
    for (var j = 0; j < 6; j++) {
      ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                       Math.floor(255 - 42.5 * j) + ', 0)';
      ctx.fillRect(j * 25, i * 25, 25, 25);
    }
  }
}


function draw() {
    var ctx = document.getElementById('canvas').getContext('2d');
    for (var i = 0; i < 6; i++) {
      for (var j = 0; j < 6; j++) {
        ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                         Math.floor(255 - 42.5 * j) + ')';
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }
  }

const draw = (selector, drawfn)=>{
   const ctx = document.getElementById('selector').getContext('2d')
    drawfn(ctx)
}


```

이거 mouseDown일 떄 true하고 up일때 false? 왜 이렇게 한 걸까?

```js
canvas.addEventListener("mousemove", draw);
canvas.addEventListener("mousedown", () => (isDrawing = true));
canvas.addEventListener("mouseup", () => (isDrawing = false));
canvas.addEventListener("mouseout", () => (isDrawing = false));
```

mouseover 위에 있을 떄
mouseout 밖으로 나갈 떄
즉 평사시에는 false
mousedown 누를 때만 true

canvas에 id가 draw인 요소들을 담고, ctx에 canvas의 그리기 대상이 되는 context를 얻음
width와 height를 브라우저에 표현되도록 뷰포트 폭을 받고서
strokeStyle - 윤곽선의 색깔, lineJoin - 두 선이 만나는 지점의 모양,
lineCap - 선의 끝 모양, lineWidth - 선의 두께 설정
