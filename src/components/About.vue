<template>
  <div class="about-container">
    <header>
      <div class="title-row">
        <h1>About Me</h1>
        <p>-</p>
      </div>
    </header>

    <body>
      <div class="text">
        <p>Hello! My name is João Henrique, but my friends call me jojo or John, as in my introduction, i'm currently a
          Front-End developer
          <!-- Intern at <a href="https://huawei.com.br" target="_blank">Huawei</a> -->
        </p>
        <p> My History with development began in 2019 when I come up to the college, and the first steps were with
          language C, learning the basics of logic programming and the basics syntaxes, I was excited to learn new
          things and got involved real quickly, but my passion with
          development really shined when I learned Object-oriented programming in Java at college.
          Them in 2021 i got my first development job at Huawei as a intern for web development.
        <p style="margin-top: 1rem">Here are a few technologies I've been working with:</p>
        <ul class="list-tech">
          <li>Vue</li>
          <li>HTML5</li>
          <li>CSS3</li>
          <li>JavaScript(ES6)</li>
          <li>Git</li>
          <li>Node</li>
        </ul>
        </p>
        <!--<h3>Personal Stufs</h3>
         <p>
          I have a very flexible personality, i like do workout and plainting, i've had experience meditating and
          writing some originals, i like to go to museums and galeries arts, my favorite subject at school was History
          and Geography.
          My favorite pass time is go out and dance(i am a good dancer), but also stay home and do things more tranquil
          like playing video games, watching movies and tv shows.
        </p> -->
      </div>
    </body>
  </div>
</template>
<script>
export default {
  name: "About",
  data() {
    return {

    }
  }
}
</script>
<style lang="scss">
@import "../assets/scss/main.scss";

.about-container {
  background: transparent;
  min-height: calc(100vh - 100px);
  padding: 0 20px;
}

.title-row {
  display: flex;
}

h1 {
  color: $primary-color;
  font-size: $font-sz-subtitle;
  font-weight: 600;
}

.text {
  display: flex;
  margin-top: 0;
  margin: 0 20px;
}

.list-tech {
  display: grid;
  grid-template-columns: repeat(2, minmax(140px, 200px));
  gap: 0px 10px;
  padding: 0;
  margin: 20px 0 0;
  overflow: hidden;
  list-style: none;

  li {
    display: flex;
    align-items: center;

    margin-bottom: 10px;
    padding-left: 20px;
    color: rgba(255, 255, 255, 0.8);
  }

  ::before {
    content: "▹";
    position: absolute;
    left: 0px;
    // line-height: 25px;
    color: #950041;
  }
}
</style>