<template>
    <div>
        <span>Swagger client</span>
    </div>
</template>

<script>
    import SwaggerClient from 'swagger-client'

    export default {

        name: 'HelloWorld',
        props: {
            msg: String
        },
        methods: {},
        created() {
            new SwaggerClient('http://petstore.swagger.io/v2/swagger.json')
                .then(
                    client => client.apis.pet.addPet({id: 1, body: {name: "bobby"}}),
                )
                .then(
                    addPetResult => console.log(addPetResult.body),
                );
        }

    }
</script>
