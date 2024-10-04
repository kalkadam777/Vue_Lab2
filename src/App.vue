<script setup>
import { computed, ref } from 'vue';
import Menu from './components/MenuComponent.vue';
import CardComponent from './components/CardComponent.vue';


  const isOpen = ref(false)

  const toggleMenu = () => {
    isOpen.value = !isOpen.value
  }

  const cardsData = [
    {
      id:1,
      PersonName: 'Mark Twen',
      PubDate: 'Today, 12:00',
      Rating: 4,
      Topic: 'adventure',
      Commentary: 'This is awesome adventure that I had! Thanks!',
      Avatar: 'https://s3-alpha-sig.figma.com/img/d2bd/bd4c/d1592cda471f4ef986c6cb5ca671ef8b?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=DkDiVX6r4cZlvvDpNXl9nLEP3tkGnE3PMejiZcGR7QFTlvqEro6PjCY5trN85XK-Na85ZOR-z-9OHqEg28ExDvmmuwqyyPxmrXza5DP4SghSZ0EHlLtFedChqK3dDy-5pz6YnzrC65pgE78uRtSoxsuUYJgCXTW1e~ajY9VHSiftrf9ILJX-9zyAooF1Pr4pObCiIV~Z5af9fEvlHog0Y4NCgarFLekxN1R~ceYvt0p51vVn~YXnWEaxnG8jqygxrIIGN4u7Z~hyXitG15Bq0WMpykXRObvzmjDtj6WrDwdpoZgFiwzZulh75~ws8q2D6rPP0ugf-WQK-lI0RLqu7w__'
    },
    {
      id:2,
      PersonName: 'Katherine Johns',
      PubDate: '5 days ago, 12:15',
      Rating: 4,
      Topic: 'nature',
      Commentary: 'The place is very big. I lost the exit.',
      Avatar: 'https://s3-alpha-sig.figma.com/img/88c8/0576/ea05896c023dc82988b6ded10b86a034?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=MHIDxAsHUNr3Dm5lG8dQwUikRw7dowvP7SAN1yMYYGyxhGLbg4OhDz4V3mixEg04V4DEmBOrTy4ihka-Mo0O5LurC9D9X69UldN-1Dpee5kxxwf~8sHjyVXB6cJBfNwmTpJyvrTshPs66jAmxG~SaLsC48YPoqFWeaWIXNSVAhVuFrvNPDlG4q7P3UQUPdAdMUDrf~JsWvU8LjVrF3imoyg~x6WBhzY-OR8mvVAIvT0Ubgbt9nRZxzUUAL8OCVYYNw0tcMqAniD0GKHTgl5~DVaSSjqtvpZnbmgP4BGKIxSEXo5~dd2-6a7WzhL2o6WXKF1YNvMUvkwSnU~PBLUwPA__'
    },
    {
      id:3,
      PersonName: 'Sally Robinson',
      PubDate: 'Yesterday, 18:30',
      Rating: 4,
      Topic: 'modern',
      Commentary: 'Something new for me. Drive and emotions only',
      Avatar: 'https://s3-alpha-sig.figma.com/img/9490/73fb/0f39c6138406aaab01e478d549b01db5?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=gDNgZbvne-BG7F3P53I5HurUViPpbg9stSh9sxv3eW3awHEVWZSgTljvkwIbLa4undHGh6c3Iz42mI~TKTQPN5k3tPhdKcoGj0fKHT9ksa0Rk88UA6NlEdbgtS2DRfnyZVW~gwlh-JqenO01pf-KRWUaJ0y9TvNCYseBac0Qm1zM5lpiADGsqLnhLmjZAUiEtEGv8QO-o5tTMZ2fWkBOTBWRgLIiWJM7LPIZnhQ~sOdZKSvcCQ~6r0NS6OdSEjipm-GssGCVDfF5GGd1kAWgwKWi0QMD9LUkXz0ViP1TrsxH6Di6t5kku7x6nQA2mKy-jEQFo5IDJl5x70NGkJ-HBw__'
    },
    {
      id:4,
      PersonName: 'Stevie',
      PubDate: '2 days ago, 09:05',
      Rating: 4,
      Topic: 'fashion',
      Commentary: 'Something to be upgraded.',
      Avatar: 'https://s3-alpha-sig.figma.com/img/c6f7/8462/feb57eaf0052b5b858b9c7943e94c40e?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=WHsaxQzjD6TNrnOIZ5UseVG64qimF7~hOAApbsWiDhghPRv89IeVgkUrGPvFKypTTrtI10iDT8S9AAJbAuj2vvNThs1iT31iYWM2yyZgn~GoC8UIWx5Zg0F5t7fNBPwhXngH8zSz5wUlUlLnzm33Ivs4lgy3DRt1kQEuSGVGb9HKFBjhBP5eFSDXxnitmcUnedv9mvaWMFvUk-eACgNTQBbn-gX0K9DR~59WnJi1IZYkQ56stppZA9fTn5MEraxDsxVm4KjwTP4JTDpuzPFsen8Aru3a22~iT0o731kqn-cfp7SVm3ROSZiiEG6PMrHvbZwEsXJV1Lhl6WUoYLEQqg__'
    },
    {
      id:5,
      PersonName: 'Jeff Stud',
      PubDate: 'Today, 12:00',
      Rating: 3,
      Topic: 'adventure',
      Commentary: 'This is awesome adventure that I had! Thanks!',
      Avatar: 'https://s3-alpha-sig.figma.com/img/dbd1/f326/dbaff3bf2eccee99c86f19befa9da2d2?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=YZ5K2WRmmgOT9YON853OjwS34DWSmsHWKlr-dxuUJxLF~yibzcJ5i4LTnf2aoxQcOeIOqPr7rCk-Txuvjw2Kq9GNjJnpl~sgZxz9QDBDdtzRAOWWy1Izu1rp8R8dBEW-bo~~YugjCY2A5t6-3-O1QCmEVBYxYg5rTpTz2AdudRPm3sNOeb5qpb5A86D75FX5aHRkl7zZPYvV5cvfR5aINAaV2D-2jNWrR2LNs4UsOLLSjCpn5EuZFmc8pwoeUs1pZRJEFykCY2PSVaBXYrbZn~w~qo6NAUPmktOc~hDTDawkAHWsEzEdVFK3gV8sMymTExD-284QQAzPYnV-nP8z5w__'
    },
    {
      id:6,
      PersonName: 'Milla Loren ',
      PubDate: '1 days ago, 12:10',
      Rating: 2,
      Topic: 'adventure',
      Commentary: 'The place is very big. I lost the exit.',
      Avatar: 'https://s3-alpha-sig.figma.com/img/3a6b/e814/73c95cdf26040c22e1ba016e3ef134ba?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=XJ7qrghlYb-vlJqDCGCakJuZGs-9U4uHAth2rupfYvCNGizi4pF9NK7-AEKk7wvOq9rmRreXS99uW2i-25Pm30c71oKBpx29Dyw3qMKiVcWmEL3cHQW4CUEMhrcl5zR1vzPu9wRzOjXdK1a1J7a17NWnvm4CzNriwCxuWPlgsS8tw2SybjIojrtDV9CJ7LwA-JzbSGH4z7HsdHAp6YbDZa~oj33n49JP9JqJuwUfcLV6i7HJN7NCKxQH46RC3FtSfCkdYXNDtuwdpdRMpeypgkJmJUwPvQ~c2WP7IVjAQ-YgJzNvQTmPjqQUHmk3qQav8HIgxU78aPRnlL072RBvNA__'
    },
    {
      id:7,
      PersonName: 'Sally Robinson',
      PubDate: 'Yesterday, 18:30',
      Rating: 3,
      Topic: 'nature',
      Commentary: 'Something new for me. Drive and emotions only',
      Avatar: 'https://s3-alpha-sig.figma.com/img/9490/73fb/0f39c6138406aaab01e478d549b01db5?Expires=1728259200&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=gDNgZbvne-BG7F3P53I5HurUViPpbg9stSh9sxv3eW3awHEVWZSgTljvkwIbLa4undHGh6c3Iz42mI~TKTQPN5k3tPhdKcoGj0fKHT9ksa0Rk88UA6NlEdbgtS2DRfnyZVW~gwlh-JqenO01pf-KRWUaJ0y9TvNCYseBac0Qm1zM5lpiADGsqLnhLmjZAUiEtEGv8QO-o5tTMZ2fWkBOTBWRgLIiWJM7LPIZnhQ~sOdZKSvcCQ~6r0NS6OdSEjipm-GssGCVDfF5GGd1kAWgwKWi0QMD9LUkXz0ViP1TrsxH6Di6t5kku7x6nQA2mKy-jEQFo5IDJl5x70NGkJ-HBw__'
    },
    {
      id: 8,
      PersonName: 'Charlotte Lewis',
      PubDate: '4 weeks ago, 15:30',
      Rating: 4,
      Topic: 'adventure',
      Commentary: 'Wonderful trip with beautiful scenery.',
      Avatar: 'https://static.vecteezy.com/system/resources/previews/009/397/835/non_2x/man-avatar-clipart-illustration-free-png.png'
    },
    {
      id: 9,
      PersonName: 'John Smith',
      PubDate: '1 hours ago, 08:00',
      Rating: 5,
      Topic: 'modern',
      Commentary: 'Incredible experience! Would love to go again.',
      Avatar: 'https://static.vecteezy.com/system/resources/previews/009/398/577/non_2x/man-avatar-clipart-illustration-free-png.png'
    },
    {
      id: 10,
      PersonName: 'Emily Davis',
      PubDate: '3 hours ago, 10:30',
      Rating: 4,
      Topic: 'modern',
      Commentary: 'Beautiful location, but it was a bit crowded.',
      Avatar: 'https://www.pngitem.com/pimgs/m/22-224298_avatar-people-icon-transparent-background-hd-png-download.png'
    },
    {
      id: 11,
      PersonName: 'Michael Brown',
      PubDate: 'Yesterday, 18:45',
      Rating: 5,
      Topic: 'nature',
      Commentary: 'A must-see! Everything was perfect.',
      Avatar: 'https://icons.veryicon.com/png/o/miscellaneous/user-avatar/user-avatar-male-5.png'
    },
    {
      id: 12,
      PersonName: 'Sophia Johnson',
      PubDate: '2 days ago, 14:15',
      Rating: 3,
      Topic: 'adventure',
      Commentary: 'It was okay, but I expected more from the trip.',
      Avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-PNG-Photo.png'
    },
    {
      id: 13,
      PersonName: 'Daniel Miller',
      PubDate: '1 weeks ago, 17:30',
      Rating: 4,
      Topic: 'fashion',
      Commentary: 'Great overall, but the guide could’ve been better.',
      Avatar: 'https://png.pngtree.com/png-vector/20230831/ourmid/pngtree-man-avatar-image-for-profile-png-image_9197908.png'
    },
    {
      id: 14,
      PersonName: 'Emma Wilson',
      PubDate: '3 weeks ago, 11:00',
      Rating: 2,
      Topic: 'adventure',
      Commentary: 'The weather ruined the experience, but the views were nice.',
      Avatar: 'https://static.vecteezy.com/system/resources/previews/011/459/674/original/people-avatar-icon-png.png'
    },
    {
      id: 15,
      PersonName: 'Stevie',
      PubDate: '2 days ago, 09:05',
      Rating: 1,
      Topic: 'modern',
      Commentary: 'Something to be upgraded.',
      Avatar: 'https://www.pngitem.com/pimgs/m/22-224065_avatar-people-icon-png-transparent-png.png'
    },
    {
      id: 16,
      PersonName: 'Olivia Garcia',
      PubDate: '1 months ago, 16:20',
      Rating: 4,
      Topic: 'adventure',
      Commentary: 'Hands down, the best trip I’ve ever been on!',
      Avatar: 'https://png.pngtree.com/png-vector/20220817/ourmid/pngtree-women-cartoon-avatar-in-flat-style-png-image_6110776.png'
    },
    {
      id: 17,
      PersonName: 'Lucas Martinez',
      PubDate: '4 days ago, 12:30',
      Rating: 4,
      Topic: 'adventure',
      Commentary: 'Very good trip, but the food could’ve been better.',
      Avatar: 'https://png.pngtree.com/png-vector/20230831/ourmid/pngtree-man-avatar-image-for-profile-png-image_9197909.png'
    },
    {
      id: 18,
      PersonName: 'Ava Thompson',
      PubDate: '5 days ago, 09:00',
      Rating: 5,
      Topic: 'fashion',
      Commentary: 'The landscapes were out of this world!',
      Avatar: 'https://png.pngtree.com/png-vector/20211027/ourmid/pngtree-avatar-a-man-with-jacket-png-image_4003791.png'
    },
    {
      id: 19,
      PersonName: 'James White',
      PubDate: '6 days ago, 10:15',
      Rating: 3,
      Topic: 'modern',
      Commentary: 'An average experience. Could’ve been better.',
      Avatar: 'https://cdn-icons-png.flaticon.com/512/5556/5556520.png'
    },
    {
      id: 20,
      PersonName: 'Isabella Harris',
      PubDate: '2 weeks ago, 13:45',
      Rating: 5,
      Topic: 'modern',
      Commentary: 'Simply fantastic! Highly recommended.',
      Avatar: 'https://icons.veryicon.com/png/o/miscellaneous/user-avatar/user-avatar-male-5.png'
    },
  ];

  function parseDate(dateStr) {
  const now = new Date();

  // Разбор времени "Today"
  if (dateStr.startsWith("Today")) {
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    now.setHours(hours);
    now.setMinutes(minutes);
    return now;
  }

  // Разбор времени "Yesterday"
  if (dateStr.startsWith("Yesterday")) {
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    const yesterday = new Date(now);
    yesterday.setDate(now.getDate() - 1);
    yesterday.setHours(hours);
    yesterday.setMinutes(minutes);
    return yesterday;
  }

  // Разбор времени "hours ago"
  if (dateStr.includes("hours ago")) {
    const hoursAgo = parseInt(dateStr.split(" ")[0], 10);
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    const date = new Date();
    date.setHours(now.getHours() - hoursAgo);
    date.setMinutes(minutes);
    return date;
  }

  // Разбор времени "days ago"
  if (dateStr.includes("days ago")) {
    const daysAgo = parseInt(dateStr.split(" ")[0], 10);
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    const date = new Date();
    date.setDate(now.getDate() - daysAgo);
    date.setHours(hours);
    date.setMinutes(minutes);
    return date;
  }

  // Разбор времени "weeks ago"
  if (dateStr.includes("weeks ago")) {
    const weeksAgo = parseInt(dateStr.split(" ")[0], 10);
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    const date = new Date();
    date.setDate(now.getDate() - weeksAgo * 7);
    date.setHours(hours);
    date.setMinutes(minutes);
    return date;
  }

  // Разбор времени "months ago"
  if (dateStr.includes("months ago")) {
    const monthsAgo = parseInt(dateStr.split(" ")[0], 10);
    const timePart = dateStr.split(", ")[1];
    const [hours, minutes] = timePart.split(":").map(Number);
    const date = new Date();
    date.setMonth(now.getMonth() - monthsAgo);
    date.setHours(hours);
    date.setMinutes(minutes);
    return date;
  }

  // Если формат не поддерживается, вернем null
  return null;
  }




  const pageNumber = ref(0);
  const selectedSort = ref('rating')
  const currentTopic = ref('All Topics')

  const props = defineProps({
    size: {
      type: Number,
      default: 4
    }
  });

  const nextPage = () => {
      pageNumber.value = (pageNumber.value + 1)%pageCount.value;
  }

  const prevPage = ()=>{
    if (pageNumber.value > 0) {
      pageNumber.value--;
    }
  }

  const filteredData = ref(cardsData)

  const filterByTopic = (topic) => {
    currentTopic.value = topic === 'all' ? 'All Topics' : topic.charAt(0).toUpperCase() + topic.slice(1)
    pageNumber.value = 0
    if(topic == 'all') {
      filteredData.value = [...cardsData]
    }
    else{
      filteredData.value = cardsData.filter(card => card.Topic === topic)
    }
    console.log('filteredData:', filteredData.value);
  }

  const sortedCardsData = computed(() => {
    return [...filteredData.value].sort((a, b) => {
    if (selectedSort.value === 'rating') {
      return b.Rating - a.Rating; 
    } else if (selectedSort.value === 'date') {
      const dateA = parseDate(a.PubDate);
      const dateB = parseDate(b.PubDate);
      return dateB - dateA; 
    }
    return 0;
    });
  })

  const pageCount = computed(() => {
    console.log('pageCount:', Math.ceil(filteredData.value.length / props.size));
    return Math.ceil(filteredData.value.length / props.size)
  })

  const paginatedData = computed(() => {
    const start = pageNumber.value * props.size
    const end = start + props.size;
    return sortedCardsData.value.slice(start, end);
  })

  const currentPage = computed(() => {
    return pageNumber.value + 1
  })




