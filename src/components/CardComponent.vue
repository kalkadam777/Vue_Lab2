<script setup>
     import { ref, watch } from 'vue';
    const props = defineProps({
        name: String,
        time: String,
        rating: {
            type: Number,
            default: 0,  
        },
        text: String,
        user_img: String,
    });
    
    const currentRating = ref(props.rating); 
    const addStar = () => {
        if (currentRating.value < 5) {
            currentRating.value += 0.1;  
        }
        emit('like'); 
        
    };

    watch(() => props.rating, (newRating) => {
        currentRating.value = Number(newRating) || 0;
        });

    console.log(currentRating.value)

    const emit = defineEmits(['like']); 
</script>

<template>
    <div class="card_container">
        <div class="top">
            <div class="top_cont">
                <div class="name_and_date">
                    <p class="name">{{ name }}</p>
                    <p class="date">{{ time }}</p>
                </div>
                <div class="rating_stars">
                    <p>Rating</p>
                    <div class="stars">
                        <span 
                            v-for="index in 5" 
                            :key="index" 
                            :class="{
                                star: true, 
                                on: index <= Math.floor(currentRating), 
                                half: index === Math.ceil(currentRating) && currentRating % 1 >= 0.5
                            }"></span>
                    </div>
                </div>
                <div>
                    <img :src="user_img" alt="" class="user_img">
                </div>
            </div>
            <div class="bottom_cont">
                <p class="mini_texts">{{ text }}</p>
            </div>
        </div>
        <div>
            <button class="like_btn" @click="addStar">LIKE</button>
        </div>
    </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&family=Jersey+15&display=swap');
    .card_container {
        border-radius: 10px;
        background: #5BB9CD;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        padding: 5px 5px 10px 10px;
        width: 500px;
    }

    .top {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
    }


    .user_img {
        width: 100px;
        height: 112px;
    }

    .top_cont {
        display: flex;
        flex-direction: row;
        justify-content: center; 
        align-items: center;
        gap: 15px;
    }
    
    .name_and_date {
        display: flex;
        flex-direction: column;
        gap: 15px;
        color: #FFF;
        font-family: "Jersey 15";
        font-size: 30px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        border-radius: 10px;
        background: rgba(255, 255, 245, 0.15);
        padding: 5px;
        }

    .rating_stars {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 10px;
        color: #FFF;
        font-family: "Jersey 15";
        font-size: 30px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
        margin-left: 20px;
    }

    .stars {
        display: flex;
        flex-direction: row;
        position: relative;
    }

    .star {
        font-size: x-large;
        width: 25px;
        display: inline-block;
        color: gray;
        position: relative;
    }

    .star:before {
        content: '\2605';
    }

    .star.on {
        color: gold;
    }

    .star.half:after {
        content: '\2605';
        color: gold;
        position: absolute;
        left: 0;
        width: 45%;
        overflow: hidden;
    }

    .bottom_cont {
        display: flex;
        flex-direction: column;
        gap: 5px;
        justify-content: center;
        align-items: flex-end;
    
    }
    .mini_texts {
        color: #FFF;
        font-family: "Jersey 15";
        font-size: 27px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
    }

    .like_btn {
        border-radius: 8px;
        background: #43EF27; 
        color: #FFF;
        font-family: "Jersey 15";
        font-size: 25px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;   
        width: 62px;
        height: 29px;
        border: none;
    }


</style>
