<template>
    <div :class="[prefix, `${prefix}-${direction}`]">
        <slot></slot>
    </div>
</template>
<script>
export default {
    name: 'vutSteps',
    props: {
        activeStep: Number,
        direction: {
            type: String,
            default: 'horizontal'
        }
    },
    data(){
        return {
            prefix: this.global.prefix + 'steps',
            steps: []
        }
    },
    watch: {
        steps(){
            this.$children.forEach(function(item, index){
                item.index = index;
            })
        }
    }
}
</script>
