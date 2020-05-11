<template>
  <div class="rating">
      <ul class="list">
          <li v-for="star in maxStars"
          :key="star.stars"
          @click="rating(star)"
          :class="{ 'active' : star <= stars}"
          class="star">
          <i :class="star <= stars ? 'fas fa-star' : 'far fa-star'"></i>
          </li>
      </ul>

      <div v-if="hasCounter" 
      class="info counter">
        <span class="score-rating">{{ stars }}</span>
        <span class="divider">/</span>
        <span class="score-max">{{ maxStars }}</span>
      </div>
  </div>
</template>

<script>
export default {
    name : 'Rating',
    props : {
        'rate':{
            type : Number,
            default : 0
        },
        'maxStars':{
            type : Number,
            default : 5
        },
        'hasCounter':{
            type : Boolean,
            default : false
        }
    },
    data : function () {
        return {
            stars : this.rate
        }
    },
    methods : {
        rating(star){
            if (typeof star == "number" && star <= this.maxStars && star >= 0){
                this.stars = this.stars === star ? star - 1 : star
            }
        }
    }

}
</script>

<style>
.rating{
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 50px;
    color: #b7b7b7;
    background: #fff;
    border-radius: 8px;
    box-shadow: 0 6px 33px rgba(19, 18, 18, 0.09);
}
.list{
    display: flex;
    flex-direction: row;
    list-style: none;
    padding: 0;
    margin: auto;
}
.star {
    font-size: 42px;
    transition: all .2s ease-in-out; 
    cursor: pointer; 
}
li.active, .star:hover{
    color: darkgoldenrod;
}

.info{
    margin-top: 15px;
    font-size: 40px;
    text-align: center;
}
.divider{
    margin: 0 5px;
    font-size: 30px;
}
.score-max{
    font-size: 30px;
    vertical-align: sub;
}
</style>