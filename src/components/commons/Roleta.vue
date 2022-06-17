<template>
  <v-row>
     <v-col cols="4">
                <div  class="d-flex card" width="80%" outlined height="130px">
                    <div class="ma-auto">
                        <img class="pa-10" width="100px" :src="niquels[roleta1]" alt="">
                    </div>
                </div> 
            </v-col>

            <v-col cols="4">
                <div  width="80%" class="d-flex pa-3 card" outlined height="130px">
                    <div class="ma-auto">
                        <img width="100px" :src="niquels[roleta2]" alt="">
                    </div>
                </div> 
            </v-col>

            <v-col cols="4">
                <div width="80%" class="d-flex pa-3 card" outlined height="130px">
                    <div class="ma-auto">
                        <img width="100px" :src="niquels[roleta3]" alt="">
                    </div>
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
    height: 130px;
    border-radius: 6px;
    padding: 4px 20px;
    font-family: none;
    font-weight: 600;
    box-shadow: 0px 2px 0px 0px rgb(0 0 0 / 20%);
    margin: 15px 10px;
}

</style>