<template>
  <div class="user">
    <div class="flex mt-20">
      <div class="w-1/5 h-12"></div>
      <div class="w-3/5 bg-gray-400 h-12">
        <div class="mx-auto">
          <div class="w-2 bg-gray-800"></div>
          <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-black rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
            <div class="mb-8">
              <div class="text-orange-500 font-bold text-3xl mb-2">{{ response.name }}</div>
              <p class="text-gray-200 text-base">{{ response.bio }}</p>
            </div>
             <div class="flex items-center">
              <img class="w-12 h-12 rounded-full mr-4" :src="response.avatar_url">
              <div class="text-sm">
                <p class="text-gray-200">{{ response.location }}</p>
                <a v-bind:href="response.bio" class="text-gray-200">{{ response.blog }}</a>
              </div>
            </div>
          </div>
        </div>
        
        <div class="flex">
          <div class="w-1/6 bg-gray-400 h-10"></div>
          <div class="w-1/6 bg-gray-500 h-10"></div>
          <div class="w-1/6 bg-gray-400 h-10"></div>
          <div class="w-1/6 bg-gray-500 h-10"></div>
          <div class="w-1/6 bg-gray-400 h-10"></div>
          <div class="w-1/6 bg-gray-500 h-10"></div>
        </div>

        <div class="mt-10 flex  flex-wrap min-w-full">
          <a class="px-4 py-2 mt-2 text-lg text-gray-900 bg-gray-200 rounded-lg sm:mt-0 hover:text-gray-900 focus:text-gray-900 hover:bg-gray-300" href="#"><span class="badge mb-3 bg-red-800 rounded-full px-2 py-1 text-center object-right-top text-white text-sm mr-1">24</span>Messages</a>
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

