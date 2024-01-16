<template>
    <div class="header-nav">
        <div>
            <h1>Estelar Biscuit</h1>
        </div>
        
        <v-tabs
        v-model="categoriaAtual"
        color="white"
        align-tabs="left"
        >
        <v-tab class="tab" v-for="tab in tabs" :key="tab.value" :value="tab.value">
            
            <v-icon class="icon">{{tab.icon}}</v-icon>
            {{ tab.label }}
        
        </v-tab>
        </v-tabs>
    </div>
</template>


<style>
    .icon{
        margin-right: 0.3rem;
    }
    .tab{
        display: flex;
        align-items: center;
    }
    .header-nav{
        background-color: indigo;
        color: white;
    }
    
</style>

<script setup>
    import { ref } from 'vue'

    const categoriaAtual = ref('funko')

    const tabs = [
        {value: 'funko', label: 'Funko Pop', icon: 'mdi-account'},
        {value: 'qposket', label: 'Qposket', icon: 'mdi-account'},
        {value: 'canecas', label: 'Canecas Pet', icon: 'mdi-dog'},
        {value: 'about', label: 'Sobre', icon: 'mdi-information-outline'}
    ]

    

</script>
