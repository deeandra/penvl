<script>
    import "../../app.css"
    export let data
</script>

<div class="absolute inset-0 bg-white" data-theme="cupcake">
    <div class="navbar bg-white absolute">
        <div class="navbar-start">
          <div class="dropdown">
            <label tabindex="0" class="btn btn-ghost">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" /></svg>
            </label>
            <ul tabindex="0" class="menu menu-compact dropdown-content mt-3 p-2 shadow-xl bg-neutral text-white rounded-box w-52">
              <li><a href="/stories">Stories</a></li>
              <!-- <li tabindex="0">
                <a class="justify-between">
                  Parent
                  <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z"/></svg>
                </a>
                <ul class="p-2">
                  <li><a>Submenu 1</a></li>
                  <li><a>Submenu 2</a></li>
                </ul>
              </li> -->
              {#if data.session}
              <form action="/logout" method="POST">
                <li><button type="submit">Log Out</button></li>
              </form>
              {/if}
            </ul>
          </div>
          <a class="btn btn-ghost normal-case text-xl font-serif" href="/">Penvl</a>
        </div>
        <div class="navbar-end">
        {#if !data.session}
          <a class="btn" href="/login">Log In</a>
        <!-- {:else}
          <p class="px-3">Welcome back!</p> -->
        {/if}
      </div>
      </div>
    <slot />
</div>