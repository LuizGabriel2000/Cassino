<template>
  <v-row>
    <v-col cols="12" md="4">
        <div class="card">
            <img width="100px" :src="niquels[roleta1]" alt="">
        </div> 
    </v-col>

    <v-col cols="12" md="4">
        <div  class="card">
            <img width="100px" :src="niquels[roleta2]" alt="">
        </div> 
    </v-col>

    <v-col cols="12" md="4">
        <div class="card">
            <img width="100px" :src="niquels[roleta3]" alt="">
        </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
    props: {
        niquels: Array,
        roleta1: Number,
        roleta2: Number,
        roleta3: Number
    },
    data() {
        return {
           
        }
    }
}
</script>

<style>
.card {
    background-color: rgba(209, 171, 235, 0.473);
    border: none;
    border-radius: 30px;
    box-shadow: 0px 2px 0px 0px rgb(0 0 0 / 20%);
    padding: inherit;
    height: 120px;
    text-align: center;
}

</style>