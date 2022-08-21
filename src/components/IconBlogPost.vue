<template>
    <div class="icon--post">
        <div class="icon--post-hashtag">
            <h2>VIA FERRATA</h2>
            <hr>
        </div>
        <div class="icon--post-title">
            <h4>Via Ferrata na weekend z Polski! Gdzie? </h4>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {

        }
    }
}
</script>
<style scoped lang="scss">

$breakpoints: (
    xs: 512px,
    sm: 768px,
    md: 896px,
    md-xl: 950px,
    lg: 1152px,
    xl: 1300px
);

@mixin breakpoint( $breakpoint ) {
    @if map-has-key( $breakpoints, $breakpoint )  {
        @media ( max-width: #{ map-get($breakpoints, $breakpoint)} ) {
            @content;
        }
    } @else if type_of( $breakpoint ) == number and unit( $breakpoint ) == px or unit( $breakpoint ) == em or unit( $breakpoint ) == rem {
        @media ( max-width: $breakpoint ) {
            @content;
        }
   } @else {
     @warn "Nie można pobrać żadnej wartości z `#{$breakpoint}`. Nie jest zdefiniowany w mapie `$breakpoints` lub jest nieprawidłową liczbą px, em, lub rem.";
  }
}


.icon--post {


    @include breakpoint(xl) {
        width: 400px;
        height: 250px;
    }

    @include breakpoint(lg) {
        width: 350px;
        height: 250px;
    }

    @include breakpoint(md-xl) {
        width: 500px;
        height: 300px;
    }

    @include breakpoint(sm) {
        width: 400px;
        height: 250px;
    }

    @include breakpoint(xs) {
        width: 300px;
        height: 200px;
    }

    width: 500px;
    height: 300px;
    background-image: url(../assets/block/backgrounds/vfnw.v1.jpeg);
    background-size: cover;
    border-radius: 10px;
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    
    .icon--post-hashtag {
        margin: auto;
        color: #FFF;

        hr {
            width: 20%;
        }
    }
    
    .icon--post-title {
        color: #FFF;
        margin: 0px 10px 0px 10px;
        
    }
}

</style>