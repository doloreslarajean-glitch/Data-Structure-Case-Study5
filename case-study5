// Initial game setup
let towers = {
    A: [3, 2, 1],
    B: [],
    C: []
};

let moves = 0;

// Move a disk between towers
function moveDisk(from, to) {

    if (towers[from].length === 0) {
        alert("There is no disk to move!");
        return;
    }

    let disk = towers[from][towers[from].length - 1];

    let destination = towers[to];

    if (
        destination.length > 0 &&
        destination[destination.length - 1] < disk
    ) {
        alert("You cannot place a bigger disk on a smaller disk!");
        return;
    }

    towers[from].pop();
    towers[to].push(disk);

    moves++;

    console.log(towers);
    console.log("Moves:", moves);

    checkWinner();
}

// Check if the player wins
function checkWinner() {

    if (towers.C.length === 3) {
        alert("Congratulations! You completed Towers of Hanoi!");
    }
}
You sent
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Case Study 05 | Towers of Hanoi</title>

<!-- Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Abril+Fatface&display=swap" rel="stylesheet">

<style>
/* =================================
   COLOR PALETTE AND GLOBAL STYLES
================================= */

:root {
    --background: #F8F2EF;
    --panel: #E7EBEE;
    --primary: #DEC3B3;
    --hover: #C9A995;
    --accent: #D2DCE4;
    --text: #5F5A57;
    --secondary: #827A75;
    --sidebar: #E5D6CE;
    --sidebar-light: #F0E5DF;
    --rose: #B98E83;
    --brown: #A98273;
    --blue: #8C9DA7;
    --dark-blue: #687C87;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    min-height: 100vh;
    background: var(--background);
    color: var(--text);
    font-family: "Segoe UI", sans-serif;
}

/* =================================
   MAIN LAYOUT
================================= */

.container {
    display: flex;
    min-height: 100vh;
}

.sidebar {
    width: 245px;
    padding: 35px 22px;
    background: linear-gradient(
        180deg,
        var(--sidebar-light),
        var(--sidebar)
    );
}

.logo {
    font-family: "Abril Fatface", serif;
    font-size: 25px;
    color: var(--brown);
    line-height: 1.2;
    margin-bottom: 12px;
}

.sidebar-subtitle {
    font-size: 12px;
    color: var(--secondary);
    margin-bottom: 45px;
}

.menu-label {
    font-family: "Proxima Nova", "Segoe UI", sans-serif;
    font-weight: bold;
    font-size: 11px;
    letter-spacing: 2px;
    color: var(--secondary);
    margin-bottom: 15px;
}

.menu-item {
    display: block;
    padding: 13px 15px;
    margin-bottom: 10px;
    border-radius: 10px;
    color: var(--text);
    text-decoration: none;
    font-size: 13px;
    transition: .2s;
}

.menu-item:hover,
.menu-item.active {
    background: var(--hover);
    color: white;
}

.step-number {
    display: inline-flex;
    width: 25px;
    height: 25px;
    border-radius: 7px;
    justify-content: center;
    align-items: center;
    margin-right: 8px;
    font-weight: bold;
    background: var(--accent);
    color: var(--dark-blue);
}

.menu-item.active .step-number {
    background: var(--rose);
    color: white;
}

/* =================================
   MAIN CONTENT
================================= */

.main-content {
    flex: 1;
    padding: 40px 5%;
    min-width: 0;
}

.top-label {
    color: var(--rose);
    font-size: 12px;
    font-weight: bold;
    letter-spacing: 3px;
    margin-bottom: 12px;
}

h1 {
    font-family: "Abril Fatface", serif;
    color: var(--brown);
    font-size: clamp(32px, 5vw, 48px);
    font-weight: normal;
}

.description {
    color: var(--secondary);
    font-size: 14px;
    margin-top: 10px;
    line-height: 1.7;
    max-width: 650px;
}

.header {
    margin-bottom: 30px;
}

/* =================================
   GAME INFORMATION CARDS
================================= */

.stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    margin-bottom: 25px;
}

.stat-card {
    background: var(--panel);
    border: 1px solid var(--accent);
    border-radius: 15px;
    padding: 20px;
}

.stat-card p {
    font-size: 12px;
    color: var(--secondary);
    margin-bottom: 8px;
}

.stat-card h2 {
    font-family: "Abril Fatface", serif;
    font-size: 28px;
    color: var(--brown);
    font-weight: normal;
}

/* =================================
   GAME PANEL
================================= */

