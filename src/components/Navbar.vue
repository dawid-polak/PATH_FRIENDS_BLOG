<template>
    <nav :class="navbarActive">
        <div class="nav--logo">
            <img src="../assets/app/logo/Monochrome on Transparent.png" alt="logo">
        </div>
        <div class="nav--menu">
            <div class="nav--menu-link">
                <a href="#" :class="navbarActiveHyperlink">O NAS</a>
            </div>
            <div class="nav--menu-link">
                <a href="#" :class="navbarActiveHyperlink">BLOG</a>
            </div>
            <div class="nav--menu-link">
                <a href="#" :class="navbarActiveHyperlink">ULUBIONE</a>
            </div>  
            <div class="nav--menu-link">
                <a href="#" :class="navbarActiveHyperlink">KONTAKT</a>
            </div>
        </div>
        <div class="nav--btn">
            <button>WIRTUALNY SZLAK</button>
        </div>
        <div class="nav--hamburger">
            <i class="fi fi-br-menu-burger" @click="klikam"></i>

        </div>
    </nav>
</template>

<script>
export default {
    data(){
        return {
            navbarActive: '',
            navbarActiveHyperlink: ''
        }
    },
    created() {
        window.addEventListener('scroll', this.scrollAnimation)
    },
    methods: {
        scrollAnimation() {

            if (window.scrollY > 45) {
                this.navbarActive = 'active-nav';
                this.navbarActiveHyperlink = 'active-nav-hyperlink';
            } else {
                this.navbarActive = '';
                this.navbarActiveHyperlink = '';
            }
        },
        klikam() {
            console.log('msadjkahs')
        }
    }
}
</script>

<style scoped lang="scss">
// @import '../../src/assets/app/style/scss/navbar.scss';

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

@mixin flex($direction, $justifyContent) {
    display: flex;
    justify-content: $justifyContent;
    align-items: center;
    flex-direction: $direction;
}

@mixin hyperlink($color, $colorHover) {
    text-decoration: none;
    color: $color;
    &:hover {
        color: $colorHover;
    }
}

nav {
    position: fixed;
    z-index: 1000;
    height: 90px;
    width: 100vw;

    @include flex(row, space-between);
    .nav--logo {
        height: 80%;
        padding: 10% 0 10% 10vw;
        img {
            height: 100%;
            width: 100%;
        }
    }
    
    .nav--menu {
        @include breakpoint(md-xl){
            display: none;
        };

        height: 100%;
        @include flex(row, center);

        .nav--menu-link {
            padding: 10px;

            a {
                @include hyperlink(#FFF, #FEF4CF);
            }
        }
    }
    .nav--btn {
        @include breakpoint(sm) {
            display: none;
        }

        height: 100%;
        padding-right: calc(10vw);
        @include flex(column, center);

        button {
            border: 0;
            background-color: #FEF4CF;
            border-radius: 10px;
            padding: 17px 40px 15px 40px;
            font-family: 'Bungee Inline', cursive;
        }
        
    }

    .nav--hamburger {
        display: none;

        @include breakpoint(md-xl) {
            display: block;
            margin: 20px;
            font-size: 25px;
        }
    }

}

.active-nav {
    animation: show 0.5s ease-in-out;
    animation-fill-mode: forwards;
}

@keyframes show {
    to {
        background-color: #FFF;
        box-shadow: 0px 1px 3px #666;
        color: #000;
    }
}

.active-nav-hyperlink {
    animation: showHyperlink 0.5s ease-in-out;
    animation-fill-mode: forwards;
}

@keyframes showHyperlink {
    from {
        
    }
    to {
        color: #000;
    }
}


</style>