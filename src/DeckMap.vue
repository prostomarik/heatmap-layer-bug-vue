<template>
  <div style="position: absolute; top: 10px; left: 10px; z-index: 10">
    <button @click="showHeatmap = !showHeatmap">showHeatmap</button>
    <button @click="showIcons = !showIcons">showIcons</button>
  </div>
</template>

<script>
import { Deck } from '@deck.gl/core'
import { GeoJsonLayer, IconLayer } from "@deck.gl/layers"
import { HeatmapLayer } from "@deck.gl/aggregation-layers"
import { _TerrainExtension as TerrainExtension } from "@deck.gl/extensions"

export default {
  name: "DeckMap",
  data() {
    return {
      showHeatmap: false,
      showIcons: false
    }
  },
  computed: {
    layers() {
      const layers = [new GeoJsonLayer({
        id: 'base-map',
        data: 'https://d2ad6b4ur7yvpq.cloudfront.net/naturalearth-3.3.0/ne_50m_admin_0_scale_rank.geojson',
        stroked: true,
        filled: true,
        lineWidthMinPixels: 2,
        opacity: 0.4,
        getLineColor: [60, 60, 60],
        getFillColor: [200, 200, 200]
      })]

      if (this.showHeatmap) {
        layers.push(
          new HeatmapLayer({
            id: 'heatmap-layer',
            data: [
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.259014921,
                      59.944680354,
                      30.259014921,
                      59.944680354
                    ],
                    "coordinates": [
                      30.259014921,
                      59.944680354
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.257678032,
                      59.951157178,
                      30.257678032,
                      59.951157178
                    ],
                    "coordinates": [
                      30.257678032,
                      59.951157178
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.233581066,
                      59.948380235,
                      30.233581066,
                      59.948380235
                    ],
                    "coordinates": [
                      30.233581066,
                      59.948380235
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.299434662,
                      59.952001429,
                      30.299434662,
                      59.952001429
                    ],
                    "coordinates": [
                      30.299434662,
                      59.952001429
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.256101731,
                      59.945896196,
                      30.256101731,
                      59.945896196
                    ],
                    "coordinates": [
                      30.256101731,
                      59.945896196
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.248818756,
                      59.943221284,
                      30.248818756,
                      59.943221284
                    ],
                    "coordinates": [
                      30.248818756,
                      59.943221284
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.287246704,
                      59.940565883,
                      30.287246704,
                      59.940565883
                    ],
                    "coordinates": [
                      30.287246704,
                      59.940565883
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.228487116,
                      59.94495538,
                      30.228487116,
                      59.94495538
                    ],
                    "coordinates": [
                      30.228487116,
                      59.94495538
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.268666808,
                      59.942992066,
                      30.268666808,
                      59.942992066
                    ],
                    "coordinates": [
                      30.268666808,
                      59.942992066
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.268674853,
                      59.943045131,
                      30.268674853,
                      59.943045131
                    ],
                    "coordinates": [
                      30.268674853,
                      59.943045131
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.27084478,
                      59.942335298,
                      30.27084478,
                      59.942335298
                    ],
                    "coordinates": [
                      30.27084478,
                      59.942335298
                    ]
                  },
                  "style": {
                    "weight": 1
                  }
                }
              ],
            radiusPixels: 30,
            intensity: 1,
            threshold: 0.05,
            getPosition: d => d.geometry.coordinates,
            getWeight: d => d.style.weight
          })
        )
      }

      if (this.showIcons) {
        layers.push(
          new IconLayer({
            id: 'icon-layer',
            data: [
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.289827,
                      59.943323002,
                      30.289827,
                      59.943323002
                    ],
                    "coordinates": [
                      30.289827,
                      59.943323002
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2895789,
                      59.942851202,
                      30.2895789,
                      59.942851202
                    ],
                    "coordinates": [
                      30.2895789,
                      59.942851202
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2797357,
                      59.948249802,
                      30.2797357,
                      59.948249802
                    ],
                    "coordinates": [
                      30.2797357,
                      59.948249802
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2672128,
                      59.944606002,
                      30.2672128,
                      59.944606002
                    ],
                    "coordinates": [
                      30.2672128,
                      59.944606002
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2799855,
                      59.942783902,
                      30.2799855,
                      59.942783902
                    ],
                    "coordinates": [
                      30.2799855,
                      59.942783902
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2820403,
                      59.936933002,
                      30.2820403,
                      59.936933002
                    ],
                    "coordinates": [
                      30.2820403,
                      59.936933002
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2492012,
                      59.949279502,
                      30.2492012,
                      59.949279502
                    ],
                    "coordinates": [
                      30.2492012,
                      59.949279502
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2348468,
                      59.936475402,
                      30.2348468,
                      59.936475402
                    ],
                    "coordinates": [
                      30.2348468,
                      59.936475402
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                },
                {
                  "type": "Feature",
                  "geometry": {
                    "type": "Point",
                    "bbox": [
                      30.2495806,
                      59.952797602,
                      30.2495806,
                      59.952797602
                    ],
                    "coordinates": [
                      30.2495806,
                      59.952797602
                    ]
                  },
                  "iconData": {
                    "url": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAABCCAYAAAAL1LXDAAAFAElEQVRoge2av28rRRDHx3dxiBN+5CGliURHgpD4H2go4B94Sgt06aABagoEQjyJItKTItG/hjYVEgIefUBCJFQpXNkJAhIntm8PnXUXrb+emd31ne2L5ZFWu7nc7c3nvrNze95tUDVWVT8uS8t2MI2j84LztaCH4Ou8dN6i4CVIJ7yPw3gOd80iQxqPqdCaoxpoQzk2K7NBUqi9wX1CFdsIy8H73EMyV7hytQQ+0ZcrPG0YbGvwWv8u08LWrlOAxTYLvRYA61OmhdRMguSgi/MaUqQgsAYbMe1IUbsMvDReDUAaq8brC+gxeBuYC0+EjZjCKV8GlgNFSGNBGes8w1xPkuI2XJw/jCYRvUBEG0S0RUQvEdErRPRqt9v9yhjzdzpny+55eXn5JRE9yn15kYg2cx/Xc5/XLGFsEdSMG8EDuK/7/f6PzWbzrZIKlrLBYPD7+vr620SU5MVA4ZLaCEJSmuApjdqdTuezRcNmlvnQ7XY/zUWImXzCiimN2+LiGEI8TpLkryiKXl4A44QZY/6J4/h1IhpaSicwzsdUthXW4Efl8PDwUV1gM8t9wbGKCo/ZmjL5wCwd3d3dxfZJpb/VpjRwOM7VjPIaw3ns1STNoCJrbNgZu5mm6UWdgBuNxmtZDsvDeiAkscLd1JW0MKzr9i1MTGLFcB5rc8B4IipfN9MmPhMCuQC8EsGCzaWqFzAHV1fgIFF8QrTK+fHCrY5jMtSChlsI8ENQ1+ljqMIPJaRFxZchpClEiGUB9rZlSVretlJ42W0FvOy2AnbYor75NQvyaaWwYnVUtzBv3yRgXKB6aCb676PwQwJ3+uob0tyyZF0syLdV0gLTFp7rYkE+SgvixCxKTyw81+TXAMOAitCcwty+ifuSLWBV7/N0lvsiKcyqHTl2wOC2AtNut7+rC3DuiwEf1V093K/00lJpsb601uv1TjY2Nt6cI9uE3d7e/tFqtd611pSG1rKpyetUW1vStgYZq5Ok1Wq9d3Fx8W2SJP/OGzS7Z3bvzAef9WConRtZuFVEW/EYSgTXjfo5Ozv7aG9v77EGcn5+/mx/f/+J5TiuACZQbEWnWhAvDBXmblqE0QDadukXTr3/4QdPh8PhfxJs9r/sHAuiL/SJ9+WWRqUNaiOL4B/aViF8wgguQQ9++ennq9PT06cS8PNfn3+dnWNfoxRU04aWsvV9za24YfLC/Vkx1Fi40B61r6+vn21ubr5hw97c3Py5tbX12HqouBuHO2YgOXEK28nqvvYJaTZxWeGHKksK9U9OTr7Am+XHxGuYkB4K4aypO6GqpDK310OqcSU+ZlRuXF1dHW1vb7+Tdd7pdL7f2dn5BIYNKoh5BOcG+P5VszQq7DOWtYw5YFQf2modHR19ns2QsnJ8fPwElMTruHesKxuLsJzCeIybmHAL0FwEiPsy2+32x1lHu7u73whvA0lRqZASymPAY9uQHNCuKag6B7ed7vV6vx0cHPwgJCBUUEpK0pxZ/YjQPnik8U2eyk9sWxSWMVFhbGuAGtwErAs4FFyCxu1EEvBUScgXNARYO09TnQPFB8TN6rjhgCASlAqrgYReg+AIF8H/0ElXHrDPRXNCupwvc70U4thGCwUNgtQcrqofDVwy5zu0DKjkaJX9+bTJ85VSGpRzalZ9amPeZ0xWBis5M6t+fUJa+7sSm/UvrdP2PxPYzOb503KowtUbEf0PdRNG3nwLzyEAAAAASUVORK5CYII=",
                    "width": 60,
                    "height": 66,
                    "anchorX": 30,
                    "anchorY": 55,
                    "opacity": 1,
                    "elevation": 0,
                    "meters": false,
                    "ratio": 1
                  }
                }
              ],
            sizeUnits: "pixels",
            extensions: [new TerrainExtension({ terrainDrawMode: "drape" })],
            getIcon: f => f.iconData,
            getSize: f => f.iconData.height,
            getColor: f => [0, 0, 0, f.iconData.opacity * 255],
            getPosition: f => f.geometry.coordinates
          })
        )
      }

      return layers
    }
  },
  watch: {
    layers() {
      this.deck.setProps({ layers: this.layers })
    }
  },
  mounted() {
    this.deck = new Deck({
      initialViewState: {
        "longitude": 30.261676358050217,
        "latitude": 59.94443551896423,
        "zoom": 14,
        "bearing": 0,
        "pitch": 0
      },
      controller: true,
      layers: this.layers
    })
  }
}
</script>