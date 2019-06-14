<template>
    <div id="studentForm">
        <form v-on:submit.prevent="submitStudentDetails">
            <label for="name">Vardas</label>
            <input v-model="student.name" type="text" id="name">

            <label for="email">El.Pastas</label>
            <input v-model="student.email" type="email" id="email">

            <button>Prideti Studenta</button>
        </form>
    </div>
</template>

<script>
export default {
    name: 'StudentForm',
    data() {
        return {
            student: {
                name: '',
                email: ''
            }
        }
    },
    methods: {
        submitStudentDetails() {
            this.$emit('add:student', this.student)
        }
    }
}
</script>

