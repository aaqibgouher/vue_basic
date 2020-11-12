<template>
    <div>
        <button class="btn btn-success btn-block" data-toggle="modal" data-target="#TodoAddModal">Add Todo</button>

        <div class="modal" id="TodoAddModal">
            <div class="modal-dialog">
                <div class="modal-content">

                <!-- Modal Header -->
                <div class="modal-header">
                    <h4 class="modal-title">Add Todo</h4>
                    <button type="button" class="close" data-dismiss="modal">&times;</button>
                </div>

                <!-- Modal body -->
                <div class="modal-body">
                    <div class="row">
                        <div class="col-sm-12">
                            <div class="form-group">
                                <label>Title</label>
                                <input type="text" class="form-control" v-model="title" @keypress.enter="saveTodo">
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Modal footer -->
                <div class="modal-footer">
                    <button type="button" class="btn btn-primary" data-dismiss="modal" @click="saveTodo">Save</button>
                </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "TodoAdd",
    data() {
        return {
            title: ""
        }
    },
    methods: {
        saveTodo() {
            this.$emit("saveTodoEvent", this.title);
            this.title = "";
        }
    }
}
</script>