<template>
    <div class="apollo-playground">
        <label for="query">Query:</label>
        <textarea id="query" v-model="query" placeholder="Enter your GraphQL query here"></textarea>
        <label for="variables">Variables:</label>
        <textarea id="variables" v-model="variables" placeholder="Enter variables as a JSON object"></textarea>
        <span>Click the buttons and see the console</span>
        <div class="buttons">
            <button @click="sendQuery">Query</button>
            <button @click="sendMutation">Mutate</button>
        </div>
    </div>
</template>

<script lang='ts'>
    import { defineComponent, PropType } from "vue";
    import { ApolloClient, DocumentNode, gql, NormalizedCacheObject } from "@apollo/client/core";

    export default defineComponent({
        props: {
            apolloClient: {
                type: Object as PropType<ApolloClient<NormalizedCacheObject>>,
            },

        },
        components: {

        },
        data() {
            return {
                variables: "",
                query: "",

            };
        },
        computed: {

        },
        methods: {
            async sendMutation() {
                const mutation = gql`${this.query}`;
                const res = await this.apolloClient?.mutate({
                    mutation,
                    variables: this.variables ? JSON.parse(this.variables) : {}
                });
                console.log("sendMutation", { res, mutation });
            },

            async sendQuery() {
                const query = gql`${this.query}`;
                const res = await this.apolloClient?.query({
                    query
                });
                console.log("sendQuery", { res, query });
            },

        },
    });

    </script>

<style lang="scss" scoped>
.apollo-playground {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 16px;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.1);
}

label {
    margin-bottom: 8px;
    font-weight: bold;
}

textarea {
    width: 100%;
    height: 150px;
    padding: 8px;
    border-radius: 4px;
    border: 1px solid #ccc;
    resize: vertical;
    margin-bottom: 16px;
}

.buttons {
    display: flex;
    gap: 8px;
}

button {
    padding: 8px 16px;
    border: none;
    border-radius: 4px;
    background-color: #4caf50;
    color: #fff;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.2s ease;
}

button:hover {
    background-color: #3e8e41;
}
</style>
