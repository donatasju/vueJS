<template>
    <div id="studentTable">
        <table>
            <tr>
                <th>
                    VARDAS
                </th>
                <th>
                    El.Pastas
                </th>
            </tr>
            <tr v-for="student in students" :key="student.id">
                <td>
                    {{student.name}}
                </td>        
                <td>
                    {{student.email}}
                </td>
                
            </tr>
        </table>
    </div>
</template>

<script>
export default {
    name: 'StudentTable',
    props: {
        students: Array,
    }
}
</script>

<style scoped>
#studentTable {
    color: white;
}

table {
    width: 100%;
}

table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
}

</style>


