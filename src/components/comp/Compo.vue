  <template>
    <div>
      <div class="header" :style="'background-color: '+$store.state.color">
        <span class="header-btn" @click="toMovie" >首页</span>
        <span class="header-title">{{$store.state.title}}</span>
      </div>
      <div class="footer" :style="'background-color: '+$store.state.color">
        <ul>
          <!--<li><router-link to="/">电影</router-link></li>-->
          <!--<li><router-link to="/music">音乐</router-link></li>-->
          <!--<li><router-link to="/book">书籍</router-link></li>-->
          <!--<li><router-link to="/photo">图片</router-link></li>-->
          <li @click='routerLink("/")'>电影</li>
          <li @click='routerLink("music")'>音乐</li>
          <li @click='routerLink("book")'>书籍</li>
          <li @click='routerLink("photo")'>图片</li>
        </ul>
      </div>
    </div>
  </template>


  <script>

    import store from '@/vuex/store'
  export default({
    store,
    data(){
        return {
            bgcolor:'red'
        }
    },
      methods:{
        routerLink(path){
              this.$router.push(path);
          },
        toMovie(){
          this.$router.push('/');
        }
      }
  })
  </script>

  <style scoped>
    .header{
      height: 1rem;
      background: rgb(33,150,243);
      position: fixed;
      top:0;
      left: 0;
      width:100%;
      color: #fff;
    }

    .header .header-btn{
      height: 1rem;
      line-height:1rem;
      padding-left: 0.1rem;
    }
    .header .header-title{
      font-size: 0.5rem;
      display: block;
      text-align: center;
      position: absolute;
      top:50%;
      left:50%;
      transform: translate(-50%,-50%);
    }
    .footer{
      height: 1rem;
      background: rgb(33,150,243);
      position: fixed;
      bottom: 0;
      left:0;
      width:100%;
    }
    .footer ul{
      width: 100%;
      display: flex;/*--弹性盒模型 放父级*/
      flex-direction: row;/*方向*/
    }
    .footer ul li{
      flex-grow:1 ;/*一等分*/
      width:0; /*尽量写上*/
      color: #fff;
      /*float: left; 不使用弹性盒模型的方法
      width: 25%;
      height: 1rem;
      text-align: center;*/
      line-height: 1rem;

    }
  </style>
