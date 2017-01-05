<template>
    <div id="calc">
        <label><h5>Skriv inn antall deltakere: </h5></label>
        <input type="number" min="1" v-model="numberOfPeople"/>
        <h4>
            {{
                numberOfPeople && numberOfPeople < 0 ? 'Hva er det du tror du gjør? Slutt å være så negativ.' :
                (!numberOfPeople ? 'Du har ikke oppgitt noe antall ennå.' : '')
            }}
        </h4>
        <li> {{ Math.ceil(150*numberOfPeople/400) }} pakker kjøttdeig (á 400 gram)</li>
        <li> {{ Math.ceil(2.5*numberOfPeople) }} STORE tacolefser</li>
        <li> {{ Math.ceil(0.5*numberOfPeople) }} pakker tacokrydder</li>
        <li> {{ Math.ceil(0.25*numberOfPeople) }} pakker bacon</li>
        <li> {{ Math.ceil(0.4*numberOfPeople) }} tomater</li>
        <li> {{ Math.ceil((1/15)*numberOfPeople) }} agurker</li>
        <li> {{ Math.ceil((1/12)*numberOfPeople) }}pakker isbergsalat</li>
        <li> {{ Math.ceil(25*numberOfPeople) }} gram mais</li>
        <li> {{ Math.ceil((1/12)*numberOfPeople) }} paprika</li>
        <li> {{ Math.ceil((1/6) *numberOfPeople) }} bokser rømme</li>
        <li> {{ Math.ceil((1/12)*numberOfPeople) }} rødløk</li>
        <li> {{ Math.ceil((1/8)*numberOfPeople) }} store poser med tortillachips</li>
        <li> Også trenger du selvsagt ost, {{ numberOfPeople > 30 ? " men vi er usikre når dere er så mange. Minst en kilo i alle fall!"
        : (numberOfPeople>=15  ? " omkring 1 kilo bør holde." : " omkring en halv kilo er nok.") }} </li>

        <h5>Hvis du er i tvil om noe, er det alltid best å ta med ekstra.</h5>

        <br>
        <h5>Ellers er det nødvendig med ..</h5>
        <li>fetaost i olje </li>
        <li>chunky salsa (hot ofc og litt medium for de som liker det)</li>
        <li>cashewnøtter </li>
        <li>jalapenos </li>
        ... også noen bokser ananas til Marit.
    </div>
</template>

<script>
    export default {
        name: 'calc',
        data() {
            return {
                numberOfPeople: 9001,
            };
        },
    };
</script>
