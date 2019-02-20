
<template>
  <f7-list>
    <f7-list-item title="Fruit" smart-select :smart-select-params="{openIn: 'sheet'}">
      <select name="fruits" v-model="chooseFruit">
        <option
          v-for="(fruit,index) in fruitList"
          :value="fruit"
          :key="index"
        >{{fruit.toUpperCase()[0]+fruit.slice(1)}}</option>
      </select>
    </f7-list-item>
  </f7-list>
</template>
    
<script>
export default {
    props:['fruitList'],
    data(){
        return{
            chooseFruit:''
        }
    }
}
</script>
