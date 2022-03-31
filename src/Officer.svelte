<script>
  import { Card } from 'spaper';
  import Icon from 'mdi-svelte';
  import { mdiGithub } from '@mdi/js';

  export let image;
  export let name;
  export let title;

  export let mail, website, /* twitter, */ github;
  export let description;
</script>

<Card
  title={name}
  {image}
  imageAlt="{name}'s portrait"
  subTitle={title}
  width="12em"
>
  <p>{description}</p>
  <p slot="bottom" class="links">
    <a href={github} target="_blank">
      <!--<span><Icon path={mdiGithub} size="30px" /></span>-->
      <span><i class="fab fa-github" /></span>
    </a>

    <!-- check other options-->
    {#if mail}
      <a href={'mailto:' + mail}>
        <span><i class="fas fa-envelope" /></span>
      </a>
    {/if}

    {#if website}
      <a href={website} target="_blank">
        <span><i class="fas fa-laptop-code" /></span>
      </a>
    {/if}

    <!--
            {#if twitter}
                <a href={twitter} target="_blank">
                    <span><i class="fab fa-twitter"></i></span>
                </a>
            {/if} -->
  </p>
</Card>

<style>
  .links {
    margin-top: 2rem;
    display: flex;
    color: black;
    text-decoration: none;
  }

  a {
    background-image: none;
  }

  span {
    font-size: 30px;
    color: black;
  }
  span:hover {
    color: #0474dc;
  }
  .links,
  i:before {
    text-decoration: none !important;
  }
</style>
