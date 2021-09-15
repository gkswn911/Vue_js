<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Sample</title>
  </head>
  <body>

    <div id="app">

        <!-- 각기 다른 컴포넌트 -->
        <my-component></my-component>
        <my-component></my-component>
        <my-component></my-component>
        
    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>

        // Global로 컴포넌트를 처리
        // Vue.component('컴포넌트 태그', {template: "HTML 코드"});

        // Local로 컴포넌트를 처리
        var MyComponent = {
            template: `<p class="my-comp">카운터
                        <button v-on:click="addOne">버튼</button> {{count}}
                        </p>`,
            data: function(){
                return { count: 0 }
            },
            methods: {
                addOne(){
                    this.count++
                }
            }
        }

        new Vue({           
            el :'#app',
            components: {
                'my-component': MyComponent
            }
        })
      

    </script>
    <style>
        .my-comp {
          width: 300px;
          background-color: #f123;
          border: solid;
          border-color: darkorange;
          border-radius: 8px;
          padding: 8px;
        }
      </style>
  </body>
</html>