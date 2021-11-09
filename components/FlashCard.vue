<template>


<div class=" px-8">     
<div class="max-w-md py-4 px-8 bg-gray-100 shadow-lg rounded-lg my-20">
  
  <div>
    <h5 class="text-gray-800 text-2xl font-semibold">Email: {{item.emailadd}}</h5>
    <p class="mt-2 text-gray-600">{{item.answer}}</p>
  </div>
  <div class="flex justify-end mt-4">
    <a href="#" class="text-xl font-medium text-indigo-500">Sena Çelebi</a>
  </div>
</div>

      </div>





</template>


<script>
export default {

  props:{
    item:Object
  },
  data(){
    return{
     flipped: false
    }
  }
 
}
</script>
