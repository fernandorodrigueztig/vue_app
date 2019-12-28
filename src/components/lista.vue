<template>
 <div>
    
     
     <div class="content">
         <div class="content__chanels">
             <div :key="index" v-for="(item,index) in lista" @click="loadMultimediaContent(item.url)">
                 <img :src="item.imgurl" :alt="item.channelname" >
             </div>
         </div>
     </div>
 </div>
</template>

<script>

export default {
  name: 'listaComponent',
  components: { 
  },
  props: {
   
  },
   data:  function() {
    return { 
      url: 'https://yowi.tv/apiv2/getMediaFront',
      dataform: {
        "data":{"name":["Last Added"],"category":"live","country":"ES"},"channelid":-1,"userLang":"en-US"
      },
      lista:[],
    }
  },
  computed:{
    player () {
      return this.$refs.videoPlayer.player
    }
  },
  mounted: function() {
      this.loadData();
  },
  methods:{
    loadData(){
      this.$http.post(this.url,this.dataform,{headers:{'Content-Type': 'application/json'}}).then(result => {
       this.lista = [...result.data.data.media]
        
      });
    },
    loadMultimediaContent(url) {
        
        this.videoUrl = url;
    }
  }
}
</script>


<style lang="scss" scoped>
.content{
    display: block;
    width: 100%;
    padding: 20px;
    .content__chanels{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
        flex-wrap: wrap;
        div {
            width: 198px;
            height: 119px;
            padding: 10px;
            cursor: pointer;
            :hover{
                opacity: 0.5;
            }
            img {
                width: 100%;
                display: block;
                position: relative;
            }
        }
    }
}

</style> 
