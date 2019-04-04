<template>
    <div class="row-fluid col-xs-12 ">
        <div class="col-md-6">
            <div id="calc">
                <label><h5>Skriv inn antall deltakere: </h5></label>
                <input type="number" min="1" v-model="numberOfPeople"/>
                <h4>
                    {{
                        numberOfPeople < 0 ? 'Hva er det du tror du gjør? Slutt å være så negativ.' :
                        (!numberOfPeople ? 'Du har ikke oppgitt noe antall ennå.' : '')
                    }}
                </h4>
                <ul>
                    <li> {{ setRes(Math.ceil(150 * numberOfPeople / 400)) }} pakk{{ flertallErE(res) }} kjøttdeig (á 400 gram)</li>
                    <li> {{ setRes(Math.ceil(150 * numberOfPeople / 400 * (2/3))) }} boks{{ flertallEr(res) }} bønner</li>
                    <li> {{ Math.ceil(2.5 * numberOfPeople) }} STORE tacolefser</li>
                    <li> {{ setRes(Math.ceil(150 * numberOfPeople / 400)) }} pakk{{ flertallErE(res) }} tacokrydder</li>
                    <li> {{ setRes(Math.ceil((1/4) * numberOfPeople)) }} pakk{{ flertallErE(res) }} bacon</li>
                    <li> {{ setRes(Math.ceil((2/5) * numberOfPeople)) }} tomat{{ flertallEr(res) }}</li>
                    <li> {{ setRes(Math.ceil((1/10) * numberOfPeople)) }} agurk{{ flertallEr(res) }}</li>
                    <li> {{ setRes(Math.ceil((1/12) * numberOfPeople)) }} pakk{{ flertallErE(res) }} isbergsalat</li>
                    <li> {{ Math.ceil(25 * numberOfPeople) }} gram mais</li>
                    <li> {{ Math.ceil((1/12) * numberOfPeople) }} paprika</li>
                    <li> {{ setRes(Math.ceil((1/6) * numberOfPeople)) }} boks{{ flertallEr(res) }} rømme</li>
                    <li> {{ Math.ceil((1/12) * numberOfPeople) }} rødløk</li>
                    <li> {{ setRes(Math.ceil((1/8) * numberOfPeople)) }} stor{{ flertallE(res) }} pos{{ flertallErE(res) }} med tortillachips</li>
                    <li> Også trenger du selvsagt ost, {{ numberOfPeople > 30 ? " men vi er usikre når dere er så mange. Minst en kilo i alle fall!"
                    : (numberOfPeople >= 15  ? " omkring 1 kilo bør holde." : " omkring en halv kilo er nok.") }} </li>
                </ul>
                <h5>Hvis du er i tvil om noe, er det alltid best å ta med ekstra.</h5>

                <br>
                <h5>Ellers er det nødvendig med:</h5>
                <ul>
                    <li> {{ Math.ceil((1/15) * numberOfPeople) }} glass fetaost i olje </li>
                    <li> {{ Math.ceil((1/12) * numberOfPeople) }} glass chunky salsa (hot ofc og litt medium for de som liker det)</li>
                    <li> {{ setRes(Math.ceil((1/25) * numberOfPeople)) }} pakk{{ flertallErE(res) }} med sprøstekt løk </li>
                    <li> {{ setRes(Math.ceil((1/12) * numberOfPeople)) }} pakk{{ flertallErE(res) }} med cashewnøtter </li>
                    <li> {{ setRes(Math.ceil((1/25) * numberOfPeople)) }} pakk{{ flertallErE(res) }} med druer </li>
                    <li> {{ Math.ceil((1/25) * numberOfPeople) }} glass jalapenos </li>
                    <li> {{ setRes(Math.ceil((1/25) * numberOfPeople)) }} boks{{ flertallEr(res) }} med ananas </li>
                </ul>
            </div>
        </div>
        <div class="col-md-6">
            <h5>Også trenger man guacamole:</h5>
            <ul>
                <li> {{ Math.ceil(numberOfPeople/4) * 2 }} stk. modne avocado</li>
                <li> {{ Math.ceil(numberOfPeople/4) * 2 }} fedd hvitløk</li>
                <li> {{ Math.ceil(numberOfPeople/4) * 1 }} dl løk</li>
                <li> {{ Math.ceil(numberOfPeople/4) * 2 }} ss chili</li>
                <li> {{ Math.ceil(numberOfPeople/4) * 2 }} ss fersk koriander type hakket</li>
                <li> {{ Math.ceil(numberOfPeople/4) * 3 }} ss limesaft</li>
                <li> {{ Math.ceil(numberOfPeople/4) }} ts salt </li>
                <li> {{ Math.ceil(numberOfPeople/4) }} ts pepper </li>
                <li> {{ Math.ceil(numberOfPeople/4) * 2 }} ss rømme </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'calc',
        data() {
            return {
                numberOfPeople: 80085,
                res: 0,
            };
        },

        methods: {
            flertallE(i) {
                let out = '';
                if (Math.abs(i) !== 1) {
                    out = 'e';
                }
                return out;
            },
            flertallErE(i) {
                let out = 'e';
                if (Math.abs(i) !== 1) {
                    out = 'er';
                }
                return out;
            },
            flertallEr(i) {
                let out = '';
                if (Math.abs(i) !== 1) {
                    out = 'er';
                }
                return out;
            },
            setRes(i) {
                this.res = i;
                return i;
            },
        },
    };
</script>
