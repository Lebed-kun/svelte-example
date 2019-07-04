<script>
    import Page from './Page.svelte';

    let posts = [
        {
            title : 'Test',
            author : 'JohnByte',
            created_at : new Date(),
            body : `
                Hello world! <div style="width: 100px; height: 100px; background: green;"></div>
            `
        },
        {
            title : 'Blog',
            author : 'admin',
            created_at : new Date(),
            body : `
                <strong>Blog starts</strong>
            `
        }
    ];

    export function formatDate(date, pattern) {
        let day = date.getDate();
        day = (day < 10 ? '0' : '') + day;
        let month = date.getMonth() + 1;
        month = (month < 10 ? '0' : '') + month;
        let year = date.getFullYear();
        let hour = date.getHours();
        hour = (hour < 10 ? '0' : '') + hour;
        let minute = date.getMinutes();
        minute = (minute < 10 ? '0' : '') + minute;

        let result = pattern;
        result = result.replace('%d', day);
        result = result.replace('%m', month);
        result = result.replace('%y', year);
        result = result.replace('%H', hour);
        result = result.replace('%M', minute);

        return result;
    }
</script>

<style>
    p {
        font-style: italic;
        color: grey;
    }
</style>


    <Page>
            {#each posts as post}
                <h3>{post.title}</h3>
                <hr>
                <p>
                    <span style="float: left;">{post.author}</span>
                    <span style="float: right;">{formatDate(post.created_at, '%d.%m.%y %H:%M')}</span>
                </p>
                <br>
                <hr>
                <div>
                    {@html post.body}
                </div>
                <hr><hr>
            {/each}
    </Page>
