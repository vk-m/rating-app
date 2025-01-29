<template>
    <div v-if="isVisible" class="notification info">
        <p>{{ message }}</p>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted, watch } from 'vue';

const props = defineProps({
    message: {
        type: String,
        required: true,
    },
    duration: {
        type: Number,
        default: 3000,
    },
});

const isVisible = ref(true);

const closeNotification = () => {
    isVisible.value = false;
};

onMounted(() => {
    setTimeout(() => {
        closeNotification();
    }, props.duration);
});

watch(
    () => props.message,
    () => {
        isVisible.value = true;
        setTimeout(() => {
            closeNotification();
        }, props.duration);
    }
);
</script>


<style scoped lang="scss">
.notification {
    position: fixed;
    top: 20px;
    right: 20px;
    padding: 15px;
    border-radius: 8px;
    color: white;
    animation: slideIn 0.5s ease-out;

    &.info {
        background: rgba(54, 168, 160, 1);
    }

    @keyframes slideIn {
        from {
            transform: translateX(100%);
        }

        to {
            transform: translateX(0);
        }
    }
}
</style>