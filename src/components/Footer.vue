<template>
    <footer class="page-footer">
        <p>You can find me in various places online:</p>
        <ul class="social-icons">
            <li class="social-icon">
                <a href="https://twitter.com/brouxhaha">Twitter</a>
            </li>
            <li class="social-icon">
                <a href="https://www.linkedin.com/in/andrewdebroux/">LinkedIn</a>
            </li>
            <li class="social-icon">
                <a href="https://codepen.io/brouxhaha/">Codepen</a>
            </li>
            <li class="social-icon">
                <a href="https://github.com/brouxhaha">Github</a>
            </li>
            <li class="social-icon">
                <a href="https://stackoverflow.com/users/2184055/brouxhaha?tab=profile">StackOverflow</a>
            </li>
        </ul>
    </footer>    
</template>

<style>
    .page-footer {
        text-align: center;
        padding: 20px;
        background: var(--main-cool);
    }

    .social-icons {
        list-style: none;
        display: flex;
        margin: 0;
        width: 100%;
        flex-flow: 0 1 auto;
        margin-left: -20px;
        justify-content: center;
    }

    .social-icon {
        margin-left: 20px;
    }
</style>
