<template>

    <a
        :href="href"
        :target="target"
        :rel="rel"
        role="button"
        class="relative inline-flex items-center px-4 py-2 border border-transparent leading-5 font-medium rounded-md text-white bg-darker neumorphic-shadow hover:bg-indigo-400 focus:outline-none focus:shadow-outline-indigo focus:border-indigo-600 active:bg-indigo-600 transition duration-150 ease-in-out"
    >
        <slot />
    </a>

</template>

<script>

export default {
    props: {
        href: {
            type: String,
            required: true
        },
        target: {
            type: String,
            default: null
        }
    },
    computed: {
        rel () {
            if (this.href.charAt(0) === '/') return null

            return 'noopener'
        }
    }
}

</script>
