<script>
import * as Cesium from "cesium";
import { Viewer } from "cesium";
import "cesium/Source/Widgets/widgets.css";

const viewer = new Viewer("app");
viewer.scene.debugShowFramesPerSecond = true;
viewer.dataSources.add(
  Cesium.KmlDataSource.load("KML_Samples.kml", {
    camera: viewer.scene.camera,
    canvas: viewer.scene.canvas,
    screenOverlayContainer: viewer.container,
  })
);
viewer.entities.add({
  position: Cesium.Cartesian3.fromDegrees(-75.59777, 40.03883),
  point: {
    pixelSize: 10,
    color: Cesium.Color.YELLOW,
  },
});
// const viewer = new Cesium.Viewer("cesiumContainer", {
//   imageryProvider: Cesium.createWorldImagery({
//     style: Cesium.IonWorldImageryStyle.AERIAL_WITH_LABELS,
//   }),
//   baseLayerPicker: false,
// });
// const layers = viewer.scene.imageryLayers;
// const blackMarble = layers.addImageryProvider(
//   new Cesium.IonImageryProvider({ assetId: 3812 })
// );

// blackMarble.alpha = 0.5; // 0.0 is transparent.  1.0 is opaque.
// layers.addImageryProvider(
//   new Cesium.SingleTileImageryProvider({
//     url: "../images/Cesium_Logo_overlay.png",
//     rectangle: Cesium.Rectangle.fromDegrees(-75.0, 28.0, -67.0, 29.75),
//   })
// );

// viewer.addToolbarMenu(
//   [
//     {
//       text: "KML - Global Science Facilities",
//       onselect: function () {
//         viewer.camera.flyHome(0);
//         viewer.dataSources.add(
//           Cesium.KmlDataSource.load(
//             "/Users/animesh/cesium_test/ballon_test/src/SampleData/demo.kml",
//             options
//           )
//         );
//       },
//     },
//   ],
//   "toolbar"
// );

// viewer.reset = function () {
//   viewer.dataSources.removeAll();
//   viewer.clock.clockRange = Cesium.ClockRange.UNBOUNDED;
//   viewer.clock.clockStep = Cesium.ClockStep.SYSTEM_CLOCK;
// };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#cesium-container {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>
