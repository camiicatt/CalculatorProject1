<script>
  import bubble from '$lib/assets/bubble2.png';

    let display = $state('0.00');
    let firstNumber = 0;
    let startNewNumber = false;
    let array = [];

    function handleButtonClick(number){
        firstNumber += number;
        display = String(firstNumber.toFixed(2));
    }

    function resetButton(){
        firstNumber = 0;
        display = String(firstNumber.toFixed(2));
    }

</script>

<main>
    <div id="bubble-container">
        <img id="bubble" src={bubble} alt="Bubble" />
        <div class="number-display">${display}</div>

        <div class="button-grid">
            <button onclick={() => handleButtonClick(0.01)}>1¢</button>
            <button onclick={() => handleButtonClick(0.05)}>5¢</button>
            <button onclick={() => handleButtonClick(0.10)}>10¢</button>
            <button onclick={() => handleButtonClick(0.25)}>25¢</button>
            <button onclick={() => handleButtonClick(0.50)}>50¢</button>
            <button onclick={() => handleButtonClick(1.00)}>$1</button>
        </div>

        <div id="reset-button">
            <button onclick={() => resetButton()}>Reset</button>
        </div>  
    </div>

  </main>
  
  <style>
    main {
      min-height: 100dvh;
      display: grid;
      place-items: center;
    }
  
    #bubble {
      width: 100%;
      height:auto;
      display:block;
    }
    
    #bubble-container {
      position: relative;
      width: 500px;
    }

    .number-display {
    position: absolute;
    top: 25%;
    left: 50%;
    transform: translateX(-50%);

    background: #ffd6e7;
    color: #84445e;
    border: 1px solid rgba(255, 255, 255, 0.9);
    border-radius: 10px;

    width: 140px;
    padding: 12px;
    text-align: center;
    font-size: 28px;
    font-family: inherit;
    font-weight: 600;
    }
    
    :global(body) {
    margin: 0;
    font-family: "Avenir Next", "Trebuchet MS", sans-serif;
    }

    .button-grid {
    position: absolute;
    top: 38.5%;
    left: 50%;
    transform: translateX(-50%);
    width: 45%;

    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 6px;
    }

    .button-grid button {
  aspect-ratio: 1;
  background: rgba(255, 240, 247, 0.8);
  color: #865b73;
  border: 1px solid rgba(255, 255, 255, 0.9);
  border-radius: 10px;

  font-family: inherit;
  font-size: 22px;
  font-weight: 500;

  box-shadow: 0 2px 5px rgba(132, 68, 94, 0.08);
  cursor: pointer;
  transition: background 0.2s, transform 0.2s;
}

.button-grid button:hover {
  background: #ffe5f0;
  transform: translateY(-2px);
}

.button-grid button:active {
  transform: scale(0.95);
}

    .button-grid button:hover {
    background: #a3d0df;
    transform: translateY(-2px);
    }

    .button-grid button:active {
    transform: scale(0.95);
    }

    .button-grid button:focus-visible {
    outline: 3px solid #84445e;
    outline-offset: 3px;
    }

    #reset-button {
    position: absolute;
    top: 65%;
    left: 50%;
    transform: translateX(-50%);
    
    }

    #reset-button button {
    background: rgba(254, 215, 233, 0.8);
    color: #b2406d;
    border: 1px solid rgba(255, 255, 255, 0.9);
    border-radius: 12px;
    padding: 10px 24px;
    font-size: 20px;
    cursor: pointer;
    font-family: inherit;
    font-weight: 600;
    
    box-shadow: 0 4px 8px rgba(132, 68, 94, 0.15);
    cursor: pointer;
    transition: background 0.2s, transform 0.2s;

    }

    #reset-button button:hover {
    background: #e25690;
    transform: translateY(-2px);
    }


    main {
    min-height: 100dvh;
    display: grid;
    place-items: center;
    background: linear-gradient(
    120deg,
    #f7b3f4,
    #80b4d9,
    #ffd6e7,
    #b5a4ed
    );
    background-size: 400% 400%;
    animation: background-wave 8s ease-in-out infinite;
    }

    @keyframes background-wave {
    0%, 100% {
        background-position: 0% 0%;
    }
    25% {
        background-position: 100% 0%;
    }
    50% {
        background-position: 100% 100%;
    }
    75% {
        background-position: 0% 100%;
    }
    }
  </style>
