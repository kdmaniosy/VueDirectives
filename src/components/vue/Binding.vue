<script setup>
import { ref, computed } from 'vue';
const text = ref("hola mundo")
const checked = ref(true)
const items = ["Hola", "mundo", "cruel"]
const message = computed(()=>{
    let message;
    if(checked.value){
        message = 'Apagar'
    }else {
        message = 'Encender'
    }
    return message
    // return checked.value ? 'Apagar' : 'Encender'
})

</script>

<template>
    <ul>
        <li v-for="(text, index) in items" :key="index">
            {{ text }}
        </li>
    </ul>
    <div class="bg-blue-400 inline-block text-wrap text-white rounded py-1 px-2"
    :class="{'bg-orange-400':checked}"
    >
        
        Hola
    </div>
    <input type="checkbox" id="checkbox" v-model="checked" />
	<!-- <label for="checkbox">{{ checked ? 'Apagar' : 'Encender' }}</label> -->
    <label for="checkbox">{{ message }}</label>
    <div>
    <input class="border-gray-300 border-2 " v-model="text">
    

    </div>
    {{ text }}
</template>