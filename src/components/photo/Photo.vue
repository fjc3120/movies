  <template>
    <h1>photo</h1>
  </template>


  <script>
    import store from '@/vuex/store'
    export default({
      store,
      created(){
        this.$store.commit('routeLinks',{
          color:"black",
          title:"photo",
        });
      }
    })
  </script>

  <style scoped>


  </style>
