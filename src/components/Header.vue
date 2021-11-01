<template>
  <div class="main-header">
    <div class="line_flex">
        <div class="logo">
            <img src="../assets/images/logo.png" alt="ByCodes">
        </div>
        <nav class="main-menu">
            <ul>
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/videos">Videos</router-link></li>
                <li><router-link to="/history">Histórico</router-link></li>
            </ul>
        </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",

};
</script>

<style lang="scss">

$red: #ff0000;
$black: #282828;

.main-header {
    padding: 10px 60px;
    .logo {
        width: 180px;
    }
    .main-menu {
        ul {
            margin: 0;
            padding: 0;
            li {
                list-style: none;
                display: inline-block;
                margin-left: 20px;
                 a {
                    text-decoration: none;
                    color: $red;
                    text-transform: uppercase;
                    font-weight: bold;
                    &:hover {
                        color: $black;
                    }
                }
            }
        }
    }
}

@media(max-width: 767px) {
    .main-header {
        padding: 10px 15px;
        .line_flex {
            justify-content: center;
        }
    }   
}

</style>