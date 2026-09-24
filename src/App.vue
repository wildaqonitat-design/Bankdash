<script setup lang="ts">
import { ref } from 'vue'
import ServicesPage from './components/ServicesPage.vue'
import SettingsPage from './components/SettingsPage.vue'
import CreditCardsPage from './components/pages/CreditCardsPage.vue'


type Page=string
const activePage=ref<Page>('Credit Cards'); const sidebarOpen=ref(false); const search=ref(''); const toast=ref('')
const navItems:{label:Page;icon:string;activeIcon?:string}[]=[
    {label:'Dashboard',icon:'home.png'},
    {label:'Transactions',icon:'transfer.png'},
    {label:'Accounts',icon:'account.png'},
    {label:'Investment',icon:'investment.png'},
    {label:'Credit Cards',icon:'cc.png',activeIcon:'blue.png'},
    {label:'Loans',icon:'loans.png'},
    {label:'Services',icon:'service.png',activeIcon:'serviceblue.png'},
    {label:'My Privileges',icon:'myprivilage.png'},
    {label:'Setting',icon:'settings.png',activeIcon:'settingblue.png'},
]
function navigate(p:Page){activePage.value=p;sidebarOpen.value=false}
function notify(m:string){toast.value=m;window.setTimeout(()=>toast.value='',2200)}
function pageNavigate(m:string){if(navItems.some(x=>x.label===m))navigate(m as Page)}
</script>
<template>
    <div class="min-h-screen bg-[#f5f7fb] text-[#232323]">
        <div v-if="sidebarOpen" class="fixed inset-0 z-40 bg-[#172554]/35 lg:hidden" @click="sidebarOpen=false"/>
    <aside class="fixed inset-y-0 left-0 z-50 flex w-[250px] -translate-x-full flex-col border-r border-[#edf0f5] bg-white px-5 py-7 shadow-xl transition-transform duration-300 lg:translate-x-0 lg:shadow-none" :class="sidebarOpen?'translate-x-0':''">
        <div class="mb-10 flex items-center gap-3 px-2">
            <img src="/src/assets/logobank.png" class="h-8 w-8 rounded-xl"><b class="text-[22px] tracking-[-.8px] text-[#1f2b50]">BankDash.</b>
        <button class="ml-auto lg:hidden" @click="sidebarOpen=false">✕</button>
    </div>
    <nav class="space-y-1">
        <button v-for="item in navItems" :key="item.label" class="group relative flex w-full items-center gap-4 rounded-r-xl px-3 py-[11px] text-left text-[13px] font-medium transition" :class="activePage===item.label?'bg-[#f2f5ff] text-[#2d60e8]':'text-[#8b95a9] hover:bg-[#f7f9fd] hover:text-[#2d60e8]'" :aria-current="activePage===item.label?'page':undefined" @click="navigate(item.label)">
            <span v-if="activePage===item.label" class="absolute -left-5 top-0 h-full w-1 rounded-r-full bg-[#2f62e9]"/>
            <img :src="`/src/assets/${activePage===item.label && item.activeIcon ? item.activeIcon : item.icon}`" :alt="item.label" class="h-5 w-5 object-contain">
            <span>{{item.label}}</span>
        </button>
    </nav>
</aside>
<main class="min-w-0 lg:ml-[250px]">
                <header class="sticky top-0 z-30 border-b border-[#edf0f5] bg-white px-4 py-4 sm:px-7 lg:px-10">
                    <div class="hidden min-h-12 items-center justify-between gap-6 sm:flex">
                        <div class="flex min-w-0 items-center gap-4">
                            <h1 class="truncate text-[20px] font-semibold text-[#343c52]">{{activePage}}</h1>
                        </div>
                        <div class="flex shrink-0 items-center gap-2 sm:gap-4">
                            <div class="flex h-10 w-[250px] items-center rounded-full bg-[#f5f7fb] px-4">
                                <img src="/src/assets/search.png" alt="Search" class="mr-2 h-4 w-4 opacity-60" />
                                <input v-model="search" class="min-w-0 flex-1 bg-transparent text-xs outline-none" placeholder="Search for something" />
                            </div>
                            <button class="grid h-10 w-10 place-items-center rounded-full bg-[#f5f7fb]" aria-label="Open settings" @click="notify('Settings shortcut')">
                                <img src="/src/assets/setting.png" alt="Settings" class="h-4 w-4" />
                            </button>
                            <button class="relative grid h-10 w-10 place-items-center rounded-full bg-[#f5f7fb]" aria-label="Open notifications" @click="notify('You have 3 new notifications')">
                                <img src="/src/assets/notification.png" alt="Notifications" class="h-4 w-4" />
                                <i class="absolute right-2 top-2 h-2 w-2 rounded-full bg-[#ff5d7d]"></i>
                            </button>
                            <img src="/src/assets/image.png" alt="Profile" class="h-10 w-10 rounded-full object-cover" />
                        </div>
                    </div>

                    <div class="flex flex-col gap-3 sm:hidden">
                        <div class="grid grid-cols-[40px_1fr_40px] items-center">
                            <button class="grid h-10 w-10 place-items-center rounded-xl border border-[#e7ebf2] bg-white text-xl text-[#56627c]" aria-label="Open menu" @click="sidebarOpen=true">☰</button>
                            <h1 class="truncate text-center text-[18px] font-semibold text-[#343c52]">{{activePage}}</h1>
                            <img src="/src/assets/image.png" alt="Profile" class="h-10 w-10 rounded-full object-cover" />
                        </div>
                        <div class="flex h-10 w-full items-center rounded-full bg-[#f5f7fb] px-4">
                            <img src="/src/assets/search.png" alt="Search" class="mr-2 h-4 w-4 opacity-60" />
                            <input v-model="search" class="min-w-0 flex-1 bg-transparent text-xs outline-none" placeholder="Search for something" />
                        </div>
                    </div>
                </header>
        <div class="px-4 pb-10 pt-6 sm:px-7 sm:pt-8 lg:px-10"><DashboardPage v-if="activePage==='Dashboard'" @notify="notify" @navigate="pageNavigate"/>
            <TransactionsPage v-else-if="activePage==='Transactions'" @notify="notify"/>
            <AccountsPage v-else-if="activePage==='Accounts'" @notify="notify"/>
            <InvestmentPage v-else-if="activePage==='Investment'" @notify="notify"/>
            <CreditCardsPage v-else-if="activePage==='Credit Cards'" @notify="notify"/>
            <LoansPage v-else-if="activePage==='Loans'" @notify="notify"/>
            <ServicesPage v-else-if="activePage==='Services'" @notify="notify"/>
            <PrivilegesPage v-else-if="activePage==='My Privileges'" @notify="notify"/>
            <SettingsPage v-else @notify="notify"/></div>
            </main>
            <div v-if="toast" class="fixed bottom-5 left-1/2 z-[80] -translate-x-1/2 rounded-xl bg-[#1f2b50] px-5 py-3 text-sm text-white shadow-xl animate-fade-up">{{toast}}</div>
            </div>
            </template>
