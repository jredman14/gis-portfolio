# Building a Custom Google Map for a Nonprofit
For this assignment, I decided to build a custom map template for [Strong Towns](https://www.strongtowns.org/), "a 501(c)(3) nonprofit media advocacy organization." Strong Towns releases educational videos, materials, and other multumedia, and facilitates commmunity organization to support their mission: 

"We seek to replace America’s post-war pattern of development, the Suburban Experiment, with a pattern of development that is financially strong and resilient. We advocate for cities of all sizes to be safe, livable, and inviting. We work to elevate local government to be the highest level of collaboration for people working together in a place, not merely the lowest level in a hierarchy of governments."

With the organization's focus on localism, I designed the following map template to emphasize cities, towns, and local streets, while de-emphasizing features like interstate highways and other geographic labels. 

## Color Palette
I used the Canva Color Palette Generator to extract the following colors from images taken from the Strong Towns [website](https://www.strongtowns.org/journal/2023/4/14/announcing-this-years-strongest-town-contest-winner) and [Strategic Plan](https://static1.squarespace.com/static/53dd6676e4b0fedfbc26ea91/t/627aae62e24d6669f6496002/1652207205056/Strong+Towns+Strategic+Plan+%28WEB%29.pdf):

<img width="294" alt="Screenshot 2024-03-24 053644" src="https://github.com/jredman14/gis-portfolio/assets/156849712/e47047f3-2b3c-4229-bba1-b21291f6626e">
<img width="438" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/ccaffd51-3376-4917-a785-a513ca4eb7bb">

<img width="353" alt="Screenshot 2024-03-24 055400" src="https://github.com/jredman14/gis-portfolio/assets/156849712/a453a5c0-a350-4019-81c8-e8177d0366b0">
<img width="439" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/5644b3f1-3786-46c9-be83-b140da62df4c">

| Feature | Element | Color |
|---------|---------|-------|
| Land area | Geometry | #3ca4eb (Picton Blue) |
| Province | Label | #3ca4eb (Picton Blue) |
| Province | Label outline | #262f38 (Ebony Clay) |
| Locality | Label | #efc68a (Tacao) |
| Locality | Label outline | #42444b (Mako) |
| Points of interest | Label text | #3ca4eb (Picton Blue) |
| Points of interest | Label outline | #262f38 (Ebony Clay) |
| Roads | Geometry | #efc68a (Tacao) |
| Roads | Stroke | #262f38 (Ebony Clay) |
| Roads | Label text | #3ca4eb (Picton Blue) |
| Roads | Label outline | #262f38 (Ebony Clay) |
| Controlled-access highways | Geometry | #367ab6 (Boston Blue) |
| Transit lines | Fill | #262f38 (Ebony Clay) |
| Transit stations | Geometry | #efc68a (Tacao) |
| Transit stations | Label text | #efc68a (Tacao) |
| Transit stations | Label outline | #262f38 (Ebony Clay) |
| Water | Geometry | #262f38 (Ebony Clay) |

<img width="960" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/c4605112-495c-4a0d-b833-ecbd76441bf4">
<img width="960" alt="Screenshot 2024-03-24 232026" src="https://github.com/jredman14/gis-portfolio/assets/156849712/5f2bd182-5b52-4cf4-a7a0-3aba35baead5">
<img width="960" alt="Screenshot 2024-03-24 232055" src="https://github.com/jredman14/gis-portfolio/assets/156849712/9113b4f9-6783-4183-abb1-1aa2fb951a06">


        [
          {
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#3ca4eb"
              }
            ]
          },
          {
            "elementType": "labels.text.fill",
            "stylers": [
              {
                "color": "#8ec3b9"
              }
            ]
          },
          {
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#1a3646"
              }
            ]
          },
          {
            "featureType": "administrative.country",
            "elementType": "geometry.stroke",
            "stylers": [
              {
                "color": "#4b6878"
              }
            ]
          },
          {
            "featureType": "administrative.land_parcel",
            "elementType": "labels.text.fill",
            "stylers": [
              {
                "color": "#64779e"
              }
            ]
          },
          {
            "featureType": "administrative.locality",
            "elementType": "labels",
            "stylers": [
              {
                "color": "#efc68a"
              }
            ]
          },
          {
            "featureType": "administrative.locality",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#42444b"
              }
            ]
          },
          {
            "featureType": "administrative.province",
            "elementType": "geometry.stroke",
            "stylers": [
              {
                "color": "#4b6878"
              }
            ]
          },
          {
            "featureType": "administrative.province",
            "elementType": "labels",
            "stylers": [
              {
                "color": "#3ca4eb"
              }
            ]
          },
          {
            "featureType": "administrative.province",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "poi",
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#283d6a"
              }
            ]
          },
          {
            "featureType": "poi",
            "elementType": "labels.text",
            "stylers": [
              {
                "color": "#efc68a"
              }
            ]
          },
          {
            "featureType": "poi",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "poi.park",
            "elementType": "geometry.fill",
            "stylers": [
              {
                "color": "#023e58"
              }
            ]
          },
          {
            "featureType": "road",
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#efc68a"
              }
            ]
          },
          {
            "featureType": "road",
            "elementType": "geometry.stroke",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "road",
            "elementType": "labels.text.fill",
            "stylers": [
              {
                "color": "#3ca4eb"
              }
            ]
          },
          {
            "featureType": "road",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "road.highway.controlled_access",
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#367ab6"
              }
            ]
          },
          {
            "featureType": "transit",
            "elementType": "labels.text.fill",
            "stylers": [
              {
                "color": "#98a5be"
              }
            ]
          },
          {
            "featureType": "transit",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#1d2c4d"
              }
            ]
          },
          {
            "featureType": "transit.line",
            "elementType": "geometry.fill",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "transit.station",
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#efc68a"
              }
            ]
          },
          {
            "featureType": "transit.station",
            "elementType": "labels.text",
            "stylers": [
              {
                "color": "#efc68a"
              }
            ]
          },
          {
            "featureType": "transit.station",
            "elementType": "labels.text.stroke",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "water",
            "elementType": "geometry",
            "stylers": [
              {
                "color": "#262f38"
              }
            ]
          },
          {
            "featureType": "water",
            "elementType": "labels.text.fill",
            "stylers": [
              {
                "color": "#4e6d70"
              }
            ]
          }
        ]
