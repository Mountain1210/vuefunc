<template>
  <div class="hello">
        <ul>
            <li 
            v-for="(item,index) in tabs" 
            :class="{actives:index == num}"
             @click="tab(index)">{{item}}=={{num}}</li>
        </ul>
        <div class="tabCon">
            <div 
            v-for='(itemCon,index) in tabContents' 
            v-show=" index == num">{{itemCon}}</div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'Tabs',
 data() {
 return{
         tabs: ["标题一", "标题二","标题三"],
         tabContents: ["内容一", "内容二","内容三"],
         num: 1}
    },
    methods: {
        tab(index) {
        console.log(index)
            this.num = index;
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
