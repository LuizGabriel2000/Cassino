<template>
    <div class="img-fundo">
        <v-container class="">
            <v-row class="">
                <v-col class="" cols="11">
                    <h1 style="color:blueviolet">Cassino Luiz Vegas {{new Date().getFullYear()}}</h1>  
                </v-col>

                <v-col class="" cols="1">
                    <h2 class="">{{new Date().getHours()}}:{{new Date().getMinutes()}}</h2>  
                </v-col>

                <v-col class="" cols="12">
                    <RoletaVue :niquels="niquels" :roleta1="roleta1" :roleta2="roleta2" :roleta3="roleta3"/>
                    <RoletaVue :niquels="niquels" :roleta1="roleta4" :roleta2="roleta5" :roleta3="roleta6"/>
                    <RoletaVue :niquels="niquels" :roleta1="roleta7" :roleta2="roleta8" :roleta3="roleta9"/>
                </v-col>


                <v-col class="" cols="12">
                    <v-btn :disabled="btnOff"  color="#4c0977" width="100%" @click="RodarSorte()"> <p  style="color:beige"> Jogar</p></v-btn>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import RoletaVue from '../components/commons/Roleta.vue'
export default {

    components: {
        RoletaVue },

    data() {
        return {
            niquels: [
                "https://i.pinimg.com/originals/b4/ea/ee/b4eaeee790720d6eb151d1e864043dee.png",
                "https://imagensemoldes.com.br/wp-content/uploads/2020/06/Planeta-PNG.png",
                "https://cdn-0.imagensemoldes.com.br/wp-content/uploads/2020/05/Lua-PNG.png",
                "https://cdn.pixabay.com/photo/2018/01/26/13/04/sun-3108640_960_720.png"
            ],
            roleta1: 0,
            roleta2: 0,
            roleta3: 0,
            roleta4: 0,
            roleta5: 0,
            roleta6: 0,
            roleta7: 0,
            roleta8: 0,
            roleta9: 0,

            btnOff: false,

            
            tempoRoleta: 2500,
            tempoImagem: 50,
            
        }
    },
    methods: {
         RodarSorte() {
           
           this.btnOff = true

            this.roleta4 = 1
            this.roleta7 = 2

            let rodar1 = setInterval(() => {
                this.roleta1++
                this.roleta4++
                this.roleta7++
                if (this.roleta1 > 3)
                    this.roleta1 = 1
                if (this.roleta4 > 3)
                    this.roleta4 = 1
                if (this.roleta7 > 3)
                    this.roleta7 = 1   

            },this.tempoImagem)
                
            setTimeout(() => {
                clearInterval(rodar1)
            }, this.tempoRoleta)

            this.roleta5 = 3
            this.roleta8 = 1

            let rodar2 = setInterval(() => {
                this.roleta2++
                this.roleta5++
                this.roleta8++
                if (this.roleta2 > 3)
                    this.roleta2 = 1
                if (this.roleta5 > 3)
                    this.roleta5 = 1    
                if (this.roleta8 > 3)
                    this.roleta8 = 1   



            },this.tempoImagem)

            
            setTimeout(() => {
                clearInterval(rodar2)
            }, this.tempoRoleta + 1000)

            this.roleta6 = 2
            this.roleta9 = 3

            let rodar3 = setInterval(() => {
                this.roleta3++
                this.roleta6++
                this.roleta9++
                if (this.roleta3 > 3)
                    this.roleta3 = 1
                if (this.roleta6 > 3)
                    this.roleta6 = 1
                if (this.roleta9 > 3)
                    this.roleta9 = 1   
            },this.tempoImagem)

            
            setTimeout(() => {
                clearInterval(rodar3)
                this.btnOff = false
                if (this.tempoRoleta < 1500)
                    this.tempoRoleta += 100
                else
                    this.tempoRoleta -= 500
            }, this.tempoRoleta + 2000)

        },
    }
    
}
</script>

<style>
.img-fundo {
    background-image: url('https://i.pinimg.com/originals/3c/55/14/3c5514ec51d377145201b361b35b05a5.jpg');
    background-position: center;
    background-size: cover;
    height: 100%;

}

.btn {
    padding: 10px;
}

</style>