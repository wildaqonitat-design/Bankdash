<script setup lang="ts">
import { ref } from 'vue'

const sidebarOpen = ref(false)
const searchQuery = ref('')

const closeSidebar = () => {
  sidebarOpen.value = false
}
</script>

<template>
  <div class="animate-fade-up">
  <div class="mt-6 mb-4">
          <h2 class="mb-3 text-[16px] font-semibold text-[#344054]">My Cards</h2>
        </div>

        <div class="-mx-2 overflow-x-auto pb-2 md:overflow-visible">
          <div class="flex min-w-max gap-4 md:flex-wrap md:min-w-0 md:gap-6">
            <div class="relative h-[197px] w-[280px] min-w-[280px] shrink-0 overflow-hidden rounded-[20px] bg-gradient-to-br from-[#3d73ff] to-[#4d91f5] text-white md:w-[306px] md:min-w-0">
              <img src="/src/assets/chip.png" alt="Logo" class="absolute right-5 top-6 h-7 w-7 object-contain" />
              <div class="absolute left-6 top-6">
                <p class="text-[10px] text-white/80">Balance</p>
                <p class="text-[16px] font-medium">$5,756</p>
              </div>

              <div class="absolute left-6 top-[80px]">
                <p class="text-[10px] text-white/70">CARD HOLDER</p>
                <p class="text-[12px]">Eddy Cusuma</p>
              </div>

              <div class="absolute left-[160px] top-[80px]">
                <p class="text-[10px] text-white/70">VALID THRU</p>
                <p class="text-[12px]">12/22</p>
              </div>

              <div class="absolute bottom-0 left-0 flex h-[61px] w-full items-center justify-between border-t border-white/10 px-6">
                <p class="text-[19px]">3778 **** **** 1234</p>
                <div class="flex">
                  <span class="h-6 w-6 rounded-full bg-white/50"></span>
                  <span class="-ml-2 h-6 w-6 rounded-full bg-white/40"></span>
                </div>
              </div>
            </div>

            <div class="relative h-[197px] w-[280px] min-w-[280px] shrink-0 overflow-hidden rounded-[20px] bg-gradient-to-br from-[#0A06F4] to-[#4C49ED] text-white md:w-[306px] md:min-w-0">
              <img src="/src/assets/chip.png" alt="Logo" class="absolute right-5 top-6 h-7 w-7 object-contain" />
              <div class="absolute left-6 top-6">
                <p class="text-[10px] text-white/80">Balance</p>
                <p class="text-[16px] font-medium">$5,756</p>
              </div>

              <div class="absolute left-6 top-[80px]">
                <p class="text-[10px] text-white/70">CARD HOLDER</p>
                <p class="text-[12px]">Eddy Cusuma</p>
              </div>

              <div class="absolute left-[160px] top-[80px]">
                <p class="text-[10px] text-white/70">VALID THRU</p>
                <p class="text-[12px]">12/22</p>
              </div>

              <div class="absolute bottom-0 left-0 flex h-[61px] w-full items-center justify-between border-t border-white/10 px-6">
                <p class="text-[19px]">3778 **** **** 1234</p>
                <div class="flex">
                  <span class="h-6 w-6 rounded-full bg-white/50"></span>
                  <span class="-ml-2 h-6 w-6 rounded-full bg-white/40"></span>
                </div>
              </div>
            </div>

            <div class="relative h-[197px] w-[280px] min-w-[280px] shrink-0 overflow-hidden rounded-[20px] border border-[#dfe5ed] bg-white text-[#344054] md:w-[306px] md:min-w-0">
              <img src="/src/assets/chip.png" alt="Logo" class="absolute right-5 top-6 h-7 w-7 object-contain opacity-40" />

              <div class="absolute left-6 top-6">
                <p class="text-[10px] text-[#7890b8]">Balance</p>
                <p class="text-[16px] font-medium">$5,756</p>
              </div>

              <div class="absolute left-6 top-[80px]">
                <p class="text-[10px] text-[#7890b8]">CARD HOLDER</p>
                <p class="text-[12px]">Eddy Cusuma</p>
              </div>

              <div class="absolute left-[160px] top-[80px]">
                <p class="text-[10px] text-[#7890b8]">VALID THRU</p>
                <p class="text-[12px]">12/22</p>
              </div>

              <div class="absolute bottom-0 left-0 flex h-[61px] w-full items-center justify-between border-t border-[#e1e6ee] px-6">
                <p class="text-[19px]">3778 **** **** 1234</p>

                <div class="flex">
                  <span class="h-6 w-6 rounded-full bg-[#d1d6df]"></span>
                  <span class="-ml-2 h-6 w-6 rounded-full bg-[#b9c0cd]"></span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="mt-5 mb-5 flex flex-col gap-2 font-semibold sm:flex-row sm:gap-10">
          <p>Card Expense Statistics</p>
          <p class="ml-18 hidden lg:block">Card List</p>
        </div>

        <div class="flex flex-col gap-5 xl:flex-row">
          <div class="h-[232px] w-full rounded-[18px] bg-white p-5 sm:w-[260px]">
            <div class="flex justify-center">
              <div class="relative h-[140px] w-[140px] rounded-full" style="background: conic-gradient(#18c9c0 0deg 90deg, #ff5b91 90deg 180deg, #ffb52e 180deg 270deg, #4778f5 270deg 360deg);">
                <div class="absolute left-1/2 top-1/2 h-[50px] w-[50px] -translate-x-1/2 -translate-y-1/2 rounded-full bg-white"></div>
              </div>
            </div>
            <div class="mt-2 grid grid-cols-2 gap-y-2 text-[11px]">
              <div class="flex items-center gap-2">
                <span class="h-3 w-3 rounded-full bg-[#4778f5]"></span>
                <span class="text-[#7890b8]">DBL Bank</span>
              </div>

              <div class="flex items-center gap-2">
                <span class="h-3 w-3 rounded-full bg-[#ff5b91]"></span>
                <span class="text-[#7890b8]">BRC Bank</span>
              </div>

              <div class="flex items-center gap-2">
                <span class="h-3 w-3 rounded-full bg-[#18c9c0]"></span>
                <span class="text-[#7890b8]">ABM Bank</span>
              </div>

              <div class="flex items-center gap-2">
                <span class="h-3 w-3 rounded-full bg-[#ffb52e]"></span>
                <span class="text-[#7890b8]">MCP Bank</span>
              </div>
            </div>
          </div>

          <div class="mt-5 mb-5 flex flex-col gap-2 font-semibold sm:flex-row sm:gap-10">
            <button class="flex items-center gap-2 block md:hidden text-[13px] border-[#f5f7fb]">
            <p>Card List</p>
          </button>
          </div>

          <div class="flex flex-1 flex-col gap-4">
            <div class="flex flex-col gap-3 rounded-[15px] bg-white p-3 sm:h-[67px] sm:flex-row sm:items-center">
              <div class="mr-0 flex h-[44px] w-[44px] shrink-0 items-center justify-center rounded-[14px] bg-[#e9efff] sm:mr-4">
                <img src="/src/assets/blue.png" alt="Foto" class="h-6 w-6 rounded-md object-cover" />
              </div>

              <div class="grid grid-cols-2 gap-2 sm:flex sm:w-full sm:items-center sm:gap-0">
                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium text-[#222]">Card Type</p>
                  <p class="text-[11px] text-[#88a0c5]">Secondary</p>
                </div>

                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium text-[#222]">Bank</p>
                  <p class="text-[11px] text-[#88a0c5]">DBL Bank</p>
                </div>

                <div class="sm:w-[115px]">
                  <p class="text-[12px] font-medium text-[#222]">Card Number</p>
                  <p class="text-[11px] text-[#88a0c5]">**** **** 5600</p>
                </div>

                <div class="sm:w-[100px]">
                  <p class="text-[12px] font-medium text-[#222]">Name On Card</p>
                  <p class="text-[11px] text-[#88a0c5]">William</p>
                </div>
              </div>

              <button class="whitespace-nowrap text-left text-[11px] font-medium text-[#1717ef] sm:ml-auto">
                <a href="#">View Details</a>
              </button>
            </div>

            <div class="flex flex-col gap-3 rounded-[15px] bg-white p-3 sm:h-[67px] sm:flex-row sm:items-center">
              <div class="mr-0 flex h-[44px] w-[44px] shrink-0 items-center justify-center rounded-[14px] bg-[#ffe5ee] sm:mr-4">
                <img src="/src/assets/ccpink.png" alt="Foto" class="h-6 w-6 rounded-md object-cover" />
              </div>

              <div class="grid grid-cols-2 gap-2 sm:flex sm:w-full sm:items-center sm:gap-0">
                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium">Card Type</p>
                  <p class="text-[11px] text-[#88a0c5]">Secondary</p>
                </div>

                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium">Bank</p>
                  <p class="text-[11px] text-[#88a0c5]">BRC Bank</p>
                </div>

                <div class="sm:w-[115px]">
                  <p class="text-[12px] font-medium">Card Number</p>
                  <p class="text-[11px] text-[#88a0c5]">**** **** 4300</p>
                </div>

                <div class="sm:w-[100px]">
                  <p class="text-[12px] font-medium">Name On Card</p>
                  <p class="text-[11px] text-[#88a0c5]">Michel</p>
                </div>
              </div>

              <button class="whitespace-nowrap text-left text-[11px] font-medium text-[#1717ef] sm:ml-auto"><a href="#">View Details</a></button>
            </div>

            <div class="flex flex-col gap-3 rounded-[15px] bg-white p-3 sm:h-[67px] sm:flex-row sm:items-center">
              <div class="mr-0 flex h-[44px] w-[44px] shrink-0 items-center justify-center rounded-[14px] bg-[#fff1d4] sm:mr-4">
                <img src="/src/assets/ccyellow.png" alt="Foto" class="h-6 w-6 rounded-md object-cover" />
              </div>

              <div class="grid grid-cols-2 gap-2 sm:flex sm:w-full sm:items-center sm:gap-0">
                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium">Card Type</p>
                  <p class="text-[11px] text-[#88a0c5]">Secondary</p>
                </div>

                <div class="sm:w-[90px]">
                  <p class="text-[12px] font-medium">Bank</p>
                  <p class="text-[11px] text-[#88a0c5]">ABM Bank</p>
                </div>

                <div class="sm:w-[115px]">
                  <p class="text-[12px] font-medium">Card Number</p>
                  <p class="text-[11px] text-[#88a0c5]">**** **** 7560</p>
                </div>

                <div class="sm:w-[100px]">
                  <p class="text-[12px] font-medium">Name On Card</p>
                  <p class="text-[11px] text-[#88a0c5]">Edward</p>
                </div>
              </div>

              <button class="whitespace-nowrap text-left text-[11px] font-medium text-[#1717ef] sm:ml-auto"><a href="#">View Details</a></button>
            </div>
          </div>
        </div>

        <div class="mt-5 mb-5 flex flex-col gap-2 font-semibold sm:flex-row sm:gap-10">
          <p>Add New Card</p>
          <p class="ml-220 hidden lg:block">Card Setting</p>
        </div>

        <div class="flex flex-col gap-5 mt-5 xl:flex-row">
          <section class="flex-1 rounded-[15px]  border-[#dfe5ed] bg-white p-5 text-[#344054]">
            <p class="mb-6 text-[16px] text-slate-400">
              Credit Card generally means a plastic card issued by Scheduled Commercial Banks assigned to a Cardholder, with a credit limit, that can be used to purchase goods and services on credit or obtain cash advances.
            </p>

            <div class="grid gap-5 md:grid-cols-2">
              <div>
                <label class="mb-2 block text-[16px]">Card Type</label>
                <div class="flex h-10 items-center rounded-2xl border border-slate-300 px-3">
                  <input type="text" placeholder="Classic" class="w-full border-0 bg-transparent text-[16px] text-slate-400 outline-none" />
                </div>
              </div>

              <div>
                <label class="mb-2 block text-[16px]">Name On Card</label>
                <div class="flex h-10 items-center rounded-2xl border border-slate-300 px-3">
                  <input type="text" placeholder="My Cards" class="w-full border-0 bg-transparent text-[16px] text-slate-400 outline-none" />
                </div>
              </div>

              <div>
                <label class="mb-2 block text-[16px]">Card Number</label>
                <div class="flex h-10 items-center rounded-2xl border border-slate-300 px-3">
                  <input type="password" placeholder="**** **** **** ****" class="w-full border-0 bg-transparent text-[16px] text-slate-400 outline-none" />
                </div>
              </div>

              <div>
                <label class="mb-2 block text-[16px]">Expiration Date</label>
                <div class="flex h-10 items-center rounded-2xl border border-slate-300 px-3">
                  <select class="w-full border-0 bg-transparent text-[16px] text-slate-400 outline-none" name="date">
                    <option value="25 January 2025">25 January 2025</option>
                  </select>
                </div>
              </div>
            </div>

            <button class="mt-6 flex h-10 w-full items-center justify-center rounded-2xl bg-blue-800 text-[16px] text-white sm:w-40">
              Add Card
            </button>
          </section>

          <div class="mt-5 mb-5 flex flex-col gap-2 font-semibold sm:flex-row sm:gap-10">
            <button class="flex items-center gap-2 block md:hidden text-[13px] border-[#f5f7fb]">
            <p>Card Setting</p>
          </button>
          </div>

          <section class="w-full rounded-[18px] bg-white px-6 py-5 xl:max-w-[270px]">
            <div class="mb-4 flex items-center gap-4">
              <div class="flex h-[46px] w-[46px] shrink-0 items-center justify-center rounded-[14px] bg-[#fff1d2]">
                <img src="/src/assets/blockcard.png" alt="Block Card" class="h-6 w-6 rounded-full object-cover" />
              </div>

              <div>
                <p class="text-[13px] font-medium text-[#222]">Block Card</p>
                <p class="mt-0.5 text-[11px] text-[#7894c4]">Instantly block your card</p>
              </div>
            </div>

            <div class="mb-4 flex items-center gap-4">
              <div class="flex h-[46px] w-[46px] shrink-0 items-center justify-center rounded-[14px] bg-[#e7eeff]">
                <img src="/src/assets/lock.png" alt="Change Pin" class="h-6 w-6 rounded-full object-cover" />
              </div>

              <div>
                <p class="text-[13px] font-medium text-[#222]">Change Pin Code</p>
                <p class="mt-0.5 text-[11px] text-[#7894c4]">Choose another pin code</p>
              </div>
            </div>

            <div class="mb-4 flex items-center gap-4">
              <div class="flex h-[46px] w-[46px] shrink-0 items-center justify-center rounded-[14px] bg-[#ffe1ec]">
                <img src="/src/assets/google.png" alt="Google Pay" class="h-6 w-6 rounded-full object-cover" />
              </div>

              <div>
                <p class="text-[13px] font-medium text-[#222]">Add to Google Pay</p>
                <p class="mt-0.5 text-[11px] text-[#7894c4]">Withdraw without any card</p>
              </div>
            </div>

            <div class="mb-4 flex items-center gap-4">
              <div class="flex h-[46px] w-[46px] shrink-0 items-center justify-center rounded-[14px] bg-[#d9f8f6]">
                <img src="/src/assets/apple.png" alt="Apple Pay" class="h-6 w-6 rounded-full object-cover" />
              </div>

              <div>
                <p class="text-[13px] font-medium text-[#222]">Add to Apple Pay</p>
                <p class="mt-0.5 text-[11px] text-[#7894c4]">Withdraw without any card</p>
              </div>
            </div>

            <div class="flex items-center gap-4">
              <div class="flex h-[46px] w-[46px] shrink-0 items-center justify-center rounded-[14px] bg-[#d9f8f6]">
                <img src="/src/assets/apple.png" alt="Apple Store" class="h-6 w-6 rounded-full object-cover" />
              </div>

              <div>
                <p class="text-[13px] font-medium text-[#222]">Add to Apple Store</p>
                <p class="mt-0.5 text-[11px] text-[#7894c4]">Withdraw without any card</p>
              </div>
            </div>
          </section>
        </div>
  </div>
</template>
