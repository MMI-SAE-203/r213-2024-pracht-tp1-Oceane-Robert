<script setup lang="ts">
import { ref } from 'vue'
const sectionsData = [
    {
      label: 'bouton 1',
      texte: `texte panneau 1 Lorem ipsum dolor sit ame
      consectetur adipisicing elit. Inventore animi dolore,
      rerum magni laudantium quod excepturi laboriosam, 
      ex modi debitis harum reprehenderit eaque quam ut
      ea molestiae. Id, cum dolor!`
    },
    {
      label: 'bouton 2',
      texte: `texte panneau 2 Amet alias provident quos quis, 
      Officia ut ab dolores quos dolorem accusamus ad,
      consectetur unde minima, ipsum eligendi inventore id
      labore, laborum rerum laboriosam corrupti iste.
      Distinctio, perspiciatis!`
    },
    {
      label: 'bouton 3',
      texte: `texte panneau 3 Repudiandae corporis voluptates, 
      odit reprehenderit sint pariatur at voluptatum, cumque
      quia sit eligendi ex culpa eos, alias magnam molestiae
      id modi accusantium ipsa eveniet accusamus. Tempora 
      quis corporis et nam.`
    }
  ]
  const openSection = ref(null)
</script>

<template>
      <section v-for="({ label, texte }, key) of sectionsData" :v-key="key">
    <button @pointerdown= " openSection = openSection === key ? null : key">
        <pre class="font-mono bg-slate-500"> {{ label }}</pre>
    </button>
    <p v-show="openSection === key">
    <pre class="font-mono">key : {{ key }}</pre>
    <pre class="font-mono">{{ texte }}</pre>
    </p>    
  </section>
</template>