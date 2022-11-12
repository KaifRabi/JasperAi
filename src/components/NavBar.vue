<template>
    <div>
        <!-- Nav Desktop -->
        <nav class="flex py-6 px-8 text-white">
             <!-- Logo -->
             <img src="../assets/logo.svg" alt="logo" class="w-28 md:w-40" >
             <!-- nav items -->
                <ul class="hidden lg:flex items-center">
                    <li class="px-4 flex items-center gap-2"><a href="">Features</a><img src="../assets/drop-down.svg" alt=""></li>
                    <li class="px-4 flex items-center gap-2"><a href="">Company</a><img src="../assets/drop-down.svg" alt=""></li>
                    <li class="px-4 flex items-center gap-2"><a href="">Support</a><img src="../assets/drop-down.svg" alt=""></li>
                    <li class="px-4"><a href="">Pricing</a></li>
                    <li class="px-4"><a href="">Business</a></li>
                </ul>
                <!-- Button -->
                <div class="ml-auto flex items-center">
                    <!-- Ham menu -->
                    <img src="../assets/menu.svg" alt="menu" class="lg:hidden mx-4" @click="toggleMenu">
                    <a href="" class="hidden lg:block py-3 px-6">Login</a>
                    <a href="" class="text-sm md:text-base font-bold bg-gradient-to-b from-[#6174F9] to-[#3E67F6] rounded-sm py-1 px-4 md:py-3 md:px-6 transition-all duration-300 ease-in-out
                                    hover:drop-shadow-[0_0_15px_rgb(100,121,249)]  hover:from-[#ED6BD3] hover:to-[#F9A8D4]"
                    >Try Free</a>
                </div>
            <!-- </div> -->
        </nav>
        <!-- Nav Mobile -->
        <nav v-if="isToggle">
            <ul class="text-black font-bold w-100 ">
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Login</li>
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Request a demo</li>
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Pricing</li>
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Features</li>
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Languages</li>
                <li class="border border-1 border-white text-center py-2 px-4 bg-white">Reviews</li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {     
        data() {
            return {
                isToggle: false,
            }
        },
        methods: {
            toggleMenu() {
                this.isToggle = !this.isToggle
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>