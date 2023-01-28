<template>
    <label 
        :for="`${name}-input`"
        class="label-input"
    >
        {{ label }}
    </label>
    <input
        :id="`${name}-input`"
        :type="type"
        :name="name"
        :placeholder="placeholder"
        :value="modelValue"
        :required="required"
        class="input"
        @input="inputHandling"
    >
</template>

<script>
export default {
    name: 'UiInput',
    props: {
        type: {
            type: String,
            default: 'text',
        },
        name: {
            type: String,
            required: true,
        },
        placeholder: {
            type: String,
            default: '',
        },
        label: {
            type: String,
            default: '',
        },
        required: {
            type: Boolean,
            required: true,
        },
        modelValue: {
            type: String,
            default: '',
        },
    },
    emits: ['update:modelValue'],
    methods: {
        inputHandling({target}) {
            this.$emit('update:modelValue', target.value);
        },
    },
};
</script>
