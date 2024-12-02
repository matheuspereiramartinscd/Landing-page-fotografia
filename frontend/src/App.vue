<template>
  <div class="container">
    <!-- Primeira Seção: Título, Subtítulo e Botão -->
    <div class="container02">
      <div class="page">
        <div class="firstpagetext">
          <div class="title">WEBSITE DE FOTOGRAFIA</div>
          <div class="subtitle">Fotos encantadoras</div>
          <button @click="scrollToMyWork" id="viewwork">
            Veja o meu trabalho
          </button>
        </div>
      </div>
      <div class="homephoto">
        <img src="@/assets/images/homephoto.jpg" alt="Home Photo" class="homephotoimg" />
      </div>
    </div>

    <!-- Seção de Fotos -->
    <div id="mywork" class="mywork">Fotos</div>

    <!-- Iteração sobre as fotos e descrições -->
    <div v-for="(photo, index) in photos" :key="index" class="photo">
      <img :src="photo.src" :alt="photo.title" class="photo01" />
      <div class="photodescription">
        <h1>{{ photo.title }}</h1>
        <span>{{ photo.description }}</span>
      </div>
    </div>
  </div>

  <!-- Seção de Contato -->
  <div class="contact">
    <p class="touch">Entre em contato!</p>
    <p class="call">Nos contate através do email ou telefone</p>
    <p class="email">Email: <b>matheuspereiramartins1993@gmail.com</b></p>
    <p class="phone">Telefone: <a class="red">(31)9840-0251</a></p>
  </div>

  <!-- Copyright -->
  <div class="copyright">
    <span class="copytext">
      Matheus Pereira Martins - &copy; 2023 - 
      <a href="https://github.com/matheuspereiramartinscd/mpm">https://github.com/matheuspereiramartinscd/mpm</a>
    </span>
  </div>
</template>

<script>
export default {
  name: "PhotographyPage",
  data() {
    return {
      photos: [
        {
          src: require("@/assets/images/photo01.jpg"),
          title: "Blue Bird",
          description:
            "A arara-azul é uma espécie de arara que se destaca pela beleza de suas penas azul-cobalto e por seu tamanho.",
        },
        {
          src: require("@/assets/images/photo02.jpg"),
          title: "Festival",
          description:
            "A festa junina é uma tradicional festividade popular no Brasil que acontece todo mês de junho.",
        },
        {
          src: require("@/assets/images/photo03.jpg"),
          title: "Red Bird",
          description:
            "A arara-vermelha-grande mede de 73 a 95 centímetros de comprimento e pesa até 1,5 quilo.",
        },
        {
          src: require("@/assets/images/photo04.jpg"),
          title: "Colorful",
          description: "Comidas coloridas fazem sucesso com todo mundo.",
        },
        {
          src: require("@/assets/images/photo05.jpg"),
          title: "Fruits",
          description:
            "As frutas são importantes para a nossa alimentação, pois garantem nutrientes essenciais para o nosso corpo.",
        },
      ],
    };
  },
  methods: {
    scrollToMyWork() {
      const element = document.getElementById("mywork");
      if (element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    },
  },
};
</script>

<style scoped>
@import "@/assets/css/style.css"; /* Certifique-se de ter o arquivo CSS corretamente configurado */

/* O resto do seu CSS será mantido no arquivo externo (style.css) */
</style>
