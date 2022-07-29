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
                console.log('test')
                this.navbarActive = 'active-nav';
                this.navbarActiveHyperlink = 'active-nav-hyperlink';
            } else {
                this.navbarActive = '';
                this.navbarActiveHyperlink = '';
            }
        }
    }
}
</script>

<style scoped lang="scss">
// @import '../../src/assets/app/style/scss/navbar.scss';

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
}

.active-nav {
    animation: show 0.5s ease-in-out;
    animation-fill-mode: forwards;
}

@keyframes show {
    from {
        
    }
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