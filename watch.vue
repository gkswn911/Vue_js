<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Sample</title>
  </head>
  <body>


    <div id="app">

        <!-- input 값 주면은 forbidTextARr에 금지 단어 입력 가능하게 -->
        <input v-model="newForbidText">
        <button v-on:click="add(newForbidText)">Add</button>
       <p> 금지문자 List </p>
       <ol>
           <li v-for="item in forbidTextArr">
               {{item}}
            </li>
       </ol>
       <textarea v-model="inputText"></textarea>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    
    <script>

        var vm = new Vue({
            el: '#app',
            data: {
                forbidTextArr: [],
                inputText: "",
                newForbidText: ""
            },
            methods: {
                add(newForbidText) {
                    this.forbidTextArr.push(newForbidText)
                }
            },
            watch: {
                // 입력한 문자열을 감시한다.
                inputText: function(){
                    
                    var pos = this.inputText.indexOf(this.forbidTextArr)
                    if (pos >= 0)
                    {
                        alert(this.forbidTextArr + "는 입력할 수 없습니다.")
                        this.inputText = this.inputText.substr(0, pos-this.forbidTextArr.length)
                    }
                }
            }
        })
    </script>
  </body>
</html>