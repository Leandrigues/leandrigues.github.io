<template>
  <div id="container-about">
    <div id="buttons-container">
      <button @click="section='about'" class="buttons"><span class="buttons-words">about</span>
      </button>
      <button @click="section='projects'" class="buttons"><span class="buttons-words">projects</span>
      </button>
      <button @click="section='links'" class="buttons"><span class="buttons-words">links</span>
      </button>
    </div>
    <transition name="fade">
      <div v-show="section=='about'" id="about">
        {{ about }}
      </div>
    </transition>
    <transition name="fade">
      <div id="projects-container" v-show="section=='projects'">
        <ul>
          <li v-for="project in projects" :key="project.title" class="project">
            <a :href="project.link" target="blank" class="project-title">{{ project.title }}:</a>
            <span v-html="project.description" class="project-description"></span>
          </li>
        </ul>
      </div>
    </transition>

    <transition name="fade">
      <div v-show="section=='links'" id="links">
        <a href="http://github.com/Leandrigues" target="blank"><img id="github" class="icons" src="@/assets/001-github.svg" alt=""></a>
        <a href="https://www.linkedin.com/in/leandro-rsilva/" target="blank"><img id="linkedin" class="icons" src="@/assets/003-linkedin-1.svg" alt=""></a>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      section: '',
      about: `Hello! I'm a computer science student at Universidade de São Paulo and a Software Engineer Intern at Amazon that likes playing chess and cooking.
        Currently, I'm interested in themes like web development, information security and cryptography. Feel free to keep in touch!`,

      projects: [
        {
          title: "CompReqs",
          link: "https://compreqs.netlify.app/",
          description: `CompReqs is a project developed in 2020 with the purpose of
            facilitating the search of requisites of a given subject in our institute.
            We made this by creating a graph view of the requisites. About technologies,
            we used: TypeScript, Node, Koa, PostgreSQL (and then migrated to Neo4j), Vue, Docker and BeautifulSoup.`
        },
        {
          title: "Computer Science Week (Semana da Computação)",
          link: "https://bcc.ime.usp.br/semana-old/2019/",
          description: `Semana da Computação is an anual event that promotes lecture series about 
            various themes within the scope of computer science and technology. The event is organized
            by computer science students of IME, and I participated organizing the event in 
            <a style='color: rgb(34,34,34)' href='https://bcc.ime.usp.br/semana-old/2018/ target='blank'>2018</a>
            and <a style='color: rgb(34,34,34)' href='https://bcc.ime.usp.br/semana-old/2019/' target='blank'>2019</a>
            editions.`
        },
        {
          title: "Hackathons",
          link: "https://interhack.xyz/2019/",
          description: `As a member of USPCodeLab, I was part of the organization of some hackathons,
            such as <a style='color: rgb(34,34,34)' href='https://hackathon.ime.usp.br/2018.2' target="_blank">HackathonUSP</a>, <a style='color: rgb(34,34,34)' href='https://www.facebook.com/uspcodelab/posts/2213552665349433/' target="_blank">HackFools</a> and <a style='color: rgb(34,34,34)' href='https://interhack.xyz/2019/' target="_blank">InterHack<a>.`
        }
      ]
    }
  }
}
</script>

<style scoped>
  #year {
    color: white
  }

  #projects-container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  ul {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    list-style: none;
    margin-top: -0.6rem;
  }

  li:before { 
    content: "";
    border-color: transparent rgb(34, 34, 34);  
    border-style: solid;
    border-width: 0.35em 0 0.35em 0.45em;
    display: block;
    height: 0;
    width: 0;
    left: -1em;
    top: 1.2em;
    position: relative;
  }

  .project-title {
    font-weight: bold;
    margin-right: 0.5rem;
    color: rgb(34,  34, 35)
  }

  .project {
    font-family: 'Manrope', sans-serif;
    text-decoration: tomato;
    width: 60%;
    margin-bottom: 1rem;
  }

  .project-description {
    line-height: 1.7rem;
  }
  
  .fade-enter-active {
    transition: opacity .9s;
  }

  .fade-enter {
    opacity: 0;
  }

  #github, #linkedin {
    margin-right: 20px;
  }

  .icons {
    height: 2rem;
  }

  #container-about {
    width: 100%;
    margin-top: 1rem;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  #about {
    font-family: 'Manrope', sans-serif;
    text-align: center;
    line-height: 1.8rem;
    width: 42%;
  }

  #buttons-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 1.6rem;
  }

  .buttons {
    border: none;
    background-color: transparent;
    color:rgb(24,24,24);
    outline: none;
    cursor: pointer;
  }

  .buttons-words {
    font-family: 'Manrope', sans-serif;
    font-weight: bold;
    transition: 0.5s;
    padding: 8px;
    font-size: 1rem;
  }

  .buttons-words:hover {
    background-color: rgb(34, 34, 34);
    color: rgb(249, 251, 232);
  }
</style>