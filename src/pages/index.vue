<script setup lang="ts">
import { ref } from 'vue'
const sectionOpen = ref(1)
</script>
<template>
    <section>
        <div>
            <button class="text-xl" @pointerdown="sectionOpen = 1">bouton 1</button>
            <p v-show="sectionOpen === 1">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Alias rem ullam commodi iste error obcaecati blanditiis maiores laudantium nemo eum beatae cupiditate facilis odio, aspernatur at ipsa temporibus delectus hic.</p>
        </div>
        <div>   
            <button class="text-xl" @pointerdown="sectionOpen = 2">bouton 2</button>
            <p v-show="sectionOpen === 2">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ducimus commodi, necessitatibus magni laborum numquam corporis officia laboriosam explicabo et adipisci delectus ea reprehenderit, harum quasi nesciunt cupiditate, dolor repellat deleniti.</p>
        </div>
        <div>
            <button class="text-xl" @pointerdown="sectionOpen = 3">bouton 3</button>
            <p v-show="sectionOpen === 3">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Mollitia culpa quasi praesentium voluptate illo quos magnam esse explicabo, commodi tempora, blanditiis ex soluta, dolorum sit architecto? Repellendus quaerat aspernatur reprehenderit.</p>
        </div>
  </section>
</template>
