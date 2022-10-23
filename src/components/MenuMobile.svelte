<script>
  let open = false;
  $: menuVisiblity = open ? "block" : "hidden";
  $: menuButtonVisibility = open ? "hidden" : "block";
  const links = [
    { title: "home", href: "" },
    { title: "about me", href: "" },
    { title: "works", href: "" },
    { title: "contact", href: "" },
  ];
  const toggleMenu = () => (open = !open);
</script>

<img
  on:click={toggleMenu}
  on:keydown={() => null}
  class={`w-5 cursor-pointer ${menuButtonVisibility} md:hidden z-20`}
  src="images/icons8-menu-90.png"
  alt="menu button"
/>

<img
  on:click={toggleMenu}
  on:keydown={() => null}
  class={`w-5 cursor-pointer ${menuVisiblity} md:hidden z-20`}
  src="images/icons8-close-48.png"
  alt="menu button"
/>

<ul
  class={`${menuVisiblity} bg-indigo-900 absolute left-0 top-0 w-full p-10 rounded-b-3xl space-y-10 text-white text-center z-10`}
>
  {#each links as link}
    <li>
      <a href="#">{link.title}</a>
    </li>
  {/each}
</ul>
