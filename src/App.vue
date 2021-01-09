<template>
  <div id="app">
    <Item
     v-bind:lists="lists"
    @like-list="likeList"
    @unread-on="unreadOn"
    @on-update="onUpdate"
    />
  </div>
</template>

<script>
import Item from './components/Item';

export default {
  name: 'App', 
    data() {
      return {
   lists: [
      {id: 1, name: 'Anastasia Petrushko',unread: false, card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони', soc: '../assets/telega.png',time: '20:20', year: '2018-04-13', tel: '+38093 666 22 22'},
      {id: 2, name: 'Anastasia Petrushko', card:'../assets/woman.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони',unread: false, soc: '../assets/viber.png',time: '20:20', year: '2018-04-19', tel: '+38093 666 22 22'},
      {id: 3, name: 'Anastasia Petrushko',  card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мне позво',unread: false, soc: '../assets/telega.png',time: '20:20', year: '2018-04-08', tel: '+38093 666 22 22'},
      {id: 4, name: 'Anastasia Petrushko', card:'../assets/woman.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони',unread: true, soc: '../assets/viber.png',time: '20:20', year: '2018-04-16', tel: '+38093 666 22 22'},
      {id: 5, name: 'Anastasia Petrushko', card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мнеБ gggg', soc: '../assets/telega.png',time: '20:20',unread: false, year: '2018-04-10', tel: '+38093 666 22 22'},
      {id: 6, name: 'Anastasia Petrushko', card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони',unread: true, soc: '../assets/telega.png',time: '20:20', year: '2018-04-13', tel: '+38093 666 22 22'},
       {id: 7, name: 'Anastasia Petrushko', card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони',unread: true, soc: '../assets/telega.png',time: '20:20', year: '2018-04-11', tel: '+38093 666 22 22'},
        {id: 8, name: 'Anastasia Petrushko', card:'../assets/man.png',message: 'Позвони мне позвони, если только позвони мнеБ позвони мне позвони',unread: true, soc: '../assets/telega.png',time: '20:20', year: '2018-04-10', tel: '+38093 666 22 22'}
    ]
      }
 
  },
  methods: {
   likeList(id) {

    setTimeout( () => this.lists = this.lists.filter(t => t.id !== id), 3000)

   },
   
   onUpdate() {
  
   return window.location.reload();
   }
  },
  mounted() {
    
    this.lists = this.lists.sort((a, b) => Date.parse(b.year) - Date.parse(a.year)) 
   &&
    this.lists.sort((a, b) => b.unread - a.unread);

const data = localStorage.getItem('unread');
      data ? this.lists = JSON.parse(data) : null
  },
  updated () {
    
    
        localStorage.setItem('unread',JSON.stringify(this.lists));

  }, 
  components: {
   Item
  }
  }
</script>

<style>
* {
    margin: 0;
    padding: 0;
    /* box-sizing: border-box; */
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #15191d;
  width: 100%;
  height: 100%;
  background: rgb(255, 255, 255);
  
}
.done {
  background: rgb(230, 222, 222);
 }
</style>
