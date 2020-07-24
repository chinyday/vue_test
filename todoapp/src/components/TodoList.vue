<template>
    <div class="listWrap">
        <ul>
            <li v-for="i in dataList" v-bind:key="i">{{ i }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    data : function(){
        return{
            dataList : []
        }
    },
    created : function() {  
        if(localStorage.length > 0 ){
            for (let i = 0; i < localStorage.length; i++) {
                if( localStorage.key(i) !== "loglevel:webpack-dev-server")
                this.dataList.push(localStorage.key(i));
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.listWrap li{
    list-style: none;
    background-color: #fff;
    margin-bottom: 10px;
    width: 90%;
    height: 30px;
    font-size: 16px;
    line-height: 30px;
}
</style>
