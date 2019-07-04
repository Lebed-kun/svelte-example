<script>
    import Page from './Page.svelte';

    let contacts = [
        {
            prepend : `Email: `,
            href : 'test@example.com'
        },
        {
            prepend : 'Telegram: ',
            href : 'http://t.me/example'
        }
    ]
</script>

<Page>
    {#each contacts as contact}
        {@html contact.prepend}
        <a href="{contact.href}">{contact.href}</a>
        <hr>
    {/each}
</Page>