<script lang="js">
export default {
    name: 'OpSelect',
    props: {
        ops: { type: Object, required: true },
    },
    setup(props) {
        return { props }
    },
    methods: {
        playSound() {
            new Audio(require('../assets/sound/hover.mp3')).play()
        },
        updateOp(index) {
            this.$emit('update-op', index)
        },
        scrollToTop() {
            document.documentElement.scrollTo(0, 0);
        }
    }
}
</script>

<style scoped lang="scss">
@import './opSelect.scss';
</style>

<template>
    <div className="op-select">
        <div className="op-container --aspect-ratio: 1/2;">
            <div 
                className="op-tile"
                v-for="(op, index) in ops" :key="index"  
                @click="playSound(), updateOp(index), scrollToTop()"
            >
                <img
                    className="op-tile-image"
                    :src="op.images.thumbnail"
                    :alt="op.alias"
                    :aria-label="op.alias"
                />
            </div>
        </div>
    </div>
</template>
