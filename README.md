Installation
---

    npm install fontello-sass --save-dev


How to use
---

*First, create/select some icons on [fontello.com](http://fontello.com/) and download the fonts.*



Let's assume your file structure is like this:

    |- styles.scss
    |- fonts/
    |-     fontello.eot
    |-     fontello.woff2
    |-     fontello.woff
    |-     fontello.ttf
    |-     fontello.svg


styles.scss


    $fontello-font-path : "./fonts";
    $fontello-font-name : "fontello";
    
    @import "~fontello-sass/fontello";



Mixins
---

    fontello( $code, $position: before )
    fontello-init( $position:before )
    fontello-content( $code, $position:before )
    fontello-margin( $margin:.2em, $position:before )
    fontello-color( $color, $position:before )
    fontello-base64( $code: $fontello-font-base64 )
    fontello-produce( $prefix, $map, $margin:.2em, $position: before )


Examples
---

### 1.

icon.scss

    .my-icon {
        @include fontello( 800 ); // 800 is the fontello code, do not need to the prefix "E"
    }

icon.html

    <span class="my-icon">icon</span>


### 2.

icon.scss

    .icon {
        @include fontello-init();
        @include fontello-margin;
    }

    .icon-logo {
        @include fontello-content( 800 );
    }

    .icon-heart {
        @include fontello-content( 801 );
    }

icon.html

    <span class="icon icon-logo">logo icon</span>
    <span class="icon icon-heart">heart icon</span>

### 3.

icon.scss

    $icons: (
      logo  : 800,
      heart : 801,
    );

    @include fontello-produce( icon, $icons, .2em, both );

icon.html

    <span class="icon icon-logo">logo icon</span>
    <span class="icon icon-heart">heart icon</span>

    <span class="icon-after icon-logo-after">logo icon</span>
    <span class="icon-after icon-heart-after">heart icon</span>
