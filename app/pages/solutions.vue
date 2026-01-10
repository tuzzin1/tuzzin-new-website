<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryCollection('content').first())
if (!page.value) {
  throw createError({ statusCode: 404, statusMessage: 'Page not found', fatal: true })
}

useSeoMeta({
  title: page.value.seo?.title || page.value.title,
  ogTitle: page.value.seo?.title || page.value.title,
  description: page.value.seo?.description || page.value.description,
  ogDescription: page.value.seo?.description || page.value.description
})
</script>

<template>
    <div
    v-if="page"
    class="relative">
        <!-- <div class="hidden lg:block"> -->
            <!-- <UColorModeImage
                light="/images/light/line-1.svg"
                dark="/images/dark/line-1.svg"
                class="absolute pointer-events-none pb-14 left-0 top-0 object-cover h-[650px]"
            /> -->
        <!-- </div> -->
        
        <!-- <UPageHero :ui="{ container: 'md:pt-1 lg:pt-1' }">
            <h1 class="text-5xl sm:text-6xl text-pretty tracking-tight font-bold text-highlighted text-center" style="margin-bottom: -5%;"><span class="text-primary">Banking</span> Solutions</h1>
            <div class="text-lg sm:text-xl/8 text-muted text-pretty -mt-2" style="margin-left: 5%;">
                
            </div>
        </UPageHero> -->
        
        <!-- <USeparator :ui="{ border: 'border-(--ui-primary)/30' }" /> -->

        <UPageSection
        class="relative overflow-hidden"
        >
        
        <div class="@max-[1280px]:hidden">
          <UColorModeImage
            light="/images/light/line-3.svg"
            dark="/images/dark/line-3.svg"
            class="absolute -top-10 sm:top-0 right-1/2 h-24" 
            />
        </div>
        
        <div class="w-full max-w-(--ui-container) mx-auto">
            <div>
                <h2 class="text-3xl sm:text-4xl lg:text-5xl text-pretty tracking-tight font-bold text-highlighted text-center" style="margin-top: -5%;">
                    <div class="">
                        <p class="my-5 leading-7 text-pretty"><span class="text-primary">Banking</span> Solutions</p>
                    </div>
                </h2>
                <div class="relative">
                    <ul class="grid sm:grid-cols-1 lg:grid-cols-3 gap-8 mt-16 items-center">
                        <div data-orientation="vertical" class="relative flex rounded-lg ring ring-default group mx-auto" style="">
                            <div class="relative flex flex-col flex-1 lg:grid gap-x-8 gap-y-4 p-4 sm:p-6">
                                <div data-slot="wrapper" class="flex flex-col flex-1 mx-auto items-center">
                                    <div data-slot="body" class="flex-1">
                                        <NuxtLink to='/solutions-yokyc'>
                                            <img alt="YoKYC" class="dark:block size-auto mx-auto" src="/images/sm_yoKYC.png">
                                        </NuxtLink>
                                    </div>
                                    <div data-slot="footer" class="pt-4 mt-auto">
                                        <div data-orientation="horizontal" data-slot="root" class="relative group/user flex items-center gap-2.5">
                                            <div data-slot="wrapper" class="mx-auto items-center">
                                                <p data-slot="name" class="text-center text-lg font-semibold text-primary">
                                                   YoKYC 
                                                </p>
                                                <p data-slot="description" class="text-sm text-muted text-center font-semibold mt-4">
                                                  Automated CKYC Solution.  
                                                </p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div data-orientation="vertical" class="relative flex rounded-lg ring ring-default group mx-auto" style="">
                            <div class="relative flex flex-col flex-1 lg:grid gap-x-8 gap-y-4 p-4 sm:p-6">
                                <div data-slot="wrapper" class="flex flex-col flex-1 mx-auto items-center">
                                    <div data-slot="body" class="flex-1">
                                        <NuxtLink to="/solutions-yoinstaloans">
                                            <img alt="YoInstaLoans" class="dark:block size-auto mx-auto" src="/images/sm_yoinstaloan.png">
                                        </NuxtLink>
                                    </div>
                                    <div data-slot="footer" class="pt-4 mt-auto">
                                        <div data-orientation="horizontal" data-slot="root" class="relative group/user flex items-center gap-2.5">
                                            <div data-slot="wrapper" class="mx-auto items-center">
                                                <p data-slot="name" class="text-center text-lg font-semibold text-primary">
                                                   YoInstaLoans 
                                                </p>
                                                <p data-slot="description" class="text-sm text-muted text-center font-semibold mt-4">
                                                  Loan Origination System.  
                                                </p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div data-orientation="vertical" class="relative flex rounded-lg ring ring-default group mx-auto" style="">
                            <div class="relative flex flex-col flex-1 lg:grid gap-x-8 gap-y-4 p-4 sm:p-6">
                                <div data-slot="wrapper" class="flex flex-col flex-1 mx-auto items-center">
                                    <div data-slot="body" class="flex-1">
                                        <NuxtLink to="/solutions-yorecovery">
                                            <img alt="YoRecovery" class="dark:block size-auto mx-auto" src="/images/smRecovery.png">
                                        </NuxtLink>
                                    </div>
                                    <div data-slot="footer" class="pt-4 mt-auto">
                                        <div data-orientation="horizontal" data-slot="root" class="relative group/user flex items-center gap-2.5">
                                            <div data-slot="wrapper" class="mx-auto items-center">
                                                <p data-slot="name" class="text-center text-lg font-semibold text-primary">
                                                   YoRecovery
                                                </p>
                                                <p data-slot="description" class="text-sm text-muted text-center font-semibold mt-4">
                                                  NPA Recovery Tracking System.  
                                                </p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div data-orientation="vertical" class="relative flex rounded-lg ring ring-default group mx-auto" style="">
                            <div class="relative flex flex-col flex-1 lg:grid gap-x-8 gap-y-4 p-4 sm:p-6">
                                <div data-slot="wrapper" class="flex flex-col flex-1 mx-auto items-center">
                                    <div data-slot="body" class="flex-1">
                                        <NuxtLink to="/solutions-yocts">
                                            <img alt="YoCTS" class="dark:block size-auto mx-auto" src="/images/sm_yoCTS.png">
                                        </NuxtLink>
                                    </div>
                                    <div data-slot="footer" class="pt-4 mt-auto">
                                        <div data-orientation="horizontal" data-slot="root" class="relative group/user flex items-center gap-2.5">
                                            <div data-slot="wrapper" class="mx-auto items-center">
                                                <p data-slot="name" class="text-center text-lg font-semibold text-primary">
                                                   YoCTS 
                                                </p>
                                                <p data-slot="description" class="text-sm text-muted text-center font-semibold mt-4">
                                                  CTS Merge & Inward Clearing.  
                                                </p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div data-orientation="vertical" class="relative flex rounded-lg ring ring-default group mx-auto" style="">
                            <div class="relative flex flex-col flex-1 lg:grid gap-x-8 gap-y-4 p-4 sm:p-6">
                                <div data-slot="wrapper" class="flex flex-col flex-1 mx-auto items-center">
                                    <div data-slot="body" class="flex-1">
                                        <NuxtLink to="/solutions-yoleads">
                                            <img alt="YoLead" class="dark:block size-auto mx-auto" src="/images/sm_Yolm.png">
                                        </NuxtLink>
                                    </div>
                                    <div data-slot="footer" class="pt-4 mt-auto">
                                        <div data-orientation="horizontal" data-slot="root" class="relative group/user flex items-center gap-2.5">
                                            <div data-slot="wrapper" class="mx-auto items-center">
                                                <p data-slot="name" class="text-center text-lg font-semibold text-primary">
                                                   YoLead 
                                                </p>
                                                <p data-slot="description" class="text-sm text-muted text-center font-semibold mt-4">
                                                  Track every lead across Branches <br/>and respond to every lead within<br/> 24 hours flat.  
                                                </p>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </ul>
                </div>
            </div>
        </div>

        <div class="absolute rounded-full dark:bg-primary blur-[250px] size-40 sm:size-50 transform -translate-x-1/2 left-1/2 -translate-y-80" />
      
        <LazyStarsBg />
        </UPageSection>
        <USeparator :ui="{ border: 'border-primary/20' }" />
    </div>
</template>