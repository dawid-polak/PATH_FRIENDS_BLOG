<template>
    <div class="welcome--content">
        <div class="welcome--content-text">
            <h1>Góry milczą, wszystko co milczy <br> nadaję się do przechowywania <br> ludzkich tajemnic...</h1>
            <h6>Józef Tischner</h6>
        </div>
        <div class="welcome--content-btn">
            <router-link to="/">
                <button>
                    kim jesteśmy?
                </button>
            </router-link>
        </div>
    </div>
    <News/>
</template>

<script>
 import News from '../components/News.vue';

</script>

<style scoped lang="scss">
$breakpoints: (
    xs: 512px,
    sm: 768px,
    md: 896px,
    md-xl: 950px,
    lg: 1152px,
    xl: 1280px
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

.welcome--content {
      height: 100vh;
      position: relative;
      background-image: url(../src/assets/app/backgrounds/home-bg.jpeg);
      background-size: cover;
      
      .welcome--content-text {
        display: flex;
        justify-content: center;
        flex-flow: column;
        width: 80vw;
        height: 80%;
        margin: auto;

        h1 {

            @include breakpoint(xs) {
                font-size: 20px;
            }
            margin: 20px;
            color: #FFF;
        }
        
        h6{
            margin: 20px;
        }

      }

      .welcome--content-btn {
        display: flex;
        justify-content: center;

        button {
            border: 0;
            background-color: #0F222D;
            border-radius: 10px;
            color: #FEF4CF;
            font-family: 'Bungee Inline', cursive;
            padding: 20px 40px 20px 40px;
        }
      
      }



  }

</style>