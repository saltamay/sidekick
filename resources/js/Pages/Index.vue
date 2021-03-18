<template>
    <app-layout>
        <div class="flex w-full">
            <div class="w-1/5 max-w-xl mr-5">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis reprehenderit commodi blanditiis harum dignissimos voluptatibus id aspernatur delectus, perspiciatis at voluptatum, praesentium, error beatae reiciendis molestiae? Animi ipsum unde ipsam?

                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Neque dolores sit, nesciunt consequuntur nobis blanditiis veniam doloremque culpa pariatur, nam natus voluptatum quaerat provident minima iste. Optio eum reiciendis tempora.

                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quibusdam tempora maiores ad molestiae totam est iure voluptates, commodi officiis soluta facere, eaque aspernatur unde dolores error ducimus sit blanditiis deleniti.
            </div>
            <div class="w-4/5 max-w-4xl">
                <!-- Filters -->
                <div class="filters flex space-x-6">
                    <div class="w-1/4">
                        <select name="category" id="category" class="w-full border-none rounded-xl px-4 py-2">
                            <option value="Category One">Category One</option>
                            <option value="Category One">Category One</option>
                            <option value="Category One">Category One</option>
                        </select>
                    </div>
                    <div class="w-1/4">
                        <select name="other_filters" id="other_filters" class="w-full border-none rounded-xl px-4 py-2">
                            <option value="Filter One">Filter One</option>
                            <option value="Other One">Other One</option>
                            <option value="Other One">Other One</option>
                        </select>
                    </div>
                    <div class="relative w-2/4">
                        <div class="absolute top-0 flex items-center h-full ml-2">
                            <svg class="w-4 text-gray-700" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                            </svg>
                        </div>
                        <input 
                            type="search" 
                            placeholder="Find an idea" 
                            class="w-full border-none rounded-xl bg-white pl-8 pr-4 py-2 placeholder-gray-900" />
                    </div>
                </div>
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Libero explicabo quod a porro reprehenderit tempora, quasi nostrum, tempore laboriosam ullam natus debitis modi voluptatem possimus expedita numquam laudantium repudiandae consequuntur.

                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Esse delectus non, deserunt nihil error molestiae autem laboriosam reprehenderit ut modi quidem repellat, iusto facilis tenetur? Assumenda harum facere iste facilis.
            </div>
        </div>
    </app-layout>
    
</template>

<style scoped>

</style>

<script>
    import AppLayout from '@/Layouts/App'

    export default {
        components: {
            AppLayout,
        }
    }
</script>
