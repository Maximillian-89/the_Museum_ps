<template>
    <header>
        <div class="container-fluid">
            <div class="custom-container pt_50">
                <div class="row">
                    <div class="col">
                        <div class="head-container">
                            <div class="logo">
                                <a href="javascript:void(0)"><h3>the<br>museum</h3></a>
                            </div>
                            <div id="menu-bar" class="d-md-none" @click="isMenuOpen = !isMenuOpen" :class="{'change' : isMenuOpen}">
                                <div id="bar1" class="bar"></div>
                                <div id="bar2" class="bar"></div>
                                <div id="bar3" class="bar"></div>
                            </div>
                            <div class="nav-container d-md-flex" :class="{'is-menu-open' : isMenuOpen}">
                                <nav>
                                    <ul>
                                        <li><a href="javascript:void(0)">visita</a></li>
                                        <li><a href="javascript:void(0)">cosa vedere</a></li>
                                        <li><a href="javascript:void(0)">chi siamo</a></li>
                                        <li><a href="javascript:void(0)">attività</a></li>
                                        <li><a href="javascript:void(0)">agenda</a></li>
                                    </ul>
                                </nav>
                                <div>
                                    <ul>
                                        <li class="language"><a href="javascript:void(0)">eng</a></li>
                                        <li>
                                            <ul>
                                                <li><a href="javascript:void(0)"><i class="fa-brands fa-facebook-f"></i></a></li>
                                                <li><a href="javascript:void(0)"><i class="fa-brands fa-instagram"></i></a></li>
                                                <li><a href="javascript:void(0)"><i class="fa-brands fa-twitter"></i></a></li>
                                            </ul>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <div>
                            <h1>archivio<br>storico</h1>
                            <p>
                                Una raccolta di tutti i momenti più importanti<br>nella storia del museo e dei suoi curatori.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>


<script>
export default {
    name: 'HeaderTop',
    data() {
        return {
            isMenuOpen: false,
        }
    }
}
</script>


<style lang="scss" scoped>
@import '@/assets/style/variables.scss';

    header {
        background: linear-gradient(0deg, rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('@/assets/img/image77.png'); 
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        text-transform: uppercase;
        color: $primaryMainColor;
    }
        .container-fluid {
            .head-container, .nav-container, nav {
                display: flex;
                align-items: center;

            }
        }
            .head-container {
                justify-content: space-between;
                position: relative;
            }

            .logo h3, nav li a {
                font-weight: 600;
                line-height: 2.9375rem;
            }

                nav li a, .language {
                    font-size: 1.3125rem;
                    line-height: 1.25rem;
                }

                .logo h3 {
                    font-size: 3.1875rem;
                }
                
                #menu-bar {
                    width: 45px;
                    height: 40px;
                    margin: 30px 0 20px 20px;
                    cursor: pointer;
                }

                .bar {
                    height: 5px;
                    width: 100%;
                    background-color: #fff;
                    display: block;
                    border-radius: 5px;
                    transition: 0.3s ease;
                    }

                    #bar1 {
                    transform: translateY(-4px);
                    }

                    #bar3 {
                    transform: translateY(4px);
                }
                .change {
                    display: block;
                }

                .change .bar {
                    background-color: white;
                }

                .change #bar1 {
                    transform: translateY(4px) rotateZ(-45deg);
                }

                .change #bar2 {
                    opacity: 0;
                }

                .change #bar3 {
                    transform: translateY(-6px) rotateZ(45deg);
                }

                .nav-container {
                    nav ul {
                        align-items: center;

                    }
                    nav ul li:not(:first-child) {
                        margin-left: 5rem;

                        a {
                            color: $primaryNavColor;
                        }
                    }

                    div {
                        margin-left: 2.5rem;

                        ul {
                            background: $primaryCommColor;
                            align-items: center;

                            .language {
                                padding: .9375rem 1.25rem;
                                border-right: .125rem solid $otherNavColor;
                            }
                            ul {
                                padding: 0 1.5625rem;

                                .fa-facebook-f {
                                    font-size: 1.25rem;
                                }
                                
                                .fa-instagram, .fa-twitter {
                                    font-size: 1.375rem;
                                }

                                .fa-instagram {
                                    padding: 0 1.4rem;
                                }
                            }
                        }
                    }

                    @media only screen and (max-width: 767px) {
                        flex-direction: column;
                        width: 100%;
                        position: absolute;
                        top: 110%;
                        background: $primaryCommColor;
                        transition: height 0.4s;
                        height: 0px;
                        overflow: hidden;
                        &.is-menu-open {
                            height: 25rem;
                        }
                    }
                }
            div:last-child {
                h1 {
                    font-weight: 300;
                    font-size: 6.125rem;
                    line-height: 98%;
                    letter-spacing: -0.04em;
                    padding-top: 10.3125rem;
                }

                p {
                    font-weight: 400;
                    font-size: 2.25rem;
                    line-height: 3.125rem;
                    display: flex;
                    align-items: center;
                    color: rgba(255, 255, 255, 0.5);
                    padding: 2.5rem 0 5rem 0;
                }
            }

@import '@/assets/style/mediaQueryHeader.scss';
</style>