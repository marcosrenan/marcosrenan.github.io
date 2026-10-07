---
layout: page
title: "Welcome to my homepage!"
---

I hold a PhD in Economics from [CAEN-UFC](https://caen.ufc.br). I have experience in the areas of Applied Macroeconomics and Econometrics and I have worked with microdata from different databases, mainly with regard to the Brazilian economy. I look for simple model solutions to real world problems.

**Research Interests**: Macroeconomics, Public Economics, Health Economics

<style>
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

/* GIF acima do contador */
.profile-left {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 140px;
  max-width: 45%;
  gap: 12px;
  flex-shrink: 0;
}

.welcome-gif {
  display: block;
  width: 140px;
  max-width: 100%;
  height: auto;
}

.flag-counter {
  display: block;
  width: 118px;
  max-width: 100%;
  margin: 0;
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
  .profile-container {
    gap: 10px;
  }

  .profile-left {
    width: 90px;
    max-width: 40%;
    gap: 10px;
  }

  .welcome-gif {
    width: 90px;
  }

  .flag-counter {
    width: 82px;
  }

  .profile-photo {
    width: 120px;
    max-width: 45%;
  }
}
</style>

<div class="profile-container">

  <div class="profile-left">

    <img
      class="welcome-gif"
      src="{{ '/Obi-Wan-sem-fundo-v3.gif' | relative_url }}"
      alt="Obi-Wan Kenobi saying Hello there!"
    >

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

  </div>

  <img
    class="profile-photo"
    src="renan2-modified.png"
    alt="Renan"
  >

</div>
```
