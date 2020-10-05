<template>
    <div>
        <v-alert v-if="checkConsts('SUCCESS', alert.type)" type="success">
            {{ alert.msg }}
        </v-alert>
        <v-alert v-else-if="checkConsts('ERROR', alert.type)" type="error">
            {{ alert.msg }}
        </v-alert>
        <v-alert v-else-if="checkConsts('WARNING', alert.type)" type="warning">
            {{ alert.msg }}
        </v-alert>
        <v-alert v-else-if="checkConsts('INFO', alert.type)" type="info">
            {{ alert.msg }}
        </v-alert>
    </div>
</template>

<script>

import AlertConsts from './consts.js'

export default alert = {
    name: 'alert',
    props: {
        alert: {
            type: Object,
            required: true,
        }
    },
    data() {
        return {
        }
    },
    methods: {
        checkConsts(id, input) {
            return AlertConsts[id] == input;
        }
    }
}

export { AlertConsts }

</script>

<style>
.v-alert {
    text-align: center;
}
</style>
