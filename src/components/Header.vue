<template>
    <header class="site-header border border-0 border-b border-gray-800">
        <div class="header--wrapper flex justify-between items-center p-5 lg:p-10">
            <div class="header-logo">
                <img src="../assets/images/demologo.png" alt="">
            </div>
            <nav class="main-navigation">
                <ul class="menu-list flex justify-end">
                    <li class="list--item mr-5">
                        <RouterLink :to="{name: 'event-list'}">Home</RouterLink>
                    </li>
                    <li class="list--item mr-5">
                        <RouterLink :to="{name: 'event-list'}">Events</RouterLink>
                    </li>
                    <li class="list--item mr-5">
                        <RouterLink :to="{name: 'about'}">About</RouterLink>
                    </li>
                    <li class="list--item mr-5">
                        <RouterLink :to="{name: 'event-list'}">Contact</RouterLink>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style lang="scss">
.header-logo {
    img {
        height: max(3rem, 4vw);
        filter: invert(1);
    }
}
</style>