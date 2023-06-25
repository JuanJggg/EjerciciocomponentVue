<script setup>
import { ref } from 'vue';

var like= ref(93);
var dislike= ref(0);
var love= ref(0);
var bandera = 0;

const Ilike = function(){
  if(bandera<=0){
    like.value++;
    dislike.value--;
  }
  if(bandera == 0){
    dislike.value++;
  }
  bandera = 1;
}

const Ilove = function(){
  if(love.value==0){
    love.value++;
  }
}

const Idislike= function(){
  if(bandera>=0){
    like.value--;
    dislike.value++;
  }

  if(bandera==0){
    like.value--;
  }

  bandera = -1;
}
</script>

<template>
  <div class="bg-gray-50 w-[600px] ml-[750px] mt-[100px] flex justify-center">
    <div class="w-[550px] mt-7">
      <div class="flex justify-between">
        <p class="text-lg font-semibold">Historias</p>
        <p class="bg-blue-400 w-16 flex justify-center items-center rounded-lg cursor-pointer">Todas</p>
      </div>
      <div class=" flex mt-4">
        <div>
          <img src="https://i.pinimg.com/550x/8d/e7/fa/8de7fa2af12330350613ede63532c4fb.jpg" alt="" class="w-[120px] border-[5px] rounded-2xl border-blue-400">
          <p class="text-gray-400">Camila</p>
      </div>
      <div>
          <img src="https://i.pinimg.com/550x/8d/e7/fa/8de7fa2af12330350613ede63532c4fb.jpg" alt="" class="w-[120px] border-[5px] rounded-2xl border-blue-400 ml-5">
          <p class="ml-5 text-gray-400">Erika</p>
      </div>
      <div>
          <img src="https://i.pinimg.com/550x/8d/e7/fa/8de7fa2af12330350613ede63532c4fb.jpg" alt="" class="w-[120px] border-[5px] rounded-2xl border-blue-400 ml-5">
          <p class="ml-5 text-gray-400">Marcela</p>
      </div>
      <div>
          <img src="https://i.pinimg.com/550x/8d/e7/fa/8de7fa2af12330350613ede63532c4fb.jpg" alt="" class="w-[120px] border-[5px] rounded-2xl border-blue-400 ml-5">
          <p class="ml-5 text-gray-400">Cristina</p>
      </div>
      </div>
      <div>
        <div class="mt-5 flex">
          <img src="https://i.pinimg.com/550x/8d/e7/fa/8de7fa2af12330350613ede63532c4fb.jpg" alt="" class="w-[60px] rounded-full">
          <div>
            <p class="text-xl font-semibold ml-3">Mariana Perez</p>
            <p class="text-sm ml-3 text-gray-400">Hace 10 minutos</p>
          </div>
          <p class="ml-[280px] text-red-500 italic mt-3 cursor-pointer">Reportar</p>
        </div>
        <img src="https://t1.uc.ltmcdn.com/es/posts/0/4/0/cuanto_debe_comer_mi_cachorro_labrador_31040_600.jpg" alt="" class="mt-3 rounded-[40px]">
        <div class="flex">
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 512 512" class="ml-5 mt-2 fill-current text-orange-500 hover:text-orange-400 cursor-pointer" @click="Ilike"><path d="M323.8 34.8c-38.2-10.9-78.1 11.2-89 49.4l-5.7 20c-3.7 13-10.4 25-19.5 35l-51.3 56.4c-8.9 9.8-8.2 25 1.6 33.9s25 8.2 33.9-1.6l51.3-56.4c14.1-15.5 24.4-34 30.1-54.1l5.7-20c3.6-12.7 16.9-20.1 29.7-16.5s20.1 16.9 16.5 29.7l-5.7 20c-5.7 19.9-14.7 38.7-26.6 55.5c-5.2 7.3-5.8 16.9-1.7 24.9s12.3 13 21.3 13L448 224c8.8 0 16 7.2 16 16c0 6.8-4.3 12.7-10.4 15c-7.4 2.8-13 9-14.9 16.7s.1 15.8 5.3 21.7c2.5 2.8 4 6.5 4 10.6c0 7.8-5.6 14.3-13 15.7c-8.2 1.6-15.1 7.3-18 15.1s-1.6 16.7 3.6 23.3c2.1 2.7 3.4 6.1 3.4 9.9c0 6.7-4.2 12.6-10.2 14.9c-11.5 4.5-17.7 16.9-14.4 28.8c.4 1.3 .6 2.8 .6 4.3c0 8.8-7.2 16-16 16H286.5c-12.6 0-25-3.7-35.5-10.7l-61.7-41.1c-11-7.4-25.9-4.4-33.3 6.7s-4.4 25.9 6.7 33.3l61.7 41.1c18.4 12.3 40 18.8 62.1 18.8H384c34.7 0 62.9-27.6 64-62c14.6-11.7 24-29.7 24-50c0-4.5-.5-8.8-1.3-13c15.4-11.7 25.3-30.2 25.3-51c0-6.5-1-12.8-2.8-18.7C504.8 273.7 512 257.7 512 240c0-35.3-28.6-64-64-64l-92.3 0c4.7-10.4 8.7-21.2 11.8-32.2l5.7-20c10.9-38.2-11.2-78.1-49.4-89zM32 192c-17.7 0-32 14.3-32 32V448c0 17.7 14.3 32 32 32H96c17.7 0 32-14.3 32-32V224c0-17.7-14.3-32-32-32H32z"/></svg>
          <p class="ml-2 mt-2 select-none">{{ like }}</p>
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 512 512" class="ml-5 mt-2 fill-current text-red-500 hover:text-red-400 cursor-pointer" @click="Ilove">
            <path d="M225.8 468.2l-2.5-2.3L48.1 303.2C17.4 274.7 0 234.7 0 192.8v-3.3c0-70.4 50-130.8 119.2-144C158.6 37.9 198.9 47 231 69.6c9 6.4 17.4 13.8 25 22.3c4.2-4.8 8.7-9.2 13.5-13.3c3.7-3.2 7.5-6.2 11.5-9c0 0 0 0 0 0C313.1 47 353.4 37.9 392.8 45.4C462 58.6 512 119.1 512 189.5v3.3c0 41.9-17.4 81.9-48.1 110.4L288.7 465.9l-2.5 2.3c-8.2 7.6-19 11.9-30.2 11.9s-22-4.2-30.2-11.9zM239.1 145c-.4-.3-.7-.7-1-1.1l-17.8-20c0 0-.1-.1-.1-.1c0 0 0 0 0 0c-23.1-25.9-58-37.7-92-31.2C81.6 101.5 48 142.1 48 189.5v3.3c0 28.5 11.9 55.8 32.8 75.2L256 430.7 431.2 268c20.9-19.4 32.8-46.7 32.8-75.2v-3.3c0-47.3-33.6-88-80.1-96.9c-34-6.5-69 5.4-92 31.2c0 0 0 0-.1 .1s0 0-.1 .1l-17.8 20c-.3 .4-.7 .7-1 1.1c-4.5 4.5-10.6 7-16.9 7s-12.4-2.5-16.9-7z"/>
          </svg>
          <p class="ml-2 mt-2 select-none">{{ love }}</p>
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 512 512" class="ml-5 mt-2 fill-current text-red-500 hover:text-red-400 cursor-pointer" @click="Idislike">
            <path d="M323.8 477.2c-38.2 10.9-78.1-11.2-89-49.4l-5.7-20c-3.7-13-10.4-25-19.5-35l-51.3-56.4c-8.9-9.8-8.2-25 1.6-33.9s25-8.2 33.9 1.6l51.3 56.4c14.1 15.5 24.4 34 30.1 54.1l5.7 20c3.6 12.7 16.9 20.1 29.7 16.5s20.1-16.9 16.5-29.7l-5.7-20c-5.7-19.9-14.7-38.7-26.6-55.5c-5.2-7.3-5.8-16.9-1.7-24.9s12.3-13 21.3-13L448 288c8.8 0 16-7.2 16-16c0-6.8-4.3-12.7-10.4-15c-7.4-2.8-13-9-14.9-16.7s.1-15.8 5.3-21.7c2.5-2.8 4-6.5 4-10.6c0-7.8-5.6-14.3-13-15.7c-8.2-1.6-15.1-7.3-18-15.2s-1.6-16.7 3.6-23.3c2.1-2.7 3.4-6.1 3.4-9.9c0-6.7-4.2-12.6-10.2-14.9c-11.5-4.5-17.7-16.9-14.4-28.8c.4-1.3 .6-2.8 .6-4.3c0-8.8-7.2-16-16-16H286.5c-12.6 0-25 3.7-35.5 10.7l-61.7 41.1c-11 7.4-25.9 4.4-33.3-6.7s-4.4-25.9 6.7-33.3l61.7-41.1c18.4-12.3 40-18.8 62.1-18.8H384c34.7 0 62.9 27.6 64 62c14.6 11.7 24 29.7 24 50c0 4.5-.5 8.8-1.3 13c15.4 11.7 25.3 30.2 25.3 51c0 6.5-1 12.8-2.8 18.7C504.8 238.3 512 254.3 512 272c0 35.3-28.6 64-64 64l-92.3 0c4.7 10.4 8.7 21.2 11.8 32.2l5.7 20c10.9 38.2-11.2 78.1-49.4 89zM32 384c-17.7 0-32-14.3-32-32V128c0-17.7 14.3-32 32-32H96c17.7 0 32 14.3 32 32V352c0 17.7-14.3 32-32 32H32z"/>
          </svg>
          <p class="ml-2 mt-2 select-none">{{ dislike  }}</p>
        </div>
        <div class="bg-[#ededed] flex h-16 items-center rounded-xl mt-3 mb-5">
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 448 512" class="mr-[190px] ml-8 fill-current text-blue-600">
            <path d="M304 128a80 80 0 1 0 -160 0 80 80 0 1 0 160 0zM96 128a128 128 0 1 1 256 0A128 128 0 1 1 96 128zM49.3 464H398.7c-8.9-63.3-63.3-112-129-112H178.3c-65.7 0-120.1 48.7-129 112zM0 482.3C0 383.8 79.8 304 178.3 304h91.4C368.2 304 448 383.8 448 482.3c0 16.4-13.3 29.7-29.7 29.7H29.7C13.3 512 0 498.7 0 482.3z"/>
          </svg>
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 576 512" class="mr-[180px] fill-current text-blue-600">
            <path d="M575.8 255.5c0 18-15 32.1-32 32.1h-32l.7 160.2c0 2.7-.2 5.4-.5 8.1V472c0 22.1-17.9 40-40 40H456c-1.1 0-2.2 0-3.3-.1c-1.4 .1-2.8 .1-4.2 .1H416 392c-22.1 0-40-17.9-40-40V448 384c0-17.7-14.3-32-32-32H256c-17.7 0-32 14.3-32 32v64 24c0 22.1-17.9 40-40 40H160 128.1c-1.5 0-3-.1-4.5-.2c-1.2 .1-2.4 .2-3.6 .2H104c-22.1 0-40-17.9-40-40V360c0-.9 0-1.9 .1-2.8V287.6H32c-18 0-32-14-32-32.1c0-9 3-17 10-24L266.4 8c7-7 15-8 22-8s15 2 21 7L564.8 231.5c8 7 12 15 11 24z"/>
          </svg>
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 512 512" class="fill-current text-blue-600">
            <path d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"/>
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
