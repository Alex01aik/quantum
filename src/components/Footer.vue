<template>
    <footer class="container">
        <div class="logo"><a href="#">LOGO</a></div>
        <div class="footerInfo">
            <span class="footerInfoTitle">Information and high risk warning:</span>
            <p class="footerInfoBody">
                Trading with foreign exchange (FX), contract
                for differences (CFDs) and precious metals
                carries a high level of risk that may not be
                suitable for all investors. Leverage creates
                additional risk and loss exposure. Before you
                decide to trade foreign exchange or contract
                for differences, carefully consider your
                investment objectives, experience level, and
                risk tolerance.
            </p>    
        </div>
        <div class="footerInfo">
            <span class="footerInfoTitle">Legal disclaimer:</span>
            <p class="footerInfoBody">
                Forex trading entails significant risks and is not
                appropriate for all investors. The possibility of
                incurring substantial losses should be taken
                into account. It is therefore important to
                understand the possible consequences of
                investing. Traders should weigh their earning
                potential against the risks involved and act
                accordingly. Interactive Trade Ltd operating
                under brand and using domenLink domain
                within the European Economic Area.
            </p>
        </div>
        <div class="footerNav">
            <a class="footerLink" href="#">About us</a>
            <a class="footerLink" href="#">Instructions</a>
            <a class="footerLink" href="#">Platforms</a>
            <a class="footerLink" href="#contactBlock">Contact Us</a>
            <a class="footerLink" href="#">Sign In</a>
            <a class="footerLink" href="#">Sign up for free</a>
        </div>
        <div class="documentation">
            <a href="#">Copyright 2020, All Right Reserved</a>
            <a href="#">Terms and Conditions</a>
            <a href="#">Privacy Policy</a>
            <a href="#">Risk Warnings</a>
            <a href="#">Anti-Money Laundering</a>
        </div>
    </footer>
</template>

<style scoped>
footer{
    margin-top: 32px;
    display: grid;
    grid-template-columns: 1fr 2fr 2fr 1fr;
    grid-template-rows: 1fr 0.4fr;
    grid-template-areas: "l s s r" "b b b b";
    grid-gap: 30px;
}
.logo{
    grid-area: l;
}
.footerNav{
    grid-area: r;
}
.documentation{
    grid-area: b;
}
.footerInfoTitle{
    font-size: 18px;
    line-height: 30px;
    display: block;
    margin-bottom: 16px;
}
.footerInfoBody{
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 27px;
}
.footerNav{
    display: flex;
    flex-direction: column;
}
.footerLink{
    margin-bottom: 24px;
}
.documentation{
    display: flex;
    justify-content: space-between;
}
.documentation a{
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 27px;
    color: #828282;
}
@media screen and (max-width: 768px) {
    footer{
        grid-template-columns: 1fr;
        grid-template-rows: 0.5fr 1fr;
        grid-template-areas: "l" "s" "s" "r" "b";
    }
    .mainInfo{
        display: flex;
        flex-direction: column;
    }
    .logo{
        margin: 32px auto 64px auto;
    }
    .footerInfoTitle{
        text-align: center;
    }
    .footerInfoBody{
        margin-left: 70px;
        margin-right: 70px;
    }
    .documentation{
        flex-direction: column;
    }
    .documentation a{
        margin: 16px auto;
    }
    .footerNav{
        position: absolute;
        width: 90%;
        flex-direction: row;
        justify-content: space-around;
        margin-top: 86px;
    }
}
@media screen and (max-width: 480px) {
    footer{
        grid-template-rows: repeat(3, 1fr);
    }
    .mainInfo{
        display: grid;
        grid-template-rows: 1fr 1fr;
        grid-template-columns: 1fr;
    }
    .footerNav{
        flex-direction: column;
        margin-top: 76px;
    }
    .footerInfoTitle{
        text-align: left;
    }
    .footerInfoBody{
        margin: 0;
    }
}
</style>