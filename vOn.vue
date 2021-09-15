<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Sample</title>
  </head>
  <body>

      <h2> 입력받은 문자열을 표시하는 예제</h2>

    <div id="app">
        <!-- v-on:click으로 클릭이벤트 설정 가능 -->
        <button v-on:click = "countUp"> ++ Button</button>
        <p>{{count}}</p> 
        
        <!-- v-bind는 생략가능. => button disabled = false , click = " " 와 같이 구성된다고 본다. -->
        <button v-bind:disabled="click" v-on:click="oneClick">한 번만 클릭 가능</button>
        <p>{{text}}</p>

        <!-- 함수 Param 전달 -->
        <button v-on:click= "paramClick(10)">10씩 증가</button>
        <p>{{tenCount}}</p>

        <!-- 특정 키를 누를 때 함수 실행(포커스 상태에서) -->
        <input v-on:keyup.enter="alertClick">
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>

        var vm = new Vue({
            el: '#app',
            data: {
                count: 0,
                click: false,
                text: "",
                tenCount: 0
            },
            methods: {
                countUp() {
                    this.count++                  
                },
                oneClick() {
                    this.click = true;
                    this.text = "Click!";
                },
                paramClick(num) {
                    this.tenCount += num;                         
                },
                alertClick() {
                    alert("Enter!");
                }
            }
        })

    </script>
  </body>
</html>