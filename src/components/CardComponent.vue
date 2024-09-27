<script setup>
    const props = defineProps(['name', 'time', 'rating', 'text', 'user_img']);

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
                        <img v-for="star in Math.floor(rating)" :key="star" src="../assets/star.svg" alt="" class="star">
                        <img v-for="star in 5 - Math.floor(rating)" :key="star + 5" src="../assets/star_w.svg" alt="" class="star">
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
            <button class="like_btn">LIKE</button>
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

    .star {
        width:25px;
        height: 25px;
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
        gap: 5px;
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