.game-panel {
    background: white;
    border: 1px solid var(--accent);
    border-radius: 20px;
    padding: 25px;
    box-shadow: 0 8px 25px rgba(95, 90, 87, .05);
}

.game-heading {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 15px;
    margin-bottom: 15px;
}

.game-heading h2 {
    font-family: "Abril Fatface", serif;
    color: var(--brown);
    font-size: 23px;
    font-weight: normal;
}

.difficulty {
    padding: 10px 14px;
    border: 1px solid var(--accent);
    background: var(--background);
    border-radius: 9px;
    color: var(--text);
    font-family: inherit;
    cursor: pointer;
}

.instruction {
    background: var(--sidebar-light);
    border-left: 4px solid var(--rose);
    padding: 14px;
    border-radius: 8px;
    color: var(--secondary);
    font-size: 13px;
    line-height: 1.6;
    margin-bottom: 25px;
}

/* =================================
   TOWERS AND DISKS
================================= */

.towers {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    min-height: 310px;
    padding: 15px 5px 0;
}

.tower {
    position: relative;
    min-width: 0;
    border: 2px solid transparent;
    border-radius: 13px;
    background: var(--background);
    cursor: pointer;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    padding: 15px 5px 12px;
    transition: .2s;
    font-family: inherit;
}

.tower:hover {
    border-color: var(--hover);
    background: var(--sidebar-light);
}

.tower.selected {
    border-color: var(--rose);
    background: #F0E5DF;
}

.tower-label {
    position: absolute;
    top: 12px;
    font-size: 12px;
    font-weight: bold;
    letter-spacing: 1px;
    color: var(--dark-blue);
}

.rod {
    position: absolute;
    width: 9px;
    height: 185px;
    background: var(--blue);
    border-radius: 10px 10px 0 0;
    bottom: 48px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 0;
}

.disk-stack {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    justify-content: flex-start;
    width: 100%;
    min-height: 185px;
    pointer-events: none;
}

.disk {
    height: 27px;
    border-radius: 8px;
    margin-top: -1px;
    border: 2px solid rgba(255,255,255,.5);
    color: white;
    font-family: "Proxima Nova", "Segoe UI", sans-serif;
    font-weight: bold;
    font-size: 11px;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 2px 4px rgba(0,0,0,.08);
    transition: .2s;
}

.disk.top-disk {
    outline: 2px solid var(--rose);
}

.tower.selected .disk.top-disk {
    transform: translateY(-9px);
}

