<script setup>
import { ref } from 'vue';

var like= ref(93);
var dislike= ref(0);
var love= ref(0);
var bandera = 0;
let likes= document.querySelector('.likes')
let Dislikes= document.querySelector('.Dislikes')

const Ilike = function(){
  if(bandera<=0){
    like.value++;
    dislike.value--;
  }
  if(bandera == 0){
    dislike.value++;
  }
  bandera = 1;
  likes.setAttribute("fill","red")
  Dislikes.setAttribute("fill","none")
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
  Dislikes.setAttribute("fill","orange")
  likes.setAttribute("fill","none")
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
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-5 mt-2 hover:text-red-400 cursor-pointer" ref="likes" @click="Ilike">
          <path stroke-linecap="round" stroke-linejoin="round" d="M6.633 10.5c.806 0 1.533-.446 2.031-1.08a9.041 9.041 0 012.861-2.4c.723-.384 1.35-.956 1.653-1.715a4.498 4.498 0 00.322-1.672V3a.75.75 0 01.75-.75A2.25 2.25 0 0116.5 4.5c0 1.152-.26 2.243-.723 3.218-.266.558.107 1.282.725 1.282h3.126c1.026 0 1.945.694 2.054 1.715.045.422.068.85.068 1.285a11.95 11.95 0 01-2.649 7.521c-.388.482-.987.729-1.605.729H13.48c-.483 0-.964-.078-1.423-.23l-3.114-1.04a4.501 4.501 0 00-1.423-.23H5.904M14.25 9h2.25M5.904 18.75c.083.205.173.405.27.602.197.4-.078.898-.523.898h-.908c-.889 0-1.713-.518-1.972-1.368a12 12 0 01-.521-3.507c0-1.553.295-3.036.831-4.398C3.387 10.203 4.167 9.75 5 9.75h1.053c.472 0 .745.556.5.96a8.958 8.958 0 00-1.302 4.665c0 1.194.232 2.333.654 3.375z" />
          </svg>

          <p class="ml-2 mt-2 select-none">{{ like }}</p>
          <svg xmlns="http://www.w3.org/2000/svg" height="2em" viewBox="0 0 512 512" class="ml-5 mt-2 fill-current text-red-500 hover:text-red-400 cursor-pointer" @click="Ilove">
            <path d="M225.8 468.2l-2.5-2.3L48.1 303.2C17.4 274.7 0 234.7 0 192.8v-3.3c0-70.4 50-130.8 119.2-144C158.6 37.9 198.9 47 231 69.6c9 6.4 17.4 13.8 25 22.3c4.2-4.8 8.7-9.2 13.5-13.3c3.7-3.2 7.5-6.2 11.5-9c0 0 0 0 0 0C313.1 47 353.4 37.9 392.8 45.4C462 58.6 512 119.1 512 189.5v3.3c0 41.9-17.4 81.9-48.1 110.4L288.7 465.9l-2.5 2.3c-8.2 7.6-19 11.9-30.2 11.9s-22-4.2-30.2-11.9zM239.1 145c-.4-.3-.7-.7-1-1.1l-17.8-20c0 0-.1-.1-.1-.1c0 0 0 0 0 0c-23.1-25.9-58-37.7-92-31.2C81.6 101.5 48 142.1 48 189.5v3.3c0 28.5 11.9 55.8 32.8 75.2L256 430.7 431.2 268c20.9-19.4 32.8-46.7 32.8-75.2v-3.3c0-47.3-33.6-88-80.1-96.9c-34-6.5-69 5.4-92 31.2c0 0 0 0-.1 .1s0 0-.1 .1l-17.8 20c-.3 .4-.7 .7-1 1.1c-4.5 4.5-10.6 7-16.9 7s-12.4-2.5-16.9-7z"/>
          </svg>
          <p class="ml-2 mt-2 select-none">{{ love }}</p>
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-5 mt-2 hover:text-red-400 cursor-pointer" ref="Dislikes" @click="Idislike">
          <path stroke-linecap="round" stroke-linejoin="round" d="M7.5 15h2.25m8.024-9.75c.011.05.028.1.052.148.591 1.2.924 2.55.924 3.977a8.96 8.96 0 01-.999 4.125m.023-8.25c-.076-.365.183-.75.575-.75h.908c.889 0 1.713.518 1.972 1.368.339 1.11.521 2.287.521 3.507 0 1.553-.295 3.036-.831 4.398C20.613 14.547 19.833 15 19 15h-1.053c-.472 0-.745-.556-.5-.96a8.95 8.95 0 00.303-.54m.023-8.25H16.48a4.5 4.5 0 01-1.423-.23l-3.114-1.04a4.5 4.5 0 00-1.423-.23H6.504c-.618 0-1.217.247-1.605.729A11.95 11.95 0 002.25 12c0 .434.023.863.068 1.285C2.427 14.306 3.346 15 4.372 15h3.126c.618 0 .991.724.725 1.282A7.471 7.471 0 007.5 19.5a2.25 2.25 0 002.25 2.25.75.75 0 00.75-.75v-.633c0-.573.11-1.14.322-1.672.304-.76.93-1.33 1.653-1.715a9.04 9.04 0 002.86-2.4c.498-.634 1.226-1.08 2.032-1.08h.384" />
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