</script>

<template>

  <div class="container" >
    <header >
      <img src="./assets/pg.png" alt="" class="img_set" @click="toggleMenu">
        <div class="mid_div">
          <p class="main_text">New trips on Fall season! Full details on our Instagram accounts.</p>
        </div>
        <div class="img_container">
          <img src="./assets/user.png" alt="" class="img_user">
          <img src="./assets/ellipse2.svg" alt="" class="img_ell">
        </div>
    </header>
    <div class="trapezoid">
      <img src="./assets/figure.svg" alt="svg" class="my_svg">
      <div class="date_div"><p class="date_text">13.09.2024</p></div>
      <div class="logo_text">{{ currentTopic }}</div>
      <div class="rating">
        <div class="filter_box">
          <select v-model="selectedSort" @change="sortCards">
                <option value="rating">Rating</option>
                <option value="date">Date</option>
          </select>
        </div>
      </div>
      <div class="arrow">
        <img src="./assets/arrow_right.svg" alt="" class="arrow_svg" @click="nextPage">
      </div>
      <div class="score">{{currentPage}}/{{ pageCount }}</div>
    </div>
    
  </div>
  <div class="cards_container">
      <CardComponent
        v-for="(card, index) in paginatedData" 
        :key="index"
        :name="card.PersonName"
        :time="card.PubDate"
        :rating="card.Rating"
        :user_img="card.Avatar"
        :text="card.Commentary"
        class="card_overlay"

       />
  </div>
  
  <Menu v-if="isOpen" class="menu_overlay" @filter="filterByTopic" @toggle="toggleMenu"/>
