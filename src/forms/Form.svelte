<script>
    export let controller;
    let submitted = false;

    function handleSubmit(e) {
        e.preventDefault();
        submitted = controller(e);
    }
</script>

<div class="Form">
    {#if submitted}
        <span style="color: green; font-weight: bold;">Success!</span>
    {/if}
    
    <form on:submit="{handleSubmit}">
        Name:
        <input type="text" name="name" />
        <br>
        Email: 
        <input type="email" name="email" />
        <br>
        Text:
        <textarea name="text"></textarea>
        <br>
        <button type="submit">Submit</button>
    </form>
</div>