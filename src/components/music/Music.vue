  <template>
    <ul>
      <li class="music" v-for="item in musicList" :key="item.id">
        <router-link :to="'musicAlbums/' + item.id">
          <img :src="item.bg" alt="">
        </router-link>
      </li>
    </ul>
  </template>


  <script>
    import store from '@/vuex/store'
    import Aplayer from 'vue-aplayer'
    import axios from 'axios'
    export default({
      store,
      data(){
          return {
              musicList:[],
          }
      },
      created(){
        this.$store.commit('routerLinks',{
          color:"green",
          title:"music",
        });
        this.getData();
      },

      methods:{
          getData(){
            axios.get('/static/data/musiclist.json')
              .then((res) =>{
              console.log(res);
              this.musicList = res.data.albums;
            }).catch((res)=>{
              console.log("erroor!");
            })
          }
      },
    })
  </script>

  <style scoped>
    .music{
      width: 50%;
      float: left;
    }
    .music img{
      width: 100%;
    }
  </style>
