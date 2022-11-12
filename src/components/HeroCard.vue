<template>
    <div>
        <div class="flex flex-col gap-4 bg-white text-black text-center w-full md:w-[400px] px-8 py-6 rounded-xl">
            <slot name="title"><p class="text-lg font-bold"></p></slot>
            <slot name="subtitle"><p></p></slot>
            <hr>
            <slot name="info"><div></div></slot>

            <!-- Pricing -->
            <div class="flex justify-center gap-1 text-xl font-medium">
                <div v-if="inputValue == 0">
                    Starts at
                </div>
                <span v-if="inputValue < 8">$</span>
                <div v-if="!isToggle">{{prices.monthly[inputValue]}}</div><div v-else>{{prices.yearly[inputValue]}}</div>
                <span v-if="inputValue < 8">/mo</span>
                <span v-if="inputValue > 0 && inputValue < 8">estimated</span>
            </div>

            <!-- Range -->
            <div class="flex justify-between w-[100%] font-bold ">
                <div><slot name="starting-price"></slot></div>
                <div><slot name="ending-price"></slot></div>
            </div>
            <input id ="input-range"
                    type="range" min="0" max="8" value="0"  step="1" class="w-[100%] mx-auto" v-model="inputValue"      
            >
            <!-- Words -->
            <div class="font-bold">{{words[inputValue]}}<span class="font-normal"> words/mo</span></div>
            <!-- Button -->
            <a href="" class="text-purple-500 border border-1 border-purple-500 py-4 my-6">Start For Free</a>
            <p class="text-gray-400 -mt-8">5 day free trial with 10k credits</p>
            
            <!-- Lists -->
            <slot name="list"></slot>
            <ul class="text-left">
                <li v-for="(items, index) in list" :key="index" class="py-1">{{items}}</li>
            </ul>
            </div>

    </div>
</template>

<script>
    export default {
        props: {
            prices: {
                type: Object,
            },
            words: {
                type: Array,
            },
            isToggle: {
                type: Boolean,
            },
            list: {
                type: Array,
            },
        },
        data() {
            return {
                inputValue: 0
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>
