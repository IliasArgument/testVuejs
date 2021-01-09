<template>

  <div>
      <ul class="block">
          <li v-bind:class="{ done: list.unread }"
              v-on:click="list.unread = !list.unread"               
          >
       
        <div class="block1">
                   <div>
         <img class="car" src="../assets/man.png">
         <span class="spn1"><img class="snp" src="../assets/telega.png"></span>

                   </div>
         <div class="block2">
              <span class="name">{{list.name}}</span>
              <span>{{list.tel}}</span>
          </div>
        </div>
          
     <div class="block3"><p>{{list.message}}</p></div> 
          <div class="block4">
              <div class="time"><span>{{list.time}}</span></div>
              <div><span>{{list.year}}</span></div>
              </div> 
          </li>
      </ul>
  </div>
  
</template>

<script>
export default {
  name: 'ItemList',
  props: {
      list: {
          type: Object,
          required:true
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.block1,.block2,.block3 {
    margin-right: 5px;
    }

  .block1 {
            display: flex;
            padding-left: 20px;
            margin-right: 20px;
            padding-bottom: 15px;
            justify-content: space-between;
            align-items: left;
                width: 500px;
        }

        .block2 {
            padding-left: 10px;
            margin-right: 100px;
            position: relative;
            right: 20px;
            margin-top: 30px;
            font-size: 0.8rem;
            display: flex;
            flex-direction: column;
            text-align: left;
            color: black;
            width: 200px;
            cursor: pointer;
            }

    
    .block3 {
    color: rgb(163, 170, 235);
    margin-top: 10px;
    font-size: 1rem;
    margin-right: 90px;
    margin-left: 50px;
    width: 450px;
    cursor: pointer;

    }


    .block2:hover,.block3:hover {
       opacity: 0.5;
        }

    .car {
        margin-top: 10px;
        width: 100px;
        border-radius: 80%;
        background: lightskyblue;
        }

    
     .snp {
        width: 35px;
        position: relative;
        right:22px;
        background: rgb(250, 248, 248);
        border: 2px solid white;
        border-radius: 50%;
        box-shadow: 0 0 5px rgba(0,0,0,0.5);
        }
        
      
.name {
    margin-bottom: 20px;
}
           
.block4 {
    display:flex;
    color: rgb(199, 184, 184);
    margin-right: 30px;
    font-size: 0.9rem;

    }
    .time {
        margin-left: 7px;
        margin-right: 10px;

    }
            li {
                padding: 0,0, 0,0;
                display: flex;
                justify-content: space-between;
                align-items: center;
                border-bottom:1px solid silver;
                width: 97%;  
                background: rgb(255, 255, 255);
                height: 120px;  
                margin: 0 auto;        
            }
            
          .done {
              background: rgb(230, 222, 222);
          }

          @media screen and (max-width: 1300px) {
               .block1 {
            display: flex;
            padding-left: 30px;
            margin-right: 20px;
            padding-bottom: 10px;
            justify-content: space-between;
            align-items: left;
                max-width: 700px;
        }

        .block2 {
            padding-left: 20px;
            margin-right: 20px;
            position: relative;
            right: 20px;
            margin-top: 10px;
            font-size: 0.8rem;
            display: flex;
            flex-direction: column;
            text-align: left;
            color: black;
            max-width: 400px;
            cursor: pointer;
            }

    
    .block3 {
    color: rgb(163, 170, 235);
    margin-top: 10px;
    font-size: 1rem;
    margin-right: 30px;
    margin-left: 20px;
    max-width: 400px;
    cursor: pointer;

    }
    .btn{
        margin:10px;
    }
          }
           @media screen and (max-width: 1200px) {
               .block1 {
            display: flex;
            padding-left: 15px;
            margin-right: 10px;
            padding-bottom: 10px;
            justify-content: space-between;
            align-items: left;
            max-width: 400px;
        }

        .block2 {
            padding-left: 5px;
            margin-right: 5px;
            position: relative;
            right: 10px;
            margin-top: 10px;
            font-size: 0.6rem;
            display: flex;
            flex-direction: column;
            text-align: left;
            color: black;
            max-width: 350px;
            cursor: pointer;
            }

    
    .block3 {
    color: rgb(163, 170, 235);
    margin-top: 10px;
    font-size: 1rem;
    margin-right: 10px;
    padding-right: 50px;
    max-width: 400px;
    cursor: pointer;

    }
    .block4 {
    display:flex;
    color: rgb(199, 184, 184);
    margin-right: 30px;
    padding-right: 10px;
    font-size: 0.9rem;

    }
          }
           @media screen and (max-width: 950px) {
           .block1 {
               margin-top:30px;
            max-width: 200px;

           }
           .snp {
        width: 25px;
        position: relative;
        bottom: 35px;
        left:42px;
        background: rgb(250, 248, 248);
        border: 2px solid white;
        border-radius: 50%;
        box-shadow: 0 0 5px rgba(0,0,0,0.5);
        }
           .block2 {
            max-width: 300px;
            margin-top: 30px;
             margin-left: 30px;


           }
           .block3 {
            max-width: 300px;

           }

           }

             @media screen and (max-width: 750px) {
           .block1 {
               padding-left: 10px;
               margin: 0 auto;
               margin-top:30px;
               max-width: 200px;

           }
           .snp {
        width: 25px;
        position: relative;
        bottom: 35px;
        left:42px;
        background: rgb(250, 248, 248);
        border: 2px solid white;
        border-radius: 50%;
        box-shadow: 0 0 5px rgba(0,0,0,0.5);
        }
           .block2 {
            max-width: 300px;
            margin-top: 30px;
             margin-left: 30px;


           }
           .block3 p{
            max-width: 200px;
            padding-right: 55px;
           }
         

           }
</style>