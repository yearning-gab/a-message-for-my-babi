# a-message-for-my-babi
This message is made especially for you. I wrote this with a heart that's learned, changed, and still quietly hoping. I know I've made mistakes, but I've been trying to become better—not just for you, but for who I am. If there's even a small chance, I hope you can see that I'm trying to love you the right way this time.


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>A Message for the Girl who I Love Completely and more than Anything</title>

<style>
    body {
        margin: 0;
        padding: 0;
        background: #c7a77d;
        font-family: 'Courier New', monospace;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .container {
        text-align: center;
    }

    .note {
        margin-bottom: 15px;
        font-size: 14px;
        color: #3e2f1c;
    }

    button {
        padding: 12px 20px;
        border: none;
        border-radius: 8px;
        background: #3e2f1c;
        color: #fff;
        font-size: 14px;
        cursor: pointer;
        transition: 0.3s;
    }

    button:hover {
        background: #5a4226;
    }

    .card {
        display: none;
        margin-top: 20px;
        background: #f5f0e6;
        padding: 20px;
        border-radius: 10px;
        width: 320px;
        height: 300px;
        overflow-y: auto;
        text-align: left;
        box-shadow: 0 4px 15px rgba(0,0,0,0.2);

        transform: scale(0.8);
        opacity: 0;
        transition: all 0.5s ease;
    }

    .card.show {
        transform: scale(1);
        opacity: 1;
    }

    #text {
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 14px;
        color: #2c2c2c;
    }

    .cursor {
        display: inline-block;
        width: 8px;
        background: #2c2c2c;
        margin-left: 3px;
        animation: blink 1s infinite;
    }

    .replay {
        display: none;
        margin-top: 10px;
        background: #3e2f1c;
    }

    @keyframes blink {
        0%, 50%, 100% { opacity: 1; }
        25%, 75% { opacity: 0; }
    }
</style>
</head>

<body>

<div class="container">
    <div class="note">click this if you allow me to make things right</div>
    <button onclick="startMessage()">Click me</button>

    <div class="card" id="card">
        <div id="text"></div><span class="cursor"></span>
    </div>

    <button class="replay" id="replayBtn" onclick="replay()">Replay</button>
</div>

<audio id="bgm" src="All I Ask.mp3" loop></audio>

<script>
const message = `I know I may not have the right to ask for this, especially after everything, but I’m choosing to be honest with you.

I’ve taken time to really face myself—my mistakes, my patterns, and the way I showed up before. I’m not running from it anymore. I understand now how I made things heavy, how I let my fears control the way I loved you, and how that may have hurt you or pushed you away. I’m truly sorry for that.

But I want you to know this isn’t just words for me. I’ve been working on myself seriously—learning how to handle my emotions better, how to give space without panicking, how to love without losing myself, and how to be steady instead of overwhelming. I’m not perfect, but I’m no longer the same person who made those mistakes.

I’m saying this with confidence now—not desperation—that I can be a better partner. Not just for you, but as a person in general. Someone calmer, more understanding, more secure, and someone who won’t make you feel pressured or suffocated.

I still want you. I still choose you. And I don’t want to pretend that I’ve moved on when I haven’t.

I’m not here to beg blindly—I’m here because I believe in what we had, and I believe I can show up for you in a way I couldn’t before. I want the chance to prove that through my actions, not just my words.

I know trust isn’t something I can demand, but I’m asking for the chance to rebuild it—starting now, in the present, not stuck in who I used to be. I’m ready to be consistent, patient, and real with you.

I also understand that you don’t want to see me right now, and I respect that. I won’t force anything. I just hope you can read this with an open heart, and maybe allow a small space for us to try again.

I’m here, fully committed—not just to loving you, but to being someone who can love you the right way.

And if you can find it in you to trust me again, even just a little, I promise I won’t take it for granted this time.`;

let i = 0;
let typing = false;
const baseSpeed = 45;

function smoothScroll(element) {
    element.scrollTo({
        top: element.scrollHeight,
        behavior: "smooth"
    });
}

function typeWriter() {
    if (i < message.length) {
        const textEl = document.getElementById("text");
        const card = document.getElementById("card");

        textEl.innerHTML += message.charAt(i);

        // slow smooth auto-scroll
        smoothScroll(card);

        let delay = baseSpeed;

        if (message.charAt(i) === "\n") {
            delay = 900;
        } else if (message.charAt(i) === "." || message.charAt(i) === ",") {
            delay = 120;
        }

        i++;
        setTimeout(typeWriter, delay);
    } else {
        document.getElementById("replayBtn").style.display = "inline-block";
    }
}

function startMessage() {
    if (typing) return;
    typing = true;

    const card = document.getElementById("card");
    card.style.display = "block";

    setTimeout(() => {
        card.classList.add("show");
    }, 50);

    document.querySelector("button").style.display = "none";
    document.querySelector(".note").style.display = "none";

    document.getElementById("bgm").play();

    typeWriter();
}

function replay() {
    const textEl = document.getElementById("text");
    textEl.innerHTML = "";
    i = 0;
    document.getElementById("replayBtn").style.display = "none";
    typeWriter();
}
</script>

</body>
</html>
