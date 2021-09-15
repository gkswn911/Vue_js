<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Sample</title>
  </head>
  <body>
    <div id="app">
        
        <button v-bind:disabled="one" v-on:click="oneClick">One</button>
        <button v-bind:disabled="two" v-on:click="twoClick">Two</button>
        <button v-bind:disabled="three" v-on:click="threeClick">Three</button>

        <!-- True값을 가지며 활성화 되어있는 값 출력 -->
        <p v-if="one">One Click</p>
        <p v-if="two">Two Click</p>
        <p v-if="three">Three Click</p>

    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>

        new Vue({
            el: '#app',
            data: {
                one : true,
                two : false,
                three : false
            },
            methods: {
                oneClick() {
                    this.one = true
                    this.two = false
                    this.three = false
                },
                twoClick() {
                    this.one = false
                    this.two = true
                    this.three = false
                },
                threeClick() {
                    this.one = false
                    this.two = false
                    this.three = true
                }
            }
        })
      

    </script>
  </body>
</html>