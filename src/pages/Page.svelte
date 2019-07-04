<script>
    let menuItems = [
        {
            text : 'Home',
            href : '/'
        },
        {
            text : 'About',
            href : '/about'
        },
        {
            text : 'Contacts',
            href : '/contacts'
        }
    ]
    let search = '';
    let submitted = false;

    function handleSubmit(e) {
        submitted = true;
    }
</script>

<style>
    header {
        background: black;
    }

    header a {
        color: white;
        text-decoration: none;
    }

    .search input {
        background: white;
        color: black;
    }

    .search button {
        background: blue;
        color: white;
    }
</style>

<div>
    <header>
        <ul class="menu">
            {#each menuItems as item}
                <li>
                    <a href="{item.href}">{item.text}</a>
                </li>
            {/each}
        </ul>

        <form class="search" on:submit="{handleSubmit}">
            <input type="text" bind:value={search} />
            <button type="submit">Search</button>
        </form>
    </header>

    <main>
        {#if submitted}
            <h2>Results for '{search}': </h2>
        {/if}
        <slot>
        </slot>
    </main>

    <footer>
        &copy; John Byte 2019
    </footer>
</div>