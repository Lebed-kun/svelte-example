<script>
    import Form from './Form.svelte';

    function controller(e) {
        let input = e.currentTarget.querySelector('[name="text"]');

        if (input.value.indexOf('spam') === -1) {
            return true;
        }

        return false;
    }
</script>

<Form controller="{controller}" />