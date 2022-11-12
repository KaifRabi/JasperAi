<template>
    <div>
        <div class="flex items-center justify-center gap-6 py-4">

                <div 
                    class="cursor-pointer text-sm"
                    @click="monthlyClicked()"
                >
                    Monthly
                </div>

                <!-- switch -->
                <div class="w-10 rounded-xl h-4 bg-gray-900 flex cursor-pointer
                    transition-all duration-300 ease-in-out
                "
                    :style="{ paddingLeft: (isToggle ? '24px' : '0px'), backgroundColor: (isToggle ? '#3E67F6' : '#1F2937') }"
                    @click="toggleMenu()"
                >
                    <div class="h-4 w-4 bg-white rounded-full scale-[1.1]"></div>
                </div>

                <div 
                    class="cursor-pointer"
                    @click="yearlyClicked()"
                    >Annually
                </div>
            </div>

    </div>
</template>

<script>
    export default {
        props: ['isToggle'],
        
        methods: {
            toggleMenu() {               
                this.$emit('toggle', this.isToggle)
            },
            monthlyClicked() {
                this.$emit('monthlyToggle', this.isToggle);

            },
            yearlyClicked() {
                this.$emit('yearlyToggle', this.isToggle);
            }
        },
    }
</script>
