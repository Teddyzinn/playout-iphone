@charset "UTF-8";
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

:root{
    --size: max(5px, 1vmin);
    --heght: 80em;
    --pad: 1.25em;
    --border-radius: 6.666em;
    --gutter: calc(var(--pad) *2);
    --button-width: 0.333em;
    --notch-height: 3.33em;
    --notch-width: 33.3%;
    --notch-radius: calc(var(--border-radius) - calc(var(--pad) *2));
    --notch-duration: 0.333s;
    --ease: cubic-bezier(.666, 0, .4, 1);
    --easse-spring: cubic-bezier(.666, 0, .4, 1.2);
    --ease-out: cubic-bezier(.15, 0, .333, 1);
    --border-width: 0.4em;
    --deep-purple: 284;
    --gold: 30;
    --space-black: 215;
    --silver: 254;
    --c-h: var(--deep-purple);
    --c-s: 100%;
    --c-l: 50%;
}

@-webkit-keyframes appear{
    to{
        transform: scale3d(1, 1, 1);
        opacity: 1;
    }
}

@keyframes appear{
    to{
        transform: scale3d(1, 1, 1);
        opacity: 1;
    }
}

body{
    background: #00000a;
    display: flex;
    flex-direction: column;
    gap: 3em;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    font-family: 'Inter';
    font-size: var(--size);
}

.phone{
    position: relative;
    z-index: 1;
    aspect-ratio: 37/76;
    background: black;
    height: var(--heght);
    border-radius: var(--border-radius);
    box-shadow: 0 0 0.1em 0.25em hsl(var(--c-h), 20%, 25%), 0 0 0 var(--border-width) hsl(var(--c-h), 30%, 85%);
    box-sizing: border-box;
    opacity: 0;
    transform: scale3d(1.1, 1.1, 1);
    -webkit-animation: appear 1s var(--ease-out) forwards;
    animation: appear 1s var(--ease-out) forwards;
    --webkit-backface-visibility: hidden;
}

.phone::before{
    content: "";
    position: absolute;
    top: var(--border-radius);
    right: calc(var(--border-width) * -1);
    bottom: calc(var(--border-radius));
    left: calc(var(--border-width) * -1);
    border: 0.5em solid hsl(var(--c-h), 20%, 30%);
    border-left-width: 0; 
    border-right-width: 0;
}

.buttons{
    position: absolute;
    inset: calc(var(--border-width) * -1);
    pointer-events: none;
}

.buttons .left, .buttons .right{
    position: absolute;
    width: var(--button-width);
    display: flex;
    flex-direction: column;
    align-items: stretch;
    gap: 1.5em;
}
.buttons .left{
    right: 100%;
    top: calc(var(--border-radius) * 2);
}

.buttons .left .button:nth-child(1){
    height: 3em;
    margin-bottom: 0.5em;
}

.buttons .right{
    left: 100%;
    transform: scale3d(-1, 1, 1);
    top: calc(var(--border-radius) * 3);
}

.buttons .right .button{
    height: 9.5em;
}

.buttons .button{
    background: hsl(var(--c-h), 20%, 95%);
    height: 6em;
    box-shadow: inset -0.15em 0 0.1em black, inset 0 0 0.1em hsl(var(--c-h), 30%, 90%), inset 0 0.2em 0.1em hsl(var(--c-h), 30%, 90%), inset 0 -0.2em 0.1em hsl(var(--c-h), 30%, 90%), inset -0.1em 0.333em 0.1em rgba(0, 0, 0, 0.5), inset -0.1em -0.333em 0.1em rgba(0, 0, 0, 0.5);
}
