# Marker Clusterer for AGM

-----

this package levereges the [js-marker-clusterer][js-marker-clusterer] to add clustering support to
[AGM][agm].

this package update peer dependency from "js-marker-clusterer": "^1.0.0" to gmaps-marker-clusterer for prevent deprecate addDomListener
"gmaps-marker-clusterer": "github:gmaps-marker-clusterer/gmaps-marker-clusterer#53f09b21b464626c1f047cac9782bf58f61d935c",
and compatible with "@agm/js-marker-clusterer" just update the import path.

## Installation

@agm/js-marker-clusterer has a peer depedency on [gmaps-marker-clusterer][js-marker-clusterer]

```shell
npm install git+https://github.com/gmaps-marker-clusterer/gmaps-marker-clusterer.git#53f09b21b464626c1f047cac9782bf58f61d935c @agm-extend/js-marker-clusterer --save

```

## Usage

1. Import the module

    ```typescript
    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';
    import { AppComponent } from './app.component';

    // add these imports
    import { AgmCoreModule } from '@agm/core';
    import { AgmJsMarkerClustererModule } from '@agm-extend/js-marker-clusterer';

    @NgModule({
      declarations: [
        AppComponent
      ],
      imports: [
        BrowserModule,
        AgmCoreModule.forRoot({
          apiKey: ['YOUR_API_KEY_HERE']
        }),
        AgmJsMarkerClustererModule
      ],
      providers: [],
      bootstrap: [AppComponent]
    })
    export class AppModule { }
    ```
2. use it in your template

    ```html
    <agm-map style="height: 300px" [latitude]="51.673858" [longitude]="7.815982">
      <agm-marker-cluster imagePath="https://raw.githubusercontent.com/googlemaps/v3-utility-library/master/markerclustererplus/images/m">
        <agm-marker [latitude]="51.673858" [longitude]="7.815982">
        </agm-marker><!-- multiple markers -->
      </agm-marker-cluster>
    </agm-map>
    ```


[js-marker-clusterer]: https://github.com/googlemaps/js-marker-clusterer
[agm]: https://angular-maps.com/
