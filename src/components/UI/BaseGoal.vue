<template>
  <div>
    <base-card @click="goToStage2" :class="active" class="plus"
      ><add-icon class="plus-icon"></add-icon
    ></base-card>
    <base-card class="body">
      <div @click="goToStage2" v-show="stage === 1">
        <div class="boost-div">
          <label class="boost-label">BOOST</label>
        </div>
        <br />
        <div class="liking-div">
          <label class="liking-label">LIKING</label>
          <label class="liking-score">100</label>
        </div>
      </div>
      <div v-show="stage === 2">
        <div @click="createBoost" class="create-boost-div">
          <label class="create-boost-label">CREATE BOOST</label>
        </div>
        <br />
        <hr />

        <div class="date-period-div">
          <label class="date-label">Date Period</label>
          <br />
          <div class="date-range-div">
            <label class="date-range-label">Pick Date Range:</label>
          </div>
          <div class="date-range-div">
            <input v-model="start" type="date" name="start" id="startDate" />
            <label class="to-label">TO</label>
            <input v-model="end" type="date" name="end" id="endDate" />
          </div>
        </div>
      </div>
    </base-card>
  </div>
</template>

<script>
import BaseCard from "./BaseCard.vue";
import AddIcon from "../Icon/AddIcon.vue";
export default {
  components: { BaseCard, AddIcon },
  data() {
    return {
      stage: 1,
    start:new Date(Date.now()).toISOString().split("T")[0],end:new Date(Date.now()).toISOString().split("T")[0]
    };
  },
  computed: {
    active() {
      if (this.stage === 2) {
        return "active";
      } else return "";
    },
  },
  methods: {
    goToStage2() {
      if (this.stage === 1) {
        this.stage = 2;
      } else if (this.stage === 2) {
        this.stage = 1;
      } else console.log("some bug in goToStage2 !");
    },
    createBoost(){
      console.log(this.start,this.end)
      
    }
  },
};
</script>

<style scoped>
input[type="date"] {
  margin: 0.5rem;
  padding: 0.2rem;
  border: none;
  border-bottom: solid 1px #707070;
  font-size: 0.85rem;
}
.to-label {
  margin: auto;
  color: #3c3c3c80;
}

input[type="date"]::-webkit-inner-spin-button,
input[type="date"]::-webkit-calendar-picker-indicator {
  display: none;
  -webkit-appearance: none;
}

.date-label {
  font-size: .75rem;
  position: relative;
  bottom: 1.3rem;
  background-color: #fff;
  padding: 0 0.5rem;
  color: #3c3c3c80;
}
.plus{
       -webkit-transition: all .3s ease-in;
   -moz-transition: all .3s ease-in;
   -o-transition: all .3s ease-in;
   -ms-transition: all .3s ease-in;
   transition: all .3s ease-in;
}
.plus:hover {
  top: 1rem;
     -webkit-transition: all .3s ease-out;
   -moz-transition: all .3s ease-out;
   -o-transition: all .3s ease-out;
   -ms-transition: all .3s ease-out;
   transition: all .3s ease-out;
}
.plus.active {
  background: #4f5bd5;
  fill: #fff;
  top: 1rem;
  
}
.plus {
  fill: #4f5bd5;
}
.boost-div {
  margin: 0.5rem;
  border-radius: 0.8rem;
  border: 1px solid #ccd0de;
  padding: 0.4rem 0.8rem;
  color: #ccd0de;
  width: fit-content;
  font-size: 11px;
}
.create-boost-div {
  margin: 0.5rem auto 1rem auto;
  border-radius: 1rem;
  border: none;
  padding: 0.4rem 0.8rem;
  color: #4f5bd5;
  background: #4f5bd51f;
  width: fit-content;
  font-size: 12px;
}
.liking-div {
  margin-top: 0.5rem;
  display: flex;
  justify-content: space-between;
  color: #3c3c3c;
}
.liking-score {
  font-size: 2.1rem;
  font-weight: bold;
}
.liking-label {
  margin: auto 0;
}
hr {
  border-style: dashed;
  color: #3c3c3c80;
}
.date-range-div {
  margin: 1rem;
  display: flex;
  justify-content: center;
  justify-items: center;
  color: #3C3C3C;
  font-size: .75rem;
}
.body{
  width: 320px;
}
</style>
