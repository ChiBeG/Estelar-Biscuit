<template>
    <div class="header-nav">
        <div class="header">
            <h1>Estelar Biscuit</h1>
        </div>
        
        <v-tabs class="tabs"
        v-model="selectedTab"
        color="black"
        align-tabs="left"
        bg-color="inherit"
        >
        <v-tab class="tab" v-for="tab in tabs" :key="tab.value" :value="tab.value">
            
            <v-icon class="icon">{{tab.icon}}</v-icon>
            {{ tab.label }}
        
        </v-tab>
        </v-tabs>
    </div>

    <v-window v-model="selectedTab">
        <v-window-item v-for = "n in tabs"
            :key = "n"
            :value = "n.value"
        >
            <v-card v-if="n.value == 'about'"
                title="Sobre"
                text="Essa é a seção de sobre"
            ></v-card>
        
            <v-card v-else v-for = "item in items.filter(category = '{{ n.value }}')">
                <v-card-title>{{ item }}</v-card-title>
            </v-card>

        </v-window-item>

    </v-window>

</template>


<style>
    @import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:ital,wght@0,100..700;1,100..700&display=swap');


    h1{
        font-family: "Josefin Sans", sans-serif;
    }
    
    .icon{
        margin-right: 0.3rem;
    }
    .tab{
        display: flex;
        align-items: center;
        font-family: "Josefin Sans", sans-serif;
        color: rgb(63, 63, 63);

    }
    .header-nav{
        background-image: linear-gradient(to right,aqua, rgb(82, 82, 179));
        color: black;
    }
    
</style>

<script setup>
    import { ref } from 'vue'

    let selectedTab = ref('funko')
    
    const tabs = [
        {value: 'funko', label: 'Funko Pop', icon: 'mdi-account'},
        {value: 'qposket', label: 'Qposket', icon: 'mdi-account'},
        {value: 'canecas', label: 'Canecas Pet', icon: 'mdi-dog'},
        {value: 'about', label: 'Sobre', icon: 'mdi-information-outline'}
    ]
    const items = [
        {id: 1, category: 'funko', image: ['src/assets/test1', 'src/assets/test2'], link: 'instagram.com'}
    ]



    

</script>
