<template>
    <div class="modal">
        <div class="modal-content">
            <slot name="header"></slot>
            <slot></slot>
            <div class="modal-footer">
                <slot name="footer"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            $(this.$el).modal();
            //this.$el.addEventListener()
        },
        beforeDestroy(){
            //this.variavel = null;
            this.getModal().destroy();
            console.log('destruindo modal...');
        },
        destroyed(){
            console.log('modal destruído');
            //estrutura.destroy
            //estrutura.eventos.destroy()
            //console.log(Object.assign({}, this),'destroyed');
        },
        methods: {
            show() {
                this.getModal().open();
            },
            close() {
                this.getModal().close();
            },
            getModal() {
                return window.M.Modal.getInstance(this.$el);
            }
        }
    }
</script>