</template>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Inknut+Antiqua:wght@300;400;500;600;700;800;900&family=Jersey+15&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Italianno&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
  
  .container {
      background-image: url('./assets/bg2.png');
      background-size: cover; 
      background-position: center; 
      background-repeat: no-repeat;
      height: 100vh;
      position: relative;
  }

  option {
      font-size: 36px;
      color: #1DE390;
      background: #EDFCF7;
      font-family: "Jersey 15";

  }
  select {
      cursor: pointer;
      font-size: 36px;
      font-family: "Jersey 15";
      color: #1DE390;
      height: 1em;
      width: 5em;
      padding-left: 35px;
      border-style: none;
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none;
      background: url(./assets/try.svg) 4em 7px no-repeat,
      url(./assets/filter.png) 0px 5px no-repeat;
      background-size: 20px; /* Размер иконки */
      transition: background 0.3s ease;
  }
  select:focus {
      outline:none;
  }

  select:focus::after {
  content: '';
  position: absolute;
  background: url(./assets/filter.png) 10px center no-repeat;
  background-size: 20px;
  transform: rotate(180deg); /* Переворачиваем только иконку filter.png */
  transition: transform 0.3s ease;
  }

  .rating {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    position: absolute;
    top: 200px;
    left: 740px;
  }

  .filter_box {
    color: #1DE390;
    font-family: "Jersey 15";
    font-size: 46px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    background: #EEFCF7;
    padding: 3px 10px 3px 10px;
  }

  .trapezoid {
    width: 100%;
    height: 840px;
    /* border: 5px solid black; */
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    position: relative;
  }

  .cards_container {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 80px;
    position: absolute;
    top: 400px;
    left: 280px;
    z-index: 1;
  }
  .score {
    color: #FFF;
    font-family: Italianno;
    font-size: 64px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    position: absolute;
    top: 200px;
    right: 380px;
  }

  .arrow {
    position: absolute;
    top: 120px;
    right: 320px;
  }

  .arrow_svg {
    width: 130px;
    height: 100px;
  }

  .logo_text {
    color: #FFF;
    font-family: "Jersey 15";
    font-size: 64px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    border-radius: 8px;
    background: #5BB9CD;
    padding: 0 85px 0 19px;
    z-index: 2;
    position: absolute;
    top: 190px;
    left: 240px;
  }

  .date_text {
    color: rgba(255, 255, 255, 0.90);
    font-family: "Merriweather";
    font-size: 36px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    border-radius: 10px;
    text-align: center;

  }

  .date_div {
    padding: 0 19px 0 19px;
    border-radius: 8px;
    background: #5BB9CD;
    z-index:2 ;
    position: absolute;
    left: 240px;
    top: 90px;
  }

  .my_svg {
    position: absolute; /* Чтобы зафиксировать SVG внизу страницы */
    /* bottom: 0;
    left: 55px; */
    width: 100%; 
    height: 830px; 
    opacity: 70%; 
    z-index: 0;
    
  }

  header {
    height: 80px;
    background: rgba(255, 255, 255, 0.74);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-left: 5px;
    padding-right: 5px;
    padding-top: 4px;
    padding-bottom: 4px;
    gap: 15px;
  }

  .img_container {
    display: flex;
    justify-content: center; 
    align-items: center;    
    position: relative;
    width: 80px;  
    height: 77px;
  }

  .img_ell {
      width: 100%;
      height: 100%;
  }

  .img_user {
      position: absolute;
      width: 55px;
      height: 55px;
      top: 50%;    
      left: 50%;     
      transform: translate(-50%, -50%); 
}

  .mid_div {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 85vw;
    height: 70px;
    border-radius: 10px;
    background: linear-gradient(90deg, #E5F67C 0%, #ECEF64 33%, #D2E037 66%, #EAEE3A 100%);
  }
  .main_text {
    font-family: "Inknut Antiqua";
    font-size: 23px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    background: linear-gradient(90deg, #FFADAD 0%, #FF774C 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .img_set {
    width: 80px;
    height: 80px;
  }

  .menu_overlay {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 2;
  }

</style>
