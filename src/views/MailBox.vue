<template>
  <div class="text-3xl w-screen h-screen p-4 bg-slate-200">
    <div class="w-full h-full bg-white border rounded-lg flex">
      
      <div class="w-1/5 bg-gray-100 border-r p-4 space-y-4">

        <div class="w-full h-16 bg-slate-200 border rounded flex items-center p-2 space-x-2">
          <div class="h-12 w-12 rounded-full bg-gradient-to-r from-cyan-500 to-blue-500 flex-shrink-0"></div>
          <div class="flex flex-col justify-center -space-y-2.5 pt-2">
            <span class="text-sm font-semibold">Abednego Samuel</span>
            <span class="text-[10px] text-gray-500">abednego.example@gmail.com</span>
          </div>
        </div>
        <div class="w-full h-12 bg-blue-700 border rounded-lg text-white flex items-center text-sm pl-2 space-x-2">
          <component 
            class="h-6 w-6 stroke-2" 
            :is="OutlineIcons['PlusIcon']">
          </component>
          <span>New Message</span>
        </div>

        <div class="h-auto w-full p-0">
          <!-- <div class="h-10 w-full bg-white rounded"></div> -->
          <div class="h-12 w-full rounded-lg text-sm flex items-center justify-between text-slate-500 p-2 cursor-pointer" 
            v-for="item in mainMenuItems"
            :class="{ 'bg-white border shadow-sm': activeTab === item.tab }"
            @click="changeTab(item.tab)"
            :key="item">
              <div 
                class="flex space-x-2 items-center">
                <component 
                  class="h-6 w-6" 
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

              <!-- This is not how one references items / elements within an array -->
              <!-- <button class="ml-4"><OutlineIcons.PlusIcon  class="bg-gray-500"/></button> -->

              <button class="ml-4"><OutlineIcons.PlusIcon  class="bg-gray-500"/></button>
          </div>
        </div>
      </div>
      
      <div class="w-1/2"></div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import * as OutlineIcons from '@heroicons/vue/24/outline';

const activeTab = ref('inbox')

const changeTab = (tab) => activeTab.value = tab

const mainMenuItems = [
  { tab:'inbox', icon:'InboxIcon', name:'Inbox', unReadCount:109, readCount: 0 },
  { tab:'sentMail', icon:'InboxStackIcon', name:'Sent Mail', unReadCount:0, readCount: 0 },
  { tab:'allMail', icon:'InboxStackIcon', name:'All Mail', unReadCount:0, readCount: 0 },
  { tab:'drafts', icon:'PencilIcon', name:'Drafts', unReadCount:0, readCount: 0 },
  { tab:'favourites', icon:'StarIcon', name:'Favourites', unReadCount:0, readCount: 0 },
  { tab:'spam', icon:'FolderMinusIcon', name:'Spam', unReadCount:0, readCount: 0 },
  { tab:'trash', icon:'TrashIcon', name:'Trash', unReadCount:0, readCount: 0 },
];

</script>

<style>

</style>