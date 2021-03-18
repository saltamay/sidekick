<template>
  <div class="min-h-screen text-gray-900">
    <header>
      <nav class="mx-auto px-4 sm:px-6 lg:px-8 py-2">
        <div class="flex justify-between items-center h-16">
          <!-- Logo -->
          <div class="flex-shrink-0 flex items-center">
              <inertia-link :href="route('home')">
                  <application-logo class="block h-9 sm:h-10 lg:h-12" />
              </inertia-link>
          </div>

          <div class="hidden space-x-8 sm:-my-px sm:ml-10 sm:flex" v-if="! $page.props.auth.user">
              <nav-link :href="route('login')" class="text-sm text-gray-700 underline">
                  Log in
              </nav-link>

              <nav-link :href="route('register')" class="ml-4 text-sm text-gray-700 underline">
                  Register
              </nav-link>
          </div>

          <div class="flex" v-else>
            <div class="hidden sm:flex sm:items-center sm:ml-6">
              <!-- Settings Dropdown -->
              <div class="ml-3 relative">
                <dropdown align="right" width="48">
                    <template #trigger>
                        <span class="inline-flex rounded-md">
                            <button type="button" class="inline-flex items-center px-3 py-2 border border-transparent text-sm leading-4 font-medium rounded-md text-gray-500 bg-white hover:text-gray-700 focus:outline-none transition ease-in-out duration-150">
                                <!-- {{ $page.props.auth.user.name }}

                                <svg class="ml-2 -mr-0.5 h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
                                    <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                                </svg> -->

                                <img src="https://www.gravatar.com/avatar/00000000000000000000000000000000?d=mp" alt="avatar" class="h-10 w-10 rounded-full" />
                            </button>
                        </span>
                    </template>

                    <template #content>
                        <dropdown-link :href="route('logout')" method="post" as="button">
                            Log Out
                        </dropdown-link>
                    </template>
                </dropdown>
              </div>
            </div>
          </div>

          <!-- Hamburger -->
          <div class="-mr-2 flex items-center sm:hidden">
            <button @click="showingNavigationDropdown = ! showingNavigationDropdown" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
              <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                  <path :class="{'hidden': showingNavigationDropdown, 'inline-flex': ! showingNavigationDropdown }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                  <path :class="{'hidden': ! showingNavigationDropdown, 'inline-flex': showingNavigationDropdown }" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>
        </div>   

        <!-- Responsive Navigation Menu -->
        <div :class="{'block': showingNavigationDropdown, 'hidden': ! showingNavigationDropdown}" class="sm:hidden">
            <div v-if="! $page.props.auth.user">
              <div class="pt-2 pb-3 space-y-1">
                  <responsive-nav-link :href="route('login')" :active="route().current('dashboard')">
                      Login
                  </responsive-nav-link>
              </div>

              <div class="pt-2 pb-3 space-y-1">
                  <responsive-nav-link :href="route('register')" :active="route().current('dashboard')">
                      Register
                  </responsive-nav-link>
              </div>
            </div>
            
            <div v-else>
              <!-- Responsive Settings Options -->
              <div class="pt-4 pb-1 border-t border-gray-200">
                  <div class="flex items-center justify-between px-4">
                      <div class="font-medium text-base text-gray-800">{{ $page.props.auth.user.name }}</div>
                      <div class="font-medium text-sm text-gray-500">{{ $page.props.auth.user.email }}</div>
                  </div>

                  <div class="mt-3 space-y-1">
                      <responsive-nav-link :href="route('logout')" method="post" as="button">
                          Log Out
                      </responsive-nav-link>
                  </div>
              </div>
            </div>
        </div> 
      </nav>
    </header>

    <!-- Page Content -->
    <main class="container mx-auto px-4 sm:px-6 lg:px-8 max-w-5xl">
        <navigation />
        <div class="mt-8">
            <slot />
        </div>
    </main>
  </div>
</template>

<script>
    import ApplicationLogo from '@/Components/ApplicationLogo'
    import Dropdown from '@/Components/Dropdown'
    import DropdownLink from '@/Components/DropdownLink'
    import Navigation from '@/Components/Nav'
    import NavLink from '@/Components/NavLink'
    import ResponsiveNavLink from '@/Components/ResponsiveNavLink'

    export default {
        components: {
            ApplicationLogo,
            Dropdown,
            DropdownLink,
            Navigation,
            NavLink,
            ResponsiveNavLink,
        },

        data() {
            return {
                showingNavigationDropdown: false,
            }
        }
    }
</script>
