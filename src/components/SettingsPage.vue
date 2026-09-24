<script setup lang="ts">
import { ref } from 'vue'

const emit = defineEmits<{ notify: [message: string] }>()
const tab = ref<'Edit Profile' | 'Preferences' | 'Security'>('Edit Profile')
const notifications = ref([true, false, true])
const twoFactor = ref(true)

const profile = ref({
  name: 'Charlene Reed',
  username: 'Charlene Reed',
  email: 'charlenereed@gmail.com',
  password: '**********',
  dob: '25 January 1990',
  presentAddress: 'San Jose, California, USA',
  permanentAddress: 'San Jose, California, USA',
  city: 'San Jose',
  postal: '45962',
  country: 'USA',
  currency: 'USD',
  timezone: '(GMT-12:00) International Date Line West',
})

function save() {
  emit('notify', `${tab.value} saved successfully`)
}
</script>

<template>
  <section class="animate-fade-up">
    <div class="rounded-[18px] bg-white p-4 shadow-[0_5px_20px_rgba(25,50,100,.035)] sm:p-6 lg:p-7">
      <div class="flex overflow-x-auto border-b border-[#eef1f5]">
        <button
          v-for="item in ['Edit Profile', 'Preferences', 'Security']"
          :key="item"
          class="relative shrink-0 px-3 pb-3 text-[10px] font-medium transition sm:px-4"
          :class="tab === item ? 'text-[#315fdc]' : 'text-[#7890b7] hover:text-[#315fdc]'"
          @click="tab = item as 'Edit Profile' | 'Preferences' | 'Security'"
        >
          {{ item }}
          <span v-if="tab === item" class="absolute inset-x-2 -bottom-px h-[2px] rounded-full bg-[#2f35ff]" />
        </button>
      </div>

      <div v-if="tab === 'Edit Profile'" class="pt-7">
        <div class="grid gap-7 lg:grid-cols-[125px_minmax(0,1fr)]">
          <div class="flex justify-center lg:justify-start">
            <div class="relative h-[90px] w-[90px]">
              <img src="/src/assets/image.png" alt="Profile" class="h-[90px] w-[90px] rounded-full object-cover" />
              <button class="absolute bottom-0 right-0 grid h-6 w-6 place-items-center rounded-full bg-[#3137f5] text-[10px] text-white" @click="emit('notify', 'Profile photo editor opened')">✎</button>
            </div>
          </div>

          <div class="grid gap-x-5 gap-y-4 sm:grid-cols-2">
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Your Name</span><input v-model="profile.name" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">User Name</span><input v-model="profile.username" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Email</span><input v-model="profile.email" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Password</span><input v-model="profile.password" type="password" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Date of Birth</span><input v-model="profile.dob" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Present Address</span><input v-model="profile.presentAddress" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Permanent Address</span><input v-model="profile.permanentAddress" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">City</span><input v-model="profile.city" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Postal Code</span><input v-model="profile.postal" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label><span class="mb-2 block text-[10px] font-medium text-[#313b50]">Country</span><input v-model="profile.country" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
          </div>
        </div>
        <div class="mt-5 flex justify-end"><button class="min-w-[102px] rounded-[9px] bg-[#2525ef] px-6 py-2.5 text-[11px] font-semibold text-white transition duration-200 hover:-translate-y-px hover:bg-[#1e1ed6]" @click="save">Save</button></div>
      </div>

      <div v-else-if="tab === 'Preferences'" class="pt-7">
        <div class="grid gap-4 sm:grid-cols-2">
          <label><span class="mb-2 block text-[10px] font-medium">Currency</span><input v-model="profile.currency" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
          <label><span class="mb-2 block text-[10px] font-medium">Time Zone</span><input v-model="profile.timezone" class="w-full h-[38px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
        </div>

        <div class="mt-6">
          <h3 class="text-[11px] font-semibold text-[#3d4960]">Notification</h3>
          <div class="mt-3 space-y-3">
            <label v-for="(item, index) in ['I send or receive digital currency', 'I receive merchant order', 'There are recommendation for my account']" :key="item" class="flex cursor-pointer items-center gap-3 text-[10px] text-[#4b5568]">
              <button type="button" class="relative h-[18px] w-[31px] rounded-full transition" :class="notifications[index] ? 'bg-[#18c9c5]' : 'bg-[#dbe5f1]'" @click="notifications[index] = !notifications[index]">
                <span class="absolute top-[2px] h-[14px] w-[14px] rounded-full bg-white shadow-sm transition" :class="notifications[index] ? 'right-[2px]' : 'left-[2px]'" />
              </button>
              {{ item }}
            </label>
          </div>
        </div>
        <div class="mt-8 flex justify-end"><button class="min-w-[102px] rounded-[9px] bg-[#2525ef] px-6 py-2.5 text-[11px] font-semibold text-white transition duration-200 hover:-translate-y-px hover:bg-[#1e1ed6]" @click="save">Save</button></div>
      </div>

      <div v-else class="pt-7">
        <div class="max-w-[520px]">
          <h3 class="text-[12px] font-semibold text-[#344054]">Two-factor Authentication</h3>
          <label class="mt-4 flex cursor-pointer items-center gap-3 text-[10px] text-[#4b5568]">
            <button type="button" class="relative h-[18px] w-[31px] rounded-full transition" :class="twoFactor ? 'bg-[#18c9c5]' : 'bg-[#dbe5f1]'" @click="twoFactor = !twoFactor">
              <span class="absolute top-[2px] h-[14px] w-[14px] rounded-full bg-white shadow-sm transition" :class="twoFactor ? 'right-[2px]' : 'left-[2px]'" />
            </button>
            Enable or disable two factor authentication
          </label>

          <div class="mt-6">
            <p class="text-[11px] font-semibold text-[#344054]">Change Password</p>
            <label class="mt-3 block"><span class="mb-2 block text-[10px] font-medium">Current Password</span><input value="**********" type="password" class="h-[38px] w-full max-w-[272px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
            <label class="mt-4 block"><span class="mb-2 block text-[10px] font-medium">New Password</span><input value="**********" type="password" class="h-[38px] w-full max-w-[272px] rounded-[9px] border border-[#e1e7ef] bg-white px-3 text-[10px] text-[#7086ad] outline-none transition duration-200 focus:border-[#e1e7ef] focus:shadow-none" /></label>
          </div>
        </div>
        <div class="mt-7 flex justify-end"><button class="min-w-[102px] rounded-[9px] bg-[#2525ef] px-6 py-2.5 text-[11px] font-semibold text-white transition duration-200 hover:-translate-y-px hover:bg-[#1e1ed6]" @click="save">Save</button></div>
      </div>
    </div>
  </section>
</template>
