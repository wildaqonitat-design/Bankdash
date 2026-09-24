<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits<{ notify: [message: string] }>()
const query = ref('')

const highlights = [
  { icon: 'lifeins.png', title: 'Life Insurance', text: 'Unlimited protection', tone: 'bg-[#e7edff]' },
  { icon: 'shopping.png', title: 'Shopping', text: 'Buy. Think. Grow.', tone: 'bg-[#fff2d2]' },
  { icon: 'safety.png', title: 'Safety', text: 'We are your allies', tone: 'bg-[#d9f8f6]' },
]

const services = [
  { icon: 'loanss.png', title: 'Business loans', desc: 'It is a long established', tone: 'bg-[#ffe4ef]' },
  { icon: 'checking.png', title: 'Checking accounts', desc: 'It is a long established', tone: 'bg-[#fff0cf]' },
  { icon: 'saving.png', title: 'Savings accounts', desc: 'It is a long established', tone: 'bg-[#ffe4ef]' },
  { icon: 'accounts.png', title: 'Debit and credit cards', desc: 'It is a long established', tone: 'bg-[#e6edff]' },
  { icon: 'safety.png', title: 'Life Insurance', desc: 'It is a long established', tone: 'bg-[#d8f8f5]' },
  { icon: 'loanss.png', title: 'Business loans', desc: 'It is a long established', tone: 'bg-[#ffe4ef]' },
]

const filteredServices = () => {
  const q = query.value.trim().toLowerCase()
  if (!q) return services
  return services.filter(item => `${item.title} ${item.desc}`.toLowerCase().includes(q))
}
</script>

<template>
  <section class="animate-fade-up">
    <div class="mb-5 flex items-center justify-between gap-4">
    </div>

    <div class="flex snap-x snap-mandatory gap-4 overflow-x-auto pb-1 [-ms-overflow-style:none] [scrollbar-width:none] [&::-webkit-scrollbar]:hidden md:grid md:grid-cols-3 md:overflow-visible md:pb-0">
      <button
        v-for="item in highlights"
        :key="item.title"
        class="flex min-h-[76px] min-w-[84%] snap-start items-center gap-4 rounded-[16px] bg-white px-5 text-left shadow-[0_4px_16px_rgba(25,50,100,.03)] transition hover:-translate-y-0.5 hover:shadow-md md:min-w-0"
        @click="emit('notify', `${item.title} selected`)"
      >
        <span class="grid h-10 w-10 shrink-0 place-items-center rounded-full" :class="item.tone">
          <img :src="`/src/assets/${item.icon}`" :alt="item.title" class="h-5 w-5 object-contain" />
        </span>
        <span>
          <strong class="block text-[12px] font-semibold text-[#28324b]">{{ item.title }}</strong>
          <small class="mt-1 block text-[10px] text-[#7690bb]">{{ item.text }}</small>
        </span>
      </button>
    </div>

    <div class="mt-5">
      <h3 class="mb-3 text-[13px] font-semibold text-[#344054]">Bank Service List</h3>

      <div class="space-y-2.5">
        <div
          v-for="item in filteredServices()"
          :key="item.title + item.desc"
          class="grid gap-3 rounded-[15px] bg-white px-3 py-3 shadow-[0_3px_12px_rgba(25,50,100,.025)] sm:grid-cols-[minmax(180px,1.5fr)_minmax(110px,1fr)_minmax(110px,1fr)_minmax(110px,1fr)_80px] sm:items-center sm:px-3"
        >
          <div class="flex min-w-0 items-center gap-3">
            <span class="grid h-9 w-9 shrink-0 place-items-center rounded-xl" :class="item.tone">
              <img :src="`/src/assets/${item.icon}`" :alt="item.title" class="h-5 w-5 object-contain" />
            </span>
            <div class="min-w-0">
              <p class="truncate text-[10px] font-semibold text-[#30394e]">{{ item.title }}</p>
              <p class="mt-0.5 text-[9px] text-[#7894c4]">{{ item.desc }}</p>
            </div>
          </div>

          <div class="hidden sm:block"><p class="text-[9px] font-medium text-[#404a60]">Lorem Ipsum</p><p class="mt-1 text-[8px] text-[#7894c4]">Many publishing</p></div>
          <div class="hidden sm:block"><p class="text-[9px] font-medium text-[#404a60]">Lorem Ipsum</p><p class="mt-1 text-[8px] text-[#7894c4]">Many publishing</p></div>
          <div class="hidden sm:block"><p class="text-[9px] font-medium text-[#404a60]">Lorem Ipsum</p><p class="mt-1 text-[8px] text-[#7894c4]">Many publishing</p></div>

          <button
            class="w-full rounded-full border border-[#a9bde7] px-3 py-1.5 text-[9px] font-medium text-[#4268c8] transition hover:border-[#315fdc] hover:bg-[#315fdc] hover:text-white sm:w-[80px]"
            @click="emit('notify', `${item.title} details opened`)"
          >
            View Details
          </button>
        </div>

        <div v-if="filteredServices().length === 0" class="rounded-2xl bg-white py-10 text-center text-xs text-slate-400">Service not found.</div>
      </div>
    </div>
  </section>
</template>
