<script setup lang="ts">
import {RouterView} from 'vue-router';
import {Notifications} from "@kyvg/vue3-notification";

import IconFacebook from "@/components/icons/IconFacebook.vue";
import IconInstagram from "@/components/icons/IconInstagram.vue";
import IconX from "@/components/icons/IconX.vue";
import {useHead} from "@vueuse/head";
import IconWhatsApp from "@/components/icons/IconWhatsApp.vue";

const socials = [
  {title: 'WhatsApp', icon: IconWhatsApp, url: '#'},
  {title: 'Instagram', icon: IconInstagram, url: '#'},
  {title: 'Facebook', icon: IconFacebook, url: '#'},
  {title: 'X', icon: IconX, url: '#'},
];

useHead({
  title: 'Realtors Continent - Empowering Sales Partners to Achieve More in Real Estate.',
  meta: [
    {
      name: 'description',
      content: 'Realtors Continent empowers real estate professionals with the tools, resources, and support they need to excel. From lead generation to closing deals, we create a dynamic environment for smart, persistent sales partners to thrive.'
    },
    {
      name: 'keywords',
      content: 'real estate, real estate professionals, sales partners, lead generation, real estate tools, real estate support, real estate resources, property sales, real estate success',
    },
    {
      name: 'og:title',
      content: 'Realtors Continent - Empowering Sales Partners to Achieve More in Real Estate.',
    }
  ]
})

</script>

<template>
  <div class="flex flex-col w-full min-h-screen">
    <div class="border-b">
      <header class="px-5 md:px-16 m-auto w-full py-5 max-w-[1200px]">
        <div class="flex items-center justify-center md:justify-between">
          <RouterLink to="/">
            <div class="flex items-end">
              <div class="font-semibold text-[#002C80] leading-snug py-1">AMAZING <br/>WEBSITE</div>
            </div>
          </RouterLink>
          <div class="gap-x-5 justify-center hidden md:flex">
            <a :href="social.url" target="_blank" v-for="(social, i) in socials" :key="i" :title="social.title"
               class="bg-[#F5F7FA] hover:bg-[#F5F7FA] border rounded h-10 w-10 flex items-center justify-center">
              <component :is="social.icon" class="w-4 scale-125"/>
            </a>
          </div>
        </div>
      </header>
    </div>
    <RouterView/>
    <notifications/>
    <div class="border-t">
      <footer
          class="py-5 md:px-16 m-auto w-full max-w-[1200px] text-sm flex items-center justify-center md:justify-between flex-wrap gap-4">
        <div class="flex-wrap md:order-1">
          <div class="mb-3 text-center hidden md:block">Contact us on:</div>
          <div class="flex gap-x-5 justify-center">
            <a :href="social.url" target="_blank" v-for="(social, i) in socials" :key="i" :title="social.title"
               class="bg-[#F5F7FA] hover:bg-[#F5F7FA] border rounded h-10 w-10 flex items-center justify-center">
              <component :is="social.icon" class="w-4 scale-125"/>
            </a>
          </div>
        </div>
        <div>&copy; Amazing Website. Designed by:
          <a class="underline" href="https://zebitech.com" target="_blank">Zebitech Global Services Ltd</a>.
        </div>
      </footer>
    </div>
  </div>
</template>
