## v-model / v-if / v-show

- v-model : 단방향 데이터 바인딩
  
- v-if : visible: true/false 값으로 처리하여 true일 때 보여주는 디렉티브
  
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

- v-for : 배열이나 데이터 반복 출력 디렉티브

      <div id="app">
          <ul>
              <li v-for="n in numbers">{{ n }}</li>
          </ul>
          <table>
              <tr>
                  <th>이름</th>
                  <th>나이</th>
              </tr>
              <tbody>
                  <tr v-for="p in people" v-if="p.age >= 30">
                      <td>{{ p.name }}</td>
                      <td>{{ p.age }}</td>
                  </tr>
              </tbody>
          </table>
      </div>
  
          var app = new Vue({
              el: '#app',
              data: {
                  numbers: [1,2,3,4,5,6,7],
                  people: [
                      {
                          name: '이순신',
                          age: 30
                      },
                      {
                          name: '신사임당',
                          age: 40
                      },
                      {
                          name: '이율곡',
                          age: 20
                      },
                  ]
              }})

- v-on : 클릭이벤트 @

- v-bind : 동적 엘리먼트 값을 변경해주어야 할때 활용

    <style>
      button{
          background: white;
          border: 1px solid;
          margin:  0 5px;
          cursor: pointer;
      }
      
      button.active{
          background: blue;
          color: white;
          border: blue;
      }
      
      img{
          width: 100px;
      }
    </style>

    <div id="app">
        <button v-for="p in pages" :class="{'active' : page === p }" @click="page = p">{{p}}</button>
        <hr/>
        <div v-for="p in pages" v-if="page === p">
            <p>{{p}} contents</p>
            <img :src=" 'img/' + p + '.png' " />
        </div>
    </div>

    <script>
        var app = new Vue({
            el: '#app',
            data: {
                page: 'page1',
                pages: ['page1', 'page2', 'page3', 'page4']
            }
        });
    </script>


v-bind : 로 치환 / v-on @ 로 치환
