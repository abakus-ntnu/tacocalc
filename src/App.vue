<template>
    <div id="app" >
        <div class="page-header">
            <h1>readme sin tacokalkulator</h1>
        </div>
        <p class="lead center">
            For nye medlemmer, gamle drankere og andre som ønsker å kokkelere readmes fantastiske taco, men som er usikker på hvor mye de trenger av alt mulig.
        </p>
        <Calc />

        <div id="footer">
            <p>Made by <a href="http://svorstol.com">Stein-Otto Svorstøl</a></p>
            <p>Updated by <a href="https://github.com/AndreasHaaversen">Andreas Hammer Håversen</a></p>
        </div>
    </div>
</template>

<style src="./assets/style.css" />

<script>
    import 'jquery';
    import 'bootstrap';

    import Calc from './components/Calc';

    export default {
        name: 'app',
        components: {
            Calc,
        },
    };

</script>
