<template>
  <header>

      <nav class="container">

        <div class="logo">
            <a href="/"><img alt="DINDIN" id="logo" src="@/assets/dindin-logo.png"></a>
        
            <h1 class="containerb">dindin</h1>
        
        </div>

        <img v-on:click="openMenu" alt="Abrir menu" id="menu-button" src="@/assets/menu-mobile.png">

        <div v-on:click="closeMenu" id="menu-overlay" v-if="menuActive"></div>

        <div id="menu-items" :class="{active:menuActive}">

            <a href="/"><img alt="DINDIN" id="menu-logo" src="@/assets/dindin-logo.png"></a>


            <ul>
                <!--<li><a href="/cursos">Home</a></li>-->
                <li><a href="/">Cursos</a></li>
                <li><a href="/sobre">Sobre</a></li>
                <li><a href="/contato">Contato</a></li>

            </ul>
        </div>

      </nav>

  </header>
</template>

<script>
export default {

    name: "Header",
    data(){
        return{
            menuActive: true
        }
    },
    methods:{
        openMenu: function(){
            this.menuActive = true;
        },
        closeMenu: function(){
            this.menuActive = false;

        }
    }

};

</script>

    <style scoped>

        header {

            background-color: var(--color-background-nav);
            width: 100%;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        nav{
            display: flex;
            justify-content:space-between;
            height: 60px;
            align-items: center;

        }

        
        #logo{
            width: 40px;
        }

        #menu-button{
            width: 30px;

        }

        #menu-overlay{
            position: fixed;
            top: 0;
            left: 0;
            width: 40%;
            height: 100vh;
            background-color: black;
            opacity: 0.8;
        }

        #menu-logo{
            width: 35px;
            margin-top: 30px;
            margin-bottom: 10px;
        }

        #menu-items{
            position: fixed;
            top: 0;
            right: 0;
            background-color: var( --color-background-nav);
            width: 60%;
            height: 100vh;
            display: none;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
        }

        #menu-items.active{
            display: flex;
        }

        ul{
            list-style: none;
            text-align: center;
        }

        ul li{
            margin: 20px 0px;
        }

        ul li a{
            color: var(--color-text-light);
        }

        .logo{
            display: flex;
            left: 0%;
        }

        @media (min-width: 700px){
            #menu-button,
            #menu-logo,
            #menu-overlay{
                display: none;
            }

            #menu-items{
                display: flex;
                position: static;
                height: 60px;
                width: auto;
            }

            ul{
                display: flex;
                height: 60px;
                align-items: center;
                
            }

            ul li{
                margin: 0;
                margin-left: 20px;
            }
        }
</style>