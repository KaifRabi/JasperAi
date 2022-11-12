<template>
    <div>
        <div class="flex flex-col gap-4 bg-white text-black text-center w-full md:w-[400px] px-8 py-6 rounded-xl">
            <p class="text-lg font-bold"><slot name="title"></slot></p>
            <p><slot name="subtitle"></slot></p>
            <hr>
            <div><slot name="info"></slot></div>

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
                type: Object,
            },
            isToggle: {
                type: Object,
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