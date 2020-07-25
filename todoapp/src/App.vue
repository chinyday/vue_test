<template>
  <div id="app">
    <TodoHeader></TodoHeader> 
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <Todofooter></Todofooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
import Todofooter from './components/Todofooter.vue'

export default {
  components: {
    // '탬플릿에 연결해 줄 컴포넌트 태그명 ' :  스크립트로 연결한 컴포넌트 내용
    'TodoHeader' : TodoHeader,
    'TodoInput' : TodoInput,
    'TodoList' : TodoList,
    'Todofooter' : Todofooter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 500px;
  margin: 0 auto;
  padding: 10px 0 30px; 
  background-color: #f1f1f1;
}
</style>
