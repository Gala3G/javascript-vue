<script setup>
import { ref } from 'vue';
const nombre = ref('');
const nombres = ref([]);
const listado = ref(false)



const guardar = () => {
    if (nombre.value == '') {
        window.alert('Nombre no puede ser vacío');        
    }
    else {
        window.alert('se guarda nombre');
        nombres.value.push(nombre.value);
        nombre.value = '';
    }
}

const listar = () => {
    listado.value = true; 
    if (listado.value==true) {
        console.log('Listar'); 
    }
}

const nolistar = ()=> {
    listado.value = false; 
}

const borrar = () => {
    nombres.value=[]
}
</script>

<template>
    <input class="form-control" v-model="nombre" placeholder="Introduce tu nombre">
    <button @click="guardar" class="btn btn-secondary mt-2 mx-2">Guardar</button>
    <button @click="listar" class="btn btn-warning mt-2 mx-2">Listar</button>
    <button @click="nolistar" class="btn btn-primary mt-2 mx-2">No Listar</button>
    <button @click="borrar" class="btn btn-close mt-2 mx-2"></button>

    <div v-if="listado">
        <ul v-for="item in nombres">
            <li>{{ item }}</li>
        </ul>        
    </div>
</template>


    
<style>
@import url(../assets/boostrap.css);
</style>