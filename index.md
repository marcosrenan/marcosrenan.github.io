---
layout: page
title: "Welcome to my webpage!"
---

I hold a PhD in Economics from [CAEN-UFC](https://caen.ufc.br). I have experience in the areas of Applied Macroeconomics and Econometrics and I have worked with microdata from different databases, mainly with regard to the Brazilian economy. I look for simple model solutions to real world problems.

**Research Interests**: Macroeconomics, Public Economics, Health Economics

<style>
/* Título à esquerda; GIF no centro */
.welcome-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 14px;
  font-size: 1.35rem;
  text-align: left;
}

/* GIF centralizado */
.welcome-title .welcome-gif {
  /* grid-column: 2; */
  display: block;
  width: 120px;
  max-width: 100%;
  height: auto;
  margin: 0;
}

.profile-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  width: 100%;
  gap: 30px;
  margin-top: 20px;
  box-sizing: border-box;
}

.flag-counter {
  display: block;
  width: 118px;
  margin-top: 70px;
  flex-shrink: 0;
}

.flag-counter img {
  display: block;
  width: 97%;
  height: auto;
}

.profile-photo {
  display: block;
  width: 169px;
  max-width: 40%;
  height: auto;
  flex-shrink: 0;
}

/* Celular */
@media screen and (max-width: 600px) {
  .welcome-title {
    gap: 8px;
  }

  /* Tamanho do GIF no celular */
  .welcome-title .welcome-gif {
    width: 90px;
  }

  .profile-container {
    gap: 10px;
  }

  .flag-counter {
    width: 82px;
    max-width: 37%;
    margin-top: 20px;
  }

  .profile-photo {
    width: 120px;
    max-width: 45%;
  }
}
</style>

<div class="profile-container">

  <a
    class="flag-counter"
    href="https://info.flagcounter.com/IIUt"
  >
    <img
      src="https://s01.flagcounter.com/count2/IIUt/bg_FFFFFF/txt_000000/border_CCCCCC/columns_3/maxflags_15/viewers_0/labels_0/pageviews_0/flags_0/percent_0/"
      alt="Free counters!"
      border="0"
    >
  </a>

  <img
    class="profile-photo"
    src="renan2-modified.png"
    alt="Renan"
  >

</div>

<script>
(function () {
  function addWelcomeGif() {
    const pageTitle = {{ page.title | jsonify }};

    const heading = Array.from(document.querySelectorAll("h1"))
      .find(function (element) {
        return element.textContent.trim() === pageTitle;
      });

    if (!heading || heading.querySelector(".welcome-gif")) {
      return;
    }

    heading.classList.add("welcome-title");

    const gif = document.createElement("img");
    gif.className = "welcome-gif";
    gif.src = {{ '/Obi-Wan-sem-fundo-v3.gif' | relative_url | jsonify }};
    gif.alt = "";
    gif.setAttribute("aria-hidden", "true");

    heading.appendChild(gif);
  }

  if (document.readyState === "loading") {
    document.addEventListener("DOMContentLoaded", addWelcomeGif);
  } else {
    addWelcomeGif();
  }
})();
</script>
