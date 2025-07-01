```dataviewjs
const stats = [
    { name: "STR", label: "근력", roll: "3d6*5", row: 1, col: 1 },
    { name: "CON", label: "건강", roll: "3d6*5", row: 1, col: 2 },
    { name: "SIZ", label: "크기", roll: "(2d6+6)*5", row: 1, col: 3 },
    { name: "DEX", label: "민첩", roll: "3d6*5", row: 2, col: 1 },
    { name: "APP", label: "외모", roll: "3d6*5", row: 2, col: 2 },
    { name: "INT", label: "지능", roll: "(2d6+6)*5", row: 2, col: 3 },
    { name: "POW", label: "정신력", roll: "3d6*5", row: 3, col: 1 },
    { name: "EDU", label: "교육", roll: "(2d6+6)*5", row: 3, col: 2 },
    { name: "LUK", label: "행운", roll: "3d6*5", row: 3, col: 3 }
];

const css = `
    .coc-dice-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 16px;
    }
    .coc-dice-grid .stat-card {
        background-color:var(--background-secondary-alt);
        border-radius: 8px;
        padding: 20px 10px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        color: var(--text-faint);
        border: 1px solid var(--background-modifier-border);
        min-height: 140px;
    }
    .coc-dice-grid .stat-name {
        font-size: 1.1em;
        font-weight: bold;
        color: var(--text-faint);
        order: 1;
    }
    .coc-dice-grid .stat-value {
        font-size: 3.2em;
        font-weight: bold;
        line-height: 1.2;
        color: var(--text-normal);
        cursor: pointer;
        order: 2;
        margin: 5px 0;
    }
    .coc-dice-grid .dice-roller {
        font-size: inherit;
        background: none;
        border: none;
        box-shadow: none;
    }
    .coc-dice-grid .stat-label {
        font-size: 0.9em;
        color: var(--text-faint);
        text-transform: uppercase;
        order: 3;
    }
`;
const styleEl = document.createElement('style');
styleEl.innerHTML = css;
dv.container.appendChild(styleEl);

const grid = document.createElement('div');
grid.className = 'coc-dice-grid';

for (const stat of stats) {
    const card = document.createElement('div');
    card.className = 'stat-card';
    
    card.style.gridArea = `${stat.row} / ${stat.col}`;
    
    const nameEl = document.createElement('div');
    nameEl.className = 'stat-name';
    nameEl.textContent = stat.label;

    const valueEl = document.createElement('div');
    valueEl.className = 'stat-value';
    
    const codeEl = document.createElement('code');
    codeEl.textContent = `dice: ${stat.roll}|nodice`;

    const labelEl = document.createElement('div');
    labelEl.className = 'stat-label';
    labelEl.textContent = stat.name;

    valueEl.appendChild(codeEl);
    card.appendChild(nameEl);
    card.appendChild(valueEl);
    card.appendChild(labelEl);
    
    grid.appendChild(card);
}

dv.container.innerHTML = '';
dv.container.appendChild(styleEl);
dv.container.appendChild(grid);