<template>
    <div id="app" >
        <div class="page-header">
            <h1>readmes tacokalkulator</h1>
        </div>
        <p class="lead center">
            For nye medlemmer, gamle drankere og andre som ønsker å kokkelere readmes fantastiske taco, men som er usikker på hvor mye de trenger av alt mulig.
        </p>
        <div class="row-fluid col-xs-12 ">
            <div class="col-md-6">
                <Calc />
            </div>

            <div class="col-md-6">
                <h5>.. også trenger man guacamole</h5>
                Per 8 personer
                <li>4 stk. modne avocado</li>
                <li>4 fedd hvitløk</li>
                <li>2 dl løk</li>
                <li>4 ss chili</li>
                <li>4 ss fersk koriander type hakket</li>
                <li>6 ss limesaft</li>
                <li>1 ts salt </li>
                <li>1 ts pepper </li>
                <li>4 ss rømme </li>
            </div>
        </div>
        <div id="footer">
            <p>Made by <a href="http://svorstol.com">Stein-Otto Svorstøl</a></p>
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
