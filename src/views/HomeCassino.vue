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
                "data:image/png;base64,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",
                "https://imagensemoldes.com.br/wp-content/uploads/2020/06/Planeta-PNG.png",
                "https://www.pngkey.com/png/full/408-4088488_os-cientistas-acreditam-que-o-astro-mais.png",
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