| [Home](README.md) | [Kraken Demo](kraken-demo.md) | [Ottawa Cyclists](ottawa-cyclists.md) | [Final Project](final-project.md) |
# Building a Custom Google Map for a Nonprofit
For this assignment, I built a custom map template for a nonprofit ([Strong Towns](https://www.strongtowns.org/)), using colors from its branding.

## Introduction
As "a 501(c)(3) nonprofit media advocacy organization," Strong Towns releases educational videos, materials, and other multumedia, and facilitates commmunity organization to support their mission: 

"We seek to replace America’s post-war pattern of development, the Suburban Experiment, with a pattern of development that is financially strong and resilient. We advocate for cities of all sizes to be safe, livable, and inviting. We work to elevate local government to be the highest level of collaboration for people working together in a place, not merely the lowest level in a hierarchy of governments."

With the organization's focus on localism, I designed the following map template to emphasize cities, towns, and local streets, while de-emphasizing features like interstate highways and other geographic labels. 

## Color Palette
I used the Canva Color Palette Generator to extract the following colors from the Strong Towns [website](https://www.strongtowns.org/journal/2023/4/14/announcing-this-years-strongest-town-contest-winner) and [Strategic Plan](https://static1.squarespace.com/static/53dd6676e4b0fedfbc26ea91/t/627aae62e24d6669f6496002/1652207205056/Strong+Towns+Strategic+Plan+%28WEB%29.pdf):


<img width="900" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/ccaffd51-3376-4917-a785-a513ca4eb7bb">

<img width="900" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/5644b3f1-3786-46c9-be83-b140da62df4c">

I used **Picton Blue** and **Tacao** as the main two colors for the design, using other colors like Ebony Clay for various outlines and strokes. Picton Blue was the main background color, making up most of the land area, while Tacao was the color I used to make certain features stand out above the others (cities and local roads, for example). Building on what I mentioned above, I sort of wanted to invert conventional map design to feature smaller roads and towns rather than highways or larger geographical features. I made the highways fade into the background by using a different shade of blue (Boston Blue) and made the state labels essentially just an outline to greater focus the map on cities, towns, and communities. 

Using colors in line with the Strong Towns brand, and emphasizing the geographical features most relevant to Strong Towns's mission of encouraging Main Street development and promoting community building, this template should be a good fit for Strong Towns. Below is a breakdown of my use of color:

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

## Map Views
Below are views of my map template from various zoom extents, centered on Brattleboro, Vermont, the 2023 Strongest Town Winner.

### Eastern United States
Here, you can see the cities clearly stand out over all other features, showing that this map highlights *place* over all else.

<img width="960" alt="image" src="https://github.com/jredman14/gis-portfolio/assets/156849712/c4605112-495c-4a0d-b833-ecbd76441bf4">

### New England Region
In this view, you can see the local and regional streets clearly, as well as both large cities and smaller towns, while the interstate highways fade as background features. This was intentional, since local streets are often the bedrock of communities, whereas interstates can serve more commercial purposes (shipping, freight, etc.). 

<img width="960" alt="Screenshot 2024-03-24 232026" src="https://github.com/jredman14/gis-portfolio/assets/156849712/5f2bd182-5b52-4cf4-a7a0-3aba35baead5">

### Brattleboro, VT - 2023 Strongest Town Winner
Here, you can see Brattleboro's dense local street network and mix of businesses, cultural attractions, and scenery that helped make it Strong Towns's "[Strongest Town](https://www.strongtowns.org/journal/2023/4/14/announcing-this-years-strongest-town-contest-winner)" in 2023.

<img width="960" alt="Screenshot 2024-03-24 232055" src="https://github.com/jredman14/gis-portfolio/assets/156849712/9113b4f9-6783-4183-abb1-1aa2fb951a06">

## JSON Code
Here is the JSON code for my map template and a link to a .json text file containing the code.

[Link to JSON text file](https://1drv.ms/u/s!AgmvhI3Sh11Kgskw9-IlFnHbznsoUQ?e=ucCcpj)

### Code Block

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
