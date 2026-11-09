const quizData = [
    { cat: "Midnight", q: "What is the main character Kyung-mi's biggest disadvantage while being chased by the killer?", options: ["She cannot hear footsteps or sounds around her", "She cannot see in the dark", "She is trapped inside a locked building", "She cannot run fast"], answer: 0 },
    { cat: "Juvenile Justice", q: "What is the profession of the strict main character, Shim Eun-seok?", options: ["Defense Lawyer", "Juvenile Court Judge", "Police Detective", "School Principal"], answer: 1 },
    { cat: "Interstellar", q: "What is the primary mission of the team of astronauts travelling through space?", options: ["To find a new habitable planet for humanity", "To fight an alien invasion", "To explore a black hole for fun", "To fix a broken space station"], answer: 0 },
    { cat: "Sally", q: "What major hardship does Sally face at the beginning of her story, yet she stays strong and kind?", options: ["Losing all her wealth and becoming poor", "Moving to a different planet", "Forgetting all her memories", "Losing her ability to speak"], answer: 0 },
    { cat: "Stranger Things", q: "What is the main plot driving the friends in the series?", options: ["Searching for a missing boy", "Winning a science competition", "Building a time machine", "Escaping a haunted house"], answer: 0 },
    { cat: "Miraculous", q: "What makes Felix Fathom's character writing stand out the most to fans?", options: ["His moral ambiguity, sharp intelligence, and clever manipulation", "His constant clumsy mistakes", "His lack of interest in anyone else", "His fear of taking risks"], answer: 0 },
    { cat: "The Truman Show", q: "What shocking truth does Truman discover about his entire life?", options: ["His whole life is actually a live TV show without his knowledge", "He is a secret agent on a mission", "He lives on a spaceship in the future", "He has magical powers"], answer: 0 }
];

let currentQ = 0;
let score = 0;

function startShow() {
    document.body.classList.add('open');
    loadQuestion();
}

function loadQuestion() {
    const current = quizData[currentQ];
    document.getElementById('categoryTag').innerText = current.cat;
    document.getElementById('progressText').innerText = `Question ${currentQ + 1} of ${quizData.length}`;
    document.getElementById('questionText').innerText = current.q;
    
    const optionsGrid = document.getElementById('optionsGrid');
    optionsGrid.innerHTML = '';
    document.getElementById('nextBtn').style.display = 'none';

    current.options.forEach((opt, idx) => {
        const btn = document.createElement('button');
        btn.className = 'option-btn';
        btn.innerText = opt;
        btn.onclick = () => selectOption(idx, current.answer);
        optionsGrid.appendChild(btn);
    });
}

function selectOption(selectedIdx, correctIdx) {
    const buttons = document.querySelectorAll('.option-btn');
    buttons.forEach((btn, idx) => {
        btn.disabled = true;
        if (idx === correctIdx) btn.classList.add('correct');
        if (idx === selectedIdx && selectedIdx !== correctIdx) btn.classList.add('wrong');
    });

    if (selectedIdx === correctIdx) score++;
    document.getElementById('nextBtn').style.display = 'block';
}

function nextQuestion() {
    currentQ++;
    if (currentQ < quizData.length) {
        loadQuestion();
    } else {
        showResults();
    }
}

function showResults() {
    document.getElementById('quizBox').style.display = 'none';
    document.getElementById('resultsBox').style.display = 'block';
    document.getElementById('scoreDisplay').innerText = `${score} / ${quizData.length}`;
    setTimeout(() => { document.body.classList.remove('open'); }, 500);
}

function restartQuiz() {
    currentQ = 0;
    score = 0;
    document.getElementById('resultsBox').style.display = 'none';
    document.getElementById('quizBox').style.display = 'block';
    document.body.classList.add('open');
    loadQuestion();
}
