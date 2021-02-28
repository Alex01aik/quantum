<template>
    <header class="container">
        <div class="logo">
            <a href="#">LOGO</a>
        </div>
        <nav>
            <a class="navitem" href="#">How it works</a>
            <a class="navitem" href="#">About</a>
            <a class="navitem" href="#">Instruction</a>
            <a class="navitem" href="#">Accounts</a>
            <a class="navitem" href="#">Platforms</a>
            <a class="navitem" href="#">Contact</a>
        </nav>
        <div class="localization">
            <select>
                <option>EN</option>
                <option>RU</option>
            </select>
        </div>
        <Button 
            :text="'sign in for free'"/>
        <details v-if="window.width < 769"
        class="hidenav">
            <summary class="menu__btn"><span></span></summary>
            <nav>
                <a class="navitem" href="#">How it works</a>
                <a class="navitem" href="#">About</a>
                <a class="navitem" href="#">Instruction</a>
                <a class="navitem" href="#">Accounts</a>
                <a class="navitem" href="#">Platforms</a>
                <a class="navitem" href="#">Contact</a>
            </nav>
        </details>
    </header>
</template>

<script>
import Button from '@/components/Button'
export default {
    components: {
        Button
    },
    data: () => ({
        window: {
            width: 0,
            height: 0
        }
    }),
    mounted() {
        window.addEventListener('resize', this.handleResize);
        this.handleResize();
    },
    unmounted() {
        window.removeEventListener('resize', this.handleResize);
    },
    methods: {
        handleResize() {
            this.window.width = window.innerWidth;
            this.window.height = window.innerHeight;
        }
    }
}
</script>

<style scoped>
header{
    min-height: 80px;
    display: flex;
    align-items: center;
}
nav{
    margin-left: 41px;
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.navitem{
    margin: 0 16px;
}
.localization{
    margin-left: auto;
    margin-right: 24px;
    border: 1px solid #333333;
    border-radius: 60px;
    padding: 10px 16px;
}
select{
    border: none;
    font-family: 'Museo Sans Cyrl', sans-serif;
    font-size: 15px;
    cursor: pointer;
}
button{
    font-size: 14px;
    padding: 13px 24px;
}
.hidenav{
    margin-left: auto;
}
.menu__btn{
    padding-top: 8px;
    height: 24px;
    width: 18px;
}
.menu__btn > span,
.menu__btn > span::before,
.menu__btn > span::after {
  display: block;
  position: absolute;
  width: 18px;
  height: 2px;
  background-color: #616161;
}
.menu__btn > span::before {
  content: '';
  top: -8px;
}
.menu__btn > span::after {
  content: '';
  top: 8px;
}
details nav{
    display: flex;
    flex-direction: column;
    right: 0;
    background: white;
    margin-top: 28px;
    border-radius:  0  0 30px 30px;
    position: absolute;
}
details .navitem{
    margin: 20px 64px;
    text-align: center;
}
details summary::-webkit-details-marker {
    display:none;
}
@media screen and (max-width: 768px) {
    nav{
        display: none;
    }
    .localization{
        display: none;
    }
    button{
        position: absolute;
        right: 112px;
        margin: 0;
    }
}
@media screen and (max-width: 480px) {
    button{
        display: none;
    }
    .localization{
        display: none;
    }
}
</style>