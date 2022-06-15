<template>
    <footer>
        <div class="container-fluid">
            <div class="row">
                <div class="col-12 col-md-4 pt_custom_1">
                    <div class="left_col">
                        <div class="top">
                            <h2>the museum</h2>
                            <p>Via Sant Ottavio, 44 - 10126 Torino</p>
                        </div>
                        <div class="center">
                            <img src="@/assets/img/image84.svg" alt="Fiat Logo">
                            <h3>main<br>pattern</h3>
                        </div>
                        <div class="bottom">
                            <ul>
                                <li><a href="javascript:void(0)"><i class="fa-brands fa-facebook-square"></i></a></li>
                                <li><a href="javascript:void(0)"><i class="fa-brands fa-twitter"></i></a></li>
                                <li><a href="javascript:void(0)"><i class="fa-brands fa-youtube"></i></a></li>
                                <li><a href="javascript:void(0)"><i class="fa-brands fa-pinterest"></i></a></li>
                                <li><a href="javascript:void(0)"><i class="fa-brands fa-instagram"></i></a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-12 col-md-4">
                    <div class="center_col">
                        <div class="top">
                            <ul>
                                <li><a href="javascript:void(0)">stampa</a></li>
                                <li><a href="javascript:void(0)">statuto e codice etico</a></li>
                                <li><a href="javascript:void(0)">privacy</a></li>
                            </ul>
                        </div>
                        <div class="bottom">
                            <ul>
                                <li><i class="fa-solid fa-phone"></i><span>011.0062713</span></li>
                                <li><a href="mailto:info@themuseum.it"><i class="fa-solid fa-envelope"></i>info@themuseum.it</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="col-12 col-md-4 px-0">
                    <div class="right_col">
                        <div class="top">
                            <h3>
                                Resta sempre aggiornato su mostre, workshop ed eventi
                            </h3>
                        </div>
                        <div class="center">
                            <form>
                                <div class="mb-5">
                                    <input type="email" placeholder="email" id="email">
                                </div>
                            </form>
                            <div>
                                <label class="form-check"><span>Accetto i termini e condizioni</span>
                                    <input type="checkbox" name="radio">
                                    <span class="checkmark"></span>
                                </label>
                            </div>
                        </div>
                        <div class="bottom">
                            <a href="javascript:void(0)">iscriviti alla newsletter<span><img src="@/assets/img/arrow.png" alt="Freccia News Letter"></span></a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="bg-footer-bottom">
                <div class="row">
                    <div class="col px-0">
                        <ul>
                            <li><h5>2020 the museum®</h5></li>
                            <li><h5>publicis sapient</h5></li>
                        </ul>
                    </div>
                </div>
            </div>    
        </div>
    </footer>
</template>


<script>
export default {
    name: 'FooterBottom'
}
</script>


<style lang="scss" scoped>
@import '@/assets/style/variables.scss';
@import '@/assets/style/formsCustoms.scss';

    footer {
        background: $primaryBgColor;
        color: $primaryMainColor;
    }

    .left_col {
        .top {
            h2 {
            font-weight: 700;
            font-size: 2rem;
            line-height: 2.5rem;
            letter-spacing: -0.04em;
        }
        
        p {
            font-weight: 400;
            font-size: 1rem;
            line-height: 1.6875rem;
            display: flex;
            align-items: center;
        }
    }

    .center {
        display: flex;
        padding-top: 4.0625rem;
        h3 {
            font-weight: 700;
            font-size: 1.375rem;
            line-height: 1.625rem;
            display: flex;
            align-items: center;
            padding-left: 1.875rem;
        }
    }
    
    .bottom {
        padding-top: 4.5rem;

        ul li {
            font-size: 1.375rem;
            
        }
        ul li:not(:last-child) {
            padding-right: 3.75rem;
        }
    }
    }

    .center_col {
        padding-top: 6.25rem;
        .top, .bottom {
            ul {
                flex-direction: column;
            }
        }

        .top {
            padding-top: 1.875rem;

            & li a {
                font-weight: 400;
                font-size: 1.375rem;
                line-height: 3.4375rem;
                align-items: center;
            }
        }

        .bottom {
            ul li:not(:last-child) {
                padding: 2.1875rem 0 1.875rem 0;
            }
            .fa-phone, .fa-envelope {
                padding-right: 1.25rem;
                font-size: 1.25rem;
            }
        }
    }

    .right_col {
        background: $secondaryBgColor;
            padding-top: 6.25rem;
            padding-bottom: 2rem;
            padding-left: 1.25rem;
        .top {
            h3 {
                font-weight: 400;
                font-size: 2rem;
                line-height: 2.625rem;
                display: flex;
                align-items: center;
                letter-spacing: -0.04em;
            }
        }
        .center {
            color: $primaryMainColor;
        }

        .bottom {
            display: flex;
            align-items: center;
            padding: 2.8125rem 0 2.5rem 0;

            a {
                font-weight: 600;
                font-size: 1.75rem;
                line-height: 2.25rem;
                letter-spacing: -0.02em;
                color: $primaryMainColor;
                text-decoration: underline;

                span {
                    padding-left: 1.5625rem;
                    vertical-align: middle;
                }
            }
        }
    }

    .bg-footer-bottom {
        & .col {
            background: $primaryCommColor;
            padding: 1.875rem 0;

            & ul {
                justify-content: space-between;

                li:nth-child(1) {
                    padding-left: 3.75rem;
                }
                li:nth-child(2) {
                    padding-right: 3.75rem;
                }

                li h5 {
                    color: $primaryBgColor;
                    font-weight: 400;
                    font-size: 1rem;
                    line-height: 1.375rem;
                    align-items: center;
                }
            }
        }
    }
    
    .left_col .top h2, 
    .left_col .center h3, 
    .center_col .top ul li a,
    .right_col .bottom a,
    .bg-footer-bottom li h5 {
        text-transform: uppercase;
    }

    .left_col p, .right_col .bottom span {
        text-decoration-line: underline;
    }

    #email {
        border: none;
        background: transparent;
        border-bottom: .0625rem solid $otherColor;
        opacity: 0.5;
        width: 84%;
        padding: 1.25rem 0;
        font-size: 1.375rem;
        font-weight: 400;
        line-height: 1.9375rem;
    }

@import '@/assets/style/mediaQueryFooter.scss';
</style>