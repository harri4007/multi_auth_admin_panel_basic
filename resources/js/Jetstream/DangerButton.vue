<template>
    <button :type="type" class="inline-flex items-center justify-center px-4 py-2 bg-red-600 border border-transparent rounded-md font-semibold text-xs text-white uppercase tracking-widest hover:bg-red-500 focus:outline-none focus:border-red-700 focus:shadow-outline-red active:bg-red-600 disabled:opacity-25 transition" @click="visit">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        props: {
            type: {
                type: String,
                default: 'button',
            },
            href: {},
        },
        methods: {
            visit(event) {
                if (!this.href) {
                    return
                }
                event.preventDefault()
                this.$inertia.visit(this.href)
            }
        }
    }
</script>
