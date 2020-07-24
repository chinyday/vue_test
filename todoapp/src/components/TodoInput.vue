<template>
    <div class="inputWrap">
        <!-- v - model : input에서 입력된 것이 뷰단(스크립트)에서 인식이 되게 하려면 시용  -->
        <!-- 입력된 값이 동적으로 뷰 이스턴스 값에 바로바로 맵핑되게 하기 위해서 사용 -->
        <input class="inputText shadow" type="text" v-model="inputItemes" v-on:keyup.enter="addTodoText" placeholder="Type what you have to do">
        <button class="addBtn shadow" v-on:click="addTodoText">+</button> 
    </div>
</template>

<script>
export default {
    data : function() {
        return {
            inputItemes : ""
        }
    },
    methods : {
        addTodoText:function(){
            localStorage.setItem(this.inputItemes,this.inputItemes);
            this.inputItemes = '';
            
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{margin: 0; padding: 0;}
.inputWrap{
    position: relative;
    margin: 20px auto;
    width: 90%;
}
.inputWrap .inputText{
    width: 100%;    
    height: 35px;
    line-height: 30px;
    font-size: 16px;
    padding-left: 10px;
    box-sizing: border-box;
    border: 0;
    border-radius: 5px;
}
.inputWrap .inputText:focus{
    outline-offset: 0px;   
    outline: -webkit-focus-ring-color auto 0px;
}
.inputWrap .addBtn{
    position: absolute;
    right: 0;
    width: 35px;
    height: 35px;
    font-size: 18px;
    color: #fff;
    font-weight: bold;
    background: rgb(120,11,60);
    background: linear-gradient(180deg, rgba(120,11,60,1) 0%, rgba(210,78,138,1) 51%, rgba(222,125,168,1) 100%);
    border: 0;
    border-radius: 5px;
    border-top-left-radius: 0;
    border-bottom-left-radius: 0;
    box-sizing: border-box;

}
.shadow{
    -webkit-box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
    -moz-box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
    box-shadow: 1px 1px 4px -1px rgba(0,0,0,0.3);
}
</style>
