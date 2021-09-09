<template>
    <v-snackbar
        v-model="snackbar"
        :multi-line="multiLine"
        :timeout="timeout"
        :color="(isError) ? 'error' : 'blue'"
    >
        {{ messages }}
        <template v-slot:action="{ attrs }">
        <v-btn
            color='white'
            text
            v-bind="attrs"
            @click = "childValueChangeEmit"
        >
            Close
        </v-btn>
        </template>
    </v-snackbar>
</template>

<script>
export default {
    name: "SnackBar",
    data: () => ({
        snackbar: true,
        multiLine: true,
        timeout: 2000,
    }),
    methods:{
        childValueChangeEmit () {
            this.snackbar = false;
            this.$emit('input', this.snackbar)
        }
    },
    props: {
        value: Boolean,
        isError: Boolean,
        messages: String
    },
    watch: {
        snackbar(){
            this.$emit('input', this.snackbar)
        }
    }
}
</script>

<style>

</style>