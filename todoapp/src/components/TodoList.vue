<template>
    <div class="listWrap">
        <ul>
            <li class="shadow" v-for="(text, index) in dataList" v-bind:key="text.text" v-bind:class="{done : text.complete}">
                <i class="fa fa-check check" aria-hidden="true" v-on:click="completeTodoText(text, index)"></i>
                <span>{{ text.text }}</span>
                <i class="fa fa-trash trash" aria-hidden="true" v-on:click="removeTodoText(text, index)"></i>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data : function(){
        return {
            dataList : []
        }
    },
    methods : {
        completeTodoText : function(text, index){
            text.complete = !text.complete; 
        },
        removeTodoText : function(text, index){
            if (index > -1) this.dataList.splice(index,1); 
            localStorage.removeItem(text.text); 
        }
    },
    created : function() {  
        if(localStorage.length > 0){
            for (let i = 0; i < localStorage.length; i++) {
                if( localStorage.key(i) != "loglevel:webpack-dev-server" && localStorage.key(i) != ""){
                    this.dataList.push(JSON.parse(localStorage.getItem(localStorage.key(i))));
                }
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{margin: 0; padding: 0;}
.listWrap ul{
    width: 90%;
    margin: 0 auto;
}
.listWrap li{
    list-style: none;
    background-color: #fff;
    margin-bottom: 10px;
    height: 35px;
    font-size: 16px;
    line-height: 35px;
    text-align: left;
    border-radius: 5px;
}
.check{
    width: 30px;
    text-align: center;
    line-height: 35px;
    padding: 0 5px;
    color: #72a4f1;
}
.trash{
    float: right;
    color: #ce6363;
    font-size: 18px;
    line-height: 35px;
    padding-right: 10px;
    width: 30px;
    text-align: center;
}
.shadow{
    -webkit-box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
    -moz-box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
    box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
}

.done{
    color: #ddd;
    text-decoration: line-through;
}
.done .trash,
.done .check{
    color: #ddd;
}
</style>