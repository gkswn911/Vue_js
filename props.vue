<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Sample</title>
  </head>
  <body>

    <!-- 상위 컴포넌트 -->
    <div id="app">

        <!-- 하위 컴포넌트에 상위 컴포넌트가 갖고 있는 message를 전달함 -->
        <child-component v-bind:propsdata="message"></child-component>
        
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>

    // 하위 컴포넌트 
    // 아래의 컴포넌트 등록 방식은 전역 컴포넌트 등록 방식이다.
    Vue.component("child-component", {
        // 상위 컴포넌트의 data 속성인 message를 propsdata라는 속성으로 넘겨받는다. 
        props: ['propsdata'],
        template: '<p>{{ propsdata }}</p>'
      });

    var app = new Vue({
        el: '#app',
        data: {
            message: "Hello Vue! from parent Component"
        }
    });

    </script>
  </body>
</html>