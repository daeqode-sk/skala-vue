<script setup>
import SampleOne from './components/practices/basic/SampleOne.vue'
import SampleTwo from './components/practices/basic/SampleTwo.vue'
import VueHtml from './components/practices/basic/VueHtml.vue'
import VueHtmlXss from './components/practices/basic/VueHtmlXss.vue'
import VueText from './components/practices/basic/VueText.vue'
import VueBind from './components/practices/basic/VueBind.vue'
import VueBindClass from './components/practices/basic/VueBindClass.vue'
import VueBindStyle from './components/practices/basic/VueBindStyle.vue'
import VueBindShorthand from './components/practices/basic/VueBindShorthand.vue'
import VueIf from './components/practices/basic/VueIf.vue'
import VueShow from './components/practices/basic/VueShow.vue'
import VueFor from './components/practices/basic/VueFor.vue'
import VuePre from './components/practices/basic/VuePre.vue'
import VueCloak from './components/practices/basic/VueCloak.vue'
import VueOnce from './components/practices/basic/VueOnce.vue'
import VueMemo from './components/practices/basic/VueMemo.vue'
import EventBasic from './components/practices/basic/EventBasic.vue'
import EventObject from './components/practices/basic/EventObject.vue'
import EventModifier from './components/practices/basic/EventModifier.vue'
import ModelBasic from './components/practices/basic/ModelBasic.vue'
import ModelModifier from './components/practices/basic/ModelModifier.vue'
import StyleScoped from './components/practices/basic/StyleScoped.vue'
import ReactiveRef from './components/practices/composition/ReactiveRef.vue'
import ReactiveReactive from './components/practices/composition/ReactiveReactive.vue'
import Computed from './components/practices/composition/Computed.vue'
import WatchBasic from './components/practices/composition/WatchBasic.vue'
import WatchMulti from './components/practices/composition/WatchMulti.vue'
import WatchDeep from './components/practices/composition/WatchDeep.vue'
import WatchReactive from './components/practices/composition/WatchReactive.vue'
import WatchEffect from './components/practices/composition/WatchEffect.vue'
import WeatherMockup from './components/exercise/WeatherMockup.vue'
import SlotDefaultParent from '@/components/practices/component/SlotDefaultParent.vue'
import SlotNamedParent from '@/components/practices/component/SlotNamedParent.vue'
import SlotScopedParent from '@/components/practices/component/SlotScopedParent.vue'
import PropsEmitsParent from '@/components/practices/component/PropsEmitsParent.vue'
import StoreCounter from '@/components/practices/library/StoreCounter.vue'
</script>

<style>
@import '@/assets/practice.css';
</style>

<template>
  <div class="practice-container">
    <SampleOne />
    <hr />
    <SampleTwo />
    <hr />
    <VueHtml />
    <hr />
    <VueHtmlXss />
    <hr />
    <VueText />
    <hr />
    <VueBind />
    <hr />
    <VueBindClass />
    <hr />
    <VueBindStyle />
    <hr />
    <VueBindShorthand />
    <hr />
    <VueIf />
    <hr />
    <VueShow />
    <hr />
    <VueFor />
    <hr />
    <VuePre />
    <hr />
    <VueCloak />
    <hr />
    <VueOnce />
    <hr />
    <VueMemo />
    <hr />
    <EventBasic />
    <hr />
    <EventObject />
    <hr />
    <EventModifier />
    <hr />
    <ModelBasic />
    <hr />
    <ModelModifier />
    <hr />
    <StyleScoped />
    <hr />
    <ReactiveRef />
    <hr />
    <ReactiveReactive />
    <hr />
    <Computed />
    <hr />
    <WatchBasic />
    <hr />
    <WatchMulti />
    <hr />
    <WatchDeep />
    <hr />
    <WatchReactive />
    <hr />
    <WatchEffect />
    <hr />
    <WeatherMockup />
    <hr />
    <SlotDefaultParent />
    <hr />
    <SlotNamedParent />
    <hr />
    <SlotScopedParent />
    <hr />
    <PropsEmitsParent />
    <hr />
    <StoreCounter />
  </div>
</template>
