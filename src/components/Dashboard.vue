<template>
    <div>
        <Header></Header>

        <section>
            <Panel class="panel"></Panel>
            <div class="saved-container">
                <saved-item></saved-item>
            </div>
        </section>
    </div>
</template>

<script>
    import Header from "@/components/Header";
    import Panel from "@/components/Panel";
    import SavedItem from "@/components/SavedItem";

    export default {
        name: "Dashboard",
        components: {
            Header,
            Panel,
            SavedItem
        }
    }
</script>

<style scoped>
    section {
        display: flex;
        flex-direction: row;
        width: 100%;
    }

    .panel {
        flex: 0 1 40%;
        margin: 1%;
        border-radius: 3px;
    }

    .saved-container {
        flex: 1 1 auto;
        margin: 1%;
    }
</style>