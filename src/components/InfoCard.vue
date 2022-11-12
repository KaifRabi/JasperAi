<template>
    <div class="relative w-[80%] h-[350px] overflow-hidden mx-auto my-4 rounded-3xl
                    bg-gradient-to-r from-purple-500 to-pink-500
        " id="card">
        <div class="absolute top-10 left-0 px-4 md:px-0 md:left-10 text-center md:text-left">
            <img src="../assets/logo.svg" class="w-32 py-2 mx-auto md:mx-0 "/>
            <div class="text-2xl lg:text-3xl font-medium">Imagine if AI could create any art or image <br> in seconds?</div>
            <p class="w-full md:w-[70%] lg:w-full text-xl py-2">Meet the new AI content tool that turns your text prompt into <br> amazing art and realistic images in seconds</p>
            <p class="w-full md:w-[50%] lg:w-full text-xl py-2">Get Jasper Art for just $20/user/mo for <br> unlimited royalty-free image generations.</p>
        </div>
        <div class="hidden md:flex justify-center gap-6 rotate-45 -skew-y-12 ml-[400px]">
            <div class="w-[200px]" id="reel1"><img src="../assets/reels1.png"></div>
            <div class="w-[200px] -mt-64" id="reel2"><img src="../assets/reels2.png"></div>
        </div>
    </div>
</template>
<script>
import {gsap} from 'gsap';
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
    export default {
        mounted() {
            gsap.registerPlugin(ScrollTrigger);
            gsap.from("#reel1", {
                scrollTrigger: {
                    trigger: "#card",
                    start: "top 80%",
                    end: "bottom center",
                    scrub: 1,
                    toggleActions: "restart none none none",
                },
                y: -100,
                ease: "back.out(1.7)"
            });
            gsap.from("#reel2", {
                scrollTrigger: {
                    trigger: "#card",
                    start: "top 80%",
                    end: "bottom center",
                    scrub: 1,
                    toggleActions: "restart none none none",
                },
                y: 300,
                ease: "back.out(1.7)"
            });
        }
    }
</script>