
<template>
    <div class="grid grid-cols-1 md:grid-cols-2 big mt-20 mb-16" >
        <div>
            <p class="font-medium text-4xl pt-60 texte text-left ">"Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias veritatis harum voluptates amet ullam. Molestias quam eligendi est iste a, mollitia delectus ratione qui excepturi."</p>
        </div>
    <!--2 textes différents, ils se trouvent dans le carousel-->
    <div class="slider shadow-2xl rounded-xl">
        <!-- avec transform translateX on fait decaler les images de n pixels, sur X -->
        <div class="container-slides flex" :style="{transform: `translateX(${index}px)`, transition: `${transition}`}">
            <img class="imgSlide w-full h-auto" src="../assets/imgSlider/image-john.jpg" alt="">
            <img class="imgSlide" src="../assets/imgSlider/image-tanya.jpg" alt="">
        </div>
        <div class="glob_btn pb-3 shadow-2xl  pt-3">
        <!-- Previous -->
        <button @click="prev"  type="button" class="btn btn-left pr-10">
            <svg xmlns="http://www.w3.org/2000/svg" width="12" height="18"><path fill="none" stroke="#8585AC" stroke-width="3" d="M11 1L3 9l8 8"/></svg>
        </button>
        
        <!-- Next -->
        <button @click="next" type="button" class="btn btn-left">
            <svg xmlns="http://www.w3.org/2000/svg" width="13" height="18"><path fill="none" stroke="#8585AC" stroke-width="3" d="M2 1l8 8-8 8"/></svg>
        </button>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: 'Slider',
    data() {
        return {
            index: 0,
            transition: "transform 0.2s ease"

        }
    },
    methods: {
        // fais 0-500 a chaque fois et  Reviens a 0 qd on atteint -1500
        next(){
            console.log(this.index);
            if(this.index == -500){
                this.index = 0
            }else{
                this.index=this.index-500
            }
        },
        prev(){
            if (this.index==0) {
                this.index=-500
            } else {
                this.index= this.index + 500

            }
        }
    },
}
</script>

<style scoped>
.slider{
    width: 500px;
    margin: 100px auto 0;
    overflow-x: hidden;
    z-index: 0;
}
.glob_btn{
    position: absolute;
    top: 95%;
    left: 60%;
    background-color: white;
    border-radius: 20px;
    width: 10%;
    z-index: 7 !important;

}
.texte{
    width: 40%;
    position: absolute;
    left: 23%;
    z-index: 10;
}
.big{
    position: relative;

}
</style>