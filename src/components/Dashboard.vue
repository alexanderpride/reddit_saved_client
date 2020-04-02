<template>
    <div class="background">

        <Header class="header"></Header>

        <section>
            <div class="panel">
                <Panel></Panel>
            </div>

            <div class="items">
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

    section{
        display: flex;
    }

    .panel{
        flex-grow: 1;
        flex-shrink: 0;
        flex-basis: 30%;
        margin: 1%;
    }

    .items{
        flex-grow: 1;
        flex-shrink: 1;
        flex-basis: 66%;
        margin-right: 1%;
    }

</style>