<script>
  import { Navbar, Button } from "spaper";
  import Officer from "./Officer.svelte";
  import { Discord, Youtube, Github } from "@icons-pack/svelte-simple-icons";
  let text, email;

  const officers = [
    {
      name: "Ankith Madadi",
      description: "ma dadi is hot",
      title: "President",
      image: "./images/ankith.png",
      github: "https://github.com/Monkeyank",
      // mail: "",
    },
    {
      name: "Anish Lakkapragada",
      description: "follow me on github",
      title: "Vice President",
      image: "./images/anish.jpeg",
      github: "https://github.com/anish-lakkapragada",
      mail: "anish.lakkapragada@gmail.com",
    },
    {
      name: "Snehil Kakani",
      description: "snek is kek",
      title: "Head of Frontend",
      image: "./images/snehil.jpg",
      mail: "kakanisnehil@gmail.com",
      github: "https://github.com/r2dev2",
      website: "https://snehilkakani.me",
    },
    {
      name: "Kush Khanna",
      description: "Description",
      title: "Head of Backend",
      image: "./images/html.png",
      github: "https://bitly.com/98K8eH",
      // mail: "",
    },
    {
      name: "Dhruv Gupta",
      description: "description",
      title: "Project Coordinator",
      image: "./images/html.png",
      github: "https://bitly.com/98K8eH",
      // mail: '',
      // website: '',
    },
  ];
</script>

