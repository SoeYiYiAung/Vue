<template>
    <div>
        {{students}}
    </div>

    <div>
        <button class="btn btn-primary" @click="$event => $emit('count',students.length)">Count Students</button>
        <button class="btn btn-primary" @click="$event => $emit('filter',students.filter(student=> student.age<18))">Filter Students</button>
    </div>
</template>

<script>
    export default {
        name:'ChildComponent',
        props:['students']
    }
</script>

<style scoped>

</style>