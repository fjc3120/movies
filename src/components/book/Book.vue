  <template>
    <h1>book</h1>
  </template>


  <script>
    import store from '@/vuex/store'
    export default({
      store,
//      beforeRouteEnter:(to, from, next) => { /*钩子函数不行*/
//
//          $store.commit('routeLinks',{
//              color:"blue",
//              title:"book",
//          });
//          next();
//      }
                                            /*生命周期*/
      created(){                         /*创建成功之后*/
                 this.$store.commit('routerLinks',{
              color:"red",
              title:"book",
          });
      }
    })
  </script>

  <style scoped>


  </style>
