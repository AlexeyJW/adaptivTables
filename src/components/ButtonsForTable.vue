<template>
    <section :class="getSectionCl">
        <h5 :class="$style.title">Body:</h5>
        <p :class="getWillBeButtonCl">{{bodyTypes}}</p>
    </section>
    <section :class="getSectionCl">
        <h5 :class="$style.title">Price:</h5>
        <p :class="getWillBeButtonCl">{{priceTypes}}</p>
    </section>
</template>

<script setup>
import {computed, useCssModule} from 'vue'
import flex from '../css/flex.module.css'
import gaps from '../css/gaps.module.css'
import { isMqPortrait } from '../store-variables/media-queries';

import { headTitles, priceTypeNames } from '../stort-constant/table-data';
const bodyTypes=Object.keys(headTitles)
const priceTypes=Object.values(priceTypeNames)

const getSectionCl=computed(()=>[
    isMqPortrait.value ? flex.fb100 :flex.fg1,
    flex.flex, flex.aiCenter, gaps.pt, gaps.pb, gaps.pl2, gaps.pr2
])

const styleModule= useCssModule()
const getWillBeButtonCl=computed(()=>isMqPortrait.value 
    ? styleModule.testDesktop: styleModule.testPortrait)
</script>

<style module>
.title {
    composes: pr from '../css/gaps.module.css';
    composes: mormal from '../css/text.module.css';
    composes: grey from '../css/colors.module.css';

}
.test {
    composes: fg1 from '../css/flex.module.css';
    text-align: center;
}
.test-desktop {composes: test; border: 1px solid red;}
.test-portrait {composes: test; border: 1px solid blue;}
</style>