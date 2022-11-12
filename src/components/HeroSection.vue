<template>
    <div class="text-white py-8">
         <h3 class="text-center text-3xl md:text-5xl">Ready to get started?</h3>
        <!-- Subtitle -->
        <p class="text-center leading-10 text-sm md:text-lg">Join over 70,000 people writing content with Jasper.</p>
        <!-- Features -->
        <div class="flex justify-center gap-4 md:gap-14 py-14 px-4">
            <div class="flex flex-col items-center text-center gap-2">
                <img src="../assets/pen.svg" alt="">
                <p class="text-sm md:text-base">End Writer's Block Forever</p>
            </div>
            <div class="flex flex-col items-center text-center gap-2">
                <img src="../assets/clock.svg" alt="">
                <p class="text-sm md:text-base">Publish Content 10x Faster</p>
            </div>
            <div class="flex flex-col items-center text-center gap-2">
                <img src="../assets/cursor.svg" alt="">
                <p class="text-sm md:text-base">Boost Sales With Better Copy</p>
            </div>
        </div>
        <p class="text-center">Billing: <span class="font-bold text-pink-500">Save 17%</span> with annual</p>
        
            <!-- ToggleSwitch -->
            <ToggleSwitch 
                :is-toggle="isToggle"
                @toggle="isToggle = !isToggle"
                @monthlyToggle="isToggle = false"
                @yearlyToggle="isToggle = true"
            />
       
       
            <!-- Cards -->
            <container class="flex flex-col md:flex-row justify-center gap-4 px-4 my-12">
                <!-- Card number 1 -->
                <HeroCard 
                    :prices="prices.Starter"
                    :words="words.Monthly"
                    :is-toggle="isToggle"
                >
                    <template #title>Starter</template>
                    <template #subtitle>For the hobbyist just getting started</template>
                    <template #info>Access 50+ AI copy generators to write short-form content like ads, product descriptions, and improve existing copy.</template>       
                    <template #starting-price>20k</template>       
                    <template #ending-price>320k</template>     
                </HeroCard>
                <!-- Card number 2 -->
                <HeroCard 
                    :prices="prices.Boss"
                    :words="words.Yearly"
                    :is-toggle="isToggle"
                >
                    <template #title>Boss Mode</template>
                    <template #subtitle>For bloggers & content marketer</template>
                    <template #info>Access 50+ AI copy generators to write short-form content like ads, product descriptions, and improve existing copy.</template>       
                    <template #starting-price>50k</template>       
                    <template #ending-price>700k</template>     
                </HeroCard>
            </container>

        </div>
</template>

<script>
import HeroCard from './HeroCard.vue'
import ToggleSwitch from './ToggleSwitch.vue'
    export default {
        components: {
                HeroCard,
                ToggleSwitch
        },
        data() {
            return {
                isToggle: false,
                inputValue: 0,
                prices: {
                    Starter: {
                            monthly: [29, 49, 79, 99, 149, 199, 299, 399, "Custom Pricing"],
                            yearly: [49, 82, 232, 500, 600, 700, 800, 900, "Custom Pricing"],                    
                    },

                    Boss : {                        
                            monthly: [24, 40, 65, 82, 124, 165, 249, 332, "Custom Pricing"],                                            
                            yearly: [59, 99, 162, 173, 200, 254, 300, 400, "Custom Pricing"],
                    }
                },
                    words : {                   
                            Monthly: ['20,000','35,000', '65,000', '75,000', '115,000', '150,000', '240,000', '320,000', '320,000+' ],            
                            Yearly: ['30,000','45,000', '75,000', '90,000', '140,000', '165,000', '190,000', '400,000', '500,000+' ],           
                    },
            }
        },
    }
</script>
