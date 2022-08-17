<script setup>

import {setMq} from './store-variables/media-queries';
import ButtonsForTable from './components/ButtonsForTable.vue';

setMq()

</script>

<template>
 
  <ButtonsForTable/>
</template>

<style>
@import './css/reset.css';
@import './css/font-family.css';
@import './css/media-queries.css';
#app {padding: 1em 0;}
#app, body {
  min-height: 100%;
  width: 100%;}
:root{
  --gap:0.5em;
  --gap-twice: 1em;
}
.pt {padding-top: var(--gap);}
.pr2{padding-right: var(--gap-twice);}

.flex, #app{display: flex;}
.wrap, #app{flex-wrap: wrap;}
.ac-start, #app{align-content: flex-start;}
</style>
