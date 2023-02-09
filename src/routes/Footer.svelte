<script>
    import Copyright from './Copyright.svelte'
</script>

<div class="wave">
    <svg width="360" height="34" viewBox="0 0 360 34" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0 7.91166C0 7.91166 43.5 25.7129 180 7.91166C316.5 -9.88957 360 7.91166 360 7.91166V214H0V7.91166Z" fill="#FFDD19"/>
    </svg>
    <svg width="360" height="34" viewBox="0 0 360 34" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M0 7.91166C0 7.91166 43.5 25.7129 180 7.91166C316.5 -9.88957 360 7.91166 360 7.91166V214H0V7.91166Z" fill="#136622"/>
    </svg>
</div>
<div id="kontak" class="wrapper">
    <div class="title">
        <h2>Hubungi Kami</h2>
    </div>

    <div class="contact">
        <ul>
            <li>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" stroke-width="2" stroke="#ffffff" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                    <path d="M7 10v4h3v7h4v-7h3l1 -4h-4v-2a1 1 0 0 1 1 -1h3v-4h-3a5 5 0 0 0 -5 5v2h-3" />
                </svg>
                <span><strong>jejamuran.id</strong>/explorejejamuran</span>
            </li>
            <li>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" stroke-width="2" stroke="#ffffff" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                    <rect x="4" y="4" width="16" height="16" rx="4" />
                    <circle cx="12" cy="12" r="3" />
                    <line x1="16.5" y1="7.5" x2="16.5" y2="7.501" />
                </svg>
                <span><strong>@jejamuran.id</strong>/explorejejamuran</span>
            </li>
            <li>
                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" stroke-width="2" stroke="#ffffff" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                    <path d="M3 21l1.65 -3.8a9 9 0 1 1 3.4 2.9l-5.05 .9" />
                    <path d="M9 10a0.5 .5 0 0 0 1 0v-1a0.5 .5 0 0 0 -1 0v1a5 5 0 0 0 5 5h1a0.5 .5 0 0 0 0 -1h-1a0.5 .5 0 0 0 0 1" />
                </svg>
                <span><strong>0812266174444</strong></span>
            </li>
        </ul>
    </div>
</div>
<Copyright />

<style>
    .wave {
        position: relative;
        margin-top: 20px;
        overflow: hidden;
    }

    .wave :last-child {
        position: absolute;
        top: 5px;
    }

    .wrapper {
        background: var(--clr-accent);
        color: white;
        padding-inline: 16px;
        padding-bottom: 16px;
    }

    .title h2 {
        font-family: 'Yeseva One', cursive;
        font-size: 32px;
        line-height: 48px;
        color: white;
    }

    .contact {
        margin-top: 10px;
        padding: 15px;
        background-color: var(--clr-brand);
        border-radius: 12px;
        font-size: 12px;
        line-height: 18px;
    }

    .contact ul {
        list-style: none;
    }

    .contact ul li {
        display: flex;
        align-items: center;
    }

    .contact ul li:not(:first-child) {
        margin-top: 12px;
    }

    .contact ul li svg {
        margin-right: 16px;
    }

    strong {
        font-weight: 600;
    }
</style>