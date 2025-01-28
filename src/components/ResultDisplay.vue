<script>
export default {
    props: {
        result: [Number, String],
    },
};
</script>s
<template>
    <div class="alert alert-primary text-center">
        <strong>Resultado:</strong> {{ result }}
    </div>
</template>