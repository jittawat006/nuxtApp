<template>
    <div>
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">Navbar</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <a class="nav-link active" aria-current="page" href="/">Home</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="/about">About us</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="/limitMessage">Limit Message</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" href="/previewImage">Limit Message</a>
                        </li>
                    </ul>
                    <form class="d-flex" role="search">
                        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                        <button class="btn btn-outline-success" type="submit">Search</button>
                    </form>
                </div>
            </div>
        </nav>
        <footer class="bg-dark text-center text-white">
            <div class="container p-4 pb-0">
                <h4 class="mb-1">{{ name }}</h4>
                <section class="mb-4 d-flex">
                    <p>{{ address }}</p>
                    <p>{{ email }}</p>
                    <p>jittawat wahanarat</p>
                </section>
            </div>
            <div class="text-center p-3" style="background-color: rgb(255, 164, 36);">
                © 2023 SiteDB
                <a class="text-white" href="#"></a>
            </div>
        </footer>
    </div>
    <slot />
</template>
<style>
a {
    text-decoration: none;
    color: white;
}

section {
    justify-content: center;
    flex-direction: column;
}

footer {
    position: fixed;
    bottom: 0;
    width: 100%;
}
</style>
<script>
export default {
    data() {
        return {
            address: '79/189 ม.1 ต.สัตหีบ อ.สัตหีบ จ.ชลบุรี',
            email: '66309010006@tatc.ac.th',
            website: 'http://www.106planet.com/66309010006/website/',
            local: 'https://goo.gl/maps/mwYRz3V6iZMnYp6m7'
        }
    }
}
</script>