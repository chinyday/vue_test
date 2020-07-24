<template>
    <div class="inputWrap">
        <!-- v - model : input에서 입력된 것이 뷰단(스크립트)에서 인식이 되게 하려면 시용  -->
        <!-- 입력된 값이 동적으로 뷰 이스턴스 값에 바로바로 맵핑되게 하기 위해서 사용 -->
        <input class="inputText" type="text" v-model="inputItemes" v-on:keyup.enter="addTodoText">
        <button class="addBtn" v-on:click="addTodoText">+</button>
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
.inputWrap .inputText{
    width: 200px;
    height: 35px;
    line-height: 30px;
    font-size: 16px;
    padding-left: 10px;
    box-sizing: border-box;
    border: 0;
    border-radius: 5px;
    border-top-right-radius: 0;
    border-bottom-right-radius: 0;
}
.inputWrap .inputText:focus{
    outline-offset: 0px;   
    outline: -webkit-focus-ring-color auto 0px;
}
.inputWrap .addBtn{
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
</style>
