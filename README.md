# DiffLogicWGG



    randomWord = words[Math.floor(Math.random() * words.length) + 0];
    randomCheck = randomWord.split('');
    console.log(randomWord);
    console.log(randomCheck);



    function generateBlank() {
        for (i = 0; i < randomWord.length; i++) {
            wordBlank += "_";
        }
        wordBlank = wordBlank.split("");
        document.getElementById("blankW").innerHTML = wordBlank.join('');
    } generateBlank();

    console.log(wordBlank);

    document.onkeyup = function (event) {

        userGuess = event.key.toLowerCase();
        var userGuessIndex = randomWord.indexOf(userGuess);

        for (i = 0; i < randomWord.length; i++) {
            if (randomCheck[i].includes(userGuess)) {
                function updateBlank() {
                    wordBlank = wordBlank.splice([i], 1, userGuess);
                    randomCheck = randomCheck.splice([i], 1, '.');
                    document.getElementById("blankW").innerHTML = wordBlank.join('');
                } updateBlank();
            }