.disk-1 { background: #B98E83; }
.disk-2 { background: #C9A995; }
.disk-3 { background: #A98273; }
.disk-4 { background: #8C9DA7; }
.disk-5 { background: #687C87; }

.base {
    height: 10px;
    width: 90%;
    background: var(--dark-blue);
    border-radius: 8px;
    position: relative;
    z-index: 2;
    margin-top: 0;
}

.tower-name {
    margin-top: 12px;
    font-size: 12px;
    font-weight: bold;
    color: var(--secondary);
}

/* =================================
   GAME STATUS
================================= */

.status {
    margin-top: 22px;
    padding: 14px;
    text-align: center;
    border-radius: 10px;
    background: var(--panel);
    color: var(--dark-blue);
    font-size: 13px;
    line-height: 1.5;
}

.status.success {
    background: #E4EEE5;
    color: #456B4C;
    font-weight: bold;
}

.status.error {
    background: #F4E4DF;
    color: #995B4F;
}

/* =================================
   BUTTONS
================================= */

.controls {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 22px;
}

.btn {
    border: none;
    border-radius: 9px;
    padding: 12px 22px;
    font-family: "Proxima Nova", "Segoe UI", sans-serif;
    font-weight: bold;
    cursor: pointer;
    transition: .2s;
}

.btn-primary {
    background: var(--primary);
    color: var(--text);
}

.btn-primary:hover {
    background: var(--hover);
    color: white;
}

.btn-secondary {
    background: var(--accent);
    color: var(--dark-blue);
}

.btn-secondary:hover {
    background: var(--dark-blue);
    color: white;
}

.btn:disabled {
    opacity: .5;
    cursor: not-allowed;
}

/* =================================
   GAME RULES
================================= */

.rules {
    margin-top: 25px;
    padding: 22px;
    background: var(--sidebar-light);
    border-radius: 15px;
}

.rules h3 {
    font-family: "Abril Fatface", serif;
    font-size: 20px;
    color: var(--brown);
    font-weight: normal;
    margin-bottom: 12px;
}

.rules ol {
    padding-left: 20px;
    color: var(--secondary);
    font-size: 13px;
    line-height: 2;
}

/* =================================
   FOOTER
================================= */

footer {
    text-align: center;
    color: var(--secondary);
    font-size: 11px;
    margin-top: 30px;
}

/* =================================
   RESPONSIVE DESIGN
================================= */

@media (max-width: 750px) {
    .container {
        flex-direction: column;
    }

    .sidebar {
        width: 100%;
        padding: 20px;
    }

    .sidebar-subtitle {
        margin-bottom: 18px;
    }

    .menu-items {
        display: flex;
        flex-wrap: wrap;
        gap: 5px;
    }

    .menu-item {
        margin: 0;
        padding: 8px;
    }

    .main-content {
        padding: 25px 15px;
    }

    .stats {
        gap: 8px;
    }

    .stat-card {
        padding: 12px;
    }

    .stat-card h2 {
        font-size: 23px;
    }

    .towers {
        gap: 5px;
        padding-left: 0;
        padding-right: 0;
    }

    .game-panel {
        padding: 15px 10px;
    }

    .rod {
        height: 165px;
    }

    .disk-stack {
        min-height: 165px;
    }

    .disk {
        height: 24px;
        font-size: 9px;
    }
}
</style>
</head>

<body>

<div class="container">

    <!-- SIDEBAR -->
    <aside class="sidebar">

        <div class="logo">Data Structures<br>& Algorithms</div>

        <p class="sidebar-subtitle">
            Interactive Case Studies
        </p>

        <p class="menu-label">MAIN MENU</p>

        <nav class="menu-items">

            <a href="index.html" class="menu-item">
                <span class="step-number">01</span>
                Parking Lot - Stack
            </a>

            <a href="case2-parking-queue.html" class="menu-item">
                <span class="step-number">02</span>
                Parking Lot - Queue
            </a>

            <a href="case3-binary-tree.html" class="menu-item">
                <span class="step-number">03</span>
                Binary Tree
            </a>

            <a href="case4-binary-search.html" class="menu-item">
                <span class="step-number">04</span>
                Binary Search
            </a>

            <a href="case5-towers-hanoi.html" class="menu-item active">
                <span class="step-number">05</span>
                Towers of Hanoi
            </a>

        </nav>

    </aside>

    <!-- MAIN CONTENT -->
    <main class="main-content">

        <header class="header">

            <p class="top-label">
                CASE STUDY 05 / RECURSION
            </p>

            <h1>Towers of Hanoi</h1>

            <p class="description">
                Challenge yourself with the classic Towers of Hanoi
                puzzle! Transfer all disks from Tower A to Tower C
                while following the rules of the game.
            </p>

        </header>

        <!-- STATISTICS -->
        <section class="stats">

            <div class="stat-card">
                <p>YOUR MOVES</p>
                <h2 id="moveCount">0</h2>
            </div>

            <div class="stat-card">
                <p>MINIMUM MOVES</p>
                <h2 id="minimumMoves">7</h2>
            </div>

            <div class="stat-card">
                <p>DISKS</p>
                <h2 id="diskCount">3</h2>
            </div>

        </section>

        <!-- GAME -->
        <section class="game-panel">

            <div class="game-heading">

                <h2>Let's Play!</h2>

                <select id="difficulty" class="difficulty">
                    <option value="3">Easy - 3 Disks</option>
                    <option value="4">Medium - 4 Disks</option>
                    <option value="5">Hard - 5 Disks</option>
                </select>

            </div>

            <div class="instruction">
                <strong>How to play:</strong>
                Click a tower to select its top disk. Then click
                another tower to move it. You can only move one
                disk at a time and cannot put a larger disk on
                top of a smaller disk.
            </div>

            <!-- TOWER AREA -->
            <div class="towers">

                <button class="tower" id="tower-A"
                    onclick="selectTower('A')"
                    aria-label="Tower A">

                    <span class="tower-label">TOWER A</span>
                    <div class="rod"></div>
                    <div class="disk-stack" id="stack-A"></div>
                    <div class="base"></div>
                    <span class="tower-name">SOURCE</span>

                </button>

                <button class="tower" id="tower-B"
                    onclick="selectTower('B')"
                    aria-label="Tower B">

                    <span class="tower-label">TOWER B</span>
                    <div class="rod"></div>
                    <div class="disk-stack" id="stack-B"></div>
                    <div class="base"></div>
                    <span class="tower-name">AUXILIARY</span>

                </button>

                <button class="tower" id="tower-C"
                    onclick="selectTower('C')"
                    aria-label="Tower C">

                    <span class="tower-label">TOWER C</span>
                    <div class="rod"></div>
                    <div class="disk-stack" id="stack-C"></div>
                    <div class="base"></div>
                    <span class="tower-name">DESTINATION</span>

                </button>

            </div>

            <!-- STATUS MESSAGE -->
            <div class="status" id="status">
                Welcome! Select Tower A to begin.
            </div>

            <!-- CONTROLS -->
            <div class="controls">

                <button class="btn btn-primary"
                    onclick="resetGame()">
                    ↻ Reset Game
                </button>

                <button class="btn btn-secondary"
                    onclick="showSolution()">
                    Show Solution
                </button>

            </div>

        </section>

        <!-- RULES -->
        <section class="rules">

            <h3>Game Rules</h3>

            <ol>
                <li>Only one disk can be moved at a time.</li>
                <li>Only the top disk of a tower can be moved.</li>
                <li>A larger disk cannot be placed on a smaller disk.</li>
                <li>Move all disks from Tower A to Tower C to win.</li>
            </ol>

        </section>

        <footer>
            DATA STRUCTURES AND ALGORITHMS | CASE STUDY #5
        </footer>

    </main>

</div>

<script>

/* =================================
   GAME VARIABLES
================================= */

// Each tower is represented by an array.
// The last element represents the top disk.

let towers = {
    A: [],
    B: [],
    C: []
};

let numberOfDisks = 3;
let moves = 0;
let selectedTower = null;
let gameOver = false;
let isShowingSolution = false;

// Disk colors
const diskColors = {
    1: "disk-1",
    2: "disk-2",
    3: "disk-3",
    4: "disk-4",
    5: "disk-5"
};


/* =================================
   INITIALIZE GAME
================================= */

function initializeGame() {

    towers = {
        A: [],
        B: [],
        C: []
    };

    // Add disks from largest to smallest.
    for (let i = numberOfDisks; i >= 1; i--) {
        towers.A.push(i);
    }

    moves = 0;
    selectedTower = null;
    gameOver = false;
    isShowingSolution = false;

    updateDisplay();

    setStatus(
        "Welcome! Select Tower A to begin.",
        "normal"
    );
}


/* =================================
   SELECT AND MOVE DISKS
================================= */

function selectTower(towerName) {

    if (gameOver || isShowingSolution) {
        return;
    }

    // First click: select the source tower.
    if (selectedTower === null) {

        if (towers[towerName].length === 0) {

            setStatus(
                "This tower is empty. Select another tower.",
                "error"
            );

            return;
        }

        selectedTower = towerName;

        setStatus(
            "Tower " + towerName +
            " selected. Now choose a destination tower.",
            "normal"
        );

        updateDisplay();

        return;
    }

    // Clicking the same tower cancels selection.
    if (selectedTower === towerName) {

        selectedTower = null;

        setStatus(
            "Selection cancelled. Choose a tower.",
            "normal"
        );

        updateDisplay();

        return;
    }

    // Second click: attempt to move the disk.
    moveDisk(selectedTower, towerName);
}


/* =================================
   MOVE DISK FUNCTION
================================= */

function moveDisk(from, to) {

    const source = towers[from];
    const destination = towers[to];

    // Check if source has a disk.
    if (source.length === 0) {

        setStatus(
            "Invalid move! The source tower is empty.",
            "error"
        );

        selectedTower = null;
        updateDisplay();

        return;
    }

    // Get the top disk from the source.
    const disk = source[source.length - 1];

    // Get the top disk from the destination.
    const destinationTop =
        destination[destination.length - 1];

    // Validate the move.
    if (
        destination.length > 0 &&
        disk > destinationTop
    ) {

        setStatus(
            "Invalid move! You cannot place a larger disk on a smaller disk.",
            "error"
        );

        // Keep the selected source so the player
        // can choose another destination.
        updateDisplay();

        return;
    }

    // Remove the top disk from the source.
    source.pop();

    // Place the disk on the destination.
    destination.push(disk);

    // Increase move counter.
    moves++;

    selectedTower = null;

    updateDisplay();

    setStatus(
        "Great move! Disk " + disk +
        " moved from Tower " + from +
        " to Tower " + to + ".",
        "normal"
    );

    checkWinner();
}


/* =================================
   UPDATE GAME DISPLAY
================================= */

function updateDisplay() {

    const towerNames = ["A", "B", "C"];

    towerNames.forEach(name => {

        const stack = document.getElementById(
            "stack-" + name
        );

        const tower = document.getElementById(
            "tower-" + name
        );

        stack.innerHTML = "";

        // Display every disk.
        towers[name].forEach((disk, index) => {

            const diskElement =
                document.createElement("div");

            diskElement.className =
                "disk " + diskColors[disk];

            // Adjust width depending on disk size.
            const width =
                35 + (disk / numberOfDisks) * 55;

            diskElement.style.width = width + "%";

            diskElement.textContent = "Disk " + disk;

            // Highlight the top disk.
            if (index === towers[name].length - 1) {
                diskElement.classList.add("top-disk");
            }

            stack.appendChild(diskElement);

        });

        // Highlight selected tower.
        tower.classList.toggle(
            "selected",
            selectedTower === name
        );

    });

    // Update statistics.
    document.getElementById("moveCount").textContent =
        moves;

    document.getElementById("minimumMoves").textContent =
        Math.pow(2, numberOfDisks) - 1;

    document.getElementById("diskCount").textContent =
        numberOfDisks;
}


/* =================================
   CHECK WINNER
================================= */

function checkWinner() {

    if (towers.C.length === numberOfDisks) {

        gameOver = true;

        const minimum =
            Math.pow(2, numberOfDisks) - 1;

        let message =
            "Congratulations! You completed Towers of Hanoi!";

        if (moves === minimum) {

            message +=
                " Perfect! You solved it in the minimum number of moves.";

        } else {

            message +=
                " You completed the game in " +
                moves + " moves.";

        }

        setStatus(message, "success");

    }
}


/* =================================
   RESET GAME
================================= */

function resetGame() {

    initializeGame();

}


/* =================================
   CHANGE DIFFICULTY
================================= */

document.getElementById("difficulty")
    .addEventListener("change", function() {

        numberOfDisks = parseInt(this.value);

        initializeGame();

        setStatus(
            "Difficulty changed! You are now playing with " +
            numberOfDisks + " disks.",
            "normal"
        );

    });


/* =================================
   STATUS MESSAGE
================================= */

function setStatus(message, type) {

    const status =
        document.getElementById("status");

    status.textContent = message;

    status.className = "status";

    if (type === "success") {
        status.classList.add("success");
    }

    if (type === "error") {
        status.classList.add("error");
    }

}


/* =================================
   RECURSIVE TOWERS OF HANOI
================================= */

// This function generates the correct
// sequence of moves using recursion.

function hanoi(n, source, auxiliary, destination) {

    if (n === 1) {

        return [{
            from: source,
            to: destination,
            disk: 1
        }];

    }

    let result = [];

    // Step 1: Move n-1 disks to auxiliary tower.
    result = result.concat(
        hanoi(
            n - 1,
            source,
            destination,
            auxiliary
        )
    );

    // Step 2: Move largest disk to destination.
    result.push({
        from: source,
        to: destination,
        disk: n
    });

    // Step 3: Move n-1 disks to destination.
    result = result.concat(
        hanoi(
            n - 1,
            auxiliary,
            source,
            destination
        )
    );

    return result;

}


/* =================================
   SHOW AUTOMATIC SOLUTION
================================= */

async function showSolution() {

    if (isShowingSolution) {
        return;
    }

    // Start from a clean game.
    initializeGame();

    isShowingSolution = true;
    gameOver = true;

    const solution = hanoi(
        numberOfDisks,
        "A",
        "B",
        "C"
    );

    setStatus(
        "Showing the recursive solution...",
        "normal"
    );

    // Perform each generated move.
    for (const step of solution) {

        await new Promise(resolve =>
            setTimeout(resolve, 650)
        );

        towers[step.from].pop();
        towers[step.to].push(step.disk);

        moves++;

        updateDisplay();

        setStatus(
            "Moving Disk " + step.disk +
            " from Tower " + step.from +
            " to Tower " + step.to,
            "normal"
        );

    }

    isShowingSolution = false;
    gameOver = true;

    setStatus(
        "Solution completed! All disks are now in Tower C. Minimum moves: " +
        solution.length + ".",
        "success"
    );

}


/* =================================
   START THE GAME
================================= */

initializeGame();

</script>

</body>
</html>
