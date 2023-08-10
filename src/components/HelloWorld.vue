<script setup>
import { onMounted, ref } from 'vue'
import * as Cesium from 'cesium'
onMounted(() => {
  const viewer = new Cesium.Viewer('cesium-container', {
    baseLayer: Cesium.ImageryLayer.fromProviderAsync(
      Cesium.TileMapServiceImageryProvider.fromUrl(
        Cesium.buildModuleUrl("Assets/Textures/NaturalEarthII")
      )
    ),
    baseLayerPicker: false,
    geocoder: false,
  })
})
// defineProps({
//   msg: String,
// })

// const count = ref(0)
</script>

<template>
  <div id="cesium-container"></div>
</template>

<style scoped>
#cesium-container {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
</style>
