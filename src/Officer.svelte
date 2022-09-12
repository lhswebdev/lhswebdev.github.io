<script>
  import { Card } from "spaper";
  import { Github } from "@icons-pack/svelte-simple-icons";
  import Icon from "@iconify/svelte";

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
      <span><Github /></span>
    </a>

    <!-- check other options-->
    {#if mail}
      <a href={"mailto:" + mail}>
        <span><Icon icon="ci:mail" /></span>
      </a>
    {/if}

    {#if website}
      <a href={website} target="_blank">
        <span><Icon icon="ci:window-code-block" /></span>
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
    gap: 0.75rem;
  }

  a {
    background-image: none;
    margin: 0 !important;
  }

  span {
    /* font-size: 30px; */
    color: black;
  }
  span:hover {
    color: #0474dc;
  }
  .links,
  i:before {
    text-decoration: none !important;
  }

  :global(svg) {
    height: 30px;
    width: 30px;
  }
</style>
