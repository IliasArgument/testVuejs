<template>
  <div class="hello">
 
     <div class="icon">
    <img src='../assets/ico.png' alt="icon" class="icons" v-on:click="$emit('on-update')">
       </div>
     <div class="msg">
       <p>Повiдомлень - {{lists.length}}</p>
      </div> 
      <div class="not">
        <p>Непрочитаних - {{lists.filter(t => t.unread).length}}</p>
      </div>

  </div>
</template>

<script>
export default {
  name: 'Home',
   props: ['lists'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.hello {
  display: flex;
  justify-content: left;
  align-items: left;
padding-top: 15px;
padding-left: 10px;
}
.icon {
  margin-left: 15px;
  color: darkblue;
  margin-bottom: 10px;
}
.icons {
  cursor: pointer;
}
.msg {
  margin-left: 20px;
  margin-right: 20px;
}

</style>
