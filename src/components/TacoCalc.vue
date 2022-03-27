<template>
  <div class="row-fluid col-xs-12">
    <div class="col-md-6">
      <div id="calc">
        <label>
          <h5>Skriv inn antall deltakere:</h5>
        </label>
        <input type="number" min="1" v-model="numberOfPeople">
        <h4>
          {{
          numberOfPeople &lt; 0 ? 'Hva er det du tror du gjør? Slutt å være så negativ.' :
          (!numberOfPeople ? 'Du har ikke oppgitt noe antall ennå.' : '')
          }}
        </h4>
        <ul>
          <li>{{ kjøttdeig }} pakk{{ flertallErE(kjøttdeig) }} kjøttdeig (á 400 gram)</li>
          <li>{{ bønner }} boks{{ flertallEr(bønner) }} bønner</li>
          <li>{{ tacolefser }} STORE tacolefser</li>
          <li>{{ tacokrydder }} pakk{{ flertallErE(tacokrydder) }} tacokrydder</li>
          <li>{{ bacon }} pakk{{ flertallErE(bacon) }} bacon</li>
          <li>{{ tomat }} tomat{{ flertallEr(tomat) }}</li>
          <li>{{ agurk }} agurk{{ flertallEr(agurk) }}</li>
          <li>{{ isbergsalat }} pakk{{ flertallErE(isbergsalat) }} isbergsalat</li>
          <li>{{ mais }} gram mais</li>
          <li>{{ paprika }} paprika</li>
          <li>{{ rømme }} boks{{ flertallEr(rømme) }} rømme</li>
          <li>{{ rødløk }} rødløk</li>
          <li>{{ tortillachips }} stor{{ flertallE(tortillachips) }} pos{{ flertallErE(tortillachips) }} med tortillachips</li>
          <li>
            Også trenger du selvsagt ost, {{ numberOfPeople > 30 ? " men vi er usikre når dere er så mange. Minst en kilo i alle fall!"
            : (numberOfPeople >= 15 ? " omkring 1 kilo bør holde." : " omkring en halv kilo er nok.") }}
          </li>
        </ul>
        <h5>Hvis du er i tvil om noe, er det alltid best å ta med ekstra.</h5>

        <br>
        <h5>Ellers er det nødvendig med:</h5>
        <ul>
          <li>{{ fetaost }} glass fetaost i olje</li>
          <li>{{ chunkySalsa }} glass chunky salsa (hot ofc og litt medium for de som liker det)</li>
          <li>{{ sprøstektLøk }} pakk{{ flertallErE(sprøstektLøk) }} med sprøstekt løk</li>
          <li>{{ cashewnøtter }} pakk{{ flertallErE(cashewnøtter) }} med cashewnøtter</li>
          <li>{{ druer }} pakk{{ flertallErE(druer) }} med druer</li>
          <li>{{ jalapenos }} glass jalapenos</li>
          <li>{{ ananas }} boks{{ flertallEr(ananas) }} med ananas</li>
          <li>1 stk. hemmelig ingrediens 😉</li>
        </ul>
      </div>
    </div>
    <div class="col-md-6">
      <h5>Også trenger man guacamole:</h5>
      <ul>
        <li>{{ avocado }} stk. modne avocado</li>
        <li>{{ hvitløk }} fedd hvitløk</li>
        <li>{{ aLøk }} dl løk</li>
        <li>{{ chili }} ss chili</li>
        <li>{{ koriander }} ss fersk koriander type hakket</li>
        <li>{{ limesaft }} ss limesaft</li>
        <li>{{ salt }} ts salt</li>
        <li>{{ pepper }} ts pepper</li>
        <li>{{ aRømme }} ss rømme</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "TacoCalcultator",
  data() {
    return {
      numberOfPeople: 80085,
      res: 0
    };
  },

  methods: {
    flertallE(i) {
      let output = "";
      if (Math.abs(i) !== 1) {
        output = "e";
      }
      return output;
    },
    flertallErE(i) {
      let output = "e";
      if (Math.abs(i) !== 1) {
        output = "er";
      }
      return output;
    },
    flertallEr(i) {
      let output = "";
      if (Math.abs(i) !== 1) {
        output = "er";
      }
      return output;
    }
  },

  computed: {
    kjøttdeig: function() {
      return Math.ceil((150 * this.numberOfPeople) / 400);
    },
    bønner: function() {
      return Math.ceil(((150 * this.numberOfPeople) / 400) * (2 / 3));
    },
    tacolefser: function() {
      return Math.ceil(2.5 * this.numberOfPeople);
    },
    tacokrydder: function() {
      return Math.ceil((150 * this.numberOfPeople) / 400);
    },
    bacon: function() {
      return Math.ceil((1 / 4) * this.numberOfPeople);
    },
    tomat: function() {
      return Math.ceil((2 / 5) * this.numberOfPeople);
    },
    agurk: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    isbergsalat: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    mais: function() {
      return Math.ceil(25 * this.numberOfPeople);
    },
    paprika: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    rømme: function() {
      return Math.ceil((1 / 6) * this.numberOfPeople);
    },
    rødløk: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    tortillachips: function() {
      return Math.ceil((1 / 8) * this.numberOfPeople);
    },
    fetaost: function() {
      return Math.ceil((1 / 15) * this.numberOfPeople);
    },
    chunkySalsa: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    sprøstektLøk: function() {
      return Math.ceil((1 / 25) * this.numberOfPeople);
    },
    cashewnøtter: function() {
      return Math.ceil((1 / 12) * this.numberOfPeople);
    },
    druer: function() {
      return Math.ceil((1 / 25) * this.numberOfPeople);
    },
    jalapenos: function() {
      return Math.ceil((1 / 25) * this.numberOfPeople);
    },
    ananas: function() {
      return Math.ceil((1 / 25) * this.numberOfPeople);
    },
    avocado: function() {
      return Math.ceil(this.numberOfPeople / 4) * 2;
    },
    hvitløk: function() {
      return Math.ceil(this.numberOfPeople / 4) * 2;
    },
    aLøk: function() {
      return Math.ceil(this.numberOfPeople / 4) * 1;
    },
    chili: function() {
      return Math.ceil(this.numberOfPeople / 4) * 2;
    },
    koriander: function() {
      return Math.ceil(this.numberOfPeople / 4) * 2;
    },
    limesaft: function() {
      return Math.ceil(this.numberOfPeople / 4) * 3;
    },
    salt: function() {
      return Math.ceil(this.numberOfPeople / 4);
    },
    pepper: function() {
      return Math.ceil(this.numberOfPeople / 4);
    },
    aRømme: function() {
      return Math.ceil(this.numberOfPeople / 4) * 2;
    }
  }
};
</script>
