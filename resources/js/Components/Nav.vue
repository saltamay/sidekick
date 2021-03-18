<template>
  <div class="flex w-full">
    <div class="w-1/5 max-w-xl mr-5">
    </div>
    <div class="w-4/5 max-w-4xl">
      <nav class="flex justify-between items-center text-sm">
        <ul class="flex border-b-4 pb-3 uppercase font-semibold space-x-10">
          <li>
            <inertia-link class="border-b-4 pb-3 border-blue" :href="route('home')">
              All Ideas (87)
            </inertia-link>
          </li>
          <li>
            <inertia-link class="text-gray-400 transition duration-75 ease-in border-b-4 pb-3 hover:border-blue" :href="route('home')">
              Considering (5)
            </inertia-link>
          </li>
          <li>
            <inertia-link class="text-gray-400 transition duration-75 ease-in border-b-4 pb-3 hover:border-blue" :href="route('home')">
              In Progress (1)
            </inertia-link>
          </li>
        </ul>
        <ul class="flex border-b-4 pb-3 uppercase font-semibold space-x-10">
          <li>
            <inertia-link class="text-gray-400 transition duration-75 ease-in border-b-4 pb-3 hover:border-blue" :href="route('home')">
              Implemeted (10)
            </inertia-link>
          </li>
          <li>
            <inertia-link class="text-gray-400 transition duration-75 ease-in border-b-4 pb-3 hover:border-blue" :href="route('home')">
              Closed (55)
            </inertia-link>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>