<main>
  <Navbar fixed>
    <h3 slot="brand" class="brand-logo">
      <span> &lt</span>LWD /<span>&gt </span>
    </h3>

    <ul class="inline">
      <li><a href="#what">What We Do</a></li>
      <li><a href="#who">Who We Are</a></li>
      <!-- Thinking about not using a schedule -->
      <!-- <li><a href="#">Schedule</a></li> -->
      <li id="involved-li"><a href="#involved"> Get Involved!</a></li>
      <li>
        <Button href="https://github.com/lhswebdev?type=source" external>
          Github
        </Button>
      </li>
    </ul>
  </Navbar>

  <div class="webdiv">
    <h1 id="title">Lynbrook Web Development Club</h1>
  </div>

  <div class="intro" id="what">
    <h2 class="section-header">What We Do</h2>
    <h3 id="tldr">TLDR: We do Web Development. Crazy right?</h3>
    <p id="intro-p">
      Lynbrook's Web Development club teaches Web Development from the ground
      up. <br /> Starting from 0 experience all the way to modern front-end
      projects with popular frameworks. <br /> Oh, and did I mention we make
      projects. <em> Lots </em> of them.
    </p>
  </div>

  <h2 class="section-header" id="who">Officers</h2>

  <div class="officers">
    {#each officers as officer}
      <Officer class="officer" {...officer} />
    {/each}
  </div>

  <div style="text-align:center">
    <h2 class="section-header" id="involved">Get Involved!</h2>
    <p id="involved-p">
      In order to support our members' needs, we've created various ways to
      communicate.
    </p>
  </div>

  <!-- buttons for discord, youtube, and github-->
  <div class="contacts">
    <a
      href="https://discord.gg/XVJ7Rc3ZgQ"
      target="_blank"
      class="button cta discord"
    >
      Discord <Discord />
    </a>

    <a
      href="https://www.youtube.com/channel/UCM_BhJcNcFY5ZKlt6kecCqg"
      target="_blank"
      class="button cta youtube"
    >
      YouTube <Youtube />
    </a>

    <a
      href="https://github.com/lhswebdev/meeting-demos"
      target="_blank"
      class="button cta meeting-demos"
    >
      Meeting Demos <Github />
    </a>
  </div>

  <h2 class="section-header">Technologies We Use</h2>

  <div class="programming-images no-border">
    <img
      src="./images/JavaScript-logo.png"
      alt="JavaScript Logo"
      class="progimage no-border"
    />
    <img
      src="./images/typescript.png"
      alt="TypeScript Logo"
      class="progimage no-border"
    />
    <img
      src="./images/svelte.png"
      alt="Svelte Logo"
      class="progimage no-border"
    />
    <img src="./images/html.png" alt="HTML Logo" class="progimage no-border" />
    <img src="./images/css.png" alt="CSS Logo" class="progimage no-border" />
    <img
      src="./images/flask.svg"
      alt="Flask Logo"
      class="progimage no-border"
    />
    <img
      src="./images/react.png"
      alt="React Logo"
      class="progimage no-border"
    />
  </div>

  <h2 class="section-header">Got Questions? We got answers (hopefully)</h2>
  <div class="questions">
    <form action="https://formspree.io/f/mjvlopqj" method="POST">
      <input
        type="email"
        placeholder="Email"
        bind:value={email}
        class="center-block"
        id="subject-input"
      />
      <textarea
        name="message"
        type="textarea"
        bind:value={text}
        placeholder="Message"
        class="center-block"
        id="subject-text"
      />
      <div class="subtn" type="submit">
        <Button
          type="secondary"
          size="default"
          block
          outline
          disabled={email == null ||
            text == null ||
            email.length == 0 ||
            text.length == 0}>Send!</Button
        >
      </div>
    </form>
  </div>
</main>

<style>
  :root {
    --accent-color: #e74b36;
  }

  .webdiv {
    width: 100%;
    border-radius: 10px;
    height: 3em;
    text-align: center;
    font-size: 2em;
    margin-top: 3em;
    color: var(--accent-color);
    display: table;
  }

  #title {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
  }

  .programming-images {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 2em;
  }

  .progimage {
    margin: 1em;
    width: 100px;
  }

  .questions {
    text-align: center;
    position: relative;
    padding-bottom: 2rem;
  }

  .center-block {
    display: block;
    margin-right: auto;
    margin-left: auto;
  }

  #subject-input,
  #subject-text {
    margin-top: 1em;
    width: 30%;
  }

  #subject-text {
    margin-top: 1em;
    height: 6em;
  }

  .subtn {
    margin-top: 1rem;
    display: block;
    margin-right: auto;
    margin-left: auto;
    width: 30%;
  }

  .contacts {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5%;
  }

  .button,
  .cta {
    font-size: 1em;
  }

  .brand-logo {
    font-size: 3rem;
    color: var(--accent-color);
  }

  .officers {
    display: flex;
    flex-wrap: wrap;
    gap: 2em;
    justify-content: center;
  }

  .discord {
    background-color: #738adb;
  }

  .youtube {
    background-color: #ff0000;
  }

  .meeting-demos {
    background-color: #24292e;
  }

  .intro {
    text-align: center;
  }

  .inline {
    margin-top: 1em;
  }

  #tldr {
    font-size: 2em;
    margin-top: 1em;
  }

  #intro-p {
    font-size: 1em;
    margin-left: 0.25em;
    margin-right: 0.25em;
  }

  #involved-p {
    font-size: 1.25em;
    text-align: center;
    margin-bottom: 1.25em;
  }

  a {
    text-decoration: none;
  }

  .section-header {
    text-align: center;
  }

  @media screen and (max-width: 600px) {
    /* code only running on mobile */

    #intro-p {
      margin-left: 0.25em;
      margin-right: 0.25em;
    }

    #tldr {
      margin-left: 0.25em;
      margin-right: 0.25em;
    }

    #involved-li {
      margin-bottom: 1.75em;
    }

    #involved-p {
      font-size: 1.5em;
      margin-left: 0.2em;
      margin-right: 0.2em;
    }

    .contacts {
      display: flex;
      flex-wrap: wrap;
    }

    .button,
    .cta {
      font-size: 1.2em;
      margin-bottom: 0.6em;
    }

    /** the technologies section*/
    .progimage {
      margin: 0.25em;
      width: 50px;
    }

    #title {
      font-size: 1.75em;
    }

    #subject-input,
    #subject-text {
      width: 80%;
    }

    .subtn {
      width: 80%;
    }
  }
</style>
