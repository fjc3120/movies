  <template>
    <div>
      <ul>
        <li v-for="val in datas" :key="val.id"></li>
        {{val.nm}}
      </ul>
    </div>
  </template>


  <script>
    import store from '@/vuex/store'
    import axios from 'axios'
    export default({
      data(){
        return{
          datas:[],
        }
      },
      store,
      methods:{
          getData(){//远程代理+接口    接口地址 ?  参数 & 连接
            axios.get(API_PROXY+'http://m.maoyan.com/movie/list.json?type=hot&offset=0&limit=10')  //接口，访问的地址
              .then((response)=>  {
//                  console.log(this);//匿名函数的this是windows，所以变成箭头函数
                this.datas =response.data.data.movies;
              })
              .catch((error) => {
                console.log(error);
              });
          }
      },
      created(){
        this.$store.commit('routeLinks',{
          color:"rgb(33,150,243)",
          title:"电影",
        });

        //-------ajax获取数据尽量卸载created里
        this.getData();
      }
    })
  </script>

  <style scoped>


  </style>
