<template>
    <button class="base-button" :class="{ [type + '-btn']: true, disabled: disabled }">
        <slot></slot>
    </button>
</template>
<script>
export default {
    props: {
        type: {
            type: String,
            default: "plain",
        },
        disabled: {
            type: Boolean,
            default: false,
        },
    },
};
</script>
<style scoped lang="scss">
$default-color: #3caed2;
$danger-color: #f56c6c;

.base-button {
    font-size: 13px;
    display: inline-block;
    vertical-align: top;
    min-width: 55px;
    min-height: 28px;
    border-radius: 2px;
    outline: none;
    focus-outline: none;

    &:active {
        border-style: solid;
    }

    &:hover {
        cursor: pointer;
    }
    &.disabled {
        opacity: 0.5;
        cursor: not-allowed;
    }
}

.plain-btn {
    color: #606266;
    background: #fff;
    border-color: #dcdfe6;
    &:hover {
        color: $default-color;
        background-color: rgba($default-color, 0.1);
        border-color: rgba($default-color, 0.2);
    }
    &.disabled:hover {
        color: #606266;
        background: #fff;
        border-color: #dcdfe6;
    }
}

.primary-btn {
    color: $default-color;
    background-color: rgba($default-color, 0.1);
    border-color: rgba($default-color, 0.2);
    &:hover {
        color: #fff;
        background-color: $default-color;
        border-color: $default-color;
    }
    &.disabled:hover {
        color: $default-color;
        background-color: rgba($default-color, 0.1);
        border-color: rgba($default-color, 0.2);
    }
}
.danger-btn {
    color: $danger-color;
    background-color: rgba($danger-color, 0.1);
    border-color: rgba($danger-color, 0.2);
    &:hover {
        color: #fff;
        background-color: $danger-color;
        border-color: $danger-color;
    }
    &.disabled:hover {
        color: $danger-color;
        background-color: rgba($danger-color, 0.1);
        border-color: rgba($danger-color, 0.2);
    }
}
</style>
