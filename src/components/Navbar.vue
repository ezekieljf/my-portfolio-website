<template>
    <nav class="navbar navbar-expand-lg navbar-dark border-bottom border-secondary sticky-top" id="navibar">

        <div class="container-fluid px-4 px-lg-5">

            <a class="navbar-brand d-flex align-items-center" href="#">
                <span class="badge bg-dark text-info border border-secondary me-2">EF</span>
                <small class="fw-bold">Ezekiel Figueroa</small>
            </a>

            <div class="justify-content-end">
                <ul class="navbar-nav d-lg-flex d-none">
                    <li class="nav-item">
                        <a class="nav-link text-light small mx-lg-2" href="#about">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link text-light small mx-lg-2" href="#projects">Projects</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link text-light small mx-lg-2" href="#tools">Tools</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link text-light small mx-lg-2" href="#contact">Contact</a>
                    </li>
                </ul>

                <div class="dropdown dropstart d-lg-none d-flex">
                    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                    </button>
                    <ul class="dropdown-menu bg-dark" aria-labelledby="dropdownMenuButton1">
                        <li class="nav-item">
                            <a class="nav-link text-light small mx-lg-2" href="#about">About</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link text-light small mx-lg-2" href="#projects">Projects</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link text-light small mx-lg-2" href="#tools">Tools</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link text-light small mx-lg-2" href="#contact">Contact</a>
                        </li>
                    </ul>
                </div>
            </div>

        </div>
    </nav>
</template>