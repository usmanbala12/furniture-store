<script>

let product_images = [["desktop-image-hero-1", "mobile-image-hero-1"], ["desktop-image-hero-2", "mobile-image-hero-2"], ["desktop-image-hero-3", "mobile-image-hero-3"]]

let selected_image = 1

const prevImage = () => {
    if(selected_image === 0) {
        selected_image = 2
    }
    selected_image -= 1 
}

const nextImage = () => {
    if(selected_image === 2){
        selected_image = 0
    }
    selected_image += 1
}
    
</script>

<div class="room-home">
    <div class="nav-bar">
        <img src="src/assets/images/logo.svg" alt="">
        <nav>
            <li><a href="#">home</a></li>
            <li><a href="#">shop</a></li>
            <li><a href="#">about</a></li>
            <li><a href="#">contact</a></li>
        </nav>
    </div>
    <div class="section-1">
            <!-- <img src={`src/assets/images/${product_images[0]}.jpg`} alt='chair'> -->
            <picture>
                <source srcset={`src/assets/images/${product_images[selected_image][1]}.jpg`} media="(max-width: 430px)"/>
                <img src={`src/assets/images/${product_images[selected_image][0]}.jpg`} alt="example" style="width: 100%; height: 100%"/>
            </picture>
        <div class="text-cont">
            <h1 class="heading">Discover innovative ways to decorate</h1>
            <p>We provide unmatched quality, comfort and style for property owners across the country. our experts form and function in bringing your vision to life. create a room in your style with our collection and make your property a reflection of you and what you love.</p>
            <a href="#">Shop now</a>
            <div class="img-btn">
                <div class="first-btn" on:click={prevImage}>
                    <img src="src/assets/images/icon-angle-left.svg" alt="icon-angle">
                </div>
                <div class="second-btn" on:click={nextImage}>
                    <img src="src/assets/images/icon-angle-right.svg" alt="icon-angle">
                </div>
            </div>
        </div>
    </div>
    <div class="section-2">
        <div class="img-cont">
           <img src="src/assets/images/image-about-dark.jpg" alt="">
        </div>
        <div class="text-cont">
            <h3 class="heading">
                About our furniture
            </h3>
            <p>
                Our multifunctional collection blends design and function to suit your 
                individual taste. Make each room unique, or pick a cohesive theme that best express 
                your interests and what inspires you. Find the furniture piece you need from traditional to contemporary 
                styles or anything in between. Product specialists are available to help you create your dream space.
            </p>
        </div>
        <div class="img-cont">
            <img src="src/assets/images/image-about-light.jpg" alt="">
        </div>
    </div>
</div>

<style>
    .room-home {
        display: flex;
        flex-direction: column;
    }

    .nav-bar {
        display: flex;
        align-items: center;
        justify-content: center;
        position: absolute;
        left: 4em;
    }

    .nav-bar > nav {
        display: flex;
        align-items: center;
    }

    nav li {
        list-style: none;
        margin: 1.4em;
    }

    nav li a {
        text-decoration: none;
        font-weight: 600;
        color: white;
    }

    .nav-bar img {
        padding: 1.5em;
    }

    .section-1 {
        display: flex;
        height: 70vh;
    }
    .section-1 > .text-cont {
        display: flex;
        flex-direction: column;
        padding: 5em;
        width: 40%;
        position: relative;
    }

    .section-1 > .text-cont > a {
        text-decoration: none;
        text-transform: uppercase;
        letter-spacing: 7px;
        margin-top: 2em;
        color: hsl(var(--clr-dark-gray));
    }

    .text-cont > a::after {
        content: url('src/assets/images/icon-arrow.svg');
        margin-left: 1.3em;
        color: hsl(var(--clr-dark-gray));
    }

    .img-btn {
        display: flex;
        position: absolute;
        width: 21.5%;
        height: 15%;
        background-color: black;
        bottom: 0;
        left: 0;
        align-items: center;
        justify-content: center;
    }

    .first-btn, .second-btn {
        padding: 0.5em;
        width: 100%;
        height: 100%;
        display: grid;
        place-items: center;
    }

    .first-btn:hover, .second-btn:hover{
        background-color: hsl(var(--clr-vdark-gray));
        cursor: pointer;
    }

    .section-1 picture {
        width: 60%;
    }

    .section-2 {
        display: flex;
    }


    .section-2 .text-cont {
        padding: 2em;
        width: 40%;
    }

    .section-2 .text-cont h3 {
        text-transform: uppercase;
        margin-bottom: 0.7em;
    }   

    .heading {
        color: hsl(var(--clr-black));
        margin-bottom: 1em;
    }

</style>