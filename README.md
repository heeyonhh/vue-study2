## v-model / v-if / v-show

- v-model : 단방향 데이터 바인딩
  
- v-if visible: true/false 값으로 처리하여 true일 때 보여주는 디렉티브
  
- v-show false일때 Display none으로 처리
  
    <div id="app">
        <!-- v-if true 일때만 보여주는 디렉티브 -->
        <h1 v-if="visible">나는 보입니다.</h1>
        <h1 v-show="visible">나는 보입니다.</h1>
        <!-- v-if 사용 권장 : 오래걸리는 처리 내용이 되면 v-if는 false일때 처리를 안하고 show는 false일때 Display none으로 처리함 -->
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
        var app = new Vue({
            el: '#app',
            data: {
                visible: false
            }
        })
    </script>

## 
