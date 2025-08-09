---
title: "The Unbroken Circle: An Interactive Exploration of Chanoyu"
collection: essays
permalink: /essays/chanoyu/
excerpt: 'An interactive exploration of the profound bond between Japanese Zen temples and the world of Chanoyu (茶の湯), the Way of Tea.'
date: 2025-01-01
venue: 'Culture & Essays'
classes: essays-chanoyu
author_profile: false
---

<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;400;700&display=swap" rel="stylesheet">

<style>
    .chanoyu-container {
        font-family: 'Noto Sans JP', sans-serif;
        background-color: #FDFBF5;
        color: #3a3a3a;
    }
    .bg-primary { background-color: #FDFBF5; }
    .bg-secondary { background-color: #F0EAD6; }
    .bg-accent { background-color: #6B8E23; }
    .text-accent { color: #6B8E23; }
    .border-accent { border-color: #6B8E23; }
    .highlight-accent { color: #DAA520; }
    .nav-link {
        transition: color 0.3s ease, border-color 0.3s ease;
        border-bottom: 2px solid transparent;
    }
    .nav-link:hover, .nav-link.active {
        color: #6B8E23;
        border-bottom-color: #6B8E23;
    }
    .timeline-item::before {
        content: '';
        position: absolute;
        top: 20px;
        left: -8px;
        width: 16px;
        height: 16px;
        border-radius: 50%;
        background-color: #F0EAD6;
        border: 3px solid #6B8E23;
        z-index: 1;
    }
    .modal-backdrop {
        transition: opacity 0.3s ease-in-out;
    }
    .modal-content {
        transition: transform 0.3s ease-in-out;
    }
    .chart-container {
        position: relative;
        width: 100%;
        max-width: 600px;
        margin-left: auto;
        margin-right: auto;
        height: 300px;
        max-height: 400px;
    }
    @media (min-width: 768px) {
        .chart-container { height: 350px; }
    }
</style>

<div class="chanoyu-container">
    <header class="bg-primary/80 backdrop-blur-md shadow-sm sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-3 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-accent">茶の湯</h1>
            <div class="hidden md:flex space-x-8">
                <a href="#path" class="nav-link py-2">The Path of Tea</a>
                <a href="#figures" class="nav-link py-2">Key Figures</a>
                <a href="#utensils" class="nav-link py-2">The Art of the Utensil</a>
                <a href="#temple" class="nav-link py-2">The Modern Temple</a>
            </div>
            <button id="mobile-menu-button" class="md:hidden text-accent">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <div id="mobile-menu" class="hidden md:hidden px-6 pb-4">
            <a href="#path" class="block py-2 nav-link">The Path of Tea</a>
            <a href="#figures" class="block py-2 nav-link">Key Figures</a>
            <a href="#utensils" class="block py-2 nav-link">The Art of the Utensil</a>
            <a href="#temple" class="block py-2 nav-link">The Modern Temple</a>
        </div>
    </header>

    <main>
        <section id="hero" class="container mx-auto px-6 py-16 md:py-24 text-center">
            <h2 class="text-4xl md:text-6xl font-bold mb-4">The Unbroken Circle</h2>
            <p class="text-lg md:text-xl text-gray-600 max-w-3xl mx-auto">An interactive exploration of the profound bond between Japanese Zen temples and the world of Chanoyu (茶の湯), the Way of Tea.</p>
        </section>

        <section id="path" class="py-16 md:py-24 bg-secondary">
            <div class="container mx-auto px-6">
                <h3 class="text-3xl font-bold text-center mb-4">The Path of Tea: A Historical Journey</h3>
                <p class="text-center text-gray-600 max-w-3xl mx-auto mb-12">The history of Chanoyu is not merely a sequence of events, but an evolution of philosophy and aesthetics deeply rooted in Zen. This timeline highlights the pivotal moments and figures who transformed a monastic ritual into a profound art form. Click on each event to uncover its significance.</p>
                <div id="timeline-container" class="relative border-l-4 border-accent ml-4 md:mx-auto md:max-w-3xl">
                </div>
            </div>
        </section>

        <section id="figures" class="py-16 md:py-24">
            <div class="container mx-auto px-6">
                <h3 class="text-3xl font-bold text-center mb-4">Key Figures of the Way of Tea</h3>
                 <p class="text-center text-gray-600 max-w-3xl mx-auto mb-12">The philosophy of Chanoyu was shaped by visionary monks and masters. Their insights and aesthetic choices defined the very soul of the practice, creating a legacy that endures to this day. Click on a portrait to learn about their pivotal contributions.</p>
                <div id="figures-container" class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                </div>
            </div>
        </section>

        <section id="utensils" class="py-16 md:py-24 bg-secondary">
            <div class="container mx-auto px-6">
                <h3 class="text-3xl font-bold text-center mb-4">The Art of the Utensil (道具の美)</h3>
                <p class="text-center text-gray-600 max-w-3xl mx-auto mb-12">For the collector and practitioner, utensils are not mere tools but vessels of history and philosophy. This section allows you to explore the major classifications of tea bowls (*chawan*), understand the aesthetic principles that guide their appreciation, and discover the art of creating a harmonious ensemble.</p>

                <div class="mb-12">
                    <h4 class="text-2xl font-bold text-center mb-6">Chawan Explorer</h4>
                    <div id="chawan-filters" class="flex justify-center space-x-2 md:space-x-4 mb-8">
                        <button class="filter-btn active px-4 py-2 rounded-full bg-accent text-white transition" data-filter="all">All (全て)</button>
                        <button class="filter-btn px-4 py-2 rounded-full bg-white text-gray-700 shadow-sm transition" data-filter="Wamono">Wamono (和物)</button>
                        <button class="filter-btn px-4 py-2 rounded-full bg-white text-gray-700 shadow-sm transition" data-filter="Kōraimono">Kōraimono (高麗物)</button>
                        <button class="filter-btn px-4 py-2 rounded-full bg-white text-gray-700 shadow-sm transition" data-filter="Karamono">Karamono (唐物)</button>
                    </div>
                    <div id="chawan-gallery" class="grid md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                    </div>
                </div>
            </div>
        </section>

        <section id="temple" class="py-16 md:py-24">
            <div class="container mx-auto px-6">
                <h3 class="text-3xl font-bold text-center mb-4">The Modern Temple: A Living Legacy</h3>
                <p class="text-center text-gray-600 max-w-3xl mx-auto mb-12">In the 21st century, Zen temples continue to be the spiritual heart of Chanoyu. Their role has evolved, blending ancient tradition with modern needs. Explore the multifaceted ways temples and their abbots sustain and shape the Way of Tea today, from hosting public gatherings to authenticating priceless artifacts.</p>
                
                <div class="max-w-4xl mx-auto">
                    <div class="border-b border-gray-200">
                        <nav id="temple-tabs" class="-mb-px flex space-x-6" aria-label="Tabs">
                        </nav>
                    </div>
                    <div id="temple-content" class="mt-8">
                    </div>
                </div>
            </div>
        </section>
    </main>
    
    <div id="modal-backdrop" class="fixed inset-0 bg-black bg-opacity-70 z-50 hidden opacity-0 modal-backdrop">
        <div id="modal-container" class="flex items-center justify-center min-h-screen p-4">
            <div id="modal-content" class="bg-primary rounded-lg shadow-xl p-8 max-w-2xl w-full relative transform scale-95 modal-content">
                <button id="modal-close-button" class="absolute top-4 right-4 text-gray-500 hover:text-gray-800">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
                <div id="modal-body"></div>
            </div>
        </div>
    </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {

    const timelineData = [
        {
            year: '1191',
            title: 'The Seed from the Continent',
            person: 'Myōan Eisai (明菴栄西)',
            content: `Rinzai Zen monk Eisai returns from China, bringing powdered green tea (*matcha*) and Zen teachings to Japan. He introduces tea as a tool to aid in *zazen* meditation, providing an "awakening effect" to combat drowsiness. This dual import establishes the foundational link between Zen and tea.`
        },
        {
            year: '1211',
            title: 'The Kissa Yōjōki (喫茶養生記)',
            person: 'Myōan Eisai',
            content: `Eisai authors "Drinking Tea for Health," Japan's first specialized book on tea. He strategically frames tea as a secular "miraculous remedy for health" to gain patronage from the Kamakura shogunate, ensuring the survival and spread of his Zen sect alongside the popularization of tea.`
        },
        {
            year: 'c. 1350',
            title: 'The Age of Karamono (唐物)',
            person: 'Ashikaga Shoguns',
            content: `During the Muromachi period, tea gatherings among the elite become opulent affairs focused on displaying luxurious, perfect art objects imported from China (*karamono*). Held in large reception rooms, these events are demonstrations of wealth and power, a stark contrast to tea's humble monastic origins.`
        },
        {
            year: 'c. 1480',
            title: 'The Wabi-cha Revolution',
            person: 'Murata Jukō (村田珠光)',
            content: `Studying under the monk Ikkyū Sōjun of Daitoku-ji, Jukō challenges the opulent *karamono* aesthetic. He champions humble, imperfect Japanese ceramics (Bizen, Shigaraki) and introduces Zen calligraphy (*bokuseki*) as the primary object in the tea room, shifting the focus from material wealth to spiritual depth.`
        },
        {
            year: 'c. 1500',
            title: 'Chazen Ichimi (茶禅一味)',
            person: 'Murata Jukō',
            content: `Jukō establishes the core philosophy of "Tea and Zen are one taste." This concept posits that the meticulous practice of tea is a form of active meditation, a direct path to enlightenment identical to the goal of Zen. Tea is no longer just a drink, but a *dō* (道), or Way.`
        },
        {
            year: 'c. 1580',
            title: 'The Apex of Wabi-cha',
            person: 'Sen no Rikyū (千利休)',
            content: `Rikyū, a merchant from Sakai and devoted Zen practitioner at Daitoku-ji, perfects the *wabi-cha* aesthetic. He codifies the practice, championing the small, rustic tea hut (*sōan*) and commissioning hand-formed Raku ware, the ultimate expression of simple, understated beauty.`
        },
        {
            year: '1591',
            title: 'The Sanmon Incident (山門事件)',
            person: 'Sen no Rikyū & Toyotomi Hideyoshi',
            content: `Rikyū is ordered to commit ritual suicide by the regent Hideyoshi. The pretext is a statue of Rikyū placed on Daitoku-ji's main gate, which forces Hideyoshi to walk beneath it. The true conflict lies between Rikyū's spiritual authority and *wabi* aesthetic versus Hideyoshi's absolute temporal power and love for ostentation.`
        }
    ];

    const figuresData = [
        {
            name: 'Myōan Eisai',
            kanji: '明菴栄西',
            title: 'The Tea Founder',
            image: 'https://placehold.co/400x400/F0EAD6/3a3a3a?text=栄西',
            content: `The Rinzai Zen monk who reintroduced powdered green tea (*matcha*) to Japan in 1191. He established tea as an essential aid for Zen meditation and strategically promoted its health benefits to secure patronage from the warrior class. His work, the *Kissa Yōjōki*, was instrumental in popularizing tea throughout Japan.`
        },
        {
            name: 'Murata Jukō',
            kanji: '村田珠光',
            title: 'The Father of Wabi-cha',
            image: 'https://placehold.co/400x400/F0EAD6/3a3a3a?text=珠光',
            content: `A Zen practitioner under Ikkyū Sōjun of Daitoku-ji, Jukō initiated a revolutionary aesthetic shift. He rejected the opulent Chinese *karamono* utensils in favor of rustic, imperfect Japanese wares. He established the core principle of *Chazen Ichimi* ("Tea and Zen are one taste"), laying the philosophical foundation for *wabi-cha*.`
        },
        {
            name: 'Sen no Rikyū',
            kanji: '千利休',
            title: 'The Perfecter of the Way',
            image: 'https://placehold.co/400x400/F0EAD6/3a3a3a?text=利休',
            content: `The most revered figure in the history of Chanoyu. Rikyū synthesized and perfected the *wabi-cha* aesthetic, codifying every aspect of the tea gathering, from architecture to utensils. He commissioned the first Raku ware bowls, the ultimate embodiment of *wabi* beauty. His profound spiritual authority ultimately led to his tragic conflict with the ruler Toyotomi Hideyoshi.`
        },
        {
            name: 'Ikkyū Sōjun',
            kanji: '一休宗純',
            title: 'The Zen Catalyst',
            image: 'https://placehold.co/400x400/F0EAD6/3a3a3a?text=一休',
            content: `An iconoclastic and brilliant abbot of Daitoku-ji. While not a tea master himself, his influence was pivotal. As the Zen teacher of Murata Jukō, he instilled the spiritual depth that led Jukō to reject materialism and find beauty in simplicity. His calligraphy was among the first *bokuseki* to be displayed in a tea room, setting a crucial precedent.`
        }
    ];

    const chawanData = [
        {
            origin: 'Karamono',
            name: 'Tenmoku (天目)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=天目',
            characteristics: 'Conical shape, small foot, dark iron glaze. Often used with a stand (*tenmokudai*). Varieties are defined by glaze effects like iridescent spots (*Yōhen*) or oil-spots (*Yuteki*).',
            context: 'From Song/Yuan China, originally used in Zen monasteries. The most prized *karamono* bowls, with three *Yōhen Tenmoku* designated as National Treasures of Japan.'
        },
        {
            origin: 'Kōraimono',
            name: 'Ido (井戸)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=井戸',
            characteristics: 'Simple, robust form, often with a visible potter\'s wheel mark (*rokuro-me*). Key features are a "bamboo node" foot and *kairagi* (梅花皮), a crackled glaze effect around the foot.',
            context: 'Joseon Dynasty (Korea) utilitarian rice bowls "discovered" by early tea masters. Considered the epitome of *wabi* beauty. The *Kizaemon Ido* at Daitoku-ji is a National Treasure.'
        },
        {
            origin: 'Kōraimono',
            name: 'Mishima (三島)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=三島',
            characteristics: 'Greyish clay with inlaid or stamped white slip designs under a clear glaze.',
            context: 'From the Korean "Buncheong" ware tradition. The name is said to come from the resemblance of the patterns to the calendars issued by Mishima Shrine in Japan.'
        },
        {
            origin: 'Wamono',
            name: 'Raku (楽)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=楽',
            characteristics: 'Hand-built (not wheel-thrown), low-fired, porous body. Primarily monochrome black (*kuro-raku*) or red (*aka-raku*).',
            context: 'First produced by the potter Chōjirō under the direct guidance of Sen no Rikyū. Considered the quintessential *wabi-cha* bowl, embodying the spirit of the master.'
        },
        {
            origin: 'Wamono',
            name: 'Shino (志野)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=志野',
            characteristics: 'Thick, feldspathic white glaze, often with orange "scorch" marks (*hi-iro*). Can have simple iron-underglaze designs.',
            context: 'Produced in Mino province during the Momoyama period. The first white glazed ware in Japan. The *Unohana-gaki* Shino bowl is a National Treasure.'
        },
        {
            origin: 'Wamono',
            name: 'Oribe (織部)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=織部',
            characteristics: 'Characterized by distorted, asymmetrical shapes (*kutsugata*, "shoe-shaped"), bold geometric patterns, and a distinctive deep green copper glaze.',
            context: 'Named after the tea master Furuta Oribe, a disciple of Rikyū. Represents a more dynamic and playful aesthetic than Rikyū\'s severe *wabi*.'
        },
        {
            origin: 'Wamono',
            name: 'Hagi (萩)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=萩',
            characteristics: 'Soft, whitish-pinkish glaze over a coarse, sandy clay body. Known for changing color and texture over time with use ("the seven transformations of Hagi").',
            context: 'Began in Hagi with Korean potters. Highly valued for its simple, warm feeling and the way it evolves with the user.'
        },
        {
            origin: 'Wamono',
            name: 'Karatsu (唐津)',
            image: 'https://placehold.co/600x400/3a3a3a/FDFBF5?text=唐津',
            characteristics: 'A broad category of rustic wares from Kyushu known for its earthy, strong character. Can be undecorated, iron-painted, or mottled.',
            context: 'Also began with Korean potters. The saying, "First Ido, second Raku, third Karatsu" reflects its high status among tea practitioners.'
        }
    ];

    const templeTabsData = [
        {
            id: 'stage',
            title: 'Living Stage',
            content: `
                <h5 class="text-xl font-bold mb-4">The Temple as a Venue</h5>
                <p class="mb-4">Temples with historical tea connections, like Daitoku-ji in Kyoto, are vibrant hubs for tea gatherings (*chakai*). They provide an unparalleled atmosphere of authenticity and tranquility.</p>
                <ul class="list-disc list-inside space-y-2">
                    <li><strong>Tsukigama (月釜):</strong> Regular monthly tea gatherings, often open to the public, that form the social and educational backbone of the tea community.</li>
                    <li><strong>Memorial Events:</strong> Prestigious, often exclusive gatherings commemorating great tea masters like Kobori Enshū (*Enshūki*) or celebrating annual traditions like the opening of a new tea jar (*kuchikiri*).</li>
                    <li><strong>Curated Experiences:</strong> High-end programs for small groups, often combining Zen meditation, a vegetarian meal, and a private tea ceremony in a historic room.</li>
                </ul>
            `
        },
        {
            id: 'educator',
            title: 'Cultural Educator',
            content: `
                <h5 class="text-xl font-bold mb-4">Sharing the Way of Tea</h5>
                <p class="mb-4">Temples have embraced the role of educators, offering *taiken* (体験), or "experience-based" introductions to Chanoyu for novices and tourists. These accessible sessions demystify the practice and provide a crucial revenue stream for maintaining historic properties.</p>
                <p>Participants are guided through basic etiquette, watch a demonstration (*otemae*), and are given the chance to whisk their own bowl of matcha, providing a hands-on taste of the ceremony's spirit without the need for rigorous training.</p>
            `
        },
        {
            id: 'arbiter',
            title: 'Arbiter of Value',
            content: `
                <h5 class="text-xl font-bold mb-4">The Power of Hakogaki (箱書)</h5>
                <p class="mb-4">Perhaps the most significant modern role of a high-ranking Zen abbot is as an authenticator of tea utensils through box-writing. A *hakogaki* is a written endorsement on the utensil's storage box that certifies its authenticity, gives it a poetic name (*mei*), and dramatically increases its cultural and monetary value.</p>
                <div class="border-2 border-dashed border-gray-400 p-4 rounded-lg bg-white">
                    <h6 class="font-bold text-center mb-2">Anatomy of a Hakogaki (Lid of a Kiribako 桐箱)</h6>
                    <div class="text-center space-y-2">
                        <div class="p-2 bg-gray-100 rounded"><strong>Top Right:</strong> Name of the object (e.g., 黒樂茶碗 - Black Raku Tea Bowl)</div>
                        <div class="p-2 bg-gray-100 rounded"><strong>Center:</strong> Poetic Name or *Mei* (銘) given to the object</div>
                        <div class="p-2 bg-gray-100 rounded"><strong>Bottom Left:</strong> Signature of the Abbot/Iemoto</div>
                        <div class="p-2 bg-gray-100 rounded"><strong>Beside Signature:</strong> The Abbot's/Iemoto's personal seal (*kaō* 花押)</div>
                    </div>
                </div>
                <p class="mt-4">This practice represents an unbroken chain of authority. The endorsement of an abbot from a temple like Daitoku-ji transforms an object into a certified piece of cultural heritage, underpinning the entire economic structure of the tea utensil world.</p>
            `
        }
    ];

    const timelineContainer = document.getElementById('timeline-container');
    timelineData.forEach(item => {
        const div = document.createElement('div');
        div.className = 'timeline-item mb-8 pl-8 relative cursor-pointer';
        div.innerHTML = `
            <div class="bg-white p-6 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300">
                <p class="text-sm highlight-accent font-bold">${item.year}</p>
                <h4 class="text-xl font-bold mb-2 text-accent">${item.title}</h4>
                <p class="font-semibold text-gray-700 mb-3">${item.person}</p>
                <div class="timeline-content hidden text-gray-600">
                    <p>${item.content}</p>
                </div>
            </div>
        `;
        timelineContainer.appendChild(div);
    });

    timelineContainer.addEventListener('click', (e) => {
        const item = e.target.closest('.timeline-item');
        if (item) {
            const content = item.querySelector('.timeline-content');
            content.classList.toggle('hidden');
        }
    });

    const figuresContainer = document.getElementById('figures-container');
    figuresData.forEach(figure => {
        const div = document.createElement('div');
        div.className = 'figure-card text-center cursor-pointer group';
        div.innerHTML = `
            <div class="relative overflow-hidden rounded-lg shadow-lg bg-secondary">
                <img src="${figure.image}" alt="${figure.name}" class="w-full h-auto transform group-hover:scale-105 transition-transform duration-300">
            </div>
            <h4 class="text-xl font-bold mt-4">${figure.name} <span class="text-lg text-gray-500">${figure.kanji}</span></h4>
            <p class="text-accent">${figure.title}</p>
        `;
        figuresContainer.appendChild(div);
        div.addEventListener('click', () => openModal(figure));
    });

    const chawanGallery = document.getElementById('chawan-gallery');
    const renderChawan = (filter = 'all') => {
        chawanGallery.innerHTML = '';
        const filteredData = filter === 'all' ? chawanData : chawanData.filter(c => c.origin === filter);
        filteredData.forEach(chawan => {
            const div = document.createElement('div');
            div.className = 'chawan-card bg-white rounded-lg shadow-md overflow-hidden cursor-pointer group';
            div.innerHTML = `
                <div class="relative">
                    <img src="${chawan.image}" alt="${chawan.name}" class="w-full h-48 object-cover">
                    <div class="absolute inset-0 bg-black bg-opacity-0 group-hover:bg-opacity-40 transition-all duration-300 flex items-center justify-center">
                        <p class="text-white text-lg font-bold opacity-0 group-hover:opacity-100 transition-opacity">Learn More</p>
                    </div>
                </div>
                <div class="p-4">
                    <h5 class="text-lg font-bold">${chawan.name}</h5>
                    <p class="text-sm text-gray-500">${chawan.origin}</p>
                </div>
            `;
            chawanGallery.appendChild(div);
            div.addEventListener('click', () => openModal(chawan, 'chawan'));
        });
    };

    document.querySelectorAll('.filter-btn').forEach(btn => {
        btn.addEventListener('click', () => {
            document.querySelector('.filter-btn.active').classList.remove('active', 'bg-accent', 'text-white');
            document.querySelector('.filter-btn.active').classList.add('bg-white', 'text-gray-700');
            btn.classList.add('active', 'bg-accent', 'text-white');
            btn.classList.remove('bg-white', 'text-gray-700');
            renderChawan(btn.dataset.filter);
        });
    });

    const templeTabsContainer = document.getElementById('temple-tabs');
    const templeContentContainer = document.getElementById('temple-content');
    templeTabsData.forEach((tab, index) => {
        const button = document.createElement('button');
        button.className = `temple-tab-btn whitespace-nowrap py-4 px-1 border-b-2 font-medium text-sm ${index === 0 ? 'border-accent text-accent' : 'border-transparent text-gray-500 hover:text-gray-700 hover:border-gray-300'}`;
        button.textContent = tab.title;
        button.dataset.target = tab.id;
        templeTabsContainer.appendChild(button);

        const contentDiv = document.createElement('div');
        contentDiv.id = tab.id;
        contentDiv.className = `temple-content-panel ${index !== 0 ? 'hidden' : ''}`;
        contentDiv.innerHTML = tab.content;
        templeContentContainer.appendChild(contentDiv);
    });
    
    templeTabsContainer.addEventListener('click', (e) => {
        if(e.target.classList.contains('temple-tab-btn')) {
            const targetId = e.target.dataset.target;
            
            document.querySelectorAll('.temple-tab-btn').forEach(btn => {
                btn.classList.remove('border-accent', 'text-accent');
                btn.classList.add('border-transparent', 'text-gray-500', 'hover:text-gray-700', 'hover:border-gray-300');
            });
            e.target.classList.add('border-accent', 'text-accent');
            e.target.classList.remove('border-transparent', 'text-gray-500', 'hover:text-gray-700', 'hover:border-gray-300');

            document.querySelectorAll('.temple-content-panel').forEach(panel => {
                panel.classList.add('hidden');
            });
            document.getElementById(targetId).classList.remove('hidden');
        }
    });

    const modalBackdrop = document.getElementById('modal-backdrop');
    const modalContent = document.getElementById('modal-content');
    const modalBody = document.getElementById('modal-body');
    const modalCloseButton = document.getElementById('modal-close-button');

    const openModal = (data, type = 'figure') => {
        let contentHTML = '';
        if (type === 'figure') {
            contentHTML = `
                <div class="md:flex md:space-x-6">
                    <div class="md:w-1/3 mb-4 md:mb-0">
                        <img src="${data.image}" alt="${data.name}" class="rounded-lg shadow-md w-full">
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-2xl font-bold">${data.name} <span class="text-xl text-gray-500">${data.kanji}</span></h3>
                        <p class="text-accent font-semibold mb-4">${data.title}</p>
                        <p class="text-gray-700">${data.content}</p>
                    </div>
                </div>
            `;
        } else if (type === 'chawan') {
            contentHTML = `
                <div>
                    <img src="${data.image}" alt="${data.name}" class="w-full h-64 object-cover rounded-lg mb-4">
                    <h3 class="text-2xl font-bold">${data.name}</h3>
                    <p class="text-sm text-gray-500 font-semibold mb-4">${data.origin}</p>
                    <div class="space-y-2">
                        <p><strong>Characteristics:</strong> ${data.characteristics}</p>
                        <p><strong>Context:</strong> ${data.context}</p>
                    </div>
                </div>
            `;
        }
        modalBody.innerHTML = contentHTML;
        modalBackdrop.classList.remove('hidden');
        setTimeout(() => {
            modalBackdrop.classList.remove('opacity-0');
            modalContent.classList.remove('scale-95');
        }, 10);
    };

    const closeModal = () => {
        modalBackdrop.classList.add('opacity-0');
        modalContent.classList.add('scale-95');
        setTimeout(() => {
            modalBackdrop.classList.add('hidden');
        }, 300);
    };

    modalCloseButton.addEventListener('click', closeModal);
    modalBackdrop.addEventListener('click', (e) => {
        if (e.target === modalBackdrop) {
            closeModal();
        }
    });

    const mobileMenuButton = document.getElementById('mobile-menu-button');
    const mobileMenu = document.getElementById('mobile-menu');
    mobileMenuButton.addEventListener('click', () => {
        mobileMenu.classList.toggle('hidden');
    });
    
    document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', (e) => {
            if (mobileMenu.classList.contains('hidden') === false) {
                mobileMenu.classList.add('hidden');
            }
        });
    });

    const navLinks = document.querySelectorAll('nav a.nav-link');
    const sections = document.querySelectorAll('main section');
    window.addEventListener('scroll', () => {
        let current = '';
        sections.forEach(section => {
            const sectionTop = section.offsetTop;
            if (pageYOffset >= sectionTop - 60) {
                current = section.getAttribute('id');
            }
        });

        navLinks.forEach(link => {
            link.classList.remove('active');
            if (link.getAttribute('href').substring(1) === current) {
                link.classList.add('active');
            }
        });
    });

    renderChawan();
});
</script>
