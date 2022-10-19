<template>
  <div class="text-3xl w-screen h-screen p-4 bg-slate-200">
    <div class="w-full h-full bg-white border rounded-lg flex">
      
      <div class="w-1/6 bg-gray-100 border-r p-4 space-y-4">

        <div class="w-full h-16 bg-slate-200 border rounded"></div>
        <div class="w-full h-12 bg-blue-700 border rounded"></div>

        <div class="h-auto w-full p-0">
          <!-- <div class="h-10 w-full bg-white rounded"></div> -->
          <div class="h-10 w-full rounded text-sm flex items-center justify-between text-slate-500 p-2" 
            v-for="item in mainMenuItems" 
            :class="{ 'bg-white': item.name === 'Inbox' }"
            :key="item">
              <div 
                class="flex space-x-2 items-center">
                <component 
                  class="h-5 w-5" 
                  :is="OutlineIcons[item.icon]">
                </component>
                <span class="text-xs font-normal">{{ item.name }}</span>
                <div
                  :class="{ 'hidden' : item.unReadCount === 0}" 
                  class="text-white bg-red-600 rounded px-1">
                  <span v-if="item.unReadCount > 0" class="text-[10px]">{{ item.unReadCount }}</span>
                </div>
              </div>
              <div class="text-[11px]">{{ item.readCount }}</div>
          </div>
        </div>
      </div>
      
      <div class="w-1/3 bg-gray-50 border-r p-4">
        <div class="w-full h-40 item-center text-slate-500">
          <div class="flex-col">
            <h6 class="text-[20px] font-bold">Inbox</h6>
            <div class="text-sm text-slate-400 justify-between items-center"> 
              <small>382 message</small>&nbsp;&nbsp;<small>120 Unread</small>
            </div>
          </div>
          <div class="flex"> 
            <div class="w-72"> 
              <input type="text" class="w-full bg-gray-100 border-none rounded-md text-sm h-10 p-2" placeholder="Search"/>
            </div>
              <!-- <button class="ml-4">plus</button> -->
          </div>
        </div>
      </div>
      
      <div class="w-1/2"></div>

    </div>
  </div>
</template>

<script setup>
import * as OutlineIcons from '@heroicons/vue/24/outline';

const mainMenuItems = [
  { icon:'InboxIcon', name:'Inbox', unReadCount:109, readCount: 0 },
  { icon:'InboxStackIcon', name:'Sent Mail', unReadCount:0, readCount: 0 },
  { icon:'InboxStackIcon', name:'All Mail', unReadCount:0, readCount: 0 },
  { icon:'PencilIcon', name:'Drafts', unReadCount:0, readCount: 0 },
  { icon:'StarIcon', name:'Favourites', unReadCount:0, readCount: 0 },
  { icon:'FolderMinusIcon', name:'Spam', unReadCount:0, readCount: 0 },
  { icon:'TrashIcon', name:'Trash', unReadCount:0, readCount: 0 },
];

</script>

<style>

</style>