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
      
      <div class="w-1/3 bg-gray-50 border-r"></div>
      
      <div class="w-1/2">

        <div>
        <div class="px-6">
        <div class="border-b h-20 border-gray-200"></div>
      </div>

      <div class="px-6">
        <div class="border-b h-24 border-gray-200"></div>
      </div>
    </div>

    <div>

      <div class="p-6">
      <div class="h-auto border-b border-gray-200">
        <p class="text-[22px] mb-4">Web design requirement for travel website</p>
        
        <p class="text-[18px] mb-4">Hello Asal Design</p>
        <p class="text-[18px] mb-4">I contacted you to see if you are interested and willing to help me with my website<br/>
        design. Work is still on-going and it's starting on Figma. If you're interested, let me <br/>
        know if we can chat for a bit and how much you usually charge.
        </p>
        <p class="text-[18px] mb-4">Hope to hear from you soon.</p>
        <p class="text-[18px] mb-6">Regards,<br/>Wahyu Siburan </p>
      </div>
    </div>

      <div class="px-6">
      <div class="h-28 border-b border-gray-200"></div>
    </div>

      <div class="px-6">
      <div class="h-25 border-b border-gray-200" ></div>
    </div>

      <div class="px-6">
      <div class="h-22">border</div>
    </div>
    </div>


      </div>

      

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