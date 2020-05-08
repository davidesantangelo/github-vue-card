<template>
  <div class="user">
    
    <div class="flex mt-20">
      <div class="w-1/5 h-12"></div>
      
      <div class="w-3/5 bg-gray-400 h-16 mx-auto">
         <a v-bind:href="response.html_url" class="flex flex-col bg-orange-100 border-orange-500 text-orange-700 p-4">
          <div class="text-center py-2 lg:px-4">
            <div class="items-center text-orange-500 leading-none flex lg:inline-flex" role="alert">
              <span class="font-semibold mr-2 text-left flex-auto">Visit the Awesome <span class="underline">{{ response.name }}</span> GitHub Profile </span>
              <svg class="fill-current opacity-75 h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M12.95 10.707l.707-.707L8 4.343 6.586 5.757 10.828 10l-4.242 4.243L8 15.657l4.95-4.95z"/></svg>
            </div>
          </div>
        </a>
        <div class="w-2 bg-gray-800"></div>
          <div class="bg-black p-8 flex flex-col justify-between leading-normal">
            <div class="mb-8">
              <div class="text-orange-500 font-bold text-3xl mb-2">{{ response.name }}</div>
              <p class="text-gray-200 text-xl">{{ response.bio }}</p>
            </div>
            <div class="flex items-center">
              <img class="w-16 h-16 rounded-full mr-4" :src="response.avatar_url">
              <div class="text-base">
                <p class="text-gray-200">{{ response.location }}</p>
                <a v-bind:href="response.bio" class="text-blue-200">{{ response.blog }}</a>
              </div>
            </div>
          </div>

          <div class="flex">
            <div class="w-1/6 bg-gray-800 h-8"></div>
            <div class="w-1/6 bg-gray-800 h-8"></div>
            <div class="w-1/6 bg-gray-800 h-8"></div>
            <div class="w-1/6 bg-gray-800 h-8"></div>
            <div class="w-1/6 bg-gray-800 h-8"></div>
            <div class="w-1/6 bg-gray-800 h-8"></div>
          </div>
          <div class="bg-black pt-8 pb-8 px-4 flex flex-col justify-between leading-normal">
           <div class="inline-flex">
              <span class="text-gray-300 font-bold px-4 mr-5">
                Public Repos <span class="bg-gray-400 p-2 m-1 bg-gray-600 text-gray-100  w-24 h-24 text-black  rounded-full">{{ response.public_repos }}</span>
              </span>
              <span class="text-gray-300 font-bold px-4 mr-5">
                Public Gists <span class="bg-gray-400 p-2 m-1 bg-gray-600 text-gray-100  w-24 h-24 text-black  rounded-full">{{ response.public_gists }}</span>
              </span>
               <span class="text-gray-300 font-bold px-4 mr-5">
                Followers <span class="bg-gray-400 p-2 m-1 bg-gray-600 text-gray-100  w-24 h-24 text-black  rounded-full">{{ response.followers }}</span>
              </span>
               <span class="text-gray-300 font-bold  px-4 mr-5 ">
                Following <span class="bg-gray-400 p-2 m-1 bg-gray-600 text-gray-100  w-24 h-24 text-black  rounded-full">{{ response.following }}</span>
              </span>
            </div>
          </div>
          
      </div>

      <div class="w-1/5 h-12"></div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'user',
  data () {
    return {
      response: null
    }
  },
  mounted () {
    axios
      .get(' https://api.github.com/users/davidesantangelo')
      .then(response => (this.response = response.data))
  },
  props: {
    msg: String
  }
}
</script>

