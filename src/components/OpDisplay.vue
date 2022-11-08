<script lang="js">
export default {
    name: 'OpDisplay',
    props: ['op'],
    setup(props) {
        return { props }
    }
}
</script>

<style scoped lang="scss">
@import './opDisplay.scss';
</style>

<template>
    <div className="op-display">
        <div className="display-container">
            <div className="image-container">
                <img
                    className="op-image"
                    :src="op.images.operator"
                    :alt="op.alias"
                    :aria-label="op.alias"
                />
                <span>{{ op.alias.toUpperCase() }}</span>
            </div>
            <div className="text-container">
                <p className="op-info">{{ op.info }}</p>
                <div className="display-title">
                    <img :src="op.images.icon" :alt="op.alias" aria-label="operator badge" />
                    <span>GENERAL</span>
                </div>
                <p>Name: {{ op.name }}</p>
                <p>Date of birth: {{ op.birthdate }}</p>
                <div className="op-location">
                    <p>Birthplace:&nbsp;</p>
                    <a :href="op.placeUrl" target="_blank">{{ op.birthplace }}</a>
                    <p v-if="op.birthplace">,&nbsp;</p>
                    <a :href="op.countryUrl" target="_blank">{{ op.country }}</a>
                    <img :src="op.images.flag" :alt="op.country" :aria-label="op.country" />
                </div>
                <p>Height: {{ op.height }}</p>
                <p>Weight: {{ op.weigth }}</p>
                <div className="equipment">
                    <div className="ability">
                        <span>ABILITY</span>
                        <div className="ability-image">
                            <img :src="op.images.ability" :alt="op.ability" :aria-label="op.ability" />
                        </div>
                        <p>{{ op.ability }}</p>
                        <p>{{ op.ability_desc }}</p>
                    </div>
                    <div className="weapon">
                        <span>WEAPON</span>
                        <div className="weapon-image">
                            <img :src="op.images.weapon" :alt="op.weapon" :aria-label="op.weapon" />
                        </div>
                        <p>{{ op.weapon }}</p>
                        <p>{{ op.weapon_type }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
