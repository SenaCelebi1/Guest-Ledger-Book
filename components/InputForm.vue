<template>

<div class="max-w-md py-4 px-8 my-5">
  <form @submit.prevent="sendData" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2">
        EMAIL
      </label>
      <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" v-model="emailValue" placeholder="e-mail address">
    </div>
    <div class="mb-6">
      <label class="block text-gray-700 text-sm font-bold mb-2">
        MESSAGE
      </label>
      
      <div class="mb-3 pt-0">
  <input v-model="msgValue" placeholder="text your message!" type="text" class="px-3 py-4 placeholder-blueGray-300 text-blueGray-600 relative bg-white bg-white rounded text-base border-0 shadow outline-none focus:outline-none focus:ring w-full" />
</div>
    </div>
     <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline">
        Send to the List
     </button>
  </form>

</div>






</template>


<script>
var temp={mail:'', ans:''};
export default {
 

data(){
   return{
       emailValue:'',
       msgValue:''
   }
},
methods:{
    sendData(){
       
       temp.mail= this.emailValue;
       temp.ans=this.msgValue;
       
       this.$emit('sendToData', temp);

       temp.mail= '';
       temp.ans= '';
    
    }
}

 
}
</script>
