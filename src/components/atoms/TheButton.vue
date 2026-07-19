<template>
    <button
        :class="[size, theme]"
    >
     {{  value  }}
    </button>
</template>
<script setup>
defineProps({
    value: {
        type: [String, Number],
        required: true,
    },
    width: {
        type: String,
        required: false,
        default: '100px',
    },
    theme: {
        type: String,
        required: false,
        validator: (value) => ['dark', 'light'].includes(value),
        default: 'light',
    }
});
</script>
<style scoped>
/* .button {
    width: v-bind(width);
} */
.normal {
    padding: 8px 16px;
    font-size: 16px;
}
.large {
    padding: 16px 32px;
    font-size: 24px;
}
.light {
    background-color: #1DA1F2;
    color: white;
}
.dark {
    background-color: black;
    color: #1DA1F2;
}
</style>