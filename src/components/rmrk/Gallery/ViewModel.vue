<template>
  <div class="view-model__wrapper">
    <model-viewer
      class="view-model__component"
      :src="src"
      :ios-src="iosSrc"
      camera-controls
      shadow-intensity="1"
      ar
      ar-modes="scene-viewer webxr quick-look"
    >
      <div class="progress-bar hide" slot="progress-bar">
        <div class="update-bar"></div>
      </div>
      <button class="button is-dark" slot="ar-button" id="ar-button">
        AR
      </button>
    </model-viewer>
  </div>
</template>

<script lang="ts" >
import { Component, Prop, Vue } from 'vue-property-decorator';
import '@google/model-viewer';



const testSrc = 'http://localhost:8000/Astronaut.glb';
const testIosSrc = 'http://localhost:8000/Astronaut.usdz';

@Component({})
export default class ViewModel extends Vue {
  @Prop({ default: testSrc }) public src!: string;
  @Prop({ default: testIosSrc }) public iosSrc!: string;

  // get src() {
  //   return 'https://kristina-simakova.github.io/ar-webview/assets/RocketShip_1393.gltf';  // }

  get poster() {
    return '';
  }
}
</script>

<style scoped>
.view-model__wrapper {
  height: 100%;
  width: 100%;
}

.view-model__component {
  height: 100%;
  width: 100%;
  min-width: 300px;
  min-height: 300px;
}
</style>
