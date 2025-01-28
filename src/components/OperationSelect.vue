<script>
export default {
    props: {
        modelValue: String,
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
    <select class="form-select mb-3" v-model="value">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
    </select>
</template>