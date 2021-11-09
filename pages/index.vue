<template>

<div class="flex flex-col h-screen">
 
<div class="flex-grow">
<Navbar/>
<input-form @sendToData="updateList($event)"/>         
<flashcard v-for="(item,index) in contentOfCards" :key="index" :item="item"/> 
</div>
<div>
<Footer/>
</div>
  
</div>


 
</template>


<script>

import Flashcard from '../components/FlashCard.vue';
import InputForm from '../components/InputForm.vue';
const localKey = 'a';

export default {

components:{
Flashcard,
InputForm
},
data(){
  return{    
    contentOfCards:[{emailadd:'a',answer:'b',done:null},{emailadd:'a',answer:'b',done:null}]
    
  };
  
},
methods:{
 updateList(e){

    if (!e.mail || !e.ans) {
        return; 
    }
    
  

  this.contentOfCards.push({
        emailadd: e.mail,
        answer: e.ans,
        done: false                   
    });
    
    
 }
 
      }, 
      
      mounted() {
            const items = localStorage.getItem(localKey) || '[]';
            this.contentOfCards = JSON.parse(items);
        },
               watch: {
            items: {
                deep: true,
                handler(items) {
                    localStorage.setItem(localKey, JSON.stringify(items))
                }
            }
        }



      

    }

</script>
