<template>
    <div class = "hello">
     <button @click = "loadData()">data</button>
    <div>
        <ul>
            <li :key="index" v-for="(ele, index) in lista">{{ele.url}}
        </ul>
    </div>
</div>
</template>

<script>
export default {
    name: "HelloWorld",
    data: function() {

        return {
            url: "https://yowi.tv/apiv2/getMediaFront",
            
            dataform: {

                "data":{"name":["Last Added"],"category":"live","country":"ES"},"channelid":-1,"userLang":"en-US"
            },

            lista: []
    }
},

mounted: function ()  {

//this.loadData();

},
    
props: {

    msg: String
},

methods:{

    loadData(){

        this.$http.post(this.url, this.dataform, {headers: {'Content-Type': 'application/json'}}).then(result =>{
            this.lista = result.data.data.media
        });
    }
 }
}


</script>