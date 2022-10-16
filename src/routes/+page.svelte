<script lang="ts">
    import data from "$lib/data.json"

    let reactionsToShow = data.reactions;

    let search = "";

    function onChange() {
    }
</script>

<main>
    <div class="flex flex-col font-epicfont justify-center text-center pt-4">
        <header class="fixed top-0 flex justify-center flex-col text-center w-full border-b border-gray-400 bg-white">
            <div class="text-5xl"><h1>Directory of Named Reactions</h1></div>
            <div class="text-2xl"><h1>why do these even exist</h1></div>
        </header>
        <br><br>
        <br>
        <br><br>
        <div class="flex flex-row">
            <div class="basis-1/6 w-max">
            </div>
            <div class="flex flex-col basis-4/6 w-max">
                <div class="w-full"><input on:input={onChange} bind:value={search} class="text-2xl border-2 w-full max-w-full" type="text" min="0" id="search" name="search" placeholder="Search..."></div>
                <div class="w-full">
                    <table class="border border-gray-400 lg:text-xl">
                        <tr class="bg-blue-100 border border-gray-400">
                            <td class="px-7">Name</td>
                            <td class="px-7">Category</td>
                        </tr>
                        {#each reactionsToShow as reaction}
                            <tr class="border border-gray-300">
                                <td>{reaction.name}</td>
                                <td>{reaction.category}</td>
                            </tr>
                        {/each}
                    </table>
                </div>
            </div>
            <div class="w-max basis-1/6">
            </div>
        </div>
    </div>
</main>
