<script>
export default {
    props: {
        modelValue: Number,
        placeholder: String,
    },
    computed: {
        value: {
            get() {
                return this.modelValue;
            },
            set(newValue) {
                this.$emit("update:modelValue", newValue);
            },
        },
    },
};
</script>

<template>
    <input type="number" class="form-control mb-3" v-model.number="value" :placeholder="placeholder" />
</template>