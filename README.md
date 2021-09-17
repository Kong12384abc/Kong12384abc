<div class="card">
    <h2>KGNZ</h2>
</div>
<style>
    @property --rotate {
        syntax: "<angle>";
        initial-value: 132deg;
        inherits: false;
    }

    :root {
        --card-height: 65vh;
        --card-width: calc(var(--card-height) / 1.5);
    }

    body {
        min-height: 100vh;
        background: #212534;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .card {
        background: #191c29;
        width: var(--card-width);
        height: var(--card-height);
        padding: 3px;
        position: relative;
        border-radius: 6px;
        justify-content: center;
        align-items: center;
        display: flex;
        font-size: 1.5em;
        color: rgb(88 199 250 / 0%);
        cursor: pointer;
    }

    .card:hover {
        color: rgb(88 199 250 / 100%);
        transition: color 1s;
    }

    .card:hover:before,
    .card:hover:after {
        animation: none;
        opacity: 0;
    }

    .card::before {
        content: "";
        width: 104%;
        height: 102%;
        border-radius: 8px;
        background-image: linear-gradient(var(--rotate),
                red,
                yellow,
                green,
                blue,
                purple);
        position: absolute;
        z-index: -1;
        top: -1%;
        left: -2%;
        animation: spin 2.5s linear infinite;
    }

    .card::after {
        position: absolute;
        content: "";
        top: calc(var(--card-height) / 6);
        left: 0;
        right: 0;
        z-index: -1;
        height: 100%;
        width: 100%;
        margin: 0 auto;
        transform: scale(0.8);
        filter: blur(calc(var(--card-height) / 6));
        background-image: linear-gradient(var(--rotate),
                red,
                yellow,
                green,
                blue,
                purple,
                red);
        opacity: 1;
        transition: opacity 0.5s;
        animation: spin 2.5s linear infinite;
    }

    @keyframes spin {
        0% {
            --rotate: 0deg;
        }

        100% {
            --rotate: 360deg;
        }
    }
</style>
