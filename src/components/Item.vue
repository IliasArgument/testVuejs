<template>
  <div class="hello">
     <Home  
      v-bind:lists="lists"
      v-on:on-update="onUpdate"
    />
    <div class="block">
     <ItemList
     v-for="list of lists"
     v-bind:key="list.id"
     v-bind:list="list"
     v-on:list-like="listLike"
     v-on:unread-on="unreadOn"
    />
  
    </div>
  
  </div>
</template>

<script>
import ItemList from './ItemList';
import Home from './HelloWorld';

export default {
  name: 'Item',
  props: ['lists'],
  methods: {
listLike(id) {
this.$emit('like-list', id)
  },
  unreadOn() {
this.$emit('unread-on')
  },
  onUpdate(){
    this.$emit('on-update')
  }
  }, 
  components: {
     ItemList,Home
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.block {
display: flex;
justify-content: space-between;
flex-direction: column;
align-items: center;   
max-width: 98%;
height: 100%;
background: rgb(232, 231, 247);
padding-top: 2px;
margin-bottom: 5px;
position: relative;
left: 14px;
bottom: 5px;
}
.done {
  background: rgb(230, 222, 222);
  }


@media screen and (max-width: 750px) {
.block {
  position: relative;
left: 73px;
bottom: 5px;
}

}

@media screen and (max-width: 450px) {
.block {
position: relative;
left: 120px;
bottom: 5px;}

}

</style>