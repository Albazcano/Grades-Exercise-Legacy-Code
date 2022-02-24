<template>
  <div>
    <h2>Calificación del Trimestre</h2>

    <label for="nombre"></label>
    <input type="text" placeholder="Escriba su nombre" id="nombre" />
    <p></p>
    <label for="curso"></label>
    <input
      type="text"
      v-model="curso"
      placeholder="Escriba la asignatura"
      id="asignatura"
    />
    <p></p>
    <label for="nota"></label>
    <input
      type="this.notaber"
      v-model="nota"
      placeholder="Escriba la nota"
      id="nota"
    />

    <button v-on:click="examGrade()">Aceptar</button>

    <h2>Boletin de notas</h2>
    <div id="solution"></div>
    <p>Alumno: {{ nombre }}</p>
    <ul>
      <li v-for="(result, index) in finalBulletin" :key="index">
        {{ index }}. {{ result }}
      </li>
    </ul>
  </div>
  <!-- <div id="result"></div> -->
</template>

<script>
export default {
  name: "Grades",
  data: () => ({
    nombre: "",
    curso: "",
    nota: "",
    message: "",
    finalBulletin: [],
  }),

  methods: {
    examGrade() {
      let nota = this.nota;

      if (this.nota) {
        if (this.nota < 3) {
          this.message = "MUY DEFICIENTE";
        }
        if (this.nota < 5) {
          this.message = "INSUFICIENTE";
        }
        if (this.nota < 6) {
          this.message = "SUFICIENTE";
        }
        if (this.nota < 7) {
          this.message = "BIEN";
        }
        if (this.nota < 9) {
          this.message = "NOTABLE";
        }
        if (this.nota <= 10) {
          this.message = "SOBRESALIENTE";
        }

        this.finalBulletin.push(this.curso - " - " + this.message);
      }
      // printResult.innerHTML += "Introduzca una nota entre 0 y 10";
    },
  },
};
</script>
