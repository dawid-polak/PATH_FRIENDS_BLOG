<template>
    <div class="welcome--content">
        <div class="welcome--content-text">
            <h1>Góry milczą, wszystko co milczy <br> nadaję się do przechowywania <br> ludzkich tajemnic...</h1>
            <h6>Józef Tischner</h6>
        </div>
        <div class="welcome--content-btn">
            <router-link to="/about">
                <button>
                    kim jesteśmy?
                </button>
            </router-link>
        </div>
    </div>
</template>

<script>
 

</script>

<style scoped lang="scss">
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