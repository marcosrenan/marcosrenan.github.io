---
layout: page
lang: "en"
permalink: /exploring_brazilian_economy/
---

<style>
#macro-dashboard {
  font-size: .85em;
  line-height: 1.5;
  color: inherit;
}

#macro-dashboard *,
#macro-dashboard *::before,
#macro-dashboard *::after {
  box-sizing: border-box;
}

#macro-dashboard .macro-nav {
  display: flex;
  flex-wrap: wrap;
  gap: .35em 1.15em;
  margin: 0 0 1.25em;
  font-size: .85em;
}

#macro-dashboard .macro-nav a {
  color: inherit;
  text-decoration: none;
  border-bottom: 1px solid #ccc;
}

#macro-dashboard .macro-nav a:hover {
  border-bottom-color: currentColor;
}

#macro-dashboard .macro-update-note {
  margin: -.45em 0 1.25em;
  color: #555;
  font-size: .85em;
  line-height: 1.45;
  text-align: left;
}

#macro-dashboard .macro-section {
  margin: 0 0 1.6em;
  scroll-margin-top: 1em;
}

#macro-dashboard .macro-section > .macro-heading {
  margin: 0 0 .65em;
  font-size: 1.2em;
  font-weight: 700;
  line-height: 1.25;
}

#macro-dashboard .macro-section-intro {
  margin: 0 0 .75em;
  font-size: .85em;
  line-height: 1.4;
  text-align: left;
}

#macro-dashboard .macro-panel {
  margin: 0 0 .85em;
  padding: 0;
  border: 0;
}

#macro-dashboard .macro-layout {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 170px;
  column-gap: 16px;
  row-gap: 0;
  align-items: start;
}

#macro-dashboard .macro-chart {
  width: 100%;
  min-width: 0;
  height: 352px;
}

#macro-dashboard .macro-figure {
  min-width: 0;
  grid-column: 1;
  grid-row: 2;
}

#macro-dashboard .macro-plot-title {
  margin: 0;
  padding: 0 14px 0 60px;
  font-family: "Times New Roman", Times, serif;
  font-size: 14px;
  font-weight: 400;
  line-height: 20px;
  text-align: left;
  -webkit-user-select: text;
  user-select: text;
}

#macro-dashboard .macro-canvas {
  position: relative;
  width: 100%;
  min-width: 0;
}

#macro-dashboard .macro-presidents {
  margin: 0 14px .25em 52px;
  padding: 4px 6px;
  border: 1px solid #000;
  border-radius: 2px;
  background: #fff;
  color: #222;
  font-family: "Times New Roman", Times, serif;
  font-size: 10px;
  line-height: 1.15;
  text-align: left;
}

#macro-dashboard .macro-presidents.has-two-columns {
  width: max-content;
  max-width: calc(100% - 66px);
}

#macro-dashboard .macro-presidents.is-overlay {
  position: absolute;
  z-index: 3;
  margin: 0;
  padding: 4px 6px;
  background: rgba(255,255,255,.96);
  border: 1px solid #000;
  width: max-content;
  max-width: calc(100% - var(--macro-margin-left, 60px) - var(--macro-margin-right, 14px));
}

#macro-dashboard .macro-presidents-title {
  margin: 0 0 3px;
  font-size: 10px;
  font-weight: 700;
  line-height: 1.1;
}

#macro-dashboard .macro-presidents-items {
  display: flex;
  flex-wrap: wrap;
  gap: 3px 8px;
  align-items: center;
}

#macro-dashboard .macro-presidents-items.is-two-column {
  display: grid;
  grid-template-columns: repeat(2, max-content);
  grid-auto-flow: column;
  grid-template-rows: repeat(4, auto);
  gap: 4px 10px;
  align-items: center;
}

#macro-dashboard .macro-president-item {
  display: inline-flex;
  align-items: center;
  gap: 3px;
  white-space: nowrap;
  font-size: 10px;
  line-height: 1.15;
}

#macro-dashboard .macro-president-swatch {
  display: inline-block;
  flex: 0 0 10px;
  width: 10px;
  height: 10px;
  border: 1px solid #000;
}

#macro-dashboard .macro-sidebar {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: .75em;
  min-width: 0;
  padding-top: var(--macro-plot-top, 14px);
  font-size: .85em;
  text-align: left;
  grid-column: 2;
  grid-row: 2;
}

#macro-dashboard .macro-sidebar p,
#macro-dashboard .macro-info,
#macro-dashboard .macro-info p,
#macro-dashboard .macro-source,
#macro-dashboard .macro-key-label {
  text-align: left;
}

#macro-dashboard .macro-sidebar button,
#macro-dashboard .macro-sidebar summary {
  display: inline-block;
  margin: 0;
  padding: .4em .65em;
  border: 1px solid #bbb;
  border-radius: 4px;
  box-shadow: none;
  background: #fff;
  color: #333;
  font: inherit;
  line-height: 1.4;
  text-transform: none;
  letter-spacing: normal;
  cursor: pointer;
}

#macro-dashboard .macro-sidebar button:hover,
#macro-dashboard .macro-sidebar summary:hover {
  background: #f3f3f3;
}

#macro-dashboard .macro-sidebar button:disabled {
  opacity: .5;
  cursor: wait;
}

#macro-dashboard :focus-visible {
  outline: 2px solid #555;
  outline-offset: 3px;
}

#macro-dashboard .macro-about {
  position: relative;
  margin: 0;
}

#macro-dashboard .macro-about summary {
  list-style: none;
}

#macro-dashboard .macro-about summary::-webkit-details-marker {
  display: none;
}

#macro-dashboard .macro-about summary::after {
  content: " ▾";
}

#macro-dashboard .macro-about[open] summary::after {
  content: " ▴";
}

#macro-dashboard .macro-info {
  position: absolute;
  z-index: 10;
  top: calc(100% + 8px);
  right: 0;
  width: min(340px, calc(100vw - 48px));
  max-height: min(72vh, 520px);
  overflow: auto;
  padding: 1em;
  border: 1px solid #ddd;
  border-radius: 4px;
  background: #fff;
  box-shadow: 0 4px 14px #0002;
  color: #333;
  line-height: 1.5;
}

#macro-dashboard .macro-info p {
  margin: 0 0 .75em;
}

#macro-dashboard .macro-info p:last-child {
  margin-bottom: 0;
}

#macro-dashboard .macro-info .macro-series {
  padding-bottom: .65em;
  border-bottom: 1px solid #eee;
}

#macro-dashboard .macro-info .macro-original {
  display: inline;
}

#macro-dashboard .macro-latest {
  display: grid;
  gap: .25em;
}

#macro-dashboard .macro-latest-row {
  display: flex;
  justify-content: space-between;
  gap: .75em;
}

#macro-dashboard .macro-latest-value {
  white-space: nowrap;
}

#macro-dashboard .macro-indicators {
  width: 100%;
  padding: 4px 6px;
  border: 1px solid #000;
  border-radius: 2px;
}

#macro-dashboard .macro-key-title {
  margin: .1em 0 .35em;
  font-weight: 700;
}

#macro-dashboard .macro-keys {
  display: grid;
  gap: .4em;
}

#macro-dashboard .macro-key {
  display: flex;
  align-items: center;
  gap: .5em;
  min-width: 0;
}

#macro-dashboard .macro-key-sample {
  display: inline-block;
  flex: 0 0 26px;
  width: 26px;
  height: 0;
  border-top: 1.6px solid #111;
}

#macro-dashboard .macro-key-label {
  min-width: 0;
  font-weight: 400;
  line-height: 1.3;
}

#macro-dashboard .macro-key-sample.is-bar,
#macro-dashboard .macro-key-sample[data-kind="bar"] {
  height: 9px;
  border: 1px solid #111;
  background: #111;
}

#macro-dashboard .macro-source {
  margin: .1em 0 0;
  color: #555;
  font-size: .95em;
  line-height: 1.45;
}

#macro-dashboard .macro-source a {
  overflow-wrap: anywhere;
}

#macro-dashboard .macro-status {
  margin: .4em 0;
  color: #555;
  font-size: .85em;
}

#macro-dashboard [hidden] {
  display: none !important;
}

@media (max-width: 600px) {
  #macro-dashboard {
    font-size: .8em;
  }

  #macro-dashboard .macro-nav {
    gap: .35em .85em;
  }

  #macro-dashboard .macro-layout {
    grid-template-columns: minmax(0, 1fr);
    gap: 0;
  }

  #macro-dashboard .macro-chart {
    height: 320px;
  }

  #macro-dashboard .macro-plot-title {
    margin: 0;
    font-size: 12px;
    line-height: 16px;
  }

  #macro-dashboard .macro-presidents-title {
    font-size: 8px;
  }

  #macro-dashboard .macro-president-item {
    font-size: 7px;
  }

  #macro-dashboard .macro-sidebar {
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
    gap: .55em .75em;
    padding-top: 0;
      grid-column: 1;
    grid-row: 3;
    margin-top: 6px;
}

  #macro-dashboard .macro-info {
    top: calc(100% + 8px);
    right: auto;
    left: 0;
  }

  #macro-dashboard .macro-source,
  #macro-dashboard .macro-indicators {
    flex-basis: 100%;
  }

  #macro-dashboard .macro-keys {
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: .35em .8em;
  }
}

/* Compact contents: append after the original dashboard styles. */
#macro-dashboard .macro-contents {
  margin: 0 0 1.25em;
  padding: 12px 16px 14px;
  border: 1px solid #d8d8d8;
  border-radius: 5px;
  background: #fafafa;
  text-align: left;
}

#macro-dashboard .macro-contents-label {
  margin: 0 0 .5em;
  color: #666;
  font-size: .75em;
  font-weight: 600;
  letter-spacing: .1em;
  line-height: 1.3;
  text-transform: uppercase;
}

#macro-dashboard .macro-nav {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: .35em 1.5em;
  margin: 0;
  font-size: .9em;
}

#macro-dashboard .macro-nav a {
  display: grid;
  grid-template-columns: 1.5em minmax(0, 1fr);
  align-items: start;
  gap: .45em;
  min-width: 0;
  padding: .45em 0;
  border: 0;
  border-radius: 2px;
  color: inherit;
  line-height: 1.3;
  text-decoration: none;
}

#macro-dashboard .macro-nav-number {
  padding-top: .06em;
  color: #777;
  font-size: .85em;
  font-variant-numeric: tabular-nums;
}

#macro-dashboard .macro-nav-copy {
  min-width: 0;
}

#macro-dashboard .macro-nav-copy strong {
  display: block;
  color: #222;
  font-size: 1em;
  font-weight: 600;
}

#macro-dashboard .macro-nav-copy > span {
  display: block;
  margin-top: .2em;
  color: #666;
  font-size: .83em;
  line-height: 1.35;
}

#macro-dashboard .macro-nav a:hover .macro-nav-copy strong {
  text-decoration: underline;
  text-underline-offset: .16em;
}

#macro-dashboard .macro-nav a:focus-visible {
  outline: 2px solid #555;
  outline-offset: 4px;
}

@media (max-width: 800px) {
  #macro-dashboard .macro-nav {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    column-gap: 1.25em;
  }
}

@media (max-width: 440px) {
  #macro-dashboard .macro-contents {
    padding: 10px 12px;
  }

  #macro-dashboard .macro-nav {
    grid-template-columns: minmax(0, 1fr);
    gap: .1em;
  }

  #macro-dashboard .macro-nav a {
    padding: .4em 0;
  }
}

/* Subtitles share the chart-title inset on desktop and mobile. */
#macro-dashboard .macro-plot-subtitle {
  margin: 4px 0 0;
  padding: 0 14px 0 60px;
  font-family: "Times New Roman", Times, serif;
  font-size: 11px;
  font-weight: 400;
  line-height: 1.35;
  color: #555;
  text-align: left;
}
#macro-dashboard .macro-inset-indicators {
  z-index: 3;
  border: 1px solid #000;
  border-radius: 2px;
  background: rgba(255,255,255,.96);
  color: #222;
  font-family: "Times New Roman", Times, serif;
  text-align: left;
}
#macro-dashboard .macro-inset-indicators .macro-key {
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 0;
  padding: 0;
  min-width: 0;
}
#macro-dashboard .macro-inset-indicators .macro-key-label {
  white-space: nowrap;
  line-height: 1.15;
}

/* The shared header row lets every control begin at the plot's data edge. */
#macro-dashboard .macro-plot-header {
  grid-column: 1;
  grid-row: 1;
  min-width: 0;
  margin: 0;
  padding: 12px 0 16px;
}

/* Inset legend boxes appear only after their geometry has been calculated. */
#macro-dashboard .macro-sidebar > .macro-indicators {
  display: none;
}

@media (max-width: 600px) {
  #macro-dashboard .macro-plot-header {
    padding: 10px 0 14px;
  }
}

/* Mobile keeps the desktop visual language with readable legends and controls. */
@media (max-width: 600px) {
  #macro-dashboard .macro-sidebar {
    font-size: 12px;
    gap: 8px;
    margin-top: 8px;
    align-items: flex-start;
  }
  #macro-dashboard .macro-sidebar button,
  #macro-dashboard .macro-sidebar summary {
    display: inline-flex;
    align-items: center;
    min-height: 44px;
    padding: 8px 10px;
    font-size: 12px;
    line-height: 1.4;
  }
  #macro-dashboard .macro-about {
    min-width: 0;
    max-width: 100%;
  }
  #macro-dashboard .macro-about[open] {
    flex: 1 0 100%;
    width: 100%;
  }
  #macro-dashboard .macro-about .macro-info {
    position: static;
    width: 100%;
    max-width: 100%;
    min-width: 0;
    max-height: 60vh;
    margin-top: 8px;
    font-size: 12px;
    line-height: 1.45;
    box-shadow: none;
  }
  #macro-dashboard .macro-source {
    font-size: 11px;
    line-height: 1.45;
    overflow-wrap: anywhere;
  }
}

</style>

<div id="macro-dashboard" lang="en">
  <div class="macro-contents">
    <p id="macro-contents-label" class="macro-contents-label">On this page</p>
    <nav class="macro-nav" aria-labelledby="macro-contents-label">
      <a href="#section-gdp">
        <span class="macro-nav-number" aria-hidden="true">01</span>
        <span class="macro-nav-copy"><strong>GDP, activity &amp; income</strong><span>Output, consumption, investment and income</span></span>
      </a>
      <a href="#section-monetary-fiscal">
        <span class="macro-nav-number" aria-hidden="true">02</span>
        <span class="macro-nav-copy"><strong>Monetary &amp; fiscal policy</strong><span>Inflation, interest rates and public debt</span></span>
      </a>
      <a href="#section-credit-bndes">
        <span class="macro-nav-number" aria-hidden="true">03</span>
        <span class="macro-nav-copy"><strong>Credit &amp; household finances</strong><span>Lending rates, debt and delinquency</span></span>
      </a>
      <a href="#section-industry-retail">
        <span class="macro-nav-number" aria-hidden="true">04</span>
        <span class="macro-nav-copy"><strong>Industry &amp; confidence</strong><span>Production, retail sales and confidence</span></span>
      </a>
      <a href="#section-external-sector">
        <span class="macro-nav-number" aria-hidden="true">05</span>
        <span class="macro-nav-copy"><strong>External sector</strong><span>Trade, exchange rates and reserves</span></span>
      </a>
      <a href="#section-labor-market">
        <span class="macro-nav-number" aria-hidden="true">06</span>
        <span class="macro-nav-copy"><strong>Labor market</strong><span>Employment and unemployment</span></span>
      </a>
    </nav>
  </div>
<p class="macro-update-note"><strong>Automatic monthly updates</strong> from the 20th, using the latest BCB data.</p>
  <section id="section-gdp" class="macro-section" aria-labelledby="heading-gdp">
    <h2 id="heading-gdp" class="macro-heading">GDP, activity and income</h2>
    <div id="panel-fig1a" class="macro-panel" role="group" aria-label="GDP and GDP per capita, USD (current)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1a" class="macro-plot-title">GDP and GDP per capita, USD (current)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1a" class="macro-chart" aria-labelledby="title-fig1a" aria-busy="true"></div>
            <div id="presidents-fig1a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>GDP — left axis</strong><br><span class="macro-original" lang="pt-BR"><em>PIB acumulado nos últimos 12 meses em US$ milhões</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4192" target="_blank" rel="noopener noreferrer"><strong>4192</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>GDP per capita — right axis</strong><br><span class="macro-original" lang="pt-BR"><em>PIB per capita em US$ correntes</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21776" target="_blank" rel="noopener noreferrer"><strong>21776</strong></a>.<br>Frequency: annual.</p>
            <p>GDP is the accumulated 12-month total at current prices.</p>
            <p>GDP per capita is annual; native observation dates are retained.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig1a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1a" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig1a" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4192" target="_blank" rel="noopener noreferrer"><strong>4192</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21776" target="_blank" rel="noopener noreferrer"><strong>21776</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1b" class="macro-panel" role="group" aria-label="GDP and GDP per capita, BRL (constant)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1b" class="macro-plot-title">GDP and GDP per capita, BRL (constant)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1b" class="macro-chart" aria-labelledby="title-fig1b" aria-busy="true"></div>
            <div id="presidents-fig1b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>GDP — left axis</strong><br><span class="macro-original" lang="pt-BR"><em>PIB acumulado nos últimos 12 meses a preços correntes</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4382" target="_blank" rel="noopener noreferrer"><strong>4382</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=433" target="_blank" rel="noopener noreferrer"><strong>433</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>GDP per capita — right axis</strong><br><span class="macro-original" lang="pt-BR"><em>PIB per capita a preços constantes do último ano</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21777" target="_blank" rel="noopener noreferrer"><strong>21777</strong></a>.<br>Frequency: annual.</p>
            <p>GDP is adjusted to December 2024 prices using a compounded IPCA index (SGS 433).</p>
            <p>GDP per capita is already published at constant last-year prices by the BCB and is not deflated again. The two price bases differ.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig1b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1b" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig1b" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4382" target="_blank" rel="noopener noreferrer"><strong>4382</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=433" target="_blank" rel="noopener noreferrer"><strong>433</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21777" target="_blank" rel="noopener noreferrer"><strong>21777</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1c" class="macro-panel" role="group" aria-label="Real GDP growth (y/y)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1c" class="macro-plot-title">Real GDP growth (y/y)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1c" class="macro-chart" aria-labelledby="title-fig1c" aria-busy="true"></div>
            <div id="presidents-fig1c" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1c" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1c" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Real GDP growth</strong><br><span class="macro-original" lang="pt-BR"><em>PIB – variação real no ano</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7326" target="_blank" rel="noopener noreferrer"><strong>7326</strong></a>.<br>Frequency: annual.</p>
            <p>Annual real percentage change; native annual observations are retained.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig1c" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1c" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7326" target="_blank" rel="noopener noreferrer"><strong>7326</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1c" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1d" class="macro-panel" role="group" aria-label="Real GDP growth by sector (y/y)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1d" class="macro-plot-title">Real GDP growth by sector (y/y)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1d" class="macro-chart" aria-labelledby="title-fig1d" aria-busy="true"></div>
            <div id="presidents-fig1d" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1d" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1d" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Agriculture</strong><br><span class="macro-original" lang="pt-BR"><em>PIB – agropecuária – variação real no ano</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7327" target="_blank" rel="noopener noreferrer"><strong>7327</strong></a>.<br>Frequency: annual.</p>
            <p class="macro-series"><strong>Industry</strong><br><span class="macro-original" lang="pt-BR"><em>PIB – indústria – variação real no ano</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7328" target="_blank" rel="noopener noreferrer"><strong>7328</strong></a>.<br>Frequency: annual.</p>
            <p class="macro-series"><strong>Services</strong><br><span class="macro-original" lang="pt-BR"><em>PIB – serviços – variação real no ano</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7329" target="_blank" rel="noopener noreferrer"><strong>7329</strong></a>.<br>Frequency: annual.</p>
            <p>Annual real percentage changes by sector.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig1d" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1d" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig1d" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7327" target="_blank" rel="noopener noreferrer"><strong>7327</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7328" target="_blank" rel="noopener noreferrer"><strong>7328</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7329" target="_blank" rel="noopener noreferrer"><strong>7329</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1d" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1e" class="macro-panel" role="group" aria-label="Monthly economic activity (IBC-Br)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1e" class="macro-plot-title">Monthly economic activity (IBC-Br)</h3>
          <p class="macro-plot-subtitle">IBC-Br is the Central Bank’s monthly indicator of economic activity.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1e" class="macro-chart" aria-labelledby="title-fig1e" aria-busy="true"></div>
            <div id="presidents-fig1e" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1e" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1e" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>IBC-Br</strong><br><span class="macro-original" lang="pt-BR"><em>Índice de Atividade Econômica do Banco Central – IBC-Br – com ajuste sazonal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24364" target="_blank" rel="noopener noreferrer"><strong>24364</strong></a>.<br>Frequency: monthly.</p>
            <p>Seasonally adjusted monthly activity index, as published by the BCB; average 2022 = 100.</p>
            <p>IBC-Br has a different scope from the national accounts and should not be interpreted as monthly GDP.</p>
            <p>Native monthly observations are retained; the available series starts in January 2003.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig1e" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1e" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24364" target="_blank" rel="noopener noreferrer"><strong>24364</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1e" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1f" class="macro-panel" role="group" aria-label="Real household disposable income">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1f" class="macro-plot-title">Real household disposable income</h3>
          <p class="macro-plot-subtitle">Inflation-adjusted household income from labour, capital and net transfers.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1f" class="macro-chart" aria-labelledby="title-fig1f" aria-busy="true"></div>
            <div id="presidents-fig1f" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1f" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1f" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Real household disposable income</strong><br><span class="macro-original" lang="pt-BR"><em>Renda Nacional Disponível Bruta das Famílias – em valores constantes, deflacionada pelo IPCA, com ajuste sazonal (média móvel trimestral)</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29027" target="_blank" rel="noopener noreferrer"><strong>29027</strong></a>.<br>Frequency: monthly.</p>
            <p>Household disposable income includes income from labour and capital plus net transfers; it is not a wage measure.</p>
            <p>The published series is already deflated by the IPCA, seasonally adjusted and expressed as a three-month moving average. No further deflation, seasonal adjustment or moving average is applied.</p>
            <p>Published millions of constant-price BRL are divided by 1,000 to display BRL billions; the BCB’s published price reference is retained.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig1f" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1f" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://dadosabertos.bcb.gov.br/dataset/29027-renda-nacional-disponivel-bruta-das-familias-em-valores-constantes-deflacionada-pelo-ipca-com" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29027" target="_blank" rel="noopener noreferrer"><strong>29027</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1f" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1g" class="macro-panel" role="group" aria-label="Household consumption, government consumption, investment and net exports">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1g" class="macro-plot-title">Household consumption, government consumption, investment and net exports</h3>
          <p class="macro-plot-subtitle">Average 2019 = 100. Consumption and investment: left axis; net exports: right axis.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1g" class="macro-chart" aria-labelledby="title-fig1g" aria-busy="true"></div>
            <div id="presidents-fig1g" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1g" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1g" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Households</strong><br><span class="macro-original" lang="pt-BR"><em>PIB trimestral – dados dessazonalizados – consumo das famílias</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22110" target="_blank" rel="noopener noreferrer"><strong>22110</strong></a>.<br>Frequency: quarterly.</p>
            <p class="macro-series"><strong>Government</strong><br><span class="macro-original" lang="pt-BR"><em>PIB trimestral – dados dessazonalizados – consumo do governo</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22111" target="_blank" rel="noopener noreferrer"><strong>22111</strong></a>.<br>Frequency: quarterly.</p>
            <p class="macro-series"><strong>Gross fixed capital formation</strong><br><span class="macro-original" lang="pt-BR"><em>PIB trimestral – dados dessazonalizados – formação bruta de capital fixo</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22113" target="_blank" rel="noopener noreferrer"><strong>22113</strong></a>.<br>Frequency: quarterly.</p>
            <p class="macro-series"><strong>Net exports (2019-weighted proxy)</strong><br><span class="macro-original" lang="pt-BR"><em>Exportações líquidas de bens e serviços – indicador calculado com pesos de 2019</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22114" target="_blank" rel="noopener noreferrer"><strong>22114</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22115" target="_blank" rel="noopener noreferrer"><strong>22115</strong></a>.<br>Frequency: quarterly.</p>
            <p>Consumption and investment are seasonally adjusted quarterly volume indices from the national accounts, distributed through the SGS.</p>
            <p>Each consumption and investment series is divided by its own average across the four quarters of 2019 and multiplied by 100.</p>
            <p>Net exports are a calculated volume-balance proxy. The export and import volume indices are separately divided by their own 2019 averages, then weighted by average quarterly current-price exports and imports in 2019, subtracted, and rebased to average 2019 = 100.</p>
            <p>The fixed 2019 weights are BRL 260,890.25 million for exports and BRL 272,794.50 million for imports, from IBGE SIDRA table 1846. The reference balance is −BRL 11,904.25 million per quarter.</p>
            <p>Net exports index = 100 × [260,890.25 × (export volume / its 2019 average) − 272,794.50 × (import volume / its 2019 average)] / (260,890.25 − 272,794.50).</p>
            <p>The 2019 reference balance is negative: a higher net-exports index represents a lower constructed balance; a negative index represents a positive constructed balance.</p>
            <p>All four series have an average of 100 in 2019. The indices compare changes over time, not absolute sizes or GDP shares. They are not additive and do not sum to GDP; the net-exports indicator is not an official chained-volume aggregate or the current-account balance.</p>
            <p>Investment is gross fixed capital formation (GFCF), including public and private investment in fixed assets; it excludes changes in inventories.</p>
            <p>Native quarterly dates and observations are retained. Export and import inputs are already seasonally adjusted; no further adjustment, interpolation or smoothing is applied.</p>
            <p>Consumption and investment use the left axis; net exports use the right axis. Both axes are indices with average 2019 = 100, and the reference value of 100 is aligned at the same height. The two axis scales differ.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig1g" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1g" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig1g" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22110" target="_blank" rel="noopener noreferrer"><strong>22110</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22111" target="_blank" rel="noopener noreferrer"><strong>22111</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22113" target="_blank" rel="noopener noreferrer"><strong>22113</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22114" target="_blank" rel="noopener noreferrer"><strong>22114</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22115" target="_blank" rel="noopener noreferrer"><strong>22115</strong></a>; 2019 weights: <a href="https://sidra.ibge.gov.br/tabela/1846" target="_blank" rel="noopener noreferrer">IBGE SIDRA 1846</a>. Author’s calculations.</p>
        </aside>
      </div>
      <p id="status-fig1g" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig1h" class="macro-panel" role="group" aria-label="Minimum wage: nominal and real">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig1h" class="macro-plot-title">Minimum wage: nominal and real</h3>
          <p class="macro-plot-subtitle">Monthly minimum wage; real values in December 2024 BRL.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig1h" class="macro-chart" aria-labelledby="title-fig1h" aria-busy="true"></div>
            <div id="presidents-fig1h" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig1h" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig1h" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Nominal minimum wage</strong><br><span class="macro-original" lang="pt-BR"><em>Salário mínimo</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=1619" target="_blank" rel="noopener noreferrer"><strong>1619</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Real minimum wage — December 2024 prices</strong><br><span class="macro-original" lang="pt-BR"><em>Salário mínimo deflacionado pelo IPCA</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=1619" target="_blank" rel="noopener noreferrer"><strong>1619</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=433" target="_blank" rel="noopener noreferrer"><strong>433</strong></a>.<br>Frequency: monthly.</p>
            <p>The nominal line is the statutory monthly minimum wage published in SGS 1619, in current BRL.</p>
            <p>The real line is calculated from the same nominal series using the monthly IPCA percentage changes in SGS 433. Monthly rates are compounded into a price index; they are not added.</p>
            <p>Real wage at month t = nominal wage at t × compounded IPCA index in December 2024 / compounded IPCA index at t.</p>
            <p>The price reference is December 2024. Nominal and real values therefore coincide in that month. The two lines show BRL per month, with the real line expressed in December 2024 purchasing power.</p>
            <p>The graph starts in January 1996. Observations dated after the current month are excluded, including any pre-published future minimum-wage observations.</p>
            <p>The real line ends at the latest month for which both a nominal wage and a published IPCA observation exist. No inflation values are forecast or carried forward.</p>
            <p>Native monthly observations are retained without additional seasonal adjustment or smoothing.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig1h" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig1h" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig1h" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=1619" target="_blank" rel="noopener noreferrer"><strong>1619</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=433" target="_blank" rel="noopener noreferrer"><strong>433</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig1h" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>

  <section id="section-monetary-fiscal" class="macro-section" aria-labelledby="heading-monetary-fiscal">
    <h2 id="heading-monetary-fiscal" class="macro-heading">Monetary and fiscal policy</h2>
    <div id="panel-fig2a" class="macro-panel" role="group" aria-label="IPCA, Selic and inflation target">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig2a" class="macro-plot-title">
          IPCA, Selic and inflation target
          </h3>
          <p class="macro-plot-subtitle">
          Selic is Brazil’s benchmark interest rate, which influences other interest rates across the economy.
          </p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig2a" class="macro-chart" aria-labelledby="title-fig2a" aria-busy="true"></div>
            <div id="presidents-fig2a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig2a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig2a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>IPCA — 12-month change</strong><br><span class="macro-original" lang="pt-BR"><em>IPCA – variação acumulada em 12 meses</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13522" target="_blank" rel="noopener noreferrer"><strong>13522</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Selic — annualized, 252-day basis</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa de juros – Selic anualizada base 252</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=1178" target="_blank" rel="noopener noreferrer"><strong>1178</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Inflation target</strong><br><span class="macro-original" lang="pt-BR"><em>Meta para a inflação</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13521" target="_blank" rel="noopener noreferrer"><strong>13521</strong></a>.<br>Frequency: annual.</p>
            <p>Selic is sampled at the first daily observation of each month.</p>
            <p>The inflation target retains its native annual observations; IPCA is the published 12-month rate.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig2a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig2a" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig2a" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13522" target="_blank" rel="noopener noreferrer"><strong>13522</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=1178" target="_blank" rel="noopener noreferrer"><strong>1178</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13521" target="_blank" rel="noopener noreferrer"><strong>13521</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig2a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig2b" class="macro-panel" role="group" aria-label="IPCA components (12-month inflation rate)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig2b" class="macro-plot-title">IPCA components (12-month inflation rate)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig2b" class="macro-chart" aria-labelledby="title-fig2b" aria-busy="true"></div>
            <div id="presidents-fig2b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig2b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig2b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Administered prices</strong><br><span class="macro-original" lang="pt-BR"><em>IPCA – preços monitorados</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4449" target="_blank" rel="noopener noreferrer"><strong>4449</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Food at home</strong><br><span class="macro-original" lang="pt-BR"><em>IPCA – alimentação no domicílio</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=27864" target="_blank" rel="noopener noreferrer"><strong>27864</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Industrial goods</strong><br><span class="macro-original" lang="pt-BR"><em>IPCA – bens industriais</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=27863" target="_blank" rel="noopener noreferrer"><strong>27863</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Services</strong><br><span class="macro-original" lang="pt-BR"><em>IPCA – serviços</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=10844" target="_blank" rel="noopener noreferrer"><strong>10844</strong></a>.<br>Frequency: monthly.</p>
            <p>Monthly price changes are compounded over 12 consecutive months before the display-period cutoff.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig2b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig2b" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig2b" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4449" target="_blank" rel="noopener noreferrer"><strong>4449</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=27864" target="_blank" rel="noopener noreferrer"><strong>27864</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=27863" target="_blank" rel="noopener noreferrer"><strong>27863</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=10844" target="_blank" rel="noopener noreferrer"><strong>10844</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig2b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig2c" class="macro-panel" role="group" aria-label="Primary borrowing requirements (% of GDP)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig2c" class="macro-plot-title">Primary borrowing requirements (% of GDP)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig2c" class="macro-chart" aria-labelledby="title-fig2c" aria-busy="true"></div>
            <div id="presidents-fig2c" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig2c" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig2c" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Primary borrowing requirements</strong><br><span class="macro-original" lang="pt-BR"><em>NFSP sem desvalorização cambial – resultado primário – setor público consolidado</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=5793" target="_blank" rel="noopener noreferrer"><strong>5793</strong></a>.<br>Frequency: monthly.</p>
            <p>Accumulated 12-month primary result of the consolidated public sector.</p>
            <p>BCB borrowing-requirements sign convention: positive values indicate deficits and negative values indicate surpluses.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig2c" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig2c" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=5793" target="_blank" rel="noopener noreferrer"><strong>5793</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig2c" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig2n" class="macro-panel" role="group" aria-label="Public sector borrowing requirements (% of GDP)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig2n" class="macro-plot-title">Public sector borrowing requirements (% of GDP)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig2n" class="macro-chart" aria-labelledby="title-fig2n" aria-busy="true"></div>
            <div id="presidents-fig2n" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig2n" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig2n" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Nominal borrowing requirements</strong><br><span class="macro-original" lang="pt-BR"><em>NFSP sem desvalorização cambial – resultado nominal – setor público consolidado</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=5727" target="_blank" rel="noopener noreferrer"><strong>5727</strong></a>.<br>Frequency: monthly.</p>
            <p>Nominal result, excluding exchange rate effects, accumulated over 12 months.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig2n" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig2n" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=5727" target="_blank" rel="noopener noreferrer"><strong>5727</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig2n" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig2d" class="macro-panel" role="group" aria-label="Public debt (% of GDP)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig2d" class="macro-plot-title">Public debt (% of GDP)</h3>
          <p class="macro-plot-subtitle">Net public sector debt and gross general government debt have different institutional coverage.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig2d" class="macro-chart" aria-labelledby="title-fig2d" aria-busy="true"></div>
            <div id="presidents-fig2d" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig2d" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig2d" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Net public sector debt</strong><br><span class="macro-original" lang="pt-BR"><em>Dívida Líquida do Setor Público (% PIB) – Total – setor público consolidado</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4513" target="_blank" rel="noopener noreferrer"><strong>4513</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Gross general government debt</strong><br><span class="macro-original" lang="pt-BR"><em>Dívida bruta do governo geral (% PIB) – metodologia utilizada a partir de 2008</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13762" target="_blank" rel="noopener noreferrer"><strong>13762</strong></a>.<br>Frequency: monthly.</p>
            <p>Both lines are debt stocks expressed as a percentage of GDP, plotted on the same vertical scale starting at 20% of GDP. They are not accumulated 12-month flows.</p>
            <p>Net public sector debt covers the consolidated public sector, while gross general government debt covers general government under the BCB methodology. Their institutional coverage differs; the gap between the lines is not simply government assets.</p>
            <p>Gross general government debt uses the methodology adopted from 2008, with observations available from December 2006. No earlier values are imputed.</p>
            <p>The upper axis limit adapts to both series and is rounded up to the next ten percentage points.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig2d" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig2d" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig2d" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4513" target="_blank" rel="noopener noreferrer"><strong>4513</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=13762" target="_blank" rel="noopener noreferrer"><strong>13762</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig2d" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>

  <section id="section-credit-bndes" class="macro-section" aria-labelledby="heading-credit-bndes">
    <h2 id="heading-credit-bndes" class="macro-heading">Credit and household finances</h2>
    <p class="macro-section-intro">BNDES is Brazil’s federal development bank.</p>
    <div id="panel-fig3a" class="macro-panel" role="group" aria-label="Credit and BNDES lending (% of GDP)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig3a" class="macro-plot-title">Credit and BNDES lending (% of GDP)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig3a" class="macro-chart" aria-labelledby="title-fig3a" aria-busy="true"></div>
            <div id="presidents-fig3a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig3a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig3a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Total credit / GDP</strong><br><span class="macro-original" lang="pt-BR"><em>Saldo da carteira de crédito em relação ao PIB</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20622" target="_blank" rel="noopener noreferrer"><strong>20622</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>BNDES total lending / GDP</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7415" target="_blank" rel="noopener noreferrer"><strong>7415</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4380" target="_blank" rel="noopener noreferrer"><strong>4380</strong></a>.<br>Frequency: monthly.</p>
            <p>BNDES (Brazilian Development Bank) is Brazil’s federal public development bank.</p>
            <p>The BNDES curve reproduces Fig. 3(a) in the supplied Python script: the 12-observation sum of SGS 7415, divided by the 12-month sum of GDP (4380), multiplied by 100.</p>
            <p>SGS 7415 contains year-to-date disbursements. Summing these observations reproduces the original-script indicator; it is not the total of monthly disbursements over the previous 12 months.</p>
            <p>The sector chart below retains the monthly-flow calculation described in its own notes.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig3a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig3a" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig3a" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20622" target="_blank" rel="noopener noreferrer"><strong>20622</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7415" target="_blank" rel="noopener noreferrer"><strong>7415</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4380" target="_blank" rel="noopener noreferrer"><strong>4380</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig3a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig3b" class="macro-panel" role="group" aria-label="BNDES lending by sector, BRL (current – not deflated)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig3b" class="macro-plot-title">BNDES lending by sector, BRL (current – <u>not deflated</u>)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig3b" class="macro-chart" aria-labelledby="title-fig3b" aria-busy="true"></div>
            <div id="presidents-fig3b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig3b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig3b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Total</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7415" target="_blank" rel="noopener noreferrer"><strong>7415</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Commerce &amp; services</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Comércio e serviços</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7417" target="_blank" rel="noopener noreferrer"><strong>7417</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Manufacturing</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Indústria de transformação</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7416" target="_blank" rel="noopener noreferrer"><strong>7416</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Agriculture</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Agropecuária</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7418" target="_blank" rel="noopener noreferrer"><strong>7418</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Mining</strong><br><span class="macro-original" lang="pt-BR"><em>Desembolsos do sistema BNDES – Indústria extrativa</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7419" target="_blank" rel="noopener noreferrer"><strong>7419</strong></a>.<br>Frequency: monthly.</p>
            <p>BNDES (Brazilian Development Bank) is Brazil’s federal public development bank.</p>
            <p>Nominal disbursements, converted from cumulative year-to-date observations into monthly flows and then summed over 12 consecutive months.</p>
            <p>Values are in current BRL trillions; the display cutoff is applied before the rolling sum.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig3b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig3b" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig3b" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7415" target="_blank" rel="noopener noreferrer"><strong>7415</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7417" target="_blank" rel="noopener noreferrer"><strong>7417</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7416" target="_blank" rel="noopener noreferrer"><strong>7416</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7418" target="_blank" rel="noopener noreferrer"><strong>7418</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=7419" target="_blank" rel="noopener noreferrer"><strong>7419</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig3b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig3c" class="macro-panel" role="group" aria-label="Loan delinquency rates (% of credit portfolio)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig3c" class="macro-plot-title">
          Loan delinquency rates (% of credit portfolio)
          </h3>
          <p class="macro-plot-subtitle">
          The delinquency rates shown here refer to the credit portfolio of Brazil’s financial system as a whole, not specifically to BNDES’s portfolio.
          </p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig3c" class="macro-chart" aria-labelledby="title-fig3c" aria-busy="true"></div>
            <div id="presidents-fig3c" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig3c" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig3c" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Total</strong><br><span class="macro-original" lang="pt-BR"><em>Inadimplência da carteira de crédito – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21082" target="_blank" rel="noopener noreferrer"><strong>21082</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Non-financial corporations</strong><br><span class="macro-original" lang="pt-BR"><em>Inadimplência da carteira de crédito – Pessoas jurídicas – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21083" target="_blank" rel="noopener noreferrer"><strong>21083</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Households</strong><br><span class="macro-original" lang="pt-BR"><em>Inadimplência da carteira de crédito – Pessoas físicas – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21084" target="_blank" rel="noopener noreferrer"><strong>21084</strong></a>.<br>Frequency: monthly.</p>
            <p>Share of the credit portfolio with at least one installment more than 90 days past due. Includes earmarked and non-earmarked credit.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig3c" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig3c" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig3c" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://dadosabertos.bcb.gov.br/dataset/21082-inadimplencia-da-carteira-de-credito---total" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21082" target="_blank" rel="noopener noreferrer"><strong>21082</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21083" target="_blank" rel="noopener noreferrer"><strong>21083</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=21084" target="_blank" rel="noopener noreferrer"><strong>21084</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig3c" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig3d" class="macro-panel" role="group" aria-label="Household and corporate lending rates">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig3d" class="macro-plot-title">Household and corporate lending rates</h3>
          <p class="macro-plot-subtitle">Average annual interest rates on new loans across Brazil’s financial system.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig3d" class="macro-chart" aria-labelledby="title-fig3d" aria-busy="true"></div>
            <div id="presidents-fig3d" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig3d" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig3d" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Households</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa média de juros das operações de crédito – pessoas físicas – total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20716" target="_blank" rel="noopener noreferrer"><strong>20716</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Companies</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa média de juros das operações de crédito – pessoas jurídicas – total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20715" target="_blank" rel="noopener noreferrer"><strong>20715</strong></a>.<br>Frequency: monthly.</p>
            <p>Average interest rates on new credit operations, weighted by amounts granted. The series cover both earmarked and non-earmarked credit.</p>
            <p>The rates are annual percentages observed monthly, as published by the BCB; they are not monthly interest rates and are not annualized again.</p>
            <p>These indicators refer to credit across Brazil’s financial system, not specifically to BNDES.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig3d" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig3d" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig3d" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20716" target="_blank" rel="noopener noreferrer"><strong>20716</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=20715" target="_blank" rel="noopener noreferrer"><strong>20715</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig3d" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig3e" class="macro-panel" role="group" aria-label="Household debt and debt-service burden">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig3e" class="macro-plot-title">Household debt and debt-service burden</h3>
          <p class="macro-plot-subtitle">Debt is measured against 12-month income; debt service against monthly income.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig3e" class="macro-chart" aria-labelledby="title-fig3e" aria-busy="true"></div>
            <div id="presidents-fig3e" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig3e" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig3e" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Debt / 12-month income</strong><br><span class="macro-original" lang="pt-BR"><em>Endividamento das famílias com o Sistema Financeiro Nacional em relação à renda acumulada dos últimos doze meses</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29037" target="_blank" rel="noopener noreferrer"><strong>29037</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Debt service / monthly income</strong><br><span class="macro-original" lang="pt-BR"><em>Comprometimento de renda das famílias com o serviço da dívida com o Sistema Financeiro Nacional – com ajuste sazonal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29034" target="_blank" rel="noopener noreferrer"><strong>29034</strong></a>.<br>Frequency: monthly.</p>
            <p>Household indebtedness is the outstanding debt stock with the national financial system divided by household income accumulated over the previous twelve months.</p>
            <p>The debt-service burden relates expected interest and amortization payments to monthly household income, published as a seasonally adjusted three-month moving average.</p>
            <p>Both series are percentages, but their income denominators differ. They are plotted on one common scale without additional moving averages.</p>
            <p>The indicators cover households’ debt with the national financial system, not specifically BNDES loans.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig3e" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig3e" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig3e" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29037" target="_blank" rel="noopener noreferrer"><strong>29037</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=29034" target="_blank" rel="noopener noreferrer"><strong>29034</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig3e" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>

  <section id="section-industry-retail" class="macro-section" aria-labelledby="heading-industry-retail">
    <h2 id="heading-industry-retail" class="macro-heading">Industry, retail and consumer confidence</h2>
    <div id="panel-fig4a" class="macro-panel" role="group" aria-label="Industrial production and retail trade">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig4a" class="macro-plot-title">Industrial production and retail trade</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig4a" class="macro-chart" aria-labelledby="title-fig4a" aria-busy="true"></div>
            <div id="presidents-fig4a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig4a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig4a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Industrial production</strong><br><span class="macro-original" lang="pt-BR"><em>Produção industrial – indústria geral – com ajuste sazonal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28503" target="_blank" rel="noopener noreferrer"><strong>28503</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Retail trade</strong><br><span class="macro-original" lang="pt-BR"><em>Índice de volume de vendas no varejo – Brasil – com ajuste sazonal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28473" target="_blank" rel="noopener noreferrer"><strong>28473</strong></a>.<br>Frequency: monthly.</p>
            <p>Both series are seasonally adjusted native indices with 2022 = 100. No additional rebasing is applied.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig4a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig4a" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig4a" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28503" target="_blank" rel="noopener noreferrer"><strong>28503</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28473" target="_blank" rel="noopener noreferrer"><strong>28473</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig4a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig4b" class="macro-panel" role="group" aria-label="Consumer confidence indicators">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig4b" class="macro-plot-title">Consumer confidence indicators</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig4b" class="macro-chart" aria-labelledby="title-fig4b" aria-busy="true"></div>
            <div id="presidents-fig4b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig4b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig4b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Consumer confidence index</strong><br><span class="macro-original" lang="pt-BR"><em>Índice de Confiança do Consumidor</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4393" target="_blank" rel="noopener noreferrer"><strong>4393</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Current economic conditions index</strong><br><span class="macro-original" lang="pt-BR"><em>Índice de Condições Econômicas Atuais</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4394" target="_blank" rel="noopener noreferrer"><strong>4394</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Future expectations index</strong><br><span class="macro-original" lang="pt-BR"><em>Índice de Expectativas Futuras</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4395" target="_blank" rel="noopener noreferrer"><strong>4395</strong></a>.<br>Frequency: monthly.</p>
            <p>These confidence indices are produced by FecomercioSP and distributed through BCB-SGS.</p>
            <p>Native index values are shown without additional normalization.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig4b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig4b" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig4b" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4393" target="_blank" rel="noopener noreferrer"><strong>4393</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4394" target="_blank" rel="noopener noreferrer"><strong>4394</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=4395" target="_blank" rel="noopener noreferrer"><strong>4395</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig4b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>

  <section id="section-external-sector" class="macro-section" aria-labelledby="heading-external-sector">
    <h2 id="heading-external-sector" class="macro-heading">External sector</h2>
    <div id="panel-fig5a" class="macro-panel" role="group" aria-label="Exchange rate (USD/BRL)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5a" class="macro-plot-title">Exchange rate (USD/BRL)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5a" class="macro-chart" aria-labelledby="title-fig5a" aria-busy="true"></div>
            <div id="presidents-fig5a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Exchange rate — end of period</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa de câmbio – Livre – Dólar americano (compra) – fim de período – mensal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=3695" target="_blank" rel="noopener noreferrer"><strong>3695</strong></a>.<br>Frequency: monthly.</p>
            <p>End-of-period US dollar purchase rate, in BRL per USD.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig5a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5a" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=3695" target="_blank" rel="noopener noreferrer"><strong>3695</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig5b" class="macro-panel" role="group" aria-label="Current account and FDI (% of GDP)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5b" class="macro-plot-title">Current account and FDI (% of GDP)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5b" class="macro-chart" aria-labelledby="title-fig5b" aria-busy="true"></div>
            <div id="presidents-fig5b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Direct investment liabilities / GDP</strong><br><span class="macro-original" lang="pt-BR"><em>Investimento direto no país acumulado em 12 meses em relação ao PIB</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23080" target="_blank" rel="noopener noreferrer"><strong>23080</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Current account / GDP</strong><br><span class="macro-original" lang="pt-BR"><em>Transações correntes acumuladas em 12 meses em relação ao PIB</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23079" target="_blank" rel="noopener noreferrer"><strong>23079</strong></a>.<br>Frequency: monthly.</p>
            <p>Both BCB series are already accumulated over 12 months as a percentage of GDP; no additional accumulation is applied.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig5b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5b" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig5b" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23080" target="_blank" rel="noopener noreferrer"><strong>23080</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23079" target="_blank" rel="noopener noreferrer"><strong>23079</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig5c" class="macro-panel" role="group" aria-label="Real effective exchange rate and unit labor cost">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5c" class="macro-plot-title">Real effective exchange rate and unit labor cost</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5c" class="macro-chart" aria-labelledby="title-fig5c" aria-busy="true"></div>
            <div id="presidents-fig5c" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5c" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5c" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Real effective exchange rate (IPCA), MA3</strong><br><span class="macro-original" lang="pt-BR"><em>Índice da taxa de câmbio real efetiva (IPCA)</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=11752" target="_blank" rel="noopener noreferrer"><strong>11752</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Unit labor cost (USD), MA3</strong><br><span class="macro-original" lang="pt-BR"><em>Custo unitário do trabalho – CUT-US$</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=11777" target="_blank" rel="noopener noreferrer"><strong>11777</strong></a>.<br>Frequency: monthly.</p>
            <p>Trailing three-month arithmetic means are computed after the display-period cutoff.</p>
            <p>Native index levels are retained without additional rebasing.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig5c" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5c" type="button" disabled>Download PNG</button>
        <div class="macro-indicators">
          <p class="macro-key-title">Indicators</p>
          <div id="keys-fig5c" class="macro-keys" aria-label="Indicator line styles"></div>
        </div>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=11752" target="_blank" rel="noopener noreferrer"><strong>11752</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=11777" target="_blank" rel="noopener noreferrer"><strong>11777</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5c" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig5d" class="macro-panel" role="group" aria-label="External debt rollover rate (12-month sum)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5d" class="macro-plot-title">External debt rollover rate (12-month sum)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5d" class="macro-chart" aria-labelledby="title-fig5d" aria-busy="true"></div>
            <div id="presidents-fig5d" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5d" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5d" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Credit inflows / credit amortization</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa de rolagem – acumulada em 12 meses – Total – mensal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23070" target="_blank" rel="noopener noreferrer"><strong>23070</strong></a>.<br>Frequency: monthly.</p>
            <p>The published percentage is divided by 100; a ratio of 1 represents full rollover.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig5d" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5d" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=23070" target="_blank" rel="noopener noreferrer"><strong>23070</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5d" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig5e" class="macro-panel" role="group" aria-label="Goods exports, imports and trade balance">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5e" class="macro-plot-title">Goods exports, imports and trade balance</h3>
          <p class="macro-plot-subtitle">Trade in goods, in current USD; rolling 12-month totals.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5e" class="macro-chart" aria-labelledby="title-fig5e" aria-busy="true"></div>
            <div id="presidents-fig5e" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5e" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5e" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Exports</strong><br><span class="macro-original" lang="pt-BR"><em>Exportação de bens – Balanço de Pagamentos – mensal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22708" target="_blank" rel="noopener noreferrer"><strong>22708</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Imports</strong><br><span class="macro-original" lang="pt-BR"><em>Importação de bens – Balanço de Pagamentos – mensal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22709" target="_blank" rel="noopener noreferrer"><strong>22709</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Trade balance</strong><br><span class="macro-original" lang="pt-BR"><em>Balança comercial – Balanço de Pagamentos – mensal – saldo</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22707" target="_blank" rel="noopener noreferrer"><strong>22707</strong></a>.<br>Frequency: monthly.</p>
            <p>Monthly flows of goods exports, imports and the trade balance, compiled under the BPM6 balance-of-payments framework.</p>
            <p>Each series is summed over twelve consecutive months, including the months before the display cutoff where needed, and converted from USD millions to USD billions. Values are nominal, not inflation-adjusted.</p>
            <p>A positive trade balance is a surplus; a negative balance is a deficit. Negative values are retained.</p>
            <p>BCB balance-of-payments trade data include coverage adjustments and may differ from customs-based figures published directly by the MDIC.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig5e" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5e" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig5e" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://dadosabertos.bcb.gov.br/dataset/22708-exportacao-de-bens---balanco-de-pagamentos---mensal" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22708" target="_blank" rel="noopener noreferrer"><strong>22708</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22709" target="_blank" rel="noopener noreferrer"><strong>22709</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=22707" target="_blank" rel="noopener noreferrer"><strong>22707</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5e" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig5f" class="macro-panel" role="group" aria-label="International reserves">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig5f" class="macro-plot-title">International reserves</h3>
          <p class="macro-plot-subtitle">Monthly reserve stocks, expressed in current USD.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig5f" class="macro-chart" aria-labelledby="title-fig5f" aria-busy="true"></div>
            <div id="presidents-fig5f" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig5f" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig5f" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>International reserves</strong><br><span class="macro-original" lang="pt-BR"><em>Reservas internacionais – Total – mensal</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=3546" target="_blank" rel="noopener noreferrer"><strong>3546</strong></a>.<br>Frequency: monthly.</p>
            <p>Monthly international reserve stocks, as published in SGS 3546, converted from USD millions to USD billions.</p>
            <p>Reserves are a stock: monthly positions are not summed over twelve months.</p>
            <p>Changes in the USD value may reflect transactions, asset-price movements and exchange-rate valuation effects.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig5f" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig5f" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=3546" target="_blank" rel="noopener noreferrer"><strong>3546</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig5f" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>

  <section id="section-labor-market" class="macro-section" aria-labelledby="heading-labor-market">
    <h2 id="heading-labor-market" class="macro-heading">Labor market</h2>
    <div id="panel-fig6a" class="macro-panel" role="group" aria-label="Stock of formal jobs in Brazil">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig6a" class="macro-plot-title">Stock of formal jobs in Brazil</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig6a" class="macro-chart" aria-labelledby="title-fig6a" aria-busy="true"></div>
            <div id="presidents-fig6a" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig6a" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig6a" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Formal jobs</strong><br><span class="macro-original" lang="pt-BR"><em>Estoque de empregos formais – Total</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28763" target="_blank" rel="noopener noreferrer"><strong>28763</strong></a>.<br>Frequency: monthly.</p>
            <p>The native series is measured in individual jobs and is divided by one million.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig6a" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig6a" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=28763" target="_blank" rel="noopener noreferrer"><strong>28763</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig6a" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig6b" class="macro-panel" role="group" aria-label="Unemployment rate (moving quarter)">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig6b" class="macro-plot-title">Unemployment rate (moving quarter)</h3>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig6b" class="macro-chart" aria-labelledby="title-fig6b" aria-busy="true"></div>
            <div id="presidents-fig6b" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig6b" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig6b" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Unemployment rate</strong><br><span class="macro-original" lang="pt-BR"><em>Taxa de desocupação – PNADC</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24369" target="_blank" rel="noopener noreferrer"><strong>24369</strong></a>.<br>Frequency: monthly.</p>
            <p>This is the published PNADC moving-quarter unemployment rate; no additional moving average is applied.</p>
            <p>The first available observation is March 2012.</p>
              <p><strong>Latest observation</strong></p>
              <div id="latest-fig6b" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig6b" type="button" disabled>Download PNG</button>
          <p class="macro-source">Source: <a href="https://www.bcb.gov.br/en/statistics" target="_blank" rel="noopener noreferrer">Brazilian Central Bank (BCB)</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, code <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24369" target="_blank" rel="noopener noreferrer"><strong>24369</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig6b" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>

    <div id="panel-fig6c" class="macro-panel" role="group" aria-label="Labor force, employment and unemployment">
      <div class="macro-layout">
        <div class="macro-plot-header">
          <h3 id="title-fig6c" class="macro-plot-title">Labor force, employment and unemployment</h3>
          <p class="macro-plot-subtitle">PNAD Continuous Survey, moving-quarter estimates; millions of people.</p>
        </div>
        <div class="macro-figure">
          <div class="macro-canvas">
            <div id="chart-fig6c" class="macro-chart" aria-labelledby="title-fig6c" aria-busy="true"></div>
            <div id="presidents-fig6c" class="macro-presidents" role="group" aria-label="Presidents" hidden>
              <div class="macro-presidents-title">Presidents</div>
              <div id="president-items-fig6c" class="macro-presidents-items"></div>
            </div>
          </div>
        </div>
        <aside class="macro-sidebar" aria-label="Chart information and download">
          <details id="info-fig6c" class="macro-about">
            <summary>About the data</summary>
            <div class="macro-info">
            <p class="macro-series"><strong>Labor force — left axis</strong><br><span class="macro-original" lang="pt-BR"><em>População na força de trabalho – PNADC</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24378" target="_blank" rel="noopener noreferrer"><strong>24378</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Employed people — left axis</strong><br><span class="macro-original" lang="pt-BR"><em>Pessoas ocupadas – PNADC</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24379" target="_blank" rel="noopener noreferrer"><strong>24379</strong></a>.<br>Frequency: monthly.</p>
            <p class="macro-series"><strong>Unemployed people — right axis</strong><br><span class="macro-original" lang="pt-BR"><em>Pessoas desocupadas – PNADC</em></span><br>SGS: <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24380" target="_blank" rel="noopener noreferrer"><strong>24380</strong></a>.<br>Frequency: monthly.</p>
            <p>The three series are estimates from the IBGE Continuous National Household Sample Survey (PNAD Continuous Survey), distributed through the SGS, for people aged 14 or older.</p>
            <p>Labor force and employed people use the left axis, fixed from 80 to 110 million people. Unemployed people use the right axis, fixed from 0 to 30 million people.</p>
            <p>The published SGS unit is thousands of people. Each value is divided by 1,000 to display millions of people; it is not divided by one million.</p>
            <p>Each date denotes the moving three-month reference period ending in that month. These are not counts for an isolated month. No additional moving average, seasonal adjustment or interpolation is applied.</p>
            <p>Labor force equals employed plus unemployed people, apart from rounding in the published series. The display starts with the moving quarter ending in March 2012.</p>
              <p><strong>Latest observations</strong></p>
              <div id="latest-fig6c" class="macro-latest" aria-live="polite">—</div>
            </div>
          </details>
          <button id="download-fig6c" type="button" disabled>Download PNG</button>
          <div class="macro-indicators"><p class="macro-key-title">Indicators</p><div id="keys-fig6c" class="macro-keys" aria-label="Indicator line styles"></div></div>
          <p class="macro-source">Source: <a href="https://www.ibge.gov.br/estatisticas/sociais/trabalho/9173-pnad-continua.html" target="_blank" rel="noopener noreferrer">IBGE – PNAD Continuous Survey</a> – <a href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries" target="_blank" rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>, codes <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24378" target="_blank" rel="noopener noreferrer"><strong>24378</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24379" target="_blank" rel="noopener noreferrer"><strong>24379</strong></a>, <a href="https://www3.bcb.gov.br/sgspub/consultarmetadados/consultarMetadadosSeries.do?method=consultarMetadadosSeriesInternet&amp;hdOidSerieSelecionada=24380" target="_blank" rel="noopener noreferrer"><strong>24380</strong></a>.</p>
        </aside>
      </div>
      <p id="status-fig6c" class="macro-status" role="status" aria-live="polite" hidden></p>
    </div>
  </section>
  <noscript>Enable JavaScript to view the charts.</noscript>
</div>



<script type="module">
const MANIFEST = {"sections":[{"id":"gdp","title":"GDP, activity and income","figure":1,"plots":[{"id":"fig1a","title":"GDP and GDP per capita, USD (current)","start":"2000-01-01","axis":{"title":"USD trillions","min":0,"max":3},"notes":["GDP is the accumulated 12-month total at current prices.","GDP per capita is annual; native observation dates are retained."],"traces":[{"code":4192,"label":"GDP — left axis","original_pt":"PIB acumulado nos últimos 12 meses em US$ milhões","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111","factor":1e-06},{"code":21776,"label":"GDP per capita — right axis","original_pt":"PIB per capita em US$ correntes","op":"identity","axis":"y2","frequency":"annual","type":"scatter","dash":"dash","width":1,"color":"#111","factor":0.001}],"axis2":{"title":"USD thousands"},"legend_mode":"inside","legend_layout":{"indicators":"bottom-right"},"mobile_legend_below":true,"mobile_legend_labels":["GDP (left)","Per capita (right)"]},{"id":"fig1b","title":"GDP and GDP per capita, BRL (constant)","start":"2000-01-01","axis":{"title":"BRL trillions","min":4,"max":12},"notes":["GDP is adjusted to December 2024 prices using a compounded IPCA index (SGS 433).","GDP per capita is already published at constant last-year prices by the BCB and is not deflated again. The two price bases differ."],"traces":[{"code":4382,"label":"GDP — left axis","original_pt":"PIB acumulado nos últimos 12 meses a preços correntes","op":"gdp_real","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.25,"color":"#111","factor":1e-06,"cpi":433,"base":"2024-12-01"},{"code":21777,"label":"GDP per capita — right axis","original_pt":"PIB per capita a preços constantes do último ano","op":"identity","axis":"y2","frequency":"annual","type":"scatter","dash":"dash","width":1,"color":"#111","factor":0.001}],"axis2":{"title":"BRL thousands"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["GDP (left)","Per capita (right)"]},{"id":"fig1c","title":"Real GDP growth (y/y)","start":"2000-01-01","axis":{"title":"%","min":-6,"max":17},"notes":["Annual real percentage change; native annual observations are retained."],"traces":[{"code":7326,"label":"Real GDP growth","original_pt":"PIB – variação real no ano","op":"identity","axis":"y","frequency":"annual","type":"bar","dash":"solid","width":1,"color":"#111","opacity":0.9}],"president_legend":{"columns":2,"position":"top-right"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig1d","title":"Real GDP growth by sector (y/y)","start":"2000-01-01","axis":{"title":"%","min":-6,"max":17},"notes":["Annual real percentage changes by sector."],"traces":[{"code":7327,"label":"Agriculture","original_pt":"PIB – agropecuária – variação real no ano","op":"identity","axis":"y","frequency":"annual","type":"bar","dash":"solid","width":1,"color":"#111"},{"code":7328,"label":"Industry","original_pt":"PIB – indústria – variação real no ano","op":"identity","axis":"y","frequency":"annual","type":"bar","dash":"solid","width":1,"color":"#111","opacity":0.6},{"code":7329,"label":"Services","original_pt":"PIB – serviços – variação real no ano","op":"identity","axis":"y","frequency":"annual","type":"bar","dash":"solid","width":1,"color":"#111","opacity":0.2}],"president_legend":{"columns":2,"position":"top-left"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig1e","title":"Monthly economic activity (IBC-Br)","start":"2003-01-01","axis":{"title":"Index (2022 = 100)"},"traces":[{"code":24364,"label":"IBC-Br","original_pt":"Índice de Atividade Econômica do Banco Central – IBC-Br – com ajuste sazonal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111"}],"notes":["Seasonally adjusted monthly activity index, as published by the BCB; average 2022 = 100.","IBC-Br has a different scope from the national accounts and should not be interpreted as monthly GDP.","Native monthly observations are retained; the available series starts in January 2003."],"subtitle":"IBC-Br is the Central Bank’s monthly indicator of economic activity.","source_url":"https://www.bcb.gov.br/en/statistics","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig1f","title":"Real household disposable income","start":"2003-03-01","axis":{"title":"BRL billions (constant prices)","min":300,"max":900,"fixed":true,"tickStep":100},"traces":[{"code":29027,"label":"Real household disposable income","original_pt":"Renda Nacional Disponível Bruta das Famílias – em valores constantes, deflacionada pelo IPCA, com ajuste sazonal (média móvel trimestral)","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111","factor":0.001}],"notes":["Household disposable income includes income from labour and capital plus net transfers; it is not a wage measure.","The published series is already deflated by the IPCA, seasonally adjusted and expressed as a three-month moving average. No further deflation, seasonal adjustment or moving average is applied.","Published millions of constant-price BRL are divided by 1,000 to display BRL billions; the BCB’s published price reference is retained."],"subtitle":"Inflation-adjusted household income from labour, capital and net transfers.","source_url":"https://dadosabertos.bcb.gov.br/dataset/29027-renda-nacional-disponivel-bruta-das-familias-em-valores-constantes-deflacionada-pelo-ipca-com","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig1g","title":"Household consumption, government consumption, investment and net exports","start":"2000-01-01","axis":{"title":"Index (2019 = 100)","fixed":true,"tickStep":20},"traces":[{"code":22110,"label":"Households","original_pt":"PIB trimestral – dados dessazonalizados – consumo das famílias","op":"rebase_year","axis":"y","frequency":"quarterly","type":"scatter","dash":"solid","width":1.5,"color":"#111","baseYear":2019,"legendLabel":"Households"},{"code":22111,"label":"Government","original_pt":"PIB trimestral – dados dessazonalizados – consumo do governo","op":"rebase_year","axis":"y","frequency":"quarterly","type":"scatter","dash":"dash","width":1.5,"color":"#111","baseYear":2019,"legendLabel":"Government"},{"code":22113,"label":"Gross fixed capital formation","legendLabel":"Investment","original_pt":"PIB trimestral – dados dessazonalizados – formação bruta de capital fixo","op":"rebase_year","axis":"y","frequency":"quarterly","type":"scatter","dash":"dot","width":1.5,"color":"#111","baseYear":2019},{"code":22114,"subtractCode":22115,"label":"Net exports (2019-weighted proxy)","legendLabel":"X−M proxy (right)","original_pt":"Exportações líquidas de bens e serviços – indicador calculado com pesos de 2019","op":"net_exports_rebase_year","axis":"y2","frequency":"quarterly","type":"scatter","dash":"dashdot","width":1.5,"color":"#111","baseYear":2019,"exportsWeight":260890.25,"importsWeight":272794.5}],"notes":["Consumption and investment are seasonally adjusted quarterly volume indices from the national accounts, distributed through the SGS.","Each consumption and investment series is divided by its own average across the four quarters of 2019 and multiplied by 100.","Net exports are a calculated volume-balance proxy. The export and import volume indices are separately divided by their own 2019 averages, then weighted by average quarterly current-price exports and imports in 2019, subtracted, and rebased to average 2019 = 100.","The fixed 2019 weights are BRL 260,890.25 million for exports and BRL 272,794.50 million for imports, from IBGE SIDRA table 1846. The reference balance is −BRL 11,904.25 million per quarter.","Net exports index = 100 × [260,890.25 × (export volume / its 2019 average) − 272,794.50 × (import volume / its 2019 average)] / (260,890.25 − 272,794.50).","The 2019 reference balance is negative: a higher net-exports index represents a lower constructed balance; a negative index represents a positive constructed balance.","All four series have an average of 100 in 2019. The indices compare changes over time, not absolute sizes or GDP shares. They are not additive and do not sum to GDP; the net-exports indicator is not an official chained-volume aggregate or the current-account balance.","Investment is gross fixed capital formation (GFCF), including public and private investment in fixed assets; it excludes changes in inventories.","Native quarterly dates and observations are retained. Export and import inputs are already seasonally adjusted; no further adjustment, interpolation or smoothing is applied.","Consumption and investment use the left axis; net exports use the right axis. Both axes are indices with average 2019 = 100, and the reference value of 100 is aligned at the same height. The two axis scales differ."],"subtitle":"Average 2019 = 100. Consumption and investment: left axis; net exports: right axis.","source_url":"https://www.bcb.gov.br/en/statistics","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","reference_line":100,"source_caption":"Source: BCB–SGS 22110, 22111, 22113, 22114, 22115; IBGE–SIDRA 1846 (2019 weights). Author’s calculations.","axis2":{"title":"Index (2019 = 100)","fixed":true,"tickStep":200},"align_index_base":100,"export_notes":["X−M proxy: export and import volume indices weighted by average quarterly current-price exports and imports in 2019, differenced and rebased to 2019 = 100.","This is a calculated volume-balance indicator. A higher index means a lower constructed balance; the curves are not an additive GDP decomposition."],"mobile_legend_below":true},{"id":"fig1h","title":"Minimum wage: nominal and real","start":"1996-01-01","subtitle":"Monthly minimum wage; real values in December 2024 BRL.","axis":{"title":"BRL per month","min":0},"traces":[{"code":1619,"label":"Nominal minimum wage","legendLabel":"Nominal","original_pt":"Salário mínimo","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111"},{"code":1619,"cpi":433,"base":"2024-12-01","label":"Real minimum wage — December 2024 prices","legendLabel":"Real (Dec 2024 BRL)","original_pt":"Salário mínimo deflacionado pelo IPCA","op":"deflate_ipca","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#808080"}],"notes":["The nominal line is the statutory monthly minimum wage published in SGS 1619, in current BRL.","The real line is calculated from the same nominal series using the monthly IPCA percentage changes in SGS 433. Monthly rates are compounded into a price index; they are not added.","Real wage at month t = nominal wage at t × compounded IPCA index in December 2024 / compounded IPCA index at t.","The price reference is December 2024. Nominal and real values therefore coincide in that month. The two lines show BRL per month, with the real line expressed in December 2024 purchasing power.","The graph starts in January 1996. Observations dated after the current month are excluded, including any pre-published future minimum-wage observations.","The real line ends at the latest month for which both a nominal wage and a published IPCA observation exist. No inflation values are forecast or carried forward.","Native monthly observations are retained without additional seasonal adjustment or smoothing."],"source_url":"https://www.bcb.gov.br/en/statistics","source_caption":"Source: BCB–SGS 1619 (minimum wage) and 433 (monthly IPCA). Author’s calculations; real values in December 2024 BRL.","export_notes":["Real wage = nominal wage × compounded IPCA(Dec 2024) / compounded IPCA(t). Monthly observations since January 1996."],"president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true}]},{"id":"monetary-fiscal","title":"Monetary and fiscal policy","figure":2,"plots":[{"id":"fig2a","title":"IPCA, Selic and inflation target","start":"2000-01-01","axis":{"title":"%","min":0,"max":30,"fixed":true,"tickStep":5},"notes":["Selic is sampled at the first daily observation of each month.","The inflation target retains its native annual observations; IPCA is the published 12-month rate."],"traces":[{"code":13522,"label":"IPCA — 12-month change","original_pt":"IPCA – variação acumulada em 12 meses","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111","legendLabel":"IPCA"},{"code":1178,"label":"Selic — annualized, 252-day basis","original_pt":"Taxa de juros – Selic anualizada base 252","op":"monthly_first","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111","legendLabel":"Selic"},{"code":13521,"label":"Inflation target","original_pt":"Meta para a inflação","op":"identity","axis":"y","frequency":"annual","type":"scatter","dash":"solid","width":2,"color":"#111","legendLabel":"Inflation target","legendWidth":3.5}],"president_legend":{"columns":2,"position":"top-right"},"legend_layout":{"indicators":"top-aligned"},"legend_mode":"inside","subtitle":"Selic is Brazil’s benchmark interest rate, which influences other interest rates across the economy.","mobile_legend_below":true},{"id":"fig2b","title":"IPCA components (12-month inflation rate)","start":"2000-01-01","axis":{"title":"%","min":-6,"max":32},"notes":["Monthly price changes are compounded over 12 consecutive months before the display-period cutoff."],"traces":[{"code":4449,"label":"Administered prices","original_pt":"IPCA – preços monitorados","op":"compound12","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"},{"code":27864,"label":"Food at home","original_pt":"IPCA – alimentação no domicílio","op":"compound12","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111"},{"code":27863,"label":"Industrial goods","original_pt":"IPCA – bens industriais","op":"compound12","axis":"y","frequency":"monthly","type":"scatter","dash":"dot","width":1,"color":"#111"},{"code":10844,"label":"Services","original_pt":"IPCA – serviços","op":"compound12","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":0.9,"color":"#111","marker":"x","markerEvery":3}],"president_legend":{"columns":2,"position":"top-center"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Administered","Food at home","Industrial goods","Services"]},{"id":"fig2c","title":"Primary borrowing requirements (% of GDP)","start":"2000-01-01","axis":{"title":"% of GDP (12-month sum)","min":-4.5,"max":9.5},"notes":["Accumulated 12-month primary result of the consolidated public sector.","BCB borrowing-requirements sign convention: positive values indicate deficits and negative values indicate surpluses."],"traces":[{"code":5793,"label":"Primary borrowing requirements","original_pt":"NFSP sem desvalorização cambial – resultado primário – setor público consolidado","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"}],"president_legend":{"columns":2,"position":"top-left"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig2n","title":"Public sector borrowing requirements (% of GDP)","start":"2000-01-01","axis":{"title":"% of GDP","min":0},"notes":["Nominal result, excluding exchange rate effects, accumulated over 12 months."],"traces":[{"code":5727,"label":"Nominal borrowing requirements","original_pt":"NFSP sem desvalorização cambial – resultado nominal – setor público consolidado","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.8,"color":"#111"}],"president_legend":{"columns":2,"position":"top-left"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig2d","title":"Public debt (% of GDP)","start":"2000-01-01","axis":{"title":"% of GDP","min":20,"fixedMin":true,"tickStep":10},"notes":["Both lines are debt stocks expressed as a percentage of GDP, plotted on the same vertical scale starting at 20% of GDP. They are not accumulated 12-month flows.","Net public sector debt covers the consolidated public sector, while gross general government debt covers general government under the BCB methodology. Their institutional coverage differs; the gap between the lines is not simply government assets.","Gross general government debt uses the methodology adopted from 2008, with observations available from December 2006. No earlier values are imputed.","The upper axis limit adapts to both series and is rounded up to the next ten percentage points."],"traces":[{"code":4513,"label":"Net public sector debt","original_pt":"Dívida Líquida do Setor Público (% PIB) – Total – setor público consolidado","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.8,"color":"#111"},{"code":13762,"label":"Gross general government debt","original_pt":"Dívida bruta do governo geral (% PIB) – metodologia utilizada a partir de 2008","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.5,"color":"#111"}],"president_legend":{"columns":2,"position":"external"},"legend_layout":{"indicators":"bottom-right"},"subtitle":"Net public sector debt and gross general government debt have different institutional coverage.","legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Net debt","Gross debt"]}]},{"id":"credit-bndes","title":"Credit and household finances","figure":3,"plots":[{"id":"fig3a","title":"Credit and BNDES lending (% of GDP)","start":"2000-01-01","axis":{"title":"% of GDP","min":0,"max":58},"notes":["BNDES (Brazilian Development Bank) is Brazil’s federal public development bank.","The BNDES curve reproduces Fig. 3(a) in the supplied Python script: the 12-observation sum of SGS 7415, divided by the 12-month sum of GDP (4380), multiplied by 100.","SGS 7415 contains year-to-date disbursements. Summing these observations reproduces the original-script indicator; it is not the total of monthly disbursements over the previous 12 months.","The sector chart below retains the monthly-flow calculation described in its own notes."],"traces":[{"code":20622,"label":"Total credit / GDP","original_pt":"Saldo da carteira de crédito em relação ao PIB","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.25,"color":"#111"},{"code":7415,"label":"BNDES total lending / GDP","original_pt":"Desembolsos do sistema BNDES – Total","op":"bndes_original_gdp","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.25,"color":"#111","denominator":4380}],"president_legend":{"columns":2,"position":"middle-right"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Credit / GDP","BNDES / GDP"]},{"id":"fig3b","title":"BNDES lending by sector, BRL (current – not deflated)","start":"2000-01-01","axis":{"title":"BRL trillion (12-month sum)","min":0},"notes":["BNDES (Brazilian Development Bank) is Brazil’s federal public development bank.","Nominal disbursements, converted from cumulative year-to-date observations into monthly flows and then summed over 12 consecutive months.","Values are in current BRL trillions; the display cutoff is applied before the rolling sum."],"traces":[{"code":7415,"label":"Total","original_pt":"Desembolsos do sistema BNDES – Total","op":"ytd_sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.75,"color":"#111","factor":1e-06},{"code":7417,"label":"Commerce & services","original_pt":"Desembolsos do sistema BNDES – Comércio e serviços","op":"ytd_sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"dashdot","width":1,"color":"#111","factor":1e-06},{"code":7416,"label":"Manufacturing","original_pt":"Desembolsos do sistema BNDES – Indústria de transformação","op":"ytd_sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.25,"color":"#111","factor":1e-06},{"code":7418,"label":"Agriculture","original_pt":"Desembolsos do sistema BNDES – Agropecuária","op":"ytd_sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"dot","width":1,"color":"#111","factor":1e-06},{"code":7419,"label":"Mining","original_pt":"Desembolsos do sistema BNDES – Indústria extrativa","op":"ytd_sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111","factor":1e-06,"opacity":0.7}],"president_legend":{"columns":2,"position":"top-left"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Total","Trade & services","Manufacturing","Agriculture","Mining"]},{"id":"fig3c","title":"Loan delinquency rates (% of credit portfolio)","start":"2011-03-01","axis":{"title":"% of credit portfolio","min":0},"source_url":"https://dadosabertos.bcb.gov.br/dataset/21082-inadimplencia-da-carteira-de-credito---total","notes":["Share of the credit portfolio with at least one installment more than 90 days past due. Includes earmarked and non-earmarked credit."],"traces":[{"code":21082,"label":"Total","original_pt":"Inadimplência da carteira de crédito – Total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.8,"color":"#111"},{"code":21083,"label":"Non-financial corporations","original_pt":"Inadimplência da carteira de crédito – Pessoas jurídicas – Total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.4,"color":"#111"},{"code":21084,"label":"Households","original_pt":"Inadimplência da carteira de crédito – Pessoas físicas – Total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dot","width":1.4,"color":"#111"}],"president_legend":{"columns":2,"position":"bottom-left"},"legend_mode":"inside","subtitle":"The delinquency rates shown here refer to the credit portfolio of Brazil’s financial system as a whole, not specifically to BNDES’s portfolio.","mobile_legend_below":true,"mobile_legend_labels":["Total","Companies","Households"]},{"id":"fig3d","title":"Household and corporate lending rates","start":"2011-03-01","axis":{"title":"% per year","min":0},"traces":[{"code":20716,"label":"Households","original_pt":"Taxa média de juros das operações de crédito – pessoas físicas – total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111"},{"code":20715,"label":"Companies","original_pt":"Taxa média de juros das operações de crédito – pessoas jurídicas – total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.5,"color":"#111"}],"notes":["Average interest rates on new credit operations, weighted by amounts granted. The series cover both earmarked and non-earmarked credit.","The rates are annual percentages observed monthly, as published by the BCB; they are not monthly interest rates and are not annualized again.","These indicators refer to credit across Brazil’s financial system, not specifically to BNDES."],"subtitle":"Average annual interest rates on new loans across Brazil’s financial system.","source_url":"https://www.bcb.gov.br/en/statistics","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig3e","title":"Household debt and debt-service burden","start":"2005-01-01","axis":{"title":"% of income","min":0},"traces":[{"code":29037,"label":"Debt / 12-month income","original_pt":"Endividamento das famílias com o Sistema Financeiro Nacional em relação à renda acumulada dos últimos doze meses","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111"},{"code":29034,"label":"Debt service / monthly income","original_pt":"Comprometimento de renda das famílias com o serviço da dívida com o Sistema Financeiro Nacional – com ajuste sazonal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.5,"color":"#111"}],"notes":["Household indebtedness is the outstanding debt stock with the national financial system divided by household income accumulated over the previous twelve months.","The debt-service burden relates expected interest and amortization payments to monthly household income, published as a seasonally adjusted three-month moving average.","Both series are percentages, but their income denominators differ. They are plotted on one common scale without additional moving averages.","The indicators cover households’ debt with the national financial system, not specifically BNDES loans."],"subtitle":"Debt is measured against 12-month income; debt service against monthly income.","source_url":"https://www.bcb.gov.br/en/statistics","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Debt stock","Debt service"]}],"description":"BNDES (Brazilian Development Bank) is Brazil’s federal public development bank."},{"id":"industry-retail","title":"Industry, retail and consumer confidence","figure":4,"plots":[{"id":"fig4a","title":"Industrial production and retail trade","start":"2000-01-01","axis":{"title":"Index (2022 = 100)","min":45,"max":125},"notes":["Both series are seasonally adjusted native indices with 2022 = 100. No additional rebasing is applied."],"traces":[{"code":28503,"label":"Industrial production","original_pt":"Produção industrial – indústria geral – com ajuste sazonal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"},{"code":28473,"label":"Retail trade","original_pt":"Índice de volume de vendas no varejo – Brasil – com ajuste sazonal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111"}],"president_legend":{"columns":2,"position":"bottom-right"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Industrial output","Retail trade"]},{"id":"fig4b","title":"Consumer confidence indicators","start":"2000-01-01","axis":{"title":"Index","min":20,"max":180},"notes":["These confidence indices are produced by FecomercioSP and distributed through BCB-SGS.","Native index values are shown without additional normalization."],"traces":[{"code":4393,"label":"Consumer confidence index","original_pt":"Índice de Confiança do Consumidor","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"},{"code":4394,"label":"Current economic conditions index","original_pt":"Índice de Condições Econômicas Atuais","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111"},{"code":4395,"label":"Future expectations index","original_pt":"Índice de Expectativas Futuras","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dot","width":1,"color":"#111"}],"president_legend":{"columns":2,"position":"bottom-left","inset_x":0.14},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Confidence","Current conditions","Expectations"]}]},{"id":"external-sector","title":"External sector","figure":5,"plots":[{"id":"fig5a","title":"Exchange rate (USD/BRL)","start":"2000-01-01","axis":{"title":"BRL per USD","min":1.5,"max":6.5},"notes":["End-of-period US dollar purchase rate, in BRL per USD."],"traces":[{"code":3695,"label":"Exchange rate — end of period","original_pt":"Taxa de câmbio – Livre – Dólar americano (compra) – fim de período – mensal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":0.9,"color":"#111"}],"president_legend":{"columns":2,"position":"bottom-right"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig5b","title":"Current account and FDI (% of GDP)","start":"2000-01-01","axis":{"title":"% of GDP (12-month sum)","min":-5.5,"max":5.5},"notes":["Both BCB series are already accumulated over 12 months as a percentage of GDP; no additional accumulation is applied."],"traces":[{"code":23080,"label":"Direct investment liabilities / GDP","original_pt":"Investimento direto no país acumulado em 12 meses em relação ao PIB","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"},{"code":23079,"label":"Current account / GDP","original_pt":"Transações correntes acumuladas em 12 meses em relação ao PIB","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111"}],"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["FDI","Current account"]},{"id":"fig5c","title":"Real effective exchange rate and unit labor cost","start":"2000-01-01","axis":{"title":"Index, 3-month moving average","min":20,"max":180},"notes":["Trailing three-month arithmetic means are computed after the display-period cutoff.","Native index levels are retained without additional rebasing."],"traces":[{"code":11752,"label":"Real effective exchange rate (IPCA), MA3","original_pt":"Índice da taxa de câmbio real efetiva (IPCA)","op":"mean3","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111"},{"code":11777,"label":"Unit labor cost (USD), MA3","original_pt":"Custo unitário do trabalho – CUT-US$","op":"mean3","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1,"color":"#111"}],"president_legend":{"columns":2,"position":"bottom-right"},"legend_mode":"inside","mobile_legend_below":true,"mobile_legend_labels":["Real exchange rate","Unit labor cost"]},{"id":"fig5d","title":"External debt rollover rate (12-month sum)","start":"2000-01-01","axis":{"title":"Ratio","min":0,"max":5},"notes":["The published percentage is divided by 100; a ratio of 1 represents full rollover."],"traces":[{"code":23070,"label":"Credit inflows / credit amortization","original_pt":"Taxa de rolagem – acumulada em 12 meses – Total – mensal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1,"color":"#111","factor":0.01}],"president_legend":{"columns":2,"position":"top-left"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig5e","title":"Goods exports, imports and trade balance","start":"2000-01-01","axis":{"title":"USD billions (12-month sum)","min":0},"traces":[{"code":22708,"label":"Exports","original_pt":"Exportação de bens – Balanço de Pagamentos – mensal","op":"sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111","factor":0.001},{"code":22709,"label":"Imports","original_pt":"Importação de bens – Balanço de Pagamentos – mensal","op":"sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.5,"color":"#111","factor":0.001},{"code":22707,"label":"Trade balance","original_pt":"Balança comercial – Balanço de Pagamentos – mensal – saldo","op":"sum12","axis":"y","frequency":"monthly","type":"scatter","dash":"dashdot","width":1.5,"color":"#111","factor":0.001}],"notes":["Monthly flows of goods exports, imports and the trade balance, compiled under the BPM6 balance-of-payments framework.","Each series is summed over twelve consecutive months, including the months before the display cutoff where needed, and converted from USD millions to USD billions. Values are nominal, not inflation-adjusted.","A positive trade balance is a surplus; a negative balance is a deficit. Negative values are retained.","BCB balance-of-payments trade data include coverage adjustments and may differ from customs-based figures published directly by the MDIC."],"subtitle":"Trade in goods, in current USD; rolling 12-month totals.","source_url":"https://dadosabertos.bcb.gov.br/dataset/22708-exportacao-de-bens---balanco-de-pagamentos---mensal","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true},{"id":"fig5f","title":"International reserves","start":"2000-01-01","axis":{"title":"USD billions","min":0},"traces":[{"code":3546,"label":"International reserves","original_pt":"Reservas internacionais – Total – mensal","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111","factor":0.001}],"notes":["Monthly international reserve stocks, as published in SGS 3546, converted from USD millions to USD billions.","Reserves are a stock: monthly positions are not summed over twelve months.","Changes in the USD value may reflect transactions, asset-price movements and exchange-rate valuation effects."],"subtitle":"Monthly reserve stocks, expressed in current USD.","source_url":"https://www.bcb.gov.br/en/statistics","president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true}]},{"id":"labor-market","title":"Labor market","figure":6,"plots":[{"id":"fig6a","title":"Stock of formal jobs in Brazil","start":"2012-01-01","axis":{"title":"Millions of jobs","min":37.75,"max":48.25},"notes":["The native series is measured in individual jobs and is divided by one million."],"traces":[{"code":28763,"label":"Formal jobs","original_pt":"Estoque de empregos formais – Total","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.25,"color":"#111","factor":1e-06}],"legend_mode":"inside","mobile_legend_below":true},{"id":"fig6b","title":"Unemployment rate (moving quarter)","start":"2012-01-01","axis":{"title":"%","min":5.5,"max":15.5},"notes":["This is the published PNADC moving-quarter unemployment rate; no additional moving average is applied.","The first available observation is March 2012; January and February are not filled."],"traces":[{"code":24369,"label":"Unemployment rate","original_pt":"Taxa de desocupação – PNADC","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.25,"color":"#111"}],"legend_mode":"inside","mobile_legend_below":true},{"id":"fig6c","title":"Labor force, employment and unemployment","start":"2012-03-01","subtitle":"PNAD Continuous Survey, moving-quarter estimates; millions of people.","axis":{"title":"Millions of people","min":80,"max":110,"fixed":true,"tickStep":5},"axis2":{"title":"Unemployed (millions)","min":0,"max":30,"fixed":true,"tickStep":5},"traces":[{"code":24378,"label":"Labor force — left axis","legendLabel":"Labor force","original_pt":"População na força de trabalho – PNADC","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"solid","width":1.5,"color":"#111","factor":0.001},{"code":24379,"label":"Employed people — left axis","legendLabel":"Employed","original_pt":"Pessoas ocupadas – PNADC","op":"identity","axis":"y","frequency":"monthly","type":"scatter","dash":"dash","width":1.5,"color":"#111","factor":0.001},{"code":24380,"label":"Unemployed people — right axis","legendLabel":"Unemployed (right)","original_pt":"Pessoas desocupadas – PNADC","op":"identity","axis":"y2","frequency":"monthly","type":"scatter","dash":"dot","width":1.5,"color":"#111","factor":0.001}],"notes":["The three series are estimates from the IBGE Continuous National Household Sample Survey (PNAD Continuous Survey), distributed through the SGS, for people aged 14 or older.","Labor force and employed people use the left axis, fixed from 80 to 110 million people. Unemployed people use the right axis, fixed from 0 to 30 million people.","The published SGS unit is thousands of people. Each value is divided by 1,000 to display millions of people; it is not divided by one million.","Each date denotes the moving three-month reference period ending in that month. These are not counts for an isolated month. No additional moving average, seasonal adjustment or interpolation is applied.","Labor force equals employed plus unemployed people, apart from rounding in the published series. The display starts with the moving quarter ending in March 2012."],"source_url":"https://www.ibge.gov.br/estatisticas/sociais/trabalho/9173-pnad-continua.html","source_caption":"Source: IBGE, PNAD Continuous Survey; BCB–SGS 24378, 24379 and 24380. Published thousands converted to millions.","export_notes":["Moving-quarter estimates for people aged 14 or older. Labor force and employed: left axis; unemployed: right axis."],"president_legend":{"columns":2,"position":"external"},"legend_mode":"inside","mobile_legend_below":true}]}]};
const PACKED_SEEDS = {"433":"1996-01-01:1.34|1996-02-01:1.03|1996-03-01:0.35|1996-04-01:1.26|1996-05-01:1.22|1996-06-01:1.19|1996-07-01:1.11|1996-08-01:0.44|1996-09-01:0.15|1996-10-01:0.3|1996-11-01:0.32|1996-12-01:0.47|1997-01-01:1.18|1997-02-01:0.5|1997-03-01:0.51|1997-04-01:0.88|1997-05-01:0.41|1997-06-01:0.54|1997-07-01:0.22|1997-08-01:-0.02|1997-09-01:0.06|1997-10-01:0.23|1997-11-01:0.17|1997-12-01:0.43|1998-01-01:0.71|1998-02-01:0.46|1998-03-01:0.34|1998-04-01:0.24|1998-05-01:0.5|1998-06-01:0.02|1998-07-01:-0.12|1998-08-01:-0.51|1998-09-01:-0.22|1998-10-01:0.02|1998-11-01:-0.12|1998-12-01:0.33|1999-01-01:0.7|1999-02-01:1.05|1999-03-01:1.1|1999-04-01:0.56|1999-05-01:0.3|1999-06-01:0.19|1999-07-01:1.09|1999-08-01:0.56|1999-09-01:0.31|1999-10-01:1.19|1999-11-01:0.95|1999-12-01:0.6|2000-01-01:0.62|2000-02-01:0.13|2000-03-01:0.22|2000-04-01:0.42|2000-05-01:0.01|2000-06-01:0.23|2000-07-01:1.61|2000-08-01:1.31|2000-09-01:0.23|2000-10-01:0.14|2000-11-01:0.32|2000-12-01:0.59|2001-01-01:0.57|2001-02-01:0.46|2001-03-01:0.38|2001-04-01:0.58|2001-05-01:0.41|2001-06-01:0.52|2001-07-01:1.33|2001-08-01:0.7|2001-09-01:0.28|2001-10-01:0.83|2001-11-01:0.71|2001-12-01:0.65|2002-01-01:0.52|2002-02-01:0.36|2002-03-01:0.6|2002-04-01:0.8|2002-05-01:0.21|2002-06-01:0.42|2002-07-01:1.19|2002-08-01:0.65|2002-09-01:0.72|2002-10-01:1.31|2002-11-01:3.02|2002-12-01:2.1|2003-01-01:2.25|2003-02-01:1.57|2003-03-01:1.23|2003-04-01:0.97|2003-05-01:0.61|2003-06-01:-0.15|2003-07-01:0.2|2003-08-01:0.34|2003-09-01:0.78|2003-10-01:0.29|2003-11-01:0.34|2003-12-01:0.52|2004-01-01:0.76|2004-02-01:0.61|2004-03-01:0.47|2004-04-01:0.37|2004-05-01:0.51|2004-06-01:0.71|2004-07-01:0.91|2004-08-01:0.69|2004-09-01:0.33|2004-10-01:0.44|2004-11-01:0.69|2004-12-01:0.86|2005-01-01:0.58|2005-02-01:0.59|2005-03-01:0.61|2005-04-01:0.87|2005-05-01:0.49|2005-06-01:-0.02|2005-07-01:0.25|2005-08-01:0.17|2005-09-01:0.35|2005-10-01:0.75|2005-11-01:0.55|2005-12-01:0.36|2006-01-01:0.59|2006-02-01:0.41|2006-03-01:0.43|2006-04-01:0.21|2006-05-01:0.1|2006-06-01:-0.21|2006-07-01:0.19|2006-08-01:0.05|2006-09-01:0.21|2006-10-01:0.33|2006-11-01:0.31|2006-12-01:0.48|2007-01-01:0.44|2007-02-01:0.44|2007-03-01:0.37|2007-04-01:0.25|2007-05-01:0.28|2007-06-01:0.28|2007-07-01:0.24|2007-08-01:0.47|2007-09-01:0.18|2007-10-01:0.3|2007-11-01:0.38|2007-12-01:0.74|2008-01-01:0.54|2008-02-01:0.49|2008-03-01:0.48|2008-04-01:0.55|2008-05-01:0.79|2008-06-01:0.74|2008-07-01:0.53|2008-08-01:0.28|2008-09-01:0.26|2008-10-01:0.45|2008-11-01:0.36|2008-12-01:0.28|2009-01-01:0.48|2009-02-01:0.55|2009-03-01:0.2|2009-04-01:0.48|2009-05-01:0.47|2009-06-01:0.36|2009-07-01:0.24|2009-08-01:0.15|2009-09-01:0.24|2009-10-01:0.28|2009-11-01:0.41|2009-12-01:0.37|2010-01-01:0.75|2010-02-01:0.78|2010-03-01:0.52|2010-04-01:0.57|2010-05-01:0.43|2010-06-01:0|2010-07-01:0.01|2010-08-01:0.04|2010-09-01:0.45|2010-10-01:0.75|2010-11-01:0.83|2010-12-01:0.63|2011-01-01:0.83|2011-02-01:0.8|2011-03-01:0.79|2011-04-01:0.77|2011-05-01:0.47|2011-06-01:0.15|2011-07-01:0.16|2011-08-01:0.37|2011-09-01:0.53|2011-10-01:0.43|2011-11-01:0.52|2011-12-01:0.5|2012-01-01:0.56|2012-02-01:0.45|2012-03-01:0.21|2012-04-01:0.64|2012-05-01:0.36|2012-06-01:0.08|2012-07-01:0.43|2012-08-01:0.41|2012-09-01:0.57|2012-10-01:0.59|2012-11-01:0.6|2012-12-01:0.79|2013-01-01:0.86|2013-02-01:0.6|2013-03-01:0.47|2013-04-01:0.55|2013-05-01:0.37|2013-06-01:0.26|2013-07-01:0.03|2013-08-01:0.24|2013-09-01:0.35|2013-10-01:0.57|2013-11-01:0.54|2013-12-01:0.92|2014-01-01:0.55|2014-02-01:0.69|2014-03-01:0.92|2014-04-01:0.67|2014-05-01:0.46|2014-06-01:0.4|2014-07-01:0.01|2014-08-01:0.25|2014-09-01:0.57|2014-10-01:0.42|2014-11-01:0.51|2014-12-01:0.78|2015-01-01:1.24|2015-02-01:1.22|2015-03-01:1.32|2015-04-01:0.71|2015-05-01:0.74|2015-06-01:0.79|2015-07-01:0.62|2015-08-01:0.22|2015-09-01:0.54|2015-10-01:0.82|2015-11-01:1.01|2015-12-01:0.96|2016-01-01:1.27|2016-02-01:0.9|2016-03-01:0.43|2016-04-01:0.61|2016-05-01:0.78|2016-06-01:0.35|2016-07-01:0.52|2016-08-01:0.44|2016-09-01:0.08|2016-10-01:0.26|2016-11-01:0.18|2016-12-01:0.3|2017-01-01:0.38|2017-02-01:0.33|2017-03-01:0.25|2017-04-01:0.14|2017-05-01:0.31|2017-06-01:-0.23|2017-07-01:0.24|2017-08-01:0.19|2017-09-01:0.16|2017-10-01:0.42|2017-11-01:0.28|2017-12-01:0.44|2018-01-01:0.29|2018-02-01:0.32|2018-03-01:0.09|2018-04-01:0.22|2018-05-01:0.4|2018-06-01:1.26|2018-07-01:0.33|2018-08-01:-0.09|2018-09-01:0.48|2018-10-01:0.45|2018-11-01:-0.21|2018-12-01:0.15|2019-01-01:0.32|2019-02-01:0.43|2019-03-01:0.75|2019-04-01:0.57|2019-05-01:0.13|2019-06-01:0.01|2019-07-01:0.19|2019-08-01:0.11|2019-09-01:-0.04|2019-10-01:0.1|2019-11-01:0.51|2019-12-01:1.15|2020-01-01:0.21|2020-02-01:0.25|2020-03-01:0.07|2020-04-01:-0.31|2020-05-01:-0.38|2020-06-01:0.26|2020-07-01:0.36|2020-08-01:0.24|2020-09-01:0.64|2020-10-01:0.86|2020-11-01:0.89|2020-12-01:1.35|2021-01-01:0.25|2021-02-01:0.86|2021-03-01:0.93|2021-04-01:0.31|2021-05-01:0.83|2021-06-01:0.53|2021-07-01:0.96|2021-08-01:0.87|2021-09-01:1.16|2021-10-01:1.25|2021-11-01:0.95|2021-12-01:0.73|2022-01-01:0.54|2022-02-01:1.01|2022-03-01:1.62|2022-04-01:1.06|2022-05-01:0.47|2022-06-01:0.67|2022-07-01:-0.68|2022-08-01:-0.36|2022-09-01:-0.29|2022-10-01:0.59|2022-11-01:0.41|2022-12-01:0.62|2023-01-01:0.53|2023-02-01:0.84|2023-03-01:0.71|2023-04-01:0.61|2023-05-01:0.23|2023-06-01:-0.08|2023-07-01:0.12|2023-08-01:0.23|2023-09-01:0.26|2023-10-01:0.24|2023-11-01:0.28|2023-12-01:0.56|2024-01-01:0.42|2024-02-01:0.83|2024-03-01:0.16|2024-04-01:0.38|2024-05-01:0.46|2024-06-01:0.21|2024-07-01:0.38|2024-08-01:-0.02|2024-09-01:0.44|2024-10-01:0.56|2024-11-01:0.39|2024-12-01:0.52|2025-01-01:0.16|2025-02-01:1.31|2025-03-01:0.56|2025-04-01:0.43|2025-05-01:0.26|2025-06-01:0.24|2025-07-01:0.26|2025-08-01:-0.11|2025-09-01:0.48|2025-10-01:0.09|2025-11-01:0.18|2025-12-01:0.33|2026-01-01:0.33|2026-02-01:0.7|2026-03-01:0.88|2026-04-01:0.67|2026-05-01:0.58|2026-06-01:0.16|2026-07-01:0.07|2026-08-01:-0.32|2026-09-01:0.82","1178":"1999-01-01:29.04|1999-02-01:38.79|1999-03-01:38.98|1999-04-01:41.91|1999-05-01:31.9|1999-06-01:23.28|1999-07-01:20.94|1999-08-01:19.51|1999-09-01:19.51|1999-10-01:19|1999-11-01:18.82|1999-12-01:19.02|2000-01-01:19.04|2000-02-01:18.87|2000-03-01:18.88|2000-04-01:18.49|2000-05-01:18.6|2000-06-01:18.44|2000-07-01:17.26|2000-08-01:16.4|2000-09-01:16.4|2000-10-01:16.59|2000-11-01:16.53|2000-12-01:16.4|2001-01-01:15.85|2001-02-01:15.12|2001-03-01:15.12|2001-04-01:15.83|2001-05-01:16.25|2001-06-01:16.81|2001-07-01:18.32|2001-08-01:18.88|2001-09-01:19.05|2001-10-01:19.1|2001-11-01:19.05|2001-12-01:19.05|2002-01-01:19.05|2002-02-01:19.05|2002-03-01:18.8|2002-04-01:18.47|2002-05-01:18.37|2002-06-01:17.31|2002-07-01:18.41|2002-08-01:17.83|2002-09-01:17.87|2002-10-01:17.9|2002-11-01:20.9|2002-12-01:21.9|2003-01-01:24.9|2003-02-01:25.38|2003-03-01:26.29|2003-04-01:26.32|2003-05-01:26.32|2003-06-01:26.26|2003-07-01:25.76|2003-08-01:24.33|2003-09-01:21.83|2003-10-01:19.83|2003-11-01:18.85|2003-12-01:17.31|2004-01-01:16.34|2004-02-01:16.29|2004-03-01:16.29|2004-04-01:16.1|2004-05-01:15.79|2004-06-01:15.78|2004-07-01:15.8|2004-08-01:15.82|2004-09-01:15.92|2004-10-01:16.23|2004-11-01:16.74|2004-12-01:17.23|2005-01-01:17.74|2005-02-01:18.24|2005-03-01:18.74|2005-04-01:19.24|2005-05-01:19.5|2005-06-01:19.76|2005-07-01:19.73|2005-08-01:19.74|2005-09-01:19.74|2005-10-01:19.48|2005-11-01:18.95|2005-12-01:18.52|2006-01-01:17.98|2006-02-01:17.23|2006-03-01:17.29|2006-04-01:16.45|2006-05-01:15.7|2006-06-01:15.17|2006-07-01:15.17|2006-08-01:14.66|2006-09-01:14.17|2006-10-01:14.16|2006-11-01:13.68|2006-12-01:13.18|2007-01-01:13.19|2007-02-01:12.93|2007-03-01:12.93|2007-04-01:12.68|2007-05-01:12.43|2007-06-01:12.43|2007-07-01:11.93|2007-08-01:11.43|2007-09-01:11.43|2007-10-01:11.18|2007-11-01:11.18|2007-12-01:11.18|2008-01-01:11.18|2008-02-01:11.18|2008-03-01:11.18|2008-04-01:11.18|2008-05-01:11.61|2008-06-01:11.64|2008-07-01:12.17|2008-08-01:12.92|2008-09-01:12.91|2008-10-01:13.66|2008-11-01:13.65|2008-12-01:13.65|2009-01-01:13.67|2009-02-01:12.66|2009-03-01:12.66|2009-04-01:11.16|2009-05-01:10.16|2009-06-01:10.16|2009-07-01:9.16|2009-08-01:8.65|2009-09-01:8.65|2009-10-01:8.65|2009-11-01:8.65|2009-12-01:8.65|2010-01-01:8.65|2010-02-01:8.65|2010-03-01:8.65|2010-04-01:8.65|2010-05-01:9.4|2010-06-01:9.4|2010-07-01:10.16|2010-08-01:10.66|2010-09-01:10.66|2010-10-01:10.66|2010-11-01:10.66|2010-12-01:10.66|2011-01-01:10.67|2011-02-01:11.16|2011-03-01:11.17|2011-04-01:11.67|2011-05-01:11.92|2011-06-01:11.92|2011-07-01:12.17|2011-08-01:12.42|2011-09-01:11.91|2011-10-01:11.9|2011-11-01:11.4|2011-12-01:10.9|2012-01-01:10.9|2012-02-01:10.4|2012-03-01:10.4|2012-04-01:9.65|2012-05-01:8.9|2012-06-01:8.39|2012-07-01:8.39|2012-08-01:7.89|2012-09-01:7.39|2012-10-01:7.39|2012-11-01:7.14|2012-12-01:7.14|2013-01-01:7.11|2013-02-01:7.11|2013-03-01:7.14|2013-04-01:7.16|2013-05-01:7.4|2013-06-01:7.9|2013-07-01:7.9|2013-08-01:8.4|2013-09-01:8.9|2013-10-01:8.9|2013-11-01:9.4|2013-12-01:9.9|2014-01-01:9.9|2014-02-01:10.4|2014-03-01:10.65|2014-04-01:10.65|2014-05-01:10.9|2014-06-01:10.9|2014-07-01:10.9|2014-08-01:10.9|2014-09-01:10.9|2014-10-01:10.9|2014-11-01:11.15|2014-12-01:11.15|2015-01-01:11.65|2015-02-01:12.15|2015-03-01:12.15|2015-04-01:12.65|2015-05-01:13.15|2015-06-01:13.15|2015-07-01:13.65|2015-08-01:14.15|2015-09-01:14.15|2015-10-01:14.15|2015-11-01:14.15|2015-12-01:14.15|2016-01-01:14.15|2016-02-01:14.15|2016-03-01:14.15|2016-04-01:14.15|2016-05-01:14.15|2016-06-01:14.15|2016-07-01:14.15|2016-08-01:14.15|2016-09-01:14.15|2016-10-01:14.15|2016-11-01:13.9|2016-12-01:13.65|2017-01-01:13.65|2017-02-01:12.9|2017-03-01:12.15|2017-04-01:12.15|2017-05-01:11.15|2017-06-01:10.15|2017-07-01:10.15|2017-08-01:9.15|2017-09-01:9.15|2017-10-01:8.15|2017-11-01:7.4|2017-12-01:7.4|2018-01-01:6.9|2018-02-01:6.9|2018-03-01:6.65|2018-04-01:6.4|2018-05-01:6.4|2018-06-01:6.4|2018-07-01:6.4|2018-08-01:6.4|2018-09-01:6.4|2018-10-01:6.4|2018-11-01:6.4|2018-12-01:6.4|2019-01-01:6.4|2019-02-01:6.4|2019-03-01:6.4|2019-04-01:6.4|2019-05-01:6.4|2019-06-01:6.4|2019-07-01:6.4|2019-08-01:5.9|2019-09-01:5.9|2019-10-01:5.4|2019-11-01:4.9|2019-12-01:4.9|2020-01-01:4.4|2020-02-01:4.4|2020-03-01:4.15|2020-04-01:3.65|2020-05-01:3.65|2020-06-01:2.9|2020-07-01:2.15|2020-08-01:2.15|2020-09-01:1.9|2020-10-01:1.9|2020-11-01:1.9|2020-12-01:1.9|2021-01-01:1.9|2021-02-01:1.9|2021-03-01:1.9|2021-04-01:2.65|2021-05-01:2.65|2021-06-01:3.4|2021-07-01:4.15|2021-08-01:4.15|2021-09-01:5.15|2021-10-01:6.15|2021-11-01:7.65|2021-12-01:7.65|2022-01-01:9.15|2022-02-01:9.15|2022-03-01:10.65|2022-04-01:11.65|2022-05-01:11.65|2022-06-01:12.65|2022-07-01:13.15|2022-08-01:13.15|2022-09-01:13.65|2022-10-01:13.65|2022-11-01:13.65|2022-12-01:13.65|2023-01-01:13.65|2023-02-01:13.65|2023-03-01:13.65|2023-04-01:13.65|2023-05-01:13.65|2023-06-01:13.65|2023-07-01:13.65|2023-08-01:13.65|2023-09-01:13.15|2023-10-01:12.65|2023-11-01:12.65|2023-12-01:12.15|2024-01-01:11.65|2024-02-01:11.15|2024-03-01:11.15|2024-04-01:10.65|2024-05-01:10.65|2024-06-01:10.4|2024-07-01:10.4|2024-08-01:10.4|2024-09-01:10.4|2024-10-01:10.65|2024-11-01:10.65|2024-12-01:11.15|2025-01-01:12.15|2025-02-01:13.15|2025-03-01:13.15|2025-04-01:14.15|2025-05-01:14.15|2025-06-01:14.65|2025-07-01:14.9|2025-08-01:14.9|2025-09-01:14.9|2025-10-01:14.9|2025-11-01:14.9|2025-12-01:14.9|2026-01-01:14.9|2026-02-01:14.9|2026-03-01:14.9|2026-04-01:14.65|2026-05-01:14.4|2026-06-01:14.4|2026-07-01:14.15|2026-08-01:14.15|2026-09-01:13.9|2026-10-01:13.65","3695":"1999-01-01:1.9824|1999-02-01:2.064|1999-03-01:1.7212|1999-04-01:1.6599|1999-05-01:1.7232|1999-06-01:1.7687|1999-07-01:1.7884|1999-08-01:1.9151|1999-09-01:1.9215|1999-10-01:1.9522|1999-11-01:1.9219|1999-12-01:1.7882|2000-01-01:1.8016|2000-02-01:1.7677|2000-03-01:1.7465|2000-04-01:1.8059|2000-05-01:1.8258|2000-06-01:1.7992|2000-07-01:1.774|2000-08-01:1.8226|2000-09-01:1.8429|2000-10-01:1.9082|2000-11-01:1.9588|2000-12-01:1.9546|2001-01-01:1.9703|2001-02-01:2.0444|2001-03-01:2.1608|2001-04-01:2.1839|2001-05-01:2.3592|2001-06-01:2.3041|2001-07-01:2.4305|2001-08-01:2.5509|2001-09-01:2.6705|2001-10-01:2.7063|2001-11-01:2.5279|2001-12-01:2.3196|2002-01-01:2.4175|2002-02-01:2.3474|2002-03-01:2.3228|2002-04-01:2.3617|2002-05-01:2.5212|2002-06-01:2.8436|2002-07-01:3.4277|2002-08-01:3.0215|2002-09-01:3.8941|2002-10-01:3.6442|2002-11-01:3.6357|2002-12-01:3.5325|2003-01-01:3.525|2003-02-01:3.5624|2003-03-01:3.3523|2003-04-01:2.889|2003-05-01:2.9648|2003-06-01:2.8712|2003-07-01:2.9647|2003-08-01:2.9657|2003-09-01:2.9226|2003-10-01:2.8554|2003-11-01:2.9486|2003-12-01:2.8884|2004-01-01:2.9401|2004-02-01:2.913|2004-03-01:2.9078|2004-04-01:2.9439|2004-05-01:3.1283|2004-06-01:3.1067|2004-07-01:3.026|2004-08-01:2.933|2004-09-01:2.8578|2004-10-01:2.8557|2004-11-01:2.7299|2004-12-01:2.6536|2005-01-01:2.624|2005-02-01:2.5942|2005-03-01:2.6654|2005-04-01:2.5305|2005-05-01:2.403|2005-06-01:2.3496|2005-07-01:2.3897|2005-08-01:2.3629|2005-09-01:2.2214|2005-10-01:2.2535|2005-11-01:2.2062|2005-12-01:2.3399|2006-01-01:2.2152|2006-02-01:2.1347|2006-03-01:2.1716|2006-04-01:2.0884|2006-05-01:2.2997|2006-06-01:2.1635|2006-07-01:2.1754|2006-08-01:2.138|2006-09-01:2.1734|2006-10-01:2.1422|2006-11-01:2.166|2006-12-01:2.1372|2007-01-01:2.1239|2007-02-01:2.1174|2007-03-01:2.0496|2007-04-01:2.0331|2007-05-01:1.9281|2007-06-01:1.9254|2007-07-01:1.8768|2007-08-01:1.9612|2007-09-01:1.8381|2007-10-01:1.7432|2007-11-01:1.7829|2007-12-01:1.7705|2008-01-01:1.7595|2008-02-01:1.6825|2008-03-01:1.7483|2008-04-01:1.6864|2008-05-01:1.6286|2008-06-01:1.5911|2008-07-01:1.5658|2008-08-01:1.6336|2008-09-01:1.9135|2008-10-01:2.1145|2008-11-01:2.3323|2008-12-01:2.3362|2009-01-01:2.3154|2009-02-01:2.3776|2009-03-01:2.3144|2009-04-01:2.1775|2009-05-01:1.9722|2009-06-01:1.9508|2009-07-01:1.8718|2009-08-01:1.8856|2009-09-01:1.7773|2009-10-01:1.7432|2009-11-01:1.7497|2009-12-01:1.7404|2010-01-01:1.874|2010-02-01:1.8102|2010-03-01:1.7802|2010-04-01:1.7298|2010-05-01:1.8159|2010-06-01:1.8007|2010-07-01:1.7564|2010-08-01:1.7552|2010-09-01:1.6934|2010-10-01:1.7006|2010-11-01:1.7153|2010-12-01:1.6654|2011-01-01:1.6726|2011-02-01:1.6604|2011-03-01:1.6279|2011-04-01:1.5725|2011-05-01:1.5791|2011-06-01:1.5603|2011-07-01:1.5555|2011-08-01:1.5864|2011-09-01:1.8536|2011-10-01:1.6878|2011-11-01:1.8102|2011-12-01:1.8751|2012-01-01:1.7385|2012-02-01:1.7086|2012-03-01:1.8215|2012-04-01:1.8912|2012-05-01:2.0217|2012-06-01:2.0207|2012-07-01:2.0494|2012-08-01:2.0366|2012-09-01:2.03|2012-10-01:2.0308|2012-11-01:2.1068|2012-12-01:2.0429|2013-01-01:1.9877|2013-02-01:1.9749|2013-03-01:2.0132|2013-04-01:2.0011|2013-05-01:2.1314|2013-06-01:2.215|2013-07-01:2.2897|2013-08-01:2.3719|2013-09-01:2.2294|2013-10-01:2.202|2013-11-01:2.3243|2013-12-01:2.342|2014-01-01:2.4257|2014-02-01:2.3327|2014-03-01:2.2624|2014-04-01:2.2354|2014-05-01:2.2384|2014-06-01:2.2019|2014-07-01:2.2668|2014-08-01:2.239|2014-09-01:2.4504|2014-10-01:2.4436|2014-11-01:2.5595|2014-12-01:2.6556|2015-01-01:2.6617|2015-02-01:2.8777|2015-03-01:3.2074|2015-04-01:2.993|2015-05-01:3.1781|2015-06-01:3.1019|2015-07-01:3.3934|2015-08-01:3.6461|2015-09-01:3.9722|2015-10-01:3.8582|2015-11-01:3.8499|2015-12-01:3.9042|2016-01-01:4.0422|2016-02-01:3.979|2016-03-01:3.5583|2016-04-01:3.4502|2016-05-01:3.5945|2016-06-01:3.2092|2016-07-01:3.2384|2016-08-01:3.2397|2016-09-01:3.2456|2016-10-01:3.1805|2016-11-01:3.3961|2016-12-01:3.2585|2017-01-01:3.1264|2017-02-01:3.0987|2017-03-01:3.1678|2017-04-01:3.1978|2017-05-01:3.2431|2017-06-01:3.3076|2017-07-01:3.1301|2017-08-01:3.1465|2017-09-01:3.1674|2017-10-01:3.2763|2017-11-01:3.261|2017-12-01:3.3074|2018-01-01:3.1618|2018-02-01:3.2443|2018-03-01:3.3232|2018-04-01:3.4805|2018-05-01:3.7364|2018-06-01:3.8552|2018-07-01:3.7543|2018-08-01:4.1347|2018-09-01:4.0033|2018-10-01:3.7171|2018-11-01:3.8627|2018-12-01:3.8742|2019-01-01:3.6513|2019-02-01:3.7379|2019-03-01:3.8961|2019-04-01:3.9447|2019-05-01:3.9401|2019-06-01:3.8316|2019-07-01:3.7643|2019-08-01:4.1379|2019-09-01:4.1638|2019-10-01:4.0035|2019-11-01:4.2234|2019-12-01:4.0301|2020-01-01:4.2689|2020-02-01:4.4981|2020-03-01:5.1981|2020-04-01:5.4264|2020-05-01:5.4257|2020-06-01:5.4754|2020-07-01:5.2027|2020-08-01:5.4707|2020-09-01:5.6401|2020-10-01:5.7712|2020-11-01:5.3311|2020-12-01:5.1961|2021-01-01:5.4753|2021-02-01:5.5296|2021-03-01:5.6967|2021-04-01:5.403|2021-05-01:5.2316|2021-06-01:5.0016|2021-07-01:5.121|2021-08-01:5.1427|2021-09-01:5.4388|2021-10-01:5.6424|2021-11-01:5.6193|2021-12-01:5.5799|2022-01-01:5.3568|2022-02-01:5.1388|2022-03-01:4.7372|2022-04-01:4.9185|2022-05-01:4.7283|2022-06-01:5.2374|2022-07-01:5.1878|2022-08-01:5.1784|2022-09-01:5.406|2022-10-01:5.2564|2022-11-01:5.2935|2022-12-01:5.2171|2023-01-01:5.0987|2023-02-01:5.2072|2023-03-01:5.0798|2023-04-01:5.0001|2023-05-01:5.0953|2023-06-01:4.8186|2023-07-01:4.7409|2023-08-01:4.9213|2023-09-01:5.007|2023-10-01:5.0569|2023-11-01:4.9349|2023-12-01:4.8407|2024-01-01:4.9529|2024-02-01:4.9827|2024-03-01:4.9956|2024-04-01:5.1712|2024-05-01:5.241|2024-06-01:5.5583|2024-07-01:5.6615|2024-08-01:5.6556|2024-09-01:5.4475|2024-10-01:5.7773|2024-11-01:6.0529|2024-12-01:6.1917|2025-01-01:5.8295|2025-02-01:5.8482|2025-03-01:5.7416|2025-04-01:5.6602|2025-05-01:5.7081|2025-06-01:5.4565|2025-07-01:5.6015|2025-08-01:5.4258|2025-09-01:5.318|2025-10-01:5.3837|2025-11-01:5.3332|2025-12-01:5.5018|2026-01-01:5.2295|2026-02-01:5.1489|2026-03-01:5.2188|2026-04-01:4.988|2026-05-01:5.0563|2026-06-01:5.176|2026-07-01:5.0767|2026-08-01:5.181|2026-09-01:5.1803","4192":"1999-01-01:842708|1999-02-01:822205|1999-03-01:800879|1999-04-01:779123|1999-05-01:755512|1999-06-01:733232|1999-07-01:709083|1999-08-01:685813|1999-09-01:663082|1999-10-01:640037|1999-11-01:618440|1999-12-01:599290|2000-01-01:602406|2000-02-01:608291|2000-03-01:612496|2000-04-01:615430|2000-05-01:620436|2000-06-01:625726|2000-07-01:631179|2000-08-01:636585|2000-09-01:640669|2000-10-01:646185|2000-11-01:651141|2000-12-01:655707|2001-01-01:650346|2001-02-01:643305|2001-03-01:636504|2001-04-01:631110|2001-05-01:624846|2001-06-01:614766|2001-07-01:606172|2001-08-01:597320|2001-09-01:588496|2001-10-01:578770|2001-11-01:569415|2001-12-01:559563|2002-01-01:554487|2002-02-01:549214|2002-03-01:543554|2002-04-01:538925|2002-05-01:533047|2002-06-01:529383|2002-07-01:525337|2002-08-01:521077|2002-09-01:517619|2002-10-01:514407|2002-11-01:510930|2002-12-01:508101|2003-01-01:505405|2003-02-01:502712|2003-03-01:501192|2003-04-01:503940|2003-05-01:508507|2003-06-01:514607|2003-07-01:521239|2003-08-01:524838|2003-09-01:532287|2003-10-01:542051|2003-11-01:550590|2003-12-01:559465|2004-01-01:573027|2004-02-01:584992|2004-03-01:599893|2004-04-01:609753|2004-05-01:614351|2004-06-01:618800|2004-07-01:624299|2004-08-01:632461|2004-09-01:639706|2004-10-01:645689|2004-11-01:656556|2004-12-01:669340|2005-01-01:679276|2005-02-01:692267|2005-03-01:702468|2005-04-01:716260|2005-05-01:736725|2005-06-01:758593|2005-07-01:779167|2005-08-01:801720|2005-09-01:823145|2005-10-01:847038|2005-11-01:871600|2005-12-01:892033|2006-01-01:911881|2006-02-01:932283|2006-03-01:957569|2006-04-01:977546|2006-05-01:996670|2006-06-01:1009455|2006-07-01:1026494|2006-08-01:1044909|2006-09-01:1059933|2006-10-01:1076997|2006-11-01:1091089|2006-12-01:1107131|2007-01-01:1124034|2007-02-01:1138334|2007-03-01:1154170|2007-04-01:1173033|2007-05-01:1196126|2007-06-01:1224951|2007-07-01:1253834|2007-08-01:1275036|2007-09-01:1298724|2007-10-01:1331883|2007-11-01:1365508|2007-12-01:1396797|2008-01-01:1429857|2008-02-01:1466351|2008-03-01:1502466|2008-04-01:1542702|2008-05-01:1579885|2008-06-01:1622659|2008-07-01:1668206|2008-08-01:1713568|2008-09-01:1743714|2008-10-01:1737108|2008-11-01:1718746|2008-12-01:1693147|2009-01-01:1667469|2009-02-01:1637700|2009-03-01:1608803|2009-04-01:1578186|2009-05-01:1554463|2009-06-01:1532198|2009-07-01:1507664|2009-08-01:1494582|2009-09-01:1502030|2009-10-01:1548647|2009-11-01:1607014|2009-12-01:1672625|2010-01-01:1727099|2010-02-01:1777245|2010-03-01:1841034|2010-04-01:1900914|2010-05-01:1947085|2010-06-01:1986283|2010-07-01:2029329|2010-08-01:2068046|2010-09-01:2108126|2010-10-01:2141805|2010-11-01:2175351|2010-12-01:2209751|2011-01-01:2247147|2011-02-01:2293630|2011-03-01:2330991|2011-04-01:2377566|2011-05-01:2431692|2011-06-01:2485572|2011-07-01:2534235|2011-08-01:2579542|2011-09-01:2594558|2011-10-01:2601894|2011-11-01:2610684|2011-12-01:2614482|2012-01-01:2622006|2012-02-01:2636393|2012-03-01:2642850|2012-04-01:2627326|2012-05-01:2601465|2012-06-01:2565254|2012-07-01:2532093|2012-08-01:2503801|2012-09-01:2490888|2012-10-01:2486914|2012-11-01:2474484|2012-12-01:2463549|2013-01-01:2461055|2013-02-01:2448513|2013-03-01:2445624|2013-04-01:2459996|2013-05-01:2473941|2013-06-01:2480553|2013-07-01:2479436|2013-08-01:2466487|2013-09-01:2464871|2013-10-01:2469533|2013-11-01:2468142|2013-12-01:2468456|2014-01-01:2457848|2014-02-01:2447791|2014-03-01:2434496|2014-04-01:2427134|2014-05-01:2427692|2014-06-01:2434554|2014-07-01:2452845|2014-08-01:2472523|2014-09-01:2485782|2014-10-01:2475806|2014-11-01:2465601|2014-12-01:2454846|2015-01-01:2442698|2015-02-01:2415605|2015-03-01:2372156|2015-04-01:2318090|2015-05-01:2259454|2015-06-01:2208469|2015-07-01:2144559|2015-08-01:2071940|2015-09-01:1987924|2015-10-01:1913054|2015-11-01:1852770|2015-12-01:1796168|2016-01-01:1735733|2016-02-01:1693740|2016-03-01:1673018|2016-04-01:1656873|2016-05-01:1643565|2016-06-01:1639875|2016-07-01:1643726|2016-08-01:1667956|2016-09-01:1702695|2016-10-01:1739374|2016-11-01:1768321|2016-12-01:1800134|2017-01-01:1843286|2017-02-01:1885978|2017-03-01:1924338|2017-04-01:1951294|2017-05-01:1977992|2017-06-01:1991469|2017-07-01:2004136|2017-08-01:2016197|2017-09-01:2029214|2017-10-01:2038400|2017-11-01:2051307|2017-12-01:2063185|2018-01-01:2073941|2018-02-01:2075340|2018-03-01:2074669|2018-04-01:2074422|2018-05-01:2056603|2018-06-01:2045703|2018-07-01:2028334|2018-08-01:2003378|2018-09-01:1969094|2018-10-01:1953249|2018-11-01:1937218|2018-12-01:1916213|2019-01-01:1898870|2019-02-01:1887942|2019-03-01:1865809|2019-04-01:1851831|2019-05-01:1852312|2019-06-01:1853294|2019-07-01:1866934|2019-08-01:1872277|2019-09-01:1882748|2019-10-01:1879144|2019-11-01:1872412|2019-12-01:1872800|2020-01-01:1865832|2020-02-01:1852303|2020-03-01:1824747|2020-04-01:1773270|2020-05-01:1720330|2020-06-01:1680998|2020-07-01:1634353|2020-08-01:1593093|2020-09-01:1562125|2020-10-01:1522462|2020-11-01:1493875|2020-12-01:1475529|2021-01-01:1454503|2021-02-01:1443156|2021-03-01:1450119|2021-04-01:1476808|2021-05-01:1513586|2021-06-01:1543796|2021-07-01:1571533|2021-08-01:1602186|2021-09-01:1627874|2021-10-01:1648622|2021-11-01:1665956|2021-12-01:1670493|2022-01-01:1674872|2022-02-01:1689689|2022-03-01:1723026|2022-04-01:1765144|2022-05-01:1796626|2022-06-01:1817310|2022-07-01:1830232|2022-08-01:1853449|2022-09-01:1872375|2022-10-01:1900011|2022-11-01:1924818|2022-12-01:1951572|2023-01-01:1976571|2023-02-01:1991939|2023-03-01:2002654|2023-04-01:2009110|2023-05-01:2022368|2023-06-01:2042149|2023-07-01:2072361|2023-08-01:2092871|2023-09-01:2114620|2023-10-01:2135375|2023-11-01:2164759|2023-12-01:2190991|2024-01-01:2216647|2024-02-01:2237820|2024-03-01:2252020|2024-04-01:2263926|2024-05-01:2268898|2024-06-01:2263172|2024-07-01:2254723|2024-08-01:2245095|2024-09-01:2238690|2024-10-01:2236066|2024-11-01:2215105|2024-12-01:2184822|2025-01-01:2162221|2025-02-01:2152847|2025-03-01:2144830|2025-04-01:2139432|2025-05-01:2138820|2025-06-01:2147159|2025-07-01:2161540|2025-08-01:2176563|2025-09-01:2197796|2025-10-01:2218228|2025-11-01:2245876|2025-12-01:2280894|2026-01-01:2314437|2026-02-01:2343991|2026-03-01:2381898|2026-04-01:2424674|2026-05-01:2464460|2026-06-01:2496197|2026-07-01:2526286|2026-08-01:2552974|2026-09-01:2573697","4380":"1999-01-01:80936.3|1999-02-01:80929.1|1999-03-01:88802.6|1999-04-01:87739|1999-05-01:89223|1999-06-01:91746.9|1999-07-01:91230.4|1999-08-01:92283.4|1999-09-01:90611.8|1999-10-01:95872.4|1999-11-01:99563.1|1999-12-01:98772.5|2000-01-01:92576.6|2000-02-01:91770.4|2000-03-01:92579.9|2000-04-01:91376.2|2000-05-01:98727|2000-06-01:102685.4|2000-07-01:103410.4|2000-08-01:105177.8|2000-09-01:100307.6|2000-10-01:106951.1|2000-11-01:107678|2000-12-01:105851.6|2001-01-01:102530.7|2001-02-01:101635.3|2001-03-01:108303.8|2001-04-01:107572|2001-05-01:111202.2|2001-06-01:104949.4|2001-07-01:110758.9|2001-08-01:113064.7|2001-09-01:108700.8|2001-10-01:116139|2001-11-01:117882|2001-12-01:113016.7|2002-01-01:112374.8|2002-02-01:111477.1|2002-03-01:118444.7|2002-04-01:120385.9|2002-05-01:123552.5|2002-06-01:123424.4|2002-07-01:126856.6|2002-08-01:127800.1|2002-09-01:125137.8|2002-10-01:133125.4|2002-11-01:135966.6|2002-12-01:130241.2|2003-01-01:125713.7|2003-02-01:131377.7|2003-03-01:140150.3|2003-04-01:141001.3|2003-05-01:140056.9|2003-06-01:137929.2|2003-07-01:144627.1|2003-08-01:144366.4|2003-09-01:150356.3|2003-10-01:158347.6|2003-11-01:154764.9|2003-12-01:149259.1|2004-01-01:142455|2004-02-01:141654.6|2004-03-01:160673.9|2004-04-01:159113.9|2004-05-01:160112|2004-06-01:162569|2004-07-01:168216.4|2004-08-01:168068.5|2004-09-01:168967.4|2004-10-01:174390.5|2004-11-01:178012|2004-12-01:173518|2005-01-01:161646.6|2005-02-01:159966.7|2005-03-01:178097.1|2005-04-01:177918.1|2005-05-01:178129.4|2005-06-01:179509.8|2005-07-01:181673.2|2005-08-01:186712.8|2005-09-01:184473.1|2005-10-01:192948.3|2005-11-01:196419.8|2005-12-01:193089.5|2006-01-01:181707.7|2006-02-01:176988.5|2006-03-01:195574.3|2006-04-01:188585.8|2006-05-01:198731.5|2006-06-01:194659.5|2006-07-01:203488.6|2006-08-01:208799.8|2006-09-01:205559.3|2006-10-01:219035|2006-11-01:220981.6|2006-12-01:215338.3|2007-01-01:206662.3|2007-02-01:201552.1|2007-03-01:223208.6|2007-04-01:218931.2|2007-05-01:227535.3|2007-06-01:224188.2|2007-07-01:230916.3|2007-08-01:233905.1|2007-09-01:227024.5|2007-10-01:245688|2007-11-01:243269.2|2007-12-01:237382.1|2008-01-01:232824.8|2008-02-01:231982.2|2008-03-01:247248.3|2008-04-01:253194.4|2008-05-01:255747.4|2008-06-01:260583.4|2008-07-01:271290.4|2008-08-01:268546.1|2008-09-01:272766.1|2008-10-01:284913.7|2008-11-01:272120.8|2008-12-01:258585.7|2009-01-01:244784.1|2009-02-01:242496.9|2009-03-01:268846.1|2009-04-01:263434.9|2009-05-01:268734.4|2009-06-01:271408.2|2009-07-01:281453.8|2009-08-01:282514.8|2009-09-01:288874.7|2009-10-01:309141.3|2009-11-01:307943.5|2009-12-01:303406.8|2010-01-01:284387.8|2010-02-01:283355|2010-03-01:318654.6|2010-04-01:311649.1|2010-05-01:315947.2|2010-06-01:316548.7|2010-07-01:328892.6|2010-08-01:332376.6|2010-09-01:336665.5|2010-10-01:350938.6|2010-11-01:358431.8|2010-12-01:347999.4|2011-01-01:327592.4|2011-02-01:332316.4|2011-03-01:356621.8|2011-04-01:354607.7|2011-05-01:368282.8|2011-06-01:363821.7|2011-07-01:367341.2|2011-08-01:374873.1|2011-09-01:370119.9|2011-10-01:383767.3|2011-11-01:391536.4|2011-12-01:385501.3|2012-01-01:364188.6|2012-02-01:367527.7|2012-03-01:397757.8|2012-04-01:385882.7|2012-05-01:401863.7|2012-06-01:395379.2|2012-07-01:409025|2012-08-01:418752.4|2012-09-01:402671.5|2012-10-01:431399.9|2012-11-01:426614.8|2012-12-01:413696.7|2013-01-01:408895|2013-02-01:398087.4|2013-03-01:434631.2|2013-04-01:446508.1|2013-05-01:441321.9|2013-06-01:434750|2013-07-01:452593.2|2013-08-01:453785.4|2013-09-01:447755.6|2013-10-01:475721|2013-11-01:470316.1|2013-12-01:467254.2|2014-01-01:453274.1|2014-02-01:455505.4|2014-03-01:477201.5|2014-04-01:479725.1|2014-05-01:481271.4|2014-06-01:461325.2|2014-07-01:486894.3|2014-08-01:483786.8|2014-09-01:491444.4|2014-10-01:508978.9|2014-11-01:498508.4|2014-12-01:501037.4|2015-01-01:474014.8|2015-02-01:467678.1|2015-03-01:514965.8|2015-04-01:496943.6|2015-05-01:491765.5|2015-06-01:491260.7|2015-07-01:507052.9|2015-08-01:501119.6|2015-09-01:500055.8|2015-10-01:520406.8|2015-11-01:513887|2015-12-01:516636.5|2016-01-01:482533.7|2016-02-01:490234.2|2016-03-01:527530.9|2016-04-01:520430.9|2016-05-01:516186.4|2016-06-01:522432.9|2016-07-01:522090.5|2016-08-01:530129|2016-09-01:524950.9|2016-10-01:538764.1|2016-11-01:545661.8|2016-12-01:548382.6|2017-01-01:513959.1|2017-02-01:511053.8|2017-03-01:560660.4|2017-04-01:537763.9|2017-05-01:549615.7|2017-06-01:543350|2017-07-01:548406|2017-08-01:555845.1|2017-09-01:544384.1|2017-10-01:567942.1|2017-11-01:574089.3|2017-12-01:578409.4|2018-01-01:552484.1|2018-02-01:540669|2018-03-01:588929.9|2018-04-01:587220.7|2018-05-01:561812.3|2018-06-01:585066|2018-07-01:592371.6|2018-08-01:598821.4|2018-09-01:576662.7|2018-10-01:611623.5|2018-11-01:607513.8|2018-12-01:600965.9|2019-01-01:577573.1|2019-02-01:577948.5|2019-03-01:602031.9|2019-04-01:612800.1|2019-05-01:615980.7|2019-06-01:597980.4|2019-07-01:632362.3|2019-08-01:630435.9|2019-09-01:617812|2019-10-01:648258.1|2019-11-01:637852|2019-12-01:638095.9|2020-01-01:614086.4|2020-02-01:618983.2|2020-03-01:635024.9|2020-04-01:569040.8|2020-05-01:576158.8|2020-06-01:607524|2020-07-01:644128.9|2020-08-01:637450|2020-09-01:647744.6|2020-10-01:673706.6|2020-11-01:679816.5|2020-12-01:705932.4|2021-01-01:678993.3|2021-02-01:708129.6|2021-03-01:769547.2|2021-04-01:738697.1|2021-05-01:730267.6|2021-06-01:734674.1|2021-07-01:765663.8|2021-08-01:767591.9|2021-09-01:762595.3|2021-10-01:772174.3|2021-11-01:787907.6|2021-12-01:795900.1|2022-01-01:722633.3|2022-02-01:754614.9|2022-03-01:842279.9|2022-04-01:832795.4|2022-05-01:841154.8|2022-06-01:843531.3|2022-07-01:868906.7|2022-08-01:873911.2|2022-09-01:858364.1|2022-10-01:879650.3|2022-11-01:881234.6|2022-12-01:880600.2|2023-01-01:810360.1|2023-02-01:831160.4|2023-03-01:939497.5|2023-04-01:910661.4|2023-05-01:911271.3|2023-06-01:905647.3|2023-07-01:921219.9|2023-08-01:932653.9|2023-09-01:915571.6|2023-10-01:952784.8|2023-11-01:961700|2023-12-01:950816.5|2024-01-01:892018|2024-02-01:903476.1|2024-03-01:969338.6|2024-04-01:992717.3|2024-05-01:965544.7|2024-06-01:976496.7|2024-07-01:1018145|2024-08-01:1004155.4|2024-09-01:993635.5|2024-10-01:1044631.8|2024-11-01:1019396.2|2024-12-01:999695.3|2025-01-01:957152.7|2025-02-01:995304.4|2025-03-01:1072265.8|2025-04-01:1087705.9|2025-05-01:1061957.9|2025-06-01:1050681.2|2025-07-01:1094342.9|2025-08-01:1065942.8|2025-09-01:1075421.9|2025-10-01:1109296.9|2025-11-01:1084264.6|2025-12-01:1084228.7|2026-01-01:1026731.5|2026-02-01:1050631.1|2026-03-01:1173616.3|2026-04-01:1161086.3|2026-05-01:1131408.9|2026-06-01:1133232.4|2026-07-01:1165427.4|2026-08-01:1145330.3|2026-09-01:1136769.3","4382":"1999-01-01:1003923.4|1999-02-01:1009024.4|1999-03-01:1017318.3|1999-04-01:1023891.3|1999-05-01:1027906.8|1999-06-01:1034091.4|1999-07-01:1038383.3|1999-08-01:1044295.4|1999-09-01:1050173.6|1999-10-01:1058743.2|1999-11-01:1071989.7|1999-12-01:1087710.5|2000-01-01:1099350.8|2000-02-01:1110192.1|2000-03-01:1113969.4|2000-04-01:1117606.6|2000-05-01:1127110.5|2000-06-01:1138049|2000-07-01:1150228.9|2000-08-01:1163123.4|2000-09-01:1172819.2|2000-10-01:1183898|2000-11-01:1192012.9|2000-12-01:1199092.1|2001-01-01:1209046.1|2001-02-01:1218911|2001-03-01:1234635|2001-04-01:1250830.7|2001-05-01:1263306|2001-06-01:1265570|2001-07-01:1272918.6|2001-08-01:1280805.4|2001-09-01:1289198.6|2001-10-01:1298386.5|2001-11-01:1308590.4|2001-12-01:1315755.5|2002-01-01:1325599.6|2002-02-01:1335441.4|2002-03-01:1345582.3|2002-04-01:1358396.3|2002-05-01:1370746.6|2002-06-01:1389221.6|2002-07-01:1405319.2|2002-08-01:1420054.7|2002-09-01:1436491.7|2002-10-01:1453478.1|2002-11-01:1471562.8|2002-12-01:1488787.3|2003-01-01:1502126.1|2003-02-01:1522026.7|2003-03-01:1543732.2|2003-04-01:1564347.6|2003-05-01:1580851.9|2003-06-01:1595356.7|2003-07-01:1613127.2|2003-08-01:1629693.6|2003-09-01:1654912|2003-10-01:1680134.1|2003-11-01:1698932.4|2003-12-01:1717950.4|2004-01-01:1734691.7|2004-02-01:1744968.7|2004-03-01:1765492.2|2004-04-01:1783604.9|2004-05-01:1803660.1|2004-06-01:1828299.9|2004-07-01:1851889.2|2004-08-01:1875591.3|2004-09-01:1894202.4|2004-10-01:1910245.3|2004-11-01:1933492.3|2004-12-01:1957751.2|2005-01-01:1976942.8|2005-02-01:1995254.9|2005-03-01:2012678.1|2005-04-01:2031482.3|2005-05-01:2049499.7|2005-06-01:2066440.5|2005-07-01:2079897.4|2005-08-01:2098541.7|2005-09-01:2114047.4|2005-10-01:2132605.2|2005-11-01:2151013|2005-12-01:2170584.5|2006-01-01:2190645.6|2006-02-01:2207667.4|2006-03-01:2225144.6|2006-04-01:2235812.3|2006-05-01:2256414.4|2006-06-01:2271564|2006-07-01:2293379.4|2006-08-01:2315466.5|2006-09-01:2336552.6|2006-10-01:2362639.4|2006-11-01:2387201.1|2006-12-01:2409449.9|2007-01-01:2434404.5|2007-02-01:2458968.1|2007-03-01:2486602.5|2007-04-01:2516947.8|2007-05-01:2545751.6|2007-06-01:2575280.3|2007-07-01:2602708|2007-08-01:2627813.3|2007-09-01:2649278.5|2007-10-01:2675931.5|2007-11-01:2698219.1|2007-12-01:2720262.9|2008-01-01:2746425.4|2008-02-01:2776855.5|2008-03-01:2800895.2|2008-04-01:2835158.4|2008-05-01:2863370.5|2008-06-01:2899765.6|2008-07-01:2940139.7|2008-08-01:2974780.7|2008-09-01:3020522.3|2008-10-01:3059748|2008-11-01:3088599.6|2008-12-01:3109803.1|2009-01-01:3121762.4|2009-02-01:3132277.1|2009-03-01:3153874.9|2009-04-01:3164115.4|2009-05-01:3177102.5|2009-06-01:3187927.3|2009-07-01:3198090.6|2009-08-01:3212059.3|2009-09-01:3228167.9|2009-10-01:3252395.5|2009-11-01:3288218.2|2009-12-01:3333039.4|2010-01-01:3372643|2010-02-01:3413501.1|2010-03-01:3463309.7|2010-04-01:3511523.9|2010-05-01:3558736.7|2010-06-01:3603877.2|2010-07-01:3651316.1|2010-08-01:3701177.9|2010-09-01:3748968.7|2010-10-01:3790766|2010-11-01:3841254.3|2010-12-01:3885847|2011-01-01:3929051.6|2011-02-01:3978013.1|2011-03-01:4015980.3|2011-04-01:4058938.8|2011-05-01:4111274.5|2011-06-01:4158547.4|2011-07-01:4196996.1|2011-08-01:4239492.6|2011-09-01:4272946.9|2011-10-01:4305775.6|2011-11-01:4338880.2|2011-12-01:4376382|2012-01-01:4412978.2|2012-02-01:4448189.5|2012-03-01:4489325.5|2012-04-01:4520600.5|2012-05-01:4554181.4|2012-06-01:4585738.9|2012-07-01:4627422.6|2012-08-01:4671301.8|2012-09-01:4703853.5|2012-10-01:4751486.1|2012-11-01:4786564.6|2012-12-01:4814760|2013-01-01:4859466.4|2013-02-01:4890026.1|2013-03-01:4926899.5|2013-04-01:4987524.8|2013-05-01:5026983|2013-06-01:5066353.9|2013-07-01:5109922.1|2013-08-01:5144955.1|2013-09-01:5190039.1|2013-10-01:5234360.2|2013-11-01:5278061.5|2013-12-01:5331619|2014-01-01:5375998.1|2014-02-01:5433416.1|2014-03-01:5475986.4|2014-04-01:5509203.5|2014-05-01:5549153|2014-06-01:5575728.2|2014-07-01:5610029.4|2014-08-01:5640030.8|2014-09-01:5683719.6|2014-10-01:5716977.6|2014-11-01:5745169.8|2014-12-01:5778953|2015-01-01:5799693.7|2015-02-01:5811866.4|2015-03-01:5849630.6|2015-04-01:5866849.1|2015-05-01:5877343.2|2015-06-01:5907278.6|2015-07-01:5927437.1|2015-08-01:5944769.9|2015-09-01:5953381.4|2015-10-01:5964809.2|2015-11-01:5980187.9|2015-12-01:5995787|2016-01-01:6004305.9|2016-02-01:6026862.1|2016-03-01:6039427.2|2016-04-01:6062914.5|2016-05-01:6087335.4|2016-06-01:6118507.6|2016-07-01:6133545.3|2016-08-01:6162554.7|2016-09-01:6187449.8|2016-10-01:6205807.1|2016-11-01:6237581.9|2016-12-01:6269328|2017-01-01:6300753.4|2017-02-01:6321573|2017-03-01:6354702.5|2017-04-01:6372035.6|2017-05-01:6405464.9|2017-06-01:6426381.9|2017-07-01:6452697.4|2017-08-01:6478413.5|2017-09-01:6497846.7|2017-10-01:6527024.8|2017-11-01:6555452.2|2017-12-01:6585479|2018-01-01:6624004|2018-02-01:6653619.2|2018-03-01:6681888.7|2018-04-01:6731345.4|2018-05-01:6743542.1|2018-06-01:6785258.1|2018-07-01:6829223.6|2018-08-01:6872199.9|2018-09-01:6904478.5|2018-10-01:6948159.9|2018-11-01:6981584.5|2018-12-01:7004141|2019-01-01:7029230.1|2019-02-01:7066509.5|2019-03-01:7079611.5|2019-04-01:7105190.9|2019-05-01:7159359.2|2019-06-01:7172273.7|2019-07-01:7212264.3|2019-08-01:7243878.9|2019-09-01:7285028.2|2019-10-01:7321662.8|2019-11-01:7352001|2019-12-01:7389131|2020-01-01:7425644.3|2020-02-01:7466679.1|2020-03-01:7499672|2020-04-01:7455912.7|2020-05-01:7416090.8|2020-06-01:7425634.4|2020-07-01:7437401.1|2020-08-01:7444415.1|2020-09-01:7474347.6|2020-10-01:7499796.1|2020-11-01:7541760.6|2020-12-01:7609597|2021-01-01:7674503.9|2021-02-01:7763650.2|2021-03-01:7898172.6|2021-04-01:8067828.9|2021-05-01:8221937.7|2021-06-01:8349087.7|2021-07-01:8470622.7|2021-08-01:8600764.7|2021-09-01:8715615.4|2021-10-01:8814083.1|2021-11-01:8922174.2|2021-12-01:9012142|2022-01-01:9055782|2022-02-01:9102267.3|2022-03-01:9175000|2022-04-01:9269098.3|2022-05-01:9379985.5|2022-06-01:9488842.7|2022-07-01:9592085.5|2022-08-01:9698404.8|2022-09-01:9794173.6|2022-10-01:9901649.5|2022-11-01:9994976.6|2022-12-01:10079676.7|2023-01-01:10167403.5|2023-02-01:10243949|2023-03-01:10341166.6|2023-04-01:10419032.6|2023-05-01:10489149|2023-06-01:10551265|2023-07-01:10603578.3|2023-08-01:10662321|2023-09-01:10719528.5|2023-10-01:10792663.1|2023-11-01:10873128.4|2023-12-01:10943344.7|2024-01-01:11025002.6|2024-02-01:11097318.2|2024-03-01:11127159.3|2024-04-01:11209215.3|2024-05-01:11263488.7|2024-06-01:11334338.1|2024-07-01:11431263.2|2024-08-01:11502764.7|2024-09-01:11580828.6|2024-10-01:11672675.6|2024-11-01:11730371.8|2024-12-01:11779250.6|2025-01-01:11844385.2|2025-02-01:11936213.6|2025-03-01:12039140.8|2025-04-01:12134129.4|2025-05-01:12230542.6|2025-06-01:12304727.1|2025-07-01:12380925.1|2025-08-01:12442712.4|2025-09-01:12524498.7|2025-10-01:12589163.8|2025-11-01:12654032.2|2025-12-01:12738565.6|2026-01-01:12808144.4|2026-02-01:12863471.1|2026-03-01:12964821.6|2026-04-01:13038202|2026-05-01:13107653|2026-06-01:13190204.2|2026-07-01:13261288.7|2026-08-01:13340676.3|2026-09-01:13402023.7","4393":"1999-03-01:75.72|1999-04-01:75.86|1999-05-01:77.29|1999-06-01:91.51|1999-07-01:99.11|1999-08-01:98.17|1999-09-01:99.03|1999-10-01:95.52|1999-11-01:93.87|1999-12-01:94.62|2000-01-01:100.91|2000-02-01:107.34|2000-03-01:100.09|2000-04-01:93.93|2000-05-01:89.44|2000-06-01:94.54|2000-07-01:98.31|2000-08-01:91.2|2000-09-01:92.02|2000-10-01:98.51|2000-11-01:99.37|2000-12-01:100.82|2001-01-01:111.34|2001-02-01:113.47|2001-03-01:108.55|2001-04-01:105.22|2001-05-01:102.4|2001-06-01:79.44|2001-07-01:87.2|2001-08-01:86.38|2001-09-01:90.74|2001-10-01:80.65|2001-11-01:78.31|2001-12-01:86.28|2002-01-01:87.04|2002-02-01:90.66|2002-03-01:91.3|2002-04-01:96|2002-05-01:96.15|2002-06-01:84.4|2002-07-01:93.81|2002-08-01:89.8|2002-09-01:99.22|2002-10-01:94.91|2002-11-01:98.68|2002-12-01:102.92|2003-01-01:102.97|2003-02-01:103.53|2003-03-01:101.89|2003-04-01:107.66|2003-05-01:112.04|2003-06-01:116.81|2003-07-01:111.47|2003-08-01:109.37|2003-09-01:106.41|2003-10-01:104.72|2003-11-01:108.68|2003-12-01:115.33|2004-01-01:124.16|2004-02-01:123.4|2004-03-01:113.29|2004-04-01:108.01|2004-05-01:124.23|2004-06-01:117.07|2004-07-01:118.5|2004-08-01:120.72|2004-09-01:128.43|2004-10-01:141.92|2004-11-01:144.96|2004-12-01:140.41|2005-01-01:145.02|2005-02-01:146.48|2005-03-01:144.95|2005-04-01:141.75|2005-05-01:133.62|2005-06-01:132.74|2005-07-01:133.21|2005-08-01:124.89|2005-09-01:109.24|2005-10-01:107.65|2005-11-01:117.23|2005-12-01:130.16|2006-01-01:131.52|2006-02-01:138.03|2006-03-01:137.75|2006-04-01:132.38|2006-05-01:138.2|2006-06-01:134.4|2006-07-01:134.17|2006-08-01:128.24|2006-09-01:131.36|2006-10-01:132.29|2006-11-01:134.62|2006-12-01:127.5|2007-01-01:133.89|2007-02-01:134.39|2007-03-01:127.87|2007-04-01:127.97|2007-05-01:126.49|2007-06-01:129.77|2007-07-01:130.12|2007-08-01:130.3|2007-09-01:131.81|2007-10-01:133.34|2007-11-01:136.25|2007-12-01:139.9|2008-01-01:142.61|2008-02-01:146.9|2008-03-01:147.72|2008-04-01:148.56|2008-05-01:147.36|2008-06-01:142.59|2008-07-01:131.23|2008-08-01:137.05|2008-09-01:141.28|2008-10-01:140.46|2008-11-01:133.85|2008-12-01:128.66|2009-01-01:125.16|2009-02-01:134.12|2009-03-01:130.88|2009-04-01:126.33|2009-05-01:128.95|2009-06-01:139.99|2009-07-01:145.01|2009-08-01:145.61|2009-09-01:148.81|2009-10-01:157.15|2009-11-01:155.79|2009-12-01:156.63|2010-01-01:160.47|2010-02-01:161.43|2010-03-01:159.92|2010-04-01:154.66|2010-05-01:155.77|2010-06-01:160.55|2010-07-01:157.16|2010-08-01:164.5|2010-09-01:162.62|2010-10-01:155.37|2010-11-01:160.06|2010-12-01:164.26|2011-01-01:160.83|2011-02-01:164.21|2011-03-01:160.29|2011-04-01:159.44|2011-05-01:153|2011-06-01:153.81|2011-07-01:152.93|2011-08-01:152.71|2011-09-01:154.08|2011-10-01:151.91|2011-11-01:155.36|2011-12-01:158.17|2012-01-01:158.33|2012-02-01:170.18|2012-03-01:164.42|2012-04-01:164.99|2012-05-01:163.05|2012-06-01:162.35|2012-07-01:160.56|2012-08-01:156.3|2012-09-01:158.29|2012-10-01:161.38|2012-11-01:159.69|2012-12-01:161.81|2013-01-01:160.55|2013-02-01:165.85|2013-03-01:159.96|2013-04-01:155.62|2013-05-01:145.97|2013-06-01:145.04|2013-07-01:136.73|2013-08-01:133.04|2013-09-01:136.74|2013-10-01:139.24|2013-11-01:138.01|2013-12-01:136.57|2014-01-01:131.74|2014-02-01:136.39|2014-03-01:125.78|2014-04-01:120.25|2014-05-01:109.48|2014-06-01:107.37|2014-07-01:109.55|2014-08-01:110.54|2014-09-01:118.92|2014-10-01:115.82|2014-11-01:115.99|2014-12-01:112.95|2015-01-01:112.69|2015-02-01:112.89|2015-03-01:106.86|2015-04-01:101.56|2015-05-01:91.77|2015-06-01:90.58|2015-07-01:84.55|2015-08-01:84.66|2015-09-01:85.53|2015-10-01:88.77|2015-11-01:85.55|2015-12-01:87.17|2016-01-01:89.04|2016-02-01:95.23|2016-03-01:89.31|2016-04-01:87.68|2016-05-01:90.85|2016-06-01:98.05|2016-07-01:97.67|2016-08-01:100.05|2016-09-01:106.95|2016-10-01:105.98|2016-11-01:110.3|2016-12-01:110.73|2017-01-01:102.25|2017-02-01:113.8|2017-03-01:109.38|2017-04-01:109.01|2017-05-01:103.49|2017-06-01:100.06|2017-07-01:104.78|2017-08-01:101.48|2017-09-01:99.67|2017-10-01:102.81|2017-11-01:103.96|2017-12-01:109.46|2018-01-01:116.96|2018-02-01:120.57|2018-03-01:115.64|2018-04-01:109.94|2018-05-01:113.5|2018-06-01:104|2018-07-01:103.48|2018-08-01:104.38|2018-09-01:106.79|2018-10-01:107.91|2018-11-01:114.5|2018-12-01:127.8|2019-01-01:128.64|2019-02-01:139.39|2019-03-01:125.53|2019-04-01:121.71|2019-05-01:117.01|2019-06-01:107.38|2019-07-01:110.92|2019-08-01:114.58|2019-09-01:112.19|2019-10-01:111.82|2019-11-01:118.64|2019-12-01:121.26|2020-01-01:121.27|2020-02-01:131.79|2020-03-01:124.58|2020-04-01:111.97|2020-05-01:96.82|2020-06-01:100.43|2020-07-01:102.84|2020-08-01:102.62|2020-09-01:108.36|2020-10-01:107.61|2020-11-01:111.65|2020-12-01:111.71|2021-01-01:116.09|2021-02-01:116.23|2021-03-01:112.9|2021-04-01:104.95|2021-05-01:105.9|2021-06-01:107.32|2021-07-01:110.98|2021-08-01:111.99|2021-09-01:114.66|2021-10-01:109.37|2021-11-01:109.35|2021-12-01:112|2022-01-01:108.35|2022-02-01:104.05|2022-03-01:105.12|2022-04-01:104.35|2022-05-01:105.87|2022-06-01:103.6|2022-07-01:105.58|2022-08-01:106.76|2022-09-01:111.46|2022-10-01:114.23|2022-11-01:116.79|2022-12-01:122.84|2023-01-01:125.38|2023-02-01:128.78|2023-03-01:127.42|2023-04-01:125.1|2023-05-01:122.22|2023-06-01:125.27|2023-07-01:124.46|2023-08-01:131.02|2023-09-01:132.64|2023-10-01:132.75|2023-11-01:129.74|2023-12-01:133.46|2024-01-01:133.25|2024-02-01:138.22|2024-03-01:132.52|2024-04-01:129.59|2024-05-01:126.46|2024-06-01:127.05|2024-07-01:127.78|2024-08-01:127.27|2024-09-01:123.23|2024-10-01:120.97|2024-11-01:123.93|2024-12-01:125.62|2025-01-01:123.51|2025-02-01:120.48|2025-03-01:115.21|2025-04-01:111.01|2025-05-01:111.73|2025-06-01:112.89|2025-07-01:108.94|2025-08-01:111.88|2025-09-01:110.2|2025-10-01:113.63|2025-11-01:118.65|2025-12-01:124.46|2026-01-01:127.39|2026-02-01:127.39|2026-03-01:125.87|2026-04-01:121.06|2026-05-01:120.55|2026-06-01:124.07|2026-07-01:121.6|2026-08-01:120.84|2026-09-01:121.11|2026-10-01:118.59","4394":"1999-03-01:52.27|1999-04-01:49.01|1999-05-01:50.86|1999-06-01:60.45|1999-07-01:66.07|1999-08-01:64.59|1999-09-01:64.57|1999-10-01:61.94|1999-11-01:64.52|1999-12-01:64.17|2000-01-01:71.17|2000-02-01:86.37|2000-03-01:79.93|2000-04-01:70.42|2000-05-01:69.29|2000-06-01:74.58|2000-07-01:74.01|2000-08-01:68.83|2000-09-01:72.96|2000-10-01:79.11|2000-11-01:73.14|2000-12-01:77.35|2001-01-01:104.53|2001-02-01:104.07|2001-03-01:90.6|2001-04-01:88.88|2001-05-01:83.55|2001-06-01:64.82|2001-07-01:68.72|2001-08-01:68.8|2001-09-01:70.18|2001-10-01:62.66|2001-11-01:65.5|2001-12-01:71.36|2002-01-01:70.7|2002-02-01:74.34|2002-03-01:77.69|2002-04-01:74.39|2002-05-01:74.99|2002-06-01:66.6|2002-07-01:77.16|2002-08-01:69.76|2002-09-01:76.92|2002-10-01:70.85|2002-11-01:69.21|2002-12-01:74.45|2003-01-01:74.59|2003-02-01:75.49|2003-03-01:71.92|2003-04-01:78.81|2003-05-01:79.29|2003-06-01:82.37|2003-07-01:75.02|2003-08-01:74.55|2003-09-01:75.49|2003-10-01:76.84|2003-11-01:79.68|2003-12-01:85.59|2004-01-01:95.66|2004-02-01:93.94|2004-03-01:85.92|2004-04-01:82.9|2004-05-01:100.38|2004-06-01:93.86|2004-07-01:98|2004-08-01:94.22|2004-09-01:95.3|2004-10-01:112.37|2004-11-01:112.38|2004-12-01:120.05|2005-01-01:124.12|2005-02-01:124.11|2005-03-01:124.81|2005-04-01:121.18|2005-05-01:115.2|2005-06-01:113.5|2005-07-01:114.57|2005-08-01:116.31|2005-09-01:103.08|2005-10-01:99.51|2005-11-01:115.68|2005-12-01:126.32|2006-01-01:125.79|2006-02-01:128.1|2006-03-01:130.2|2006-04-01:128.72|2006-05-01:131.57|2006-06-01:124.52|2006-07-01:127.95|2006-08-01:120.06|2006-09-01:125.03|2006-10-01:123.59|2006-11-01:125.09|2006-12-01:121.31|2007-01-01:136.75|2007-02-01:138.17|2007-03-01:132.37|2007-04-01:135.81|2007-05-01:136.67|2007-06-01:138.41|2007-07-01:140.19|2007-08-01:136.44|2007-09-01:141.09|2007-10-01:147.02|2007-11-01:150.14|2007-12-01:145.79|2008-01-01:153.64|2008-02-01:153.55|2008-03-01:153.75|2008-04-01:157.13|2008-05-01:155.13|2008-06-01:152.22|2008-07-01:140.16|2008-08-01:140.48|2008-09-01:138.99|2008-10-01:139.59|2008-11-01:131.73|2008-12-01:120.39|2009-01-01:119.62|2009-02-01:130.38|2009-03-01:117.53|2009-04-01:118.16|2009-05-01:120.69|2009-06-01:128.53|2009-07-01:134.55|2009-08-01:134.83|2009-09-01:141.86|2009-10-01:148.45|2009-11-01:146.55|2009-12-01:150.53|2010-01-01:154.75|2010-02-01:160.75|2010-03-01:159.98|2010-04-01:146.53|2010-05-01:152.48|2010-06-01:155.73|2010-07-01:153.99|2010-08-01:163.38|2010-09-01:164.11|2010-10-01:155.58|2010-11-01:159.91|2010-12-01:162.82|2011-01-01:156.53|2011-02-01:161.27|2011-03-01:157.08|2011-04-01:154.09|2011-05-01:149.1|2011-06-01:149.91|2011-07-01:150.63|2011-08-01:149.82|2011-09-01:152.27|2011-10-01:148.99|2011-11-01:149.08|2011-12-01:150.52|2012-01-01:151.92|2012-02-01:167.9|2012-03-01:162.37|2012-04-01:163.22|2012-05-01:156.18|2012-06-01:159.71|2012-07-01:158.34|2012-08-01:155.62|2012-09-01:157.2|2012-10-01:159.44|2012-11-01:152.4|2012-12-01:160.11|2013-01-01:156.08|2013-02-01:165.95|2013-03-01:155.64|2013-04-01:153.02|2013-05-01:145.14|2013-06-01:147.48|2013-07-01:136.41|2013-08-01:133.09|2013-09-01:139.47|2013-10-01:139.39|2013-11-01:136.92|2013-12-01:138.16|2014-01-01:130.19|2014-02-01:142.61|2014-03-01:132.36|2014-04-01:126.93|2014-05-01:111.8|2014-06-01:110.92|2014-07-01:109.23|2014-08-01:110.11|2014-09-01:113.85|2014-10-01:107.09|2014-11-01:103.39|2014-12-01:108.7|2015-01-01:110.72|2015-02-01:109.65|2015-03-01:103.26|2015-04-01:95.17|2015-05-01:81.35|2015-06-01:74.14|2015-07-01:61.3|2015-08-01:59.31|2015-09-01:59.83|2015-10-01:56.05|2015-11-01:54.31|2015-12-01:57.95|2016-01-01:57.08|2016-02-01:66.52|2016-03-01:53.5|2016-04-01:51.88|2016-05-01:47.35|2016-06-01:52.36|2016-07-01:51.3|2016-08-01:54.69|2016-09-01:58.68|2016-10-01:59.11|2016-11-01:60.1|2016-12-01:72.63|2017-01-01:68.19|2017-02-01:74.55|2017-03-01:66.79|2017-04-01:71.32|2017-05-01:66.45|2017-06-01:70.81|2017-07-01:73.52|2017-08-01:69.31|2017-09-01:70.12|2017-10-01:73|2017-11-01:72.38|2017-12-01:82.84|2018-01-01:89.99|2018-02-01:99.09|2018-03-01:92.09|2018-04-01:85.2|2018-05-01:83.82|2018-06-01:77.95|2018-07-01:76.45|2018-08-01:83.02|2018-09-01:80.38|2018-10-01:78.74|2018-11-01:84|2018-12-01:95.9|2019-01-01:96.27|2019-02-01:112.24|2019-03-01:97.44|2019-04-01:99.29|2019-05-01:96.27|2019-06-01:84.12|2019-07-01:87.32|2019-08-01:91.69|2019-09-01:92.43|2019-10-01:95.24|2019-11-01:99.11|2019-12-01:110.61|2020-01-01:105.78|2020-02-01:120.93|2020-03-01:108.82|2020-04-01:95.71|2020-05-01:63.83|2020-06-01:68.22|2020-07-01:65.14|2020-08-01:61.1|2020-09-01:67.18|2020-10-01:66.71|2020-11-01:68.3|2020-12-01:66.16|2021-01-01:74.11|2021-02-01:72.97|2021-03-01:69.89|2021-04-01:64.27|2021-05-01:62.93|2021-06-01:63.11|2021-07-01:61.75|2021-08-01:64.19|2021-09-01:64.31|2021-10-01:59.1|2021-11-01:60.04|2021-12-01:64.74|2022-01-01:70.43|2022-02-01:67.14|2022-03-01:67.05|2022-04-01:68.91|2022-05-01:69.73|2022-06-01:66.19|2022-07-01:70.01|2022-08-01:70.19|2022-09-01:72.67|2022-10-01:74.41|2022-11-01:81.45|2022-12-01:88.79|2023-01-01:93.48|2023-02-01:98.68|2023-03-01:99.81|2023-04-01:96.97|2023-05-01:95.08|2023-06-01:101.06|2023-07-01:104.01|2023-08-01:109.76|2023-09-01:112.69|2023-10-01:117.14|2023-11-01:116.04|2023-12-01:121.39|2024-01-01:122.91|2024-02-01:125.55|2024-03-01:119.61|2024-04-01:117.02|2024-05-01:115.88|2024-06-01:116.52|2024-07-01:117.86|2024-08-01:117.85|2024-09-01:116.67|2024-10-01:113.4|2024-11-01:115.75|2024-12-01:123.71|2025-01-01:122.31|2025-02-01:118.22|2025-03-01:111.61|2025-04-01:103.94|2025-05-01:103.62|2025-06-01:107.86|2025-07-01:102.72|2025-08-01:108.09|2025-09-01:105.77|2025-10-01:109.46|2025-11-01:114|2025-12-01:121.63|2026-01-01:125.58|2026-02-01:120.98|2026-03-01:121.42|2026-04-01:119.08|2026-05-01:112.44|2026-06-01:117.58|2026-07-01:113.99|2026-08-01:114.52|2026-09-01:115.56|2026-10-01:108.95","4395":"1999-03-01:91.36|1999-04-01:93.76|1999-05-01:94.91|1999-06-01:112.22|1999-07-01:121.14|1999-08-01:120.56|1999-09-01:122|1999-10-01:117.91|1999-11-01:113.43|1999-12-01:114.92|2000-01-01:120.73|2000-02-01:121.31|2000-03-01:113.53|2000-04-01:109.61|2000-05-01:102.87|2000-06-01:107.86|2000-07-01:114.5|2000-08-01:106.11|2000-09-01:104.73|2000-10-01:111.45|2000-11-01:116.86|2000-12-01:116.47|2001-01-01:115.88|2001-02-01:119.74|2001-03-01:120.51|2001-04-01:116.11|2001-05-01:114.97|2001-06-01:89.18|2001-07-01:99.52|2001-08-01:98.1|2001-09-01:104.44|2001-10-01:92.65|2001-11-01:86.86|2001-12-01:96.22|2002-01-01:97.93|2002-02-01:101.54|2002-03-01:100.37|2002-04-01:110.41|2002-05-01:110.25|2002-06-01:96.27|2002-07-01:104.91|2002-08-01:103.16|2002-09-01:114.09|2002-10-01:110.95|2002-11-01:118.33|2002-12-01:121.89|2003-01-01:121.88|2003-02-01:122.22|2003-03-01:121.87|2003-04-01:126.89|2003-05-01:133.87|2003-06-01:139.77|2003-07-01:135.77|2003-08-01:132.59|2003-09-01:127.03|2003-10-01:123.31|2003-11-01:128.02|2003-12-01:135.15|2004-01-01:143.15|2004-02-01:143.04|2004-03-01:131.54|2004-04-01:124.76|2004-05-01:140.14|2004-06-01:132.55|2004-07-01:132.17|2004-08-01:138.39|2004-09-01:150.52|2004-10-01:161.62|2004-11-01:166.68|2004-12-01:153.99|2005-01-01:158.95|2005-02-01:161.39|2005-03-01:158.37|2005-04-01:155.46|2005-05-01:145.9|2005-06-01:145.56|2005-07-01:145.63|2005-08-01:130.62|2005-09-01:113.35|2005-10-01:113.07|2005-11-01:118.26|2005-12-01:132.73|2006-01-01:135.33|2006-02-01:144.65|2006-03-01:142.79|2006-04-01:134.82|2006-05-01:142.62|2006-06-01:140.98|2006-07-01:138.32|2006-08-01:133.69|2006-09-01:135.58|2006-10-01:138.1|2006-11-01:140.97|2006-12-01:131.63|2007-01-01:131.98|2007-02-01:131.86|2007-03-01:124.87|2007-04-01:122.74|2007-05-01:119.71|2007-06-01:124|2007-07-01:123.4|2007-08-01:126.21|2007-09-01:125.63|2007-10-01:124.23|2007-11-01:127|2007-12-01:135.97|2008-01-01:135.26|2008-02-01:142.47|2008-03-01:143.7|2008-04-01:142.86|2008-05-01:142.19|2008-06-01:136.17|2008-07-01:125.28|2008-08-01:134.76|2008-09-01:142.81|2008-10-01:141.04|2008-11-01:135.27|2008-12-01:134.18|2009-01-01:128.85|2009-02-01:136.62|2009-03-01:139.77|2009-04-01:131.77|2009-05-01:134.45|2009-06-01:147.63|2009-07-01:151.99|2009-08-01:152.8|2009-09-01:153.44|2009-10-01:162.94|2009-11-01:161.95|2009-12-01:160.69|2010-01-01:164.28|2010-02-01:161.87|2010-03-01:159.88|2010-04-01:160.08|2010-05-01:157.96|2010-06-01:163.76|2010-07-01:159.27|2010-08-01:165.25|2010-09-01:161.62|2010-10-01:155.23|2010-11-01:160.16|2010-12-01:165.22|2011-01-01:163.71|2011-02-01:166.17|2011-03-01:162.43|2011-04-01:163.01|2011-05-01:155.6|2011-06-01:156.42|2011-07-01:154.47|2011-08-01:154.64|2011-09-01:155.29|2011-10-01:153.85|2011-11-01:159.55|2011-12-01:163.28|2012-01-01:162.6|2012-02-01:171.7|2012-03-01:165.79|2012-04-01:166.17|2012-05-01:167.62|2012-06-01:164.11|2012-07-01:162.04|2012-08-01:156.75|2012-09-01:159.01|2012-10-01:162.68|2012-11-01:164.56|2012-12-01:162.94|2013-01-01:163.54|2013-02-01:165.78|2013-03-01:162.84|2013-04-01:157.35|2013-05-01:146.53|2013-06-01:143.42|2013-07-01:136.94|2013-08-01:133.01|2013-09-01:134.92|2013-10-01:139.15|2013-11-01:138.74|2013-12-01:135.51|2014-01-01:132.78|2014-02-01:132.24|2014-03-01:121.39|2014-04-01:115.8|2014-05-01:107.94|2014-06-01:105.01|2014-07-01:109.76|2014-08-01:110.83|2014-09-01:122.3|2014-10-01:121.64|2014-11-01:124.39|2014-12-01:115.79|2015-01-01:114.01|2015-02-01:115.05|2015-03-01:109.26|2015-04-01:105.82|2015-05-01:98.71|2015-06-01:101.54|2015-07-01:100.04|2015-08-01:101.56|2015-09-01:102.66|2015-10-01:110.57|2015-11-01:106.38|2015-12-01:106.65|2016-01-01:110.34|2016-02-01:114.36|2016-03-01:113.19|2016-04-01:111.54|2016-05-01:119.85|2016-06-01:128.5|2016-07-01:128.59|2016-08-01:130.29|2016-09-01:139.13|2016-10-01:137.23|2016-11-01:143.76|2016-12-01:136.13|2017-01-01:124.95|2017-02-01:139.96|2017-03-01:137.77|2017-04-01:134.14|2017-05-01:128.18|2017-06-01:119.56|2017-07-01:125.62|2017-08-01:122.93|2017-09-01:119.38|2017-10-01:122.69|2017-11-01:125.01|2017-12-01:127.2|2018-01-01:134.94|2018-02-01:134.89|2018-03-01:131.35|2018-04-01:126.44|2018-05-01:133.29|2018-06-01:121.36|2018-07-01:121.5|2018-08-01:118.61|2018-09-01:124.4|2018-10-01:127.36|2018-11-01:134.83|2018-12-01:149.07|2019-01-01:150.22|2019-02-01:157.48|2019-03-01:144.25|2019-04-01:136.66|2019-05-01:130.83|2019-06-01:122.89|2019-07-01:126.65|2019-08-01:129.85|2019-09-01:125.36|2019-10-01:122.87|2019-11-01:131.66|2019-12-01:128.36|2020-01-01:131.6|2020-02-01:139.03|2020-03-01:135.08|2020-04-01:122.82|2020-05-01:118.82|2020-06-01:121.9|2020-07-01:127.97|2020-08-01:130.3|2020-09-01:135.8|2020-10-01:134.88|2020-11-01:140.56|2020-12-01:142.08|2021-01-01:144.08|2021-02-01:145.06|2021-03-01:141.58|2021-04-01:132.08|2021-05-01:134.55|2021-06-01:136.8|2021-07-01:143.8|2021-08-01:143.86|2021-09-01:148.22|2021-10-01:142.89|2021-11-01:142.22|2021-12-01:143.51|2022-01-01:133.63|2022-02-01:128.65|2022-03-01:130.5|2022-04-01:127.97|2022-05-01:129.96|2022-06-01:128.53|2022-07-01:129.29|2022-08-01:131.14|2022-09-01:137.32|2022-10-01:140.78|2022-11-01:140.35|2022-12-01:145.54|2023-01-01:146.65|2023-02-01:148.86|2023-03-01:145.83|2023-04-01:143.86|2023-05-01:140.31|2023-06-01:141.41|2023-07-01:138.08|2023-08-01:145.2|2023-09-01:145.94|2023-10-01:143.16|2023-11-01:138.87|2023-12-01:141.5|2024-01-01:140.14|2024-02-01:146.66|2024-03-01:141.13|2024-04-01:137.98|2024-05-01:133.52|2024-06-01:134.07|2024-07-01:134.39|2024-08-01:133.54|2024-09-01:127.61|2024-10-01:126.03|2024-11-01:129.37|2024-12-01:126.89|2025-01-01:124.3|2025-02-01:121.98|2025-03-01:117.61|2025-04-01:115.73|2025-05-01:117.14|2025-06-01:116.24|2025-07-01:113.08|2025-08-01:114.4|2025-09-01:113.16|2025-10-01:116.42|2025-11-01:121.75|2025-12-01:126.35|2026-01-01:128.59|2026-02-01:131.66|2026-03-01:128.84|2026-04-01:122.39|2026-05-01:125.96|2026-06-01:128.41|2026-07-01:126.67|2026-08-01:125.05|2026-09-01:124.82|2026-10-01:125.01","4449":"1999-01-01:1.2|1999-02-01:1.63|1999-03-01:1.41|1999-04-01:1.49|1999-05-01:0.68|1999-06-01:1.62|1999-07-01:5.83|1999-08-01:1.55|1999-09-01:0.55|1999-10-01:0.75|1999-11-01:1.86|1999-12-01:0.67|2000-01-01:0.54|2000-02-01:-0.15|2000-03-01:1.22|2000-04-01:0.06|2000-05-01:0.26|2000-06-01:0.19|2000-07-01:4.23|2000-08-01:2.63|2000-09-01:-0.03|2000-10-01:-0.04|2000-11-01:1.07|2000-12-01:2.32|2001-01-01:0.83|2001-02-01:0.58|2001-03-01:0.02|2001-04-01:-0.06|2001-05-01:0.42|2001-06-01:1.51|2001-07-01:3.4|2001-08-01:0.96|2001-09-01:0.44|2001-10-01:1.15|2001-11-01:0.55|2001-12-01:0.51|2002-01-01:0.36|2002-02-01:-0.38|2002-03-01:1.21|2002-04-01:2.16|2002-05-01:0.3|2002-06-01:1.14|2002-07-01:2.56|2002-08-01:0.15|2002-09-01:-0.07|2002-10-01:1.18|2002-11-01:4.29|2002-12-01:1.53|2003-01-01:3.83|2003-02-01:2.71|2003-03-01:1.08|2003-04-01:1.21|2003-05-01:0.81|2003-06-01:-1.02|2003-07-01:0.73|2003-08-01:0.86|2003-09-01:1.44|2003-10-01:0.07|2003-11-01:0.36|2003-12-01:0.47|2004-01-01:0.84|2004-02-01:0.26|2004-03-01:-0.07|2004-04-01:0.32|2004-05-01:0.35|2004-06-01:1.03|2004-07-01:1.89|2004-08-01:0.92|2004-09-01:0.59|2004-10-01:0.8|2004-11-01:1.41|2004-12-01:1.43|2005-01-01:0.51|2005-02-01:0.16|2005-03-01:1.29|2005-04-01:1.14|2005-05-01:0.25|2005-06-01:-0.16|2005-07-01:0.84|2005-08-01:0.69|2005-09-01:0.92|2005-10-01:1.62|2005-11-01:0.84|2005-12-01:0.53|2006-01-01:0.58|2006-02-01:0.42|2006-03-01:0.68|2006-04-01:0.54|2006-05-01:0.45|2006-06-01:0.06|2006-07-01:0.33|2006-08-01:-0.03|2006-09-01:0.22|2006-10-01:0.12|2006-11-01:0|2006-12-01:0.83|2007-01-01:0.27|2007-02-01:0.12|2007-03-01:0.21|2007-04-01:0.39|2007-05-01:0.35|2007-06-01:-0.05|2007-07-01:-0.22|2007-08-01:0.12|2007-09-01:-0.04|2007-10-01:0.05|2007-11-01:0.26|2007-12-01:0.18|2008-01-01:0.2|2008-02-01:0.1|2008-03-01:0.47|2008-04-01:0.15|2008-05-01:0.26|2008-06-01:0.22|2008-07-01:0.6|2008-08-01:0.35|2008-09-01:0.17|2008-10-01:0.24|2008-11-01:0.18|2008-12-01:0.29|2009-01-01:0.75|2009-02-01:0.28|2009-03-01:0.14|2009-04-01:0.51|2009-05-01:0.3|2009-06-01:0.23|2009-07-01:0.57|2009-08-01:0.16|2009-09-01:0.37|2009-10-01:0.42|2009-11-01:0.4|2009-12-01:0.51|2010-01-01:0.83|2010-02-01:0.42|2010-03-01:-0.14|2010-04-01:0.14|2010-05-01:0.33|2010-06-01:0.12|2010-07-01:0.32|2010-08-01:-0.01|2010-09-01:0.19|2010-10-01:0.3|2010-11-01:0.33|2010-12-01:0.26|2011-01-01:0.94|2011-02-01:0.47|2011-03-01:1.05|2011-04-01:1.29|2011-05-01:0.55|2011-06-01:-0.12|2011-07-01:0.29|2011-08-01:0.03|2011-09-01:0.62|2011-10-01:0.46|2011-11-01:0.27|2011-12-01:0.19|2012-01-01:0.47|2012-02-01:0.26|2012-03-01:0.18|2012-04-01:0.47|2012-05-01:0.32|2012-06-01:0.15|2012-07-01:0.19|2012-08-01:0.13|2012-09-01:0.3|2012-10-01:0.25|2012-11-01:0.54|2012-12-01:0.33|2013-01-01:-0.22|2013-02-01:-1.11|2013-03-01:0.26|2013-04-01:0.41|2013-05-01:0.31|2013-06-01:0.38|2013-07-01:-0.27|2013-08-01:0.09|2013-09-01:0.16|2013-10-01:0.14|2013-11-01:0.48|2013-12-01:0.91|2014-01-01:0.38|2014-02-01:0.4|2014-03-01:-0.02|2014-04-01:0.77|2014-05-01:0.59|2014-06-01:0.25|2014-07-01:0.39|2014-08-01:0.51|2014-09-01:0.4|2014-10-01:0.38|2014-11-01:0.72|2014-12-01:0.43|2015-01-01:2.5|2015-02-01:2.37|2015-03-01:3.36|2015-04-01:0.78|2015-05-01:1.22|2015-06-01:1.12|2015-07-01:1.17|2015-08-01:0.32|2015-09-01:0.92|2015-10-01:1.39|2015-11-01:1.09|2015-12-01:0.53|2016-01-01:1.75|2016-02-01:0.39|2016-03-01:-0.36|2016-04-01:0.69|2016-05-01:1.4|2016-06-01:0.24|2016-07-01:-0.1|2016-08-01:0.26|2016-09-01:0.37|2016-10-01:0.54|2016-11-01:0.22|2016-12-01:-0.01|2017-01-01:0.8|2017-02-01:0.58|2017-03-01:0.48|2017-04-01:-0.6|2017-05-01:1.56|2017-06-01:-0.83|2017-07-01:1.28|2017-08-01:1.73|2017-09-01:0.24|2017-10-01:0.98|2017-11-01:1.32|2017-12-01:0.21|2018-01-01:0.2|2018-02-01:0.55|2018-03-01:0.23|2018-04-01:0.6|2018-05-01:1.37|2018-06-01:2.49|2018-07-01:0.89|2018-08-01:0.12|2018-09-01:0.96|2018-10-01:0.54|2018-11-01:-1|2018-12-01:-0.89|2019-01-01:0.05|2019-02-01:0.29|2019-03-01:0.75|2019-04-01:1.03|2019-05-01:1.16|2019-06-01:-0.19|2019-07-01:0.4|2019-08-01:0.6|2019-09-01:0.12|2019-10-01:-0.11|2019-11-01:0.97|2019-12-01:0.35|2020-01-01:0.51|2020-02-01:-0.28|2020-03-01:-0.22|2020-04-01:-2.06|2020-05-01:-1.02|2020-06-01:0.89|2020-07-01:1.23|2020-08-01:0.78|2020-09-01:0.13|2020-10-01:0.23|2020-11-01:0.41|2020-12-01:2.04|2021-01-01:-0.29|2021-02-01:1.69|2021-03-01:2.81|2021-04-01:0.38|2021-05-01:2.11|2021-06-01:0.81|2021-07-01:1.68|2021-08-01:0.95|2021-09-01:1.93|2021-10-01:1.35|2021-11-01:2.3|2021-12-01:0.05|2022-01-01:-0.35|2022-02-01:0.12|2022-03-01:2.65|2022-04-01:0.55|2022-05-01:-0.51|2022-06-01:0.48|2022-07-01:-4.35|2022-08-01:-2.55|2022-09-01:-1.21|2022-10-01:0.18|2022-11-01:1|2022-12-01:0.27|2023-01-01:0.72|2023-02-01:0.84|2023-03-01:2.33|2023-04-01:0.86|2023-05-01:0.71|2023-06-01:0.06|2023-07-01:0.46|2023-08-01:1.26|2023-09-01:1.11|2023-10-01:-0.03|2023-11-01:0.16|2023-12-01:0.31|2024-01-01:0.19|2024-02-01:0.88|2024-03-01:0.25|2024-04-01:0.74|2024-05-01:0.55|2024-06-01:0.33|2024-07-01:1.08|2024-08-01:-0.12|2024-09-01:1.01|2024-10-01:0.71|2024-11-01:-0.87|2024-12-01:-0.17|2025-01-01:-1.52|2025-02-01:3.16|2025-03-01:0.18|2025-04-01:0.35|2025-05-01:0.7|2025-06-01:0.6|2025-07-01:0.67|2025-08-01:-0.61|2025-09-01:1.87|2025-10-01:-0.16|2025-11-01:0.21|2025-12-01:-0.22|2026-01-01:0.53|2026-02-01:0.17|2026-03-01:1.22|2026-04-01:1|2026-05-01:0.44|2026-06-01:0.29|2026-07-01:0.27|2026-08-01:-1.25|2026-09-01:1.59","4513":"2001-12-01:51.49|2002-01-01:52.28|2002-02-01:51.43|2002-03-01:51.01|2002-04-01:50.95|2002-05-01:52.17|2002-06-01:54.54|2002-07-01:58.79|2002-08-01:55.91|2002-09-01:62.45|2002-10-01:60.4|2002-11-01:59.85|2002-12-01:59.93|2003-01-01:59.97|2003-02-01:60.26|2003-03-01:58.46|2003-04-01:54.44|2003-05-01:54.96|2003-06-01:54.42|2003-07-01:55.11|2003-08-01:55.49|2003-09-01:54.73|2003-10-01:53.8|2003-11-01:54.22|2003-12-01:54.26|2004-01-01:54.05|2004-02-01:53.8|2004-03-01:53.19|2004-04-01:52.91|2004-05-01:53.45|2004-06-01:52.83|2004-07-01:52.07|2004-08-01:51.44|2004-09-01:50.86|2004-10-01:50.75|2004-11-01:50.05|2004-12-01:50.19|2005-01-01:49.56|2005-02-01:49.3|2005-03-01:49.31|2005-04-01:48.32|2005-05-01:47.94|2005-06-01:48.04|2005-07-01:48.14|2005-08-01:47.95|2005-09-01:47.65|2005-10-01:47.53|2005-11-01:47.42|2005-12-01:47.92|2006-01-01:47.82|2006-02-01:47.78|2006-03-01:47.66|2006-04-01:47.14|2006-05-01:47.02|2006-06-01:46.96|2006-07-01:46.83|2006-08-01:46.62|2006-09-01:46.57|2006-10-01:46.17|2006-11-01:46.01|2006-12-01:46.49|2007-01-01:45.95|2007-02-01:45.86|2007-03-01:45.81|2007-04-01:45.08|2007-05-01:45.23|2007-06-01:44.8|2007-07-01:44.73|2007-08-01:44.09|2007-09-01:44.59|2007-10-01:44.6|2007-11-01:44.11|2007-12-01:44.55|2008-01-01:43.71|2008-02-01:43.79|2008-03-01:43|2008-04-01:42.82|2008-05-01:43.03|2008-06-01:42.89|2008-07-01:42.74|2008-08-01:42.02|2008-09-01:39.96|2008-10-01:38.3|2008-11-01:36.95|2008-12-01:37.57|2009-01-01:38.05|2009-02-01:38.02|2009-03-01:38.04|2009-04-01:38.65|2009-05-01:39.66|2009-06-01:39.98|2009-07-01:40.64|2009-08-01:40.63|2009-09-01:41.56|2009-10-01:41.42|2009-11-01:40.94|2009-12-01:40.88|2010-01-01:39.59|2010-02-01:39.82|2010-03-01:39.91|2010-04-01:39.47|2010-05-01:38.97|2010-06-01:38.89|2010-07-01:38.99|2010-08-01:38.76|2010-09-01:38.22|2010-10-01:37.89|2010-11-01:37.77|2010-12-01:37.98|2011-01-01:37.57|2011-02-01:37.49|2011-03-01:37.53|2011-04-01:37.42|2011-05-01:37.25|2011-06-01:37.08|2011-07-01:36.82|2011-08-01:36.55|2011-09-01:34.67|2011-10-01:35.65|2011-11-01:34.76|2011-12-01:34.47|2012-01-01:35|2012-02-01:35.15|2012-03-01:34.26|2012-04-01:33.5|2012-05-01:32.77|2012-06-01:32.78|2012-07-01:32.51|2012-08-01:32.6|2012-09-01:32.62|2012-10-01:32.44|2012-11-01:32.08|2012-12-01:32.19|2013-01-01:32.17|2013-02-01:32.59|2013-03-01:32.4|2013-04-01:32.14|2013-05-01:31.51|2013-06-01:31.19|2013-07-01:30.8|2013-08-01:30.58|2013-09-01:31.51|2013-10-01:31.62|2013-11-01:30.58|2013-12-01:30.5|2014-01-01:30.01|2014-02-01:30.36|2014-03-01:30.78|2014-04-01:30.78|2014-05-01:31.1|2014-06-01:31.48|2014-07-01:31.6|2014-08-01:32.14|2014-09-01:32.07|2014-10-01:32.22|2014-11-01:32.18|2014-12-01:32.59|2015-01-01:32.5|2015-02-01:32.3|2015-03-01:31.59|2015-04-01:32.35|2015-05-01:32.39|2015-06-01:33.23|2015-07-01:32.91|2015-08-01:32.46|2015-09-01:32.02|2015-10-01:33.07|2015-11-01:33.9|2015-12-01:35.64|2016-01-01:35.33|2016-02-01:36.28|2016-03-01:38.33|2016-04-01:38.87|2016-05-01:39.08|2016-06-01:41.35|2016-07-01:41.93|2016-08-01:42.81|2016-09-01:43.63|2016-10-01:43.88|2016-11-01:43.99|2016-12-01:46.14|2017-01-01:46.46|2017-02-01:47.26|2017-03-01:47.53|2017-04-01:47.47|2017-05-01:48.01|2017-06-01:48.44|2017-07-01:49.69|2017-08-01:50.1|2017-09-01:50.76|2017-10-01:50.54|2017-11-01:50.85|2017-12-01:51.37|2018-01-01:51.43|2018-02-01:51.58|2018-03-01:51.83|2018-04-01:51.22|2018-05-01:50.67|2018-06-01:50.71|2018-07-01:51.3|2018-08-01:50.33|2018-09-01:51.32|2018-10-01:52.42|2018-11-01:52.2|2018-12-01:52.77|2019-01-01:53.11|2019-02-01:53.11|2019-03-01:53.04|2019-04-01:53.06|2019-05-01:53.24|2019-06-01:53.82|2019-07-01:54.26|2019-08-01:53.31|2019-09-01:53.64|2019-10-01:54.11|2019-11-01:53.79|2019-12-01:54.7|2020-01-01:53.18|2020-02-01:52.54|2020-03-01:50.63|2020-04-01:51.57|2020-05-01:53.71|2020-06-01:56.24|2020-07-01:58.12|2020-08-01:58.67|2020-09-01:59.3|2020-10-01:59.14|2020-11-01:60.57|2020-12-01:61.37|2021-01-01:59.71|2021-02-01:59.5|2021-03-01:58.53|2021-04-01:57.7|2021-05-01:57.54|2021-06-01:58.43|2021-07-01:57.77|2021-08-01:57.18|2021-09-01:56.17|2021-10-01:55.21|2021-11-01:54.98|2021-12-01:55.11|2022-01-01:54.82|2022-02-01:55.45|2022-03-01:56.66|2022-04-01:56.4|2022-05-01:56.91|2022-06-01:56.03|2022-07-01:55.59|2022-08-01:56.05|2022-09-01:56.03|2022-10-01:55.98|2022-11-01:55.81|2022-12-01:56.13|2023-01-01:55.21|2023-02-01:55.71|2023-03-01:55.98|2023-04-01:55.92|2023-05-01:56.59|2023-06-01:57.78|2023-07-01:58.34|2023-08-01:58.68|2023-09-01:58.87|2023-10-01:58.85|2023-11-01:59.08|2023-12-01:60.43|2024-01-01:59.55|2024-02-01:60.32|2024-03-01:60.59|2024-04-01:60.55|2024-05-01:61.23|2024-06-01:61.28|2024-07-01:60.91|2024-08-01:61.08|2024-09-01:61.46|2024-10-01:61.12|2024-11-01:60.99|2024-12-01:61.3|2025-01-01:60.96|2025-02-01:61.13|2025-03-01:61.3|2025-04-01:61.25|2025-05-01:61.71|2025-06-01:62.6|2025-07-01:63.41|2025-08-01:64.05|2025-09-01:64.57|2025-10-01:64.68|2025-11-01:65.18|2025-12-01:65.24|2026-01-01:64.94|2026-02-01:65.46|2026-03-01:66.67|2026-04-01:67.13|2026-05-01:67.88|2026-06-01:68.49|2026-07-01:69.11|2026-08-01:69.27","5727":"2002-11-01:3.8|2002-12-01:4.42|2003-01-01:4.93|2003-02-01:5.12|2003-03-01:5.38|2003-04-01:4.97|2003-05-01:5.15|2003-06-01:5.39|2003-07-01:5.91|2003-08-01:5.92|2003-09-01:5.97|2003-10-01:5.55|2003-11-01:5.64|2003-12-01:5.18|2004-01-01:4.6|2004-02-01:4.33|2004-03-01:4|2004-04-01:4.29|2004-05-01:4.01|2004-06-01:3.7|2004-07-01:3.34|2004-08-01:3.11|2004-09-01:3.05|2004-10-01:3.1|2004-11-01:3|2004-12-01:2.88|2005-01-01:2.78|2005-02-01:2.93|2005-03-01:2.98|2005-04-01:2.74|2005-05-01:2.89|2005-06-01:3.1|2005-07-01:3.13|2005-08-01:3.14|2005-09-01:3.31|2005-10-01:3.32|2005-11-01:3.45|2005-12-01:3.54|2006-01-01:4.06|2006-02-01:4.12|2006-03-01:4.11|2006-04-01:4.02|2006-05-01:3.71|2006-06-01:3.72|2006-07-01:3.8|2006-08-01:3.71|2006-09-01:3.65|2006-10-01:3.51|2006-11-01:3.42|2006-12-01:3.57|2007-01-01:3.01|2007-02-01:2.85|2007-03-01:2.9|2007-04-01:2.83|2007-05-01:3.08|2007-06-01:2.82|2007-07-01:2.78|2007-08-01:2.7|2007-09-01:2.85|2007-10-01:2.86|2007-11-01:2.7|2007-12-01:2.74|2008-01-01:2.5|2008-02-01:2.55|2008-03-01:2.21|2008-04-01:2.25|2008-05-01:2.18|2008-06-01:2.31|2008-07-01:2.28|2008-08-01:2.22|2008-09-01:1.74|2008-10-01:1.32|2008-11-01:1.52|2008-12-01:1.99|2009-01-01:2.46|2009-02-01:2.43|2009-03-01:2.68|2009-04-01:2.85|2009-05-01:2.93|2009-06-01:3.02|2009-07-01:3.19|2009-08-01:3.32|2009-09-01:4.01|2009-10-01:4.28|2009-11-01:3.96|2009-12-01:3.19|2010-01-01:2.86|2010-02-01:2.94|2010-03-01:3.2|2010-04-01:2.96|2010-05-01:3.07|2010-06-01:3.12|2010-07-01:3.12|2010-08-01:3.16|2010-09-01:2.21|2010-10-01:2.32|2010-11-01:2.58|2010-12-01:2.41|2011-01-01:2.47|2011-02-01:2.45|2011-03-01:2.17|2011-04-01:2.32|2011-05-01:2.27|2011-06-01:2.05|2011-07-01:1.78|2011-08-01:1.91|2011-09-01:2.39|2011-10-01:2.37|2011-11-01:2.26|2011-12-01:2.47|2012-01-01:2.27|2012-02-01:2.19|2012-03-01:2.26|2012-04-01:2.27|2012-05-01:2.29|2012-06-01:2.44|2012-07-01:2.56|2012-08-01:2.52|2012-09-01:2.57|2012-10-01:2.5|2012-11-01:2.73|2012-12-01:2.26|2013-01-01:2.22|2013-02-01:2.5|2013-03-01:2.59|2013-04-01:2.65|2013-05-01:2.6|2013-06-01:2.56|2013-07-01:2.71|2013-08-01:2.82|2013-09-01:3|2013-10-01:3.1|2013-11-01:2.67|2013-12-01:2.96|2014-01-01:3.27|2014-02-01:2.98|2014-03-01:2.9|2014-04-01:2.83|2014-05-01:3.13|2014-06-01:3.27|2014-07-01:3.46|2014-08-01:3.6|2014-09-01:4.39|2014-10-01:4.48|2014-11-01:5.18|2014-12-01:5.95|2015-01-01:5.7|2015-02-01:6.53|2015-03-01:7.45|2015-04-01:7.16|2015-05-01:7.61|2015-06-01:7.83|2015-07-01:8.48|2015-08-01:8.89|2015-09-01:9.01|2015-10-01:9.18|2015-11-01:9.19|2015-12-01:10.22|2016-01-01:10.73|2016-02-01:10.6|2016-03-01:9.59|2016-04-01:9.96|2016-05-01:9.93|2016-06-01:9.81|2016-07-01:9.47|2016-08-01:9.53|2016-09-01:9.32|2016-10-01:8.77|2016-11-01:9.32|2016-12-01:8.98|2017-01-01:8.48|2017-02-01:8.47|2017-03-01:9.13|2017-04-01:9.14|2017-05-01:9.19|2017-06-01:9.45|2017-07-01:9.28|2017-08-01:8.97|2017-09-01:8.73|2017-10-01:9.21|2017-11-01:8.41|2017-12-01:7.77|2018-01-01:7.44|2018-02-01:7.28|2018-03-01:7.3|2018-04-01:7.42|2018-05-01:7.12|2018-06-01:7.18|2018-07-01:6.91|2018-08-01:7.32|2018-09-01:7.08|2018-10-01:6.68|2018-11-01:6.95|2018-12-01:6.96|2019-01-01:6.83|2019-02-01:6.78|2019-03-01:6.83|2019-04-01:6.83|2019-05-01:6.77|2019-06-01:6.37|2019-07-01:6.35|2019-08-01:6.14|2019-09-01:6.2|2019-10-01:6.23|2019-11-01:6.24|2019-12-01:5.81|2020-01-01:5.87|2020-02-01:5.9|2020-03-01:6.11|2020-04-01:7.32|2020-05-01:8.61|2020-06-01:11.02|2020-07-01:11.77|2020-08-01:12.54|2020-09-01:13.26|2020-10-01:13.48|2020-11-01:12.97|2020-12-01:13.34|2021-01-01:13.25|2021-02-01:12.99|2021-03-01:12.32|2021-04-01:10.25|2021-05-01:8.81|2021-06-01:7.06|2021-07-01:6.59|2021-08-01:5.42|2021-09-01:4.64|2021-10-01:4.52|2021-11-01:4.54|2021-12-01:4.26|2022-01-01:3.51|2022-02-01:3.29|2022-03-01:3.06|2022-04-01:3.8|2022-05-01:4.06|2022-06-01:4.1|2022-07-01:3.71|2022-08-01:4.04|2022-09-01:4.19|2022-10-01:4.04|2022-11-01:4.44|2022-12-01:4.57|2023-01-01:4.9|2023-02-01:5.52|2023-03-01:5.98|2023-04-01:5.79|2023-05-01:6.26|2023-06-01:6.28|2023-07-01:6.81|2023-08-01:7.15|2023-09-01:7.48|2023-10-01:7.73|2023-11-01:7.77|2023-12-01:8.84|2024-01-01:9|2024-02-01:9.15|2024-03-01:8.97|2024-04-01:9.3|2024-05-01:9.43|2024-06-01:9.78|2024-07-01:9.86|2024-08-01:9.66|2024-09-01:9.2|2024-10-01:9.36|2024-11-01:9.47|2024-12-01:8.47|2025-01-01:8.08|2025-02-01:7.87|2025-03-01:7.88|2025-04-01:7.7|2025-05-01:7.54|2025-06-01:7.27|2025-07-01:7.82|2025-08-01:7.79|2025-09-01:8.13|2025-10-01:8.14|2025-11-01:8.12|2025-12-01:8.34|2026-01-01:8.48|2026-02-01:8.47|2026-03-01:9.39|2026-04-01:9.37|2026-05-01:9.61|2026-06-01:9.99|2026-07-01:9.35|2026-08-01:9.48","5793":"2002-11-01:-3.31|2002-12-01:-3.19|2003-01-01:-3.25|2003-02-01:-3.36|2003-03-01:-3.33|2003-04-01:-3.57|2003-05-01:-3.61|2003-06-01:-3.42|2003-07-01:-3.42|2003-08-01:-3.56|2003-09-01:-3.35|2003-10-01:-3.34|2003-11-01:-3.35|2003-12-01:-3.24|2004-01-01:-3.35|2004-02-01:-3.33|2004-03-01:-3.43|2004-04-01:-3.28|2004-05-01:-3.33|2004-06-01:-3.59|2004-07-01:-3.61|2004-08-01:-3.68|2004-09-01:-3.65|2004-10-01:-3.63|2004-11-01:-3.51|2004-12-01:-3.69|2005-01-01:-3.78|2005-02-01:-3.64|2005-03-01:-3.73|2005-04-01:-4.08|2005-05-01:-4.01|2005-06-01:-3.99|2005-07-01:-4.02|2005-08-01:-4.02|2005-09-01:-3.94|2005-10-01:-3.97|2005-11-01:-3.91|2005-12-01:-3.74|2006-01-01:-3.42|2006-02-01:-3.38|2006-03-01:-3.29|2006-04-01:-3.31|2006-05-01:-3.29|2006-06-01:-3.32|2006-07-01:-3.24|2006-08-01:-3.35|2006-09-01:-3.22|2006-10-01:-3.28|2006-11-01:-3.28|2006-12-01:-3.15|2007-01-01:-3.49|2007-02-01:-3.5|2007-03-01:-3.41|2007-04-01:-3.41|2007-05-01:-3.45|2007-06-01:-3.39|2007-07-01:-3.4|2007-08-01:-3.24|2007-09-01:-3.21|2007-10-01:-3.24|2007-11-01:-3.34|2007-12-01:-3.24|2008-01-01:-3.39|2008-02-01:-3.43|2008-03-01:-3.63|2008-04-01:-3.61|2008-05-01:-3.6|2008-06-01:-3.62|2008-07-01:-3.72|2008-08-01:-3.77|2008-09-01:-3.85|2008-10-01:-3.98|2008-11-01:-3.69|2008-12-01:-3.33|2009-01-01:-2.89|2009-02-01:-2.74|2009-03-01:-2.56|2009-04-01:-2.3|2009-05-01:-2.09|2009-06-01:-1.87|2009-07-01:-1.6|2009-08-01:-1.46|2009-09-01:-1.07|2009-10-01:-0.94|2009-11-01:-1.33|2009-12-01:-1.94|2010-01-01:-2.18|2010-02-01:-2.15|2010-03-01:-1.88|2010-04-01:-2.09|2010-05-01:-2.02|2010-06-01:-1.96|2010-07-01:-1.91|2010-08-01:-1.88|2010-09-01:-2.75|2010-10-01:-2.61|2010-11-01:-2.37|2010-12-01:-2.62|2011-01-01:-2.63|2011-02-01:-2.72|2011-03-01:-3.03|2011-04-01:-2.95|2011-05-01:-3.08|2011-06-01:-3.31|2011-07-01:-3.58|2011-08-01:-3.53|2011-09-01:-3.03|2011-10-01:-3.1|2011-11-01:-3.17|2011-12-01:-2.94|2012-01-01:-3.1|2012-02-01:-3.12|2012-03-01:-3.02|2012-04-01:-2.91|2012-05-01:-2.78|2012-06-01:-2.53|2012-07-01:-2.33|2012-08-01:-2.28|2012-09-01:-2.12|2012-10-01:-2.07|2012-11-01:-1.77|2012-12-01:-2.18|2013-01-01:-2.25|2013-02-01:-1.98|2013-03-01:-1.82|2013-04-01:-1.72|2013-05-01:-1.77|2013-06-01:-1.81|2013-07-01:-1.73|2013-08-01:-1.65|2013-09-01:-1.43|2013-10-01:-1.3|2013-11-01:-1.95|2013-12-01:-1.71|2014-01-01:-1.51|2014-02-01:-1.59|2014-03-01:-1.57|2014-04-01:-1.68|2014-05-01:-1.37|2014-06-01:-1.23|2014-07-01:-1.1|2014-08-01:-0.84|2014-09-01:-0.55|2014-10-01:-0.5|2014-11-01:0.16|2014-12-01:0.56|2015-01-01:0.54|2015-02-01:0.62|2015-03-01:0.67|2015-04-01:0.73|2015-05-01:0.65|2015-06-01:0.77|2015-07-01:0.86|2015-08-01:0.74|2015-09-01:0.43|2015-10-01:0.69|2015-11-01:0.88|2015-12-01:1.86|2016-01-01:1.74|2016-02-01:2.08|2016-03-01:2.25|2016-04-01:2.3|2016-05-01:2.47|2016-06-01:2.47|2016-07-01:2.51|2016-08-01:2.74|2016-09-01:3.04|2016-10-01:2.21|2016-11-01:2.51|2016-12-01:2.48|2017-01-01:2.33|2017-02-01:2.33|2017-03-01:2.33|2017-04-01:2.28|2017-05-01:2.46|2017-06-01:2.6|2017-07-01:2.64|2017-08-01:2.44|2017-09-01:2.35|2017-10-01:2.87|2017-11-01:2.27|2017-12-01:1.68|2018-01-01:1.52|2018-02-01:1.42|2018-03-01:1.62|2018-04-01:1.76|2018-05-01:1.42|2018-06-01:1.32|2018-07-01:1.13|2018-08-01:1.23|2018-09-01:1.27|2018-10-01:1.22|2018-11-01:1.42|2018-12-01:1.55|2019-01-01:1.54|2019-02-01:1.5|2019-03-01:1.4|2019-04-01:1.35|2019-05-01:1.4|2019-06-01:1.39|2019-07-01:1.37|2019-08-01:1.32|2019-09-01:1.26|2019-10-01:1.23|2019-11-01:1.22|2019-12-01:0.84|2020-01-01:0.71|2020-02-01:0.78|2020-03-01:0.85|2020-04-01:2.21|2020-05-01:3.81|2020-06-01:6.18|2020-07-01:7.22|2020-08-01:8.21|2020-09-01:8.77|2020-10-01:8.82|2020-11-01:8.81|2020-12-01:9.24|2021-01-01:9.13|2021-02-01:8.91|2021-03-01:8.4|2021-04-01:6.75|2021-05-01:5.21|2021-06-01:3.66|2021-07-01:2.77|2021-08-01:1.52|2021-09-01:0.61|2021-10-01:0.23|2021-11-01:-0.14|2021-12-01:-0.72|2022-01-01:-1.19|2022-02-01:-1.36|2022-03-01:-1.34|2022-04-01:-1.48|2022-05-01:-1.28|2022-06-01:-2.11|2022-07-01:-2.4|2022-08-01:-1.89|2022-09-01:-1.85|2022-10-01:-1.75|2022-11-01:-1.38|2022-12-01:-1.25|2023-01-01:-1.21|2023-02-01:-0.91|2023-03-01:-0.72|2023-04-01:-0.54|2023-05-01:-0.37|2023-06-01:0.23|2023-07-01:0.76|2023-08-01:0.69|2023-09-01:0.95|2023-10-01:1.06|2023-11-01:1.21|2023-12-01:2.28|2024-01-01:2.23|2024-02-01:2.42|2024-03-01:2.27|2024-04-01:2.38|2024-05-01:2.49|2024-06-01:2.4|2024-07-01:2.25|2024-08-01:2.23|2024-09-01:2.12|2024-10-01:1.91|2024-11-01:1.64|2024-12-01:0.4|2025-01-01:0.39|2025-02-01:0.13|2025-03-01:0.11|2025-04-01:0.05|2025-05-01:-0.2|2025-06-01:-0.15|2025-07-01:0.22|2025-08-01:0.19|2025-09-01:0.27|2025-10-01:0.3|2025-11-01:0.36|2025-12-01:0.43|2026-01-01:0.43|2026-02-01:0.41|2026-03-01:1.06|2026-04-01:0.97|2026-05-01:1.14|2026-06-01:1.19|2026-07-01:0.67|2026-08-01:0.62","7326":"1999-01-01:0.47|2000-01-01:4.39|2001-01-01:1.39|2002-01-01:3.05|2003-01-01:1.14|2004-01-01:5.76|2005-01-01:3.2|2006-01-01:3.96|2007-01-01:6.07|2008-01-01:5.09|2009-01-01:-0.13|2010-01-01:7.53|2011-01-01:3.97|2012-01-01:1.92|2013-01-01:3|2014-01-01:0.5|2015-01-01:-3.55|2016-01-01:-3.28|2017-01-01:1.32|2018-01-01:1.78|2019-01-01:1.22|2020-01-01:-3.28|2021-01-01:4.76|2022-01-01:3.02|2023-01-01:3.24|2024-01-01:3.42|2025-01-01:2.29","7327":"1999-01-01:6.53|2000-01-01:2.72|2001-01-01:5.2|2002-01-01:8.02|2003-01-01:8.31|2004-01-01:2|2005-01-01:1.12|2006-01-01:4.64|2007-01-01:3.25|2008-01-01:5.77|2009-01-01:-3.73|2010-01-01:6.7|2011-01-01:5.64|2012-01-01:-3.08|2013-01-01:8.36|2014-01-01:2.79|2015-01-01:3.31|2016-01-01:-5.22|2017-01-01:14.15|2018-01-01:1.31|2019-01-01:0.42|2020-01-01:4.17|2021-01-01:0|2022-01-01:-1.13|2023-01-01:16.3|2024-01-01:-3.74|2025-01-01:11.7","7328":"1999-01-01:-2.61|2000-01-01:4.41|2001-01-01:-0.64|2002-01-01:3.8|2003-01-01:0.1|2004-01-01:8.21|2005-01-01:1.99|2006-01-01:2.01|2007-01-01:6.21|2008-01-01:4.1|2009-01-01:-4.7|2010-01-01:10.2|2011-01-01:4.11|2012-01-01:-0.72|2013-01-01:2.17|2014-01-01:-1.51|2015-01-01:-5.76|2016-01-01:-4.57|2017-01-01:-0.5|2018-01-01:0.72|2019-01-01:-0.67|2020-01-01:-2.97|2021-01-01:5.04|2022-01-01:1.52|2023-01-01:1.68|2024-01-01:3.08|2025-01-01:1.45","7329":"1999-01-01:1.82|2000-01-01:3.85|2001-01-01:2.06|2002-01-01:3.12|2003-01-01:0.99|2004-01-01:5.01|2005-01-01:3.66|2006-01-01:4.33|2007-01-01:5.83|2008-01-01:4.82|2009-01-01:2.07|2010-01-01:5.8|2011-01-01:3.46|2012-01-01:2.9|2013-01-01:2.75|2014-01-01:0.99|2015-01-01:-2.73|2016-01-01:-2.22|2017-01-01:0.77|2018-01-01:2.09|2019-01-01:1.51|2020-01-01:-3.74|2021-01-01:4.8|2022-01-01:4.26|2023-01-01:2.78|2024-01-01:3.78|2025-01-01:1.82","7415":"1999-01-01:832|1999-02-01:1878|1999-03-01:3503|1999-04-01:4537|1999-05-01:5565|1999-06-01:7203|1999-07-01:8282|1999-08-01:9789|1999-09-01:11030|1999-10-01:12637|1999-11-01:14558|1999-12-01:18052|2000-01-01:916|2000-02-01:1962|2000-03-01:3441|2000-04-01:4304|2000-05-01:5384|2000-06-01:6688|2000-07-01:9528|2000-08-01:10923|2000-09-01:12210|2000-10-01:14895|2000-11-01:18950|2000-12-01:23046|2001-01-01:1439|2001-02-01:2627|2001-03-01:5323|2001-04-01:6600|2001-05-01:8192|2001-06-01:10518|2001-07-01:11799|2001-08-01:15196|2001-09-01:16904|2001-10-01:19221|2001-11-01:21845|2001-12-01:25217|2002-01-01:1802|2002-02-01:4361|2002-03-01:6068|2002-04-01:7717|2002-05-01:10370|2002-06-01:13223|2002-07-01:16101|2002-08-01:20920|2002-09-01:24632|2002-10-01:29002|2002-11-01:32323|2002-12-01:37419|2003-01-01:1803|2003-02-01:3844|2003-03-01:5508|2003-04-01:6945|2003-05-01:8753|2003-06-01:12212|2003-07-01:15385|2003-08-01:16972|2003-09-01:18970|2003-10-01:22212|2003-11-01:28556|2003-12-01:33534|2004-01-01:2237|2004-02-01:5215|2004-03-01:8508|2004-04-01:12124|2004-05-01:13912|2004-06-01:18008|2004-07-01:20978|2004-08-01:24287|2004-09-01:27744|2004-10-01:31727|2004-11-01:35283|2004-12-01:39834|2005-01-01:3795|2005-02-01:6257|2005-03-01:9463|2005-04-01:12040|2005-05-01:15092|2005-06-01:19973|2005-07-01:24553|2005-08-01:28740|2005-09-01:31146|2005-10-01:33786|2005-11-01:39778|2005-12-01:46980|2006-01-01:2488|2006-02-01:4275|2006-03-01:6772|2006-04-01:10625|2006-05-01:13636|2006-06-01:18250|2006-07-01:22611|2006-08-01:27339|2006-09-01:31174|2006-10-01:34958|2006-11-01:41482|2006-12-01:51318|2007-01-01:4681|2007-02-01:7020|2007-03-01:11271|2007-04-01:14844|2007-05-01:19057|2007-06-01:24709|2007-07-01:31240|2007-08-01:36970|2007-09-01:41800|2007-10-01:49818|2007-11-01:56635|2007-12-01:64892|2008-01-01:4395|2008-02-01:8760|2008-03-01:16359|2008-04-01:25827|2008-05-01:32315|2008-06-01:37881|2008-07-01:44574|2008-08-01:51859|2008-09-01:59987|2008-10-01:70129|2008-11-01:78546|2008-12-01:90878|2009-01-01:4438|2009-02-01:9474|2009-03-01:17893|2009-04-01:25605|2009-05-01:31643|2009-06-01:41880|2009-07-01:74052|2009-08-01:83142|2009-09-01:95801|2009-10-01:106486|2009-11-01:117459|2009-12-01:136356|2010-01-01:7703|2010-02-01:16016|2010-03-01:25462|2010-04-01:35621|2010-05-01:46036|2010-06-01:59316|2010-07-01:72666|2010-08-01:91015|2010-09-01:128013|2010-10-01:140916|2010-11-01:153606|2010-12-01:168423|2011-01-01:8272|2011-02-01:17152|2011-03-01:24865|2011-04-01:33651|2011-05-01:43339|2011-06-01:55596|2011-07-01:69158|2011-08-01:80474|2011-09-01:91603|2011-10-01:103338|2011-11-01:118003|2011-12-01:138873|2012-01-01:7041|2012-02-01:15166|2012-03-01:24483|2012-04-01:34150|2012-05-01:43807|2012-06-01:53539|2012-07-01:67853|2012-08-01:81146|2012-09-01:94558|2012-10-01:108351|2012-11-01:121785|2012-12-01:155992|2013-01-01:10102|2013-02-01:21174|2013-03-01:37159|2013-04-01:54415|2013-05-01:73041|2013-06-01:88554|2013-07-01:102312|2013-08-01:117280|2013-09-01:131560|2013-10-01:146787|2013-11-01:162351|2013-12-01:190419|2014-01-01:15721|2014-02-01:28456|2014-03-01:43651|2014-04-01:58828|2014-05-01:68773|2014-06-01:84056|2014-07-01:97394|2014-08-01:112971|2014-09-01:129648|2014-10-01:146563|2014-11-01:162253|2014-12-01:187837|2015-01-01:9779|2015-02-01:18912|2015-03-01:33252|2015-04-01:43523|2015-05-01:54793|2015-06-01:68770|2015-07-01:77059|2015-08-01:85026|2015-09-01:94440|2015-10-01:105529|2015-11-01:116815|2015-12-01:135942|2016-01-01:5902|2016-02-01:11893|2016-03-01:18055|2016-04-01:25123|2016-05-01:31856|2016-06-01:40125|2016-07-01:48591|2016-08-01:55480|2016-09-01:62196|2016-10-01:68961|2016-11-01:76469|2016-12-01:88257|2017-01-01:4719|2017-02-01:10015|2017-03-01:15065|2017-04-01:21378|2017-05-01:27718|2017-06-01:33515|2017-07-01:40224|2017-08-01:44946|2017-09-01:49969|2017-10-01:55172|2017-11-01:61045|2017-12-01:70751|2018-01-01:3855|2018-02-01:6811|2018-03-01:11153|2018-04-01:15226|2018-05-01:22228|2018-06-01:27756|2018-07-01:33021|2018-08-01:38811|2018-09-01:43568|2018-10-01:49050|2018-11-01:55517|2018-12-01:69303|2019-01-01:5814|2019-02-01:10428|2019-03-01:14480|2019-04-01:17387|2019-05-01:21443|2019-06-01:25177|2019-07-01:28921|2019-08-01:34230|2019-09-01:38034|2019-10-01:42587|2019-11-01:49558|2019-12-01:55314|2020-01-01:2302|2020-02-01:5187|2020-03-01:8378|2020-04-01:13645|2020-05-01:19196|2020-06-01:26024|2020-07-01:32356|2020-08-01:40120|2020-09-01:45335|2020-10-01:50995|2020-11-01:56038|2020-12-01:64921|2021-01-01:2882|2021-02-01:6264|2021-03-01:11330|2021-04-01:15284|2021-05-01:19340|2021-06-01:23903|2021-07-01:29443|2021-08-01:37528|2021-09-01:45732|2021-10-01:52338|2021-11-01:58525|2021-12-01:64302|2022-01-01:3502|2022-02-01:8890|2022-03-01:14787|2022-04-01:19745|2022-05-01:27043|2022-06-01:33446|2022-07-01:38458|2022-08-01:53872|2022-09-01:62887|2022-10-01:73553|2022-11-01:83888|2022-12-01:97521|2023-01-01:5846|2023-02-01:10363|2023-03-01:19090|2023-04-01:25653|2023-05-01:30823|2023-06-01:40617|2023-07-01:50200|2023-08-01:62925|2023-09-01:75380|2023-10-01:92372|2023-11-01:101896|2023-12-01:114364|2024-01-01:7878|2024-02-01:13269|2024-03-01:23310|2024-04-01:31368|2024-05-01:39210|2024-06-01:49298|2024-07-01:60232|2024-08-01:75580|2024-09-01:87026|2024-10-01:102603|2024-11-01:117499|2024-12-01:133684|2025-01-01:8841|2025-02-01:19285|2025-03-01:25169|2025-04-01:34946|2025-05-01:43318|2025-06-01:54587|2025-07-01:69702|2025-08-01:84805|2025-09-01:101903|2025-10-01:120029|2025-11-01:141281|2025-12-01:169696|2026-01-01:10180|2026-02-01:21059|2026-03-01:36221|2026-04-01:49200|2026-05-01:57942|2026-06-01:74761","7416":"1999-01-01:425|1999-02-01:1122|1999-03-01:1809|1999-04-01:2386|1999-05-01:2939|1999-06-01:3876|1999-07-01:4436|1999-08-01:5121|1999-09-01:5703|1999-10-01:6451|1999-11-01:7083|1999-12-01:8166|2000-01-01:383|2000-02-01:989|2000-03-01:1924|2000-04-01:2314|2000-05-01:2859|2000-06-01:3571|2000-07-01:4247|2000-08-01:4882|2000-09-01:5507|2000-10-01:7411|2000-11-01:8999|2000-12-01:10283|2001-01-01:945|2001-02-01:1758|2001-03-01:3754|2001-04-01:4505|2001-05-01:5464|2001-06-01:6364|2001-07-01:7011|2001-08-01:8350|2001-09-01:9065|2001-10-01:10325|2001-11-01:11532|2001-12-01:12760|2002-01-01:1024|2002-02-01:1792|2002-03-01:2401|2002-04-01:3204|2002-05-01:4903|2002-06-01:7054|2002-07-01:8448|2002-08-01:10080|2002-09-01:11661|2002-10-01:13933|2002-11-01:15441|2002-12-01:17178|2003-01-01:1235|2003-02-01:1845|2003-03-01:2513|2003-04-01:3153|2003-05-01:3866|2003-06-01:5791|2003-07-01:6385|2003-08-01:6914|2003-09-01:7587|2003-10-01:9009|2003-11-01:13480|2003-12-01:15937|2004-01-01:1107|2004-02-01:2559|2004-03-01:4302|2004-04-01:5474|2004-05-01:5976|2004-06-01:7338|2004-07-01:8251|2004-08-01:8887|2004-09-01:9562|2004-10-01:11099|2004-11-01:12842|2004-12-01:15526|2005-01-01:2089|2005-02-01:3051|2005-03-01:4797|2005-04-01:5966|2005-05-01:7363|2005-06-01:10274|2005-07-01:11523|2005-08-01:13512|2005-09-01:14681|2005-10-01:15620|2005-11-01:19479|2005-12-01:23033|2006-01-01:634|2006-02-01:1299|2006-03-01:2385|2006-04-01:4695|2006-05-01:6089|2006-06-01:8477|2006-07-01:10937|2006-08-01:13812|2006-09-01:16059|2006-10-01:17890|2006-11-01:20484|2006-12-01:25663|2007-01-01:2254|2007-02-01:3334|2007-03-01:4943|2007-04-01:6426|2007-05-01:8118|2007-06-01:10614|2007-07-01:14002|2007-08-01:16539|2007-09-01:17718|2007-10-01:20108|2007-11-01:22884|2007-12-01:25395|2008-01-01:2090|2008-02-01:4056|2008-03-01:7439|2008-04-01:11493|2008-05-01:13341|2008-06-01:15125|2008-07-01:16684|2008-08-01:19329|2008-09-01:22708|2008-10-01:26752|2008-11-01:30116|2008-12-01:35710|2009-01-01:1970|2009-02-01:4464|2009-03-01:7713|2009-04-01:9970|2009-05-01:10976|2009-06-01:15410|2009-07-01:37157|2009-08-01:40562|2009-09-01:46883|2009-10-01:50612|2009-11-01:53930|2009-12-01:60302|2010-01-01:2048|2010-02-01:5157|2010-03-01:7589|2010-04-01:10327|2010-05-01:12944|2010-06-01:18062|2010-07-01:23354|2010-08-01:33187|2010-09-01:63744|2010-10-01:68720|2010-11-01:71989|2010-12-01:77255|2011-01-01:2559|2011-02-01:4722|2011-03-01:6950|2011-04-01:9631|2011-05-01:12717|2011-06-01:17236|2011-07-01:20467|2011-08-01:23296|2011-09-01:26194|2011-10-01:29458|2011-11-01:33994|2011-12-01:40270|2012-01-01:1532|2012-02-01:3164|2012-03-01:6166|2012-04-01:9142|2012-05-01:11096|2012-06-01:14526|2012-07-01:22036|2012-08-01:27445|2012-09-01:32324|2012-10-01:36340|2012-11-01:40124|2012-12-01:45861|2013-01-01:3230|2013-02-01:6571|2013-03-01:13238|2013-04-01:19594|2013-05-01:25008|2013-06-01:28247|2013-07-01:32351|2013-08-01:35517|2013-09-01:39357|2013-10-01:42961|2013-11-01:46929|2013-12-01:53960|2014-01-01:4209|2014-02-01:8329|2014-03-01:12178|2014-04-01:14905|2014-05-01:16954|2014-06-01:21399|2014-07-01:24967|2014-08-01:29701|2014-09-01:34069|2014-10-01:38413|2014-11-01:41858|2014-12-01:47038|2015-01-01:2508|2015-02-01:5244|2015-03-01:9349|2015-04-01:11736|2015-05-01:15051|2015-06-01:18662|2015-07-01:21507|2015-08-01:23542|2015-09-01:26021|2015-10-01:28293|2015-11-01:30679|2015-12-01:35153|2016-01-01:1497|2016-02-01:3517|2016-03-01:5392|2016-04-01:6598|2016-05-01:8494|2016-06-01:11080|2016-07-01:14541|2016-08-01:18455|2016-09-01:20731|2016-10-01:23028|2016-11-01:24761|2016-12-01:28609|2017-01-01:933|2017-02-01:1902|2017-03-01:3117|2017-04-01:4490|2017-05-01:5842|2017-06-01:6944|2017-07-01:8730|2017-08-01:9885|2017-09-01:10711|2017-10-01:11551|2017-11-01:12646|2017-12-01:14364|2018-01-01:400|2018-02-01:893|2018-03-01:1668|2018-04-01:2549|2018-05-01:3602|2018-06-01:5012|2018-07-01:5737|2018-08-01:6844|2018-09-01:7955|2018-10-01:9358|2018-11-01:10571|2018-12-01:12125|2019-01-01:1022|2019-02-01:2043|2019-03-01:2574|2019-04-01:3053|2019-05-01:3746|2019-06-01:4755|2019-07-01:5264|2019-08-01:5751|2019-09-01:6270|2019-10-01:6678|2019-11-01:7202|2019-12-01:8737|2020-01-01:257|2020-02-01:792|2020-03-01:1294|2020-04-01:2254|2020-05-01:3078|2020-06-01:4283|2020-07-01:4883|2020-08-01:7081|2020-09-01:7525|2020-10-01:8319|2020-11-01:9338|2020-12-01:12673|2021-01-01:252|2021-02-01:828|2021-03-01:1427|2021-04-01:2099|2021-05-01:2992|2021-06-01:3882|2021-07-01:4387|2021-08-01:5494|2021-09-01:6604|2021-10-01:7900|2021-11-01:9338|2021-12-01:10024|2022-01-01:398|2022-02-01:1430|2022-03-01:3259|2022-04-01:4791|2022-05-01:6656|2022-06-01:8060|2022-07-01:8913|2022-08-01:10500|2022-09-01:12280|2022-10-01:14818|2022-11-01:16909|2022-12-01:18890|2023-01-01:1388|2023-02-01:2297|2023-03-01:6052|2023-04-01:6513|2023-05-01:7286|2023-06-01:9003|2023-07-01:10861|2023-08-01:12754|2023-09-01:16587|2023-10-01:18054|2023-11-01:19363|2023-12-01:21622|2024-01-01:739|2024-02-01:1663|2024-03-01:3976|2024-04-01:5489|2024-05-01:7612|2024-06-01:11047|2024-07-01:12527|2024-08-01:15289|2024-09-01:17375|2024-10-01:19899|2024-11-01:21528|2024-12-01:25748|2025-01-01:1418|2025-02-01:3044|2025-03-01:4705|2025-04-01:7242|2025-05-01:8597|2025-06-01:12219|2025-07-01:17383|2025-08-01:21299|2025-09-01:27147|2025-10-01:32589|2025-11-01:37388|2025-12-01:48480|2026-01-01:2792|2026-02-01:4737|2026-03-01:7808|2026-04-01:9600|2026-05-01:11637|2026-06-01:15134","7417":"1999-01-01:256|1999-02-01:532|1999-03-01:1333|1999-04-01:1696|1999-05-01:2063|1999-06-01:2651|1999-07-01:3003|1999-08-01:3668|1999-09-01:4208|1999-10-01:4965|1999-11-01:6144|1999-12-01:8341|2000-01-01:427|2000-02-01:776|2000-03-01:1215|2000-04-01:1573|2000-05-01:1944|2000-06-01:2356|2000-07-01:4336|2000-08-01:4867|2000-09-01:5339|2000-10-01:5886|2000-11-01:8253|2000-12-01:10734|2001-01-01:301|2001-02-01:535|2001-03-01:1032|2001-04-01:1379|2001-05-01:1810|2001-06-01:2970|2001-07-01:3300|2001-08-01:5151|2001-09-01:5874|2001-10-01:6653|2001-11-01:7779|2001-12-01:9298|2002-01-01:509|2002-02-01:2046|2002-03-01:2791|2002-04-01:3379|2002-05-01:4030|2002-06-01:4426|2002-07-01:5457|2002-08-01:8277|2002-09-01:9927|2002-10-01:11426|2002-11-01:13102|2002-12-01:15482|2003-01-01:400|2003-02-01:1670|2003-03-01:2396|2003-04-01:2934|2003-05-01:3709|2003-06-01:4777|2003-07-01:6660|2003-08-01:7365|2003-09-01:8274|2003-10-01:9472|2003-11-01:10789|2003-12-01:12844|2004-01-01:520|2004-02-01:1533|2004-03-01:2598|2004-04-01:4474|2004-05-01:5344|2004-06-01:7318|2004-07-01:8653|2004-08-01:10893|2004-09-01:12955|2004-10-01:14769|2004-11-01:15878|2004-12-01:17135|2005-01-01:1196|2005-02-01:2349|2005-03-01:3423|2005-04-01:4472|2005-05-01:5908|2005-06-01:7381|2005-07-01:10266|2005-08-01:12284|2005-09-01:13272|2005-10-01:14702|2005-11-01:16403|2005-12-01:19551|2006-01-01:1446|2006-02-01:2288|2006-03-01:3295|2006-04-01:4595|2006-05-01:5855|2006-06-01:7758|2006-07-01:9331|2006-08-01:11022|2006-09-01:12401|2006-10-01:13982|2006-11-01:17533|2006-12-01:20775|2007-01-01:1506|2007-02-01:2517|2007-03-01:4669|2007-04-01:6297|2007-05-01:8309|2007-06-01:10977|2007-07-01:13553|2007-08-01:16517|2007-09-01:19903|2007-10-01:24937|2007-11-01:28515|2007-12-01:33448|2008-01-01:1861|2008-02-01:3814|2008-03-01:7519|2008-04-01:11751|2008-05-01:15787|2008-06-01:18969|2008-07-01:22723|2008-08-01:27099|2008-09-01:31370|2008-10-01:36871|2008-11-01:41113|2008-12-01:46262|2009-01-01:1959|2009-02-01:4187|2009-03-01:8873|2009-04-01:13085|2009-05-01:16859|2009-06-01:21494|2009-07-01:31306|2009-08-01:36499|2009-09-01:42167|2009-10-01:48522|2009-11-01:54227|2009-12-01:65979|2010-01-01:4672|2010-02-01:9017|2010-03-01:15009|2010-04-01:21517|2010-05-01:28525|2010-06-01:35842|2010-07-01:43173|2010-08-01:50558|2010-09-01:56034|2010-10-01:62901|2010-11-01:71302|2010-12-01:79528|2011-01-01:4716|2011-02-01:10177|2011-03-01:14997|2011-04-01:20316|2011-05-01:26065|2011-06-01:31958|2011-07-01:41467|2011-08-01:48534|2011-09-01:55927|2011-10-01:63278|2011-11-01:72369|2011-12-01:85265|2012-01-01:4589|2012-02-01:10415|2012-03-01:15811|2012-04-01:21617|2012-05-01:28448|2012-06-01:33804|2012-07-01:39555|2012-08-01:46283|2012-09-01:53645|2012-10-01:62260|2012-11-01:70445|2012-12-01:96944|2013-01-01:5159|2013-02-01:11280|2013-03-01:18763|2013-04-01:27655|2013-05-01:39115|2013-06-01:49751|2013-07-01:58047|2013-08-01:68312|2013-09-01:77309|2013-10-01:87367|2013-11-01:96583|2013-12-01:113741|2014-01-01:9283|2014-02-01:16760|2014-03-01:27071|2014-04-01:38084|2014-05-01:44812|2014-06-01:54328|2014-07-01:62564|2014-08-01:71453|2014-09-01:81971|2014-10-01:92086|2014-11-01:102819|2014-12-01:120996|2015-01-01:5811|2015-02-01:10821|2015-03-01:19269|2015-04-01:26119|2015-05-01:32676|2015-06-01:41084|2015-07-01:45622|2015-08-01:50624|2015-09-01:56470|2015-10-01:64086|2015-11-01:71712|2015-12-01:85354|2016-01-01:3259|2016-02-01:6241|2016-03-01:9462|2016-04-01:13856|2016-05-01:17535|2016-06-01:21631|2016-07-01:25610|2016-08-01:27752|2016-09-01:30889|2016-10-01:34086|2016-11-01:38475|2016-12-01:44217|2017-01-01:2499|2017-02-01:5763|2017-03-01:8584|2017-04-01:12557|2017-05-01:16324|2017-06-01:19631|2017-07-01:22972|2017-08-01:25389|2017-09-01:28442|2017-10-01:31229|2017-11-01:34638|2017-12-01:41331|2018-01-01:2501|2018-02-01:4225|2018-03-01:6718|2018-04-01:8948|2018-05-01:13821|2018-06-01:16883|2018-07-01:20451|2018-08-01:23837|2018-09-01:26077|2018-10-01:28077|2018-11-01:31643|2018-12-01:42339|2019-01-01:3380|2019-02-01:5862|2019-03-01:8351|2019-04-01:9719|2019-05-01:11965|2019-06-01:14034|2019-07-01:16427|2019-08-01:19909|2019-09-01:21506|2019-10-01:23523|2019-11-01:27817|2019-12-01:30628|2020-01-01:951|2020-02-01:2450|2020-03-01:4068|2020-04-01:7660|2020-05-01:11584|2020-06-01:16465|2020-07-01:21244|2020-08-01:24907|2020-09-01:27331|2020-10-01:29427|2020-11-01:31433|2020-12-01:35038|2021-01-01:1595|2021-02-01:3635|2021-03-01:7229|2021-04-01:9855|2021-05-01:12146|2021-06-01:15071|2021-07-01:18471|2021-08-01:22927|2021-09-01:27805|2021-10-01:30824|2021-11-01:33755|2021-12-01:37172|2022-01-01:2027|2022-02-01:5479|2022-03-01:8734|2022-04-01:11493|2022-05-01:16405|2022-06-01:20729|2022-07-01:23747|2022-08-01:32471|2022-09-01:35605|2022-10-01:40991|2022-11-01:47293|2022-12-01:56936|2023-01-01:3372|2023-02-01:5794|2023-03-01:9300|2023-04-01:14590|2023-05-01:18225|2023-06-01:24528|2023-07-01:28861|2023-08-01:35666|2023-09-01:40444|2023-10-01:51606|2023-11-01:57074|2023-12-01:64961|2024-01-01:5375|2024-02-01:8326|2024-03-01:14443|2024-04-01:19501|2024-05-01:23677|2024-06-01:28257|2024-07-01:35283|2024-08-01:42673|2024-09-01:48034|2024-10-01:56864|2024-11-01:66059|2024-12-01:72543|2025-01-01:4309|2025-02-01:11267|2025-03-01:13876|2025-04-01:19354|2025-05-01:23707|2025-06-01:28297|2025-07-01:35181|2025-08-01:41936|2025-09-01:49619|2025-10-01:58446|2025-11-01:71607|2025-12-01:83864|2026-01-01:4672|2026-02-01:10404|2026-03-01:19108|2026-04-01:27779|2026-05-01:32324|2026-06-01:41801","7418":"1999-01-01:89|1999-02-01:160|1999-03-01:297|1999-04-01:389|1999-05-01:496|1999-06-01:599|1999-07-01:731|1999-08-01:850|1999-09-01:943|1999-10-01:1042|1999-11-01:1151|1999-12-01:1286|2000-01-01:104|2000-02-01:193|2000-03-01:293|2000-04-01:406|2000-05-01:568|2000-06-01:744|2000-07-01:927|2000-08-01:1118|2000-09-01:1305|2000-10-01:1502|2000-11-01:1596|2000-12-01:1908|2001-01-01:188|2001-02-01:321|2001-03-01:519|2001-04-01:696|2001-05-01:895|2001-06-01:1158|2001-07-01:1439|2001-08-01:1641|2001-09-01:1906|2001-10-01:2168|2001-11-01:2454|2001-12-01:2762|2002-01-01:249|2002-02-01:501|2002-03-01:822|2002-04-01:1071|2002-05-01:1367|2002-06-01:1660|2002-07-01:2099|2002-08-01:2460|2002-09-01:2842|2002-10-01:3434|2002-11-01:3561|2002-12-01:4509|2003-01-01:154|2003-02-01:310|2003-03-01:561|2003-04-01:813|2003-05-01:1127|2003-06-01:1582|2003-07-01:2267|2003-08-01:2611|2003-09-01:3021|2003-10-01:3638|2003-11-01:4145|2003-12-01:4595|2004-01-01:600|2004-02-01:1092|2004-03-01:1570|2004-04-01:2097|2004-05-01:2508|2004-06-01:3195|2004-07-01:3911|2004-08-01:4340|2004-09-01:5034|2004-10-01:5652|2004-11-01:6349|2004-12-01:6930|2005-01-01:499|2005-02-01:837|2005-03-01:1216|2005-04-01:1544|2005-05-01:1750|2005-06-01:2220|2005-07-01:2594|2005-08-01:2750|2005-09-01:2962|2005-10-01:3222|2005-11-01:3568|2005-12-01:4059|2006-01-01:397|2006-02-01:670|2006-03-01:1030|2006-04-01:1225|2006-05-01:1514|2006-06-01:1760|2006-07-01:2019|2006-08-01:2139|2006-09-01:2324|2006-10-01:2609|2006-11-01:2942|2006-12-01:3423|2007-01-01:397|2007-02-01:634|2007-03-01:1105|2007-04-01:1493|2007-05-01:1979|2007-06-01:2453|2007-07-01:2998|2007-08-01:3215|2007-09-01:3461|2007-10-01:3985|2007-11-01:4432|2007-12-01:4998|2008-01-01:432|2008-02-01:771|2008-03-01:1267|2008-04-01:1764|2008-05-01:2260|2008-06-01:2841|2008-07-01:3406|2008-08-01:3640|2008-09-01:3874|2008-10-01:4329|2008-11-01:5063|2008-12-01:5594|2009-01-01:403|2009-02-01:687|2009-03-01:1148|2009-04-01:1729|2009-05-01:2382|2009-06-01:3133|2009-07-01:3723|2009-08-01:4190|2009-09-01:4826|2009-10-01:5393|2009-11-01:6112|2009-12-01:6856|2010-01-01:940|2010-02-01:1686|2010-03-01:2642|2010-04-01:3460|2010-05-01:4196|2010-06-01:4988|2010-07-01:5667|2010-08-01:6423|2010-09-01:7150|2010-10-01:8110|2010-11-01:9059|2010-12-01:10126|2011-01-01:850|2011-02-01:1508|2011-03-01:2118|2011-04-01:2814|2011-05-01:3579|2011-06-01:4906|2011-07-01:5686|2011-08-01:6452|2011-09-01:7224|2011-10-01:7983|2011-11-01:8798|2011-12-01:9759|2012-01-01:870|2012-02-01:1494|2012-03-01:2216|2012-04-01:3007|2012-05-01:3753|2012-06-01:4432|2012-07-01:5350|2012-08-01:6401|2012-09-01:7431|2012-10-01:8528|2012-11-01:9896|2012-12-01:11362|2013-01-01:1540|2013-02-01:3056|2013-03-01:4781|2013-04-01:6640|2013-05-01:8285|2013-06-01:9627|2013-07-01:10896|2013-08-01:12060|2013-09-01:13334|2013-10-01:14806|2013-11-01:16462|2013-12-01:18662|2014-01-01:2153|2014-02-01:3162|2014-03-01:4093|2014-04-01:5157|2014-05-01:6274|2014-06-01:7520|2014-07-01:8855|2014-08-01:10391|2014-09-01:11989|2014-10-01:13590|2014-11-01:14886|2014-12-01:16775|2015-01-01:1405|2015-02-01:2335|2015-03-01:3554|2015-04-01:4555|2015-05-01:5797|2015-06-01:7416|2015-07-01:8308|2015-08-01:9218|2015-09-01:10281|2015-10-01:11457|2015-11-01:12713|2015-12-01:13710|2016-01-01:1123|2016-02-01:2100|2016-03-01:3149|2016-04-01:4336|2016-05-01:5481|2016-06-01:6651|2016-07-01:7668|2016-08-01:8488|2016-09-01:9527|2016-10-01:10791|2016-11-01:12171|2016-12-01:13898|2017-01-01:1281|2017-02-01:2340|2017-03-01:3345|2017-04-01:4296|2017-05-01:5504|2017-06-01:6887|2017-07-01:8129|2017-08-01:9269|2017-09-01:10392|2017-10-01:11741|2017-11-01:13094|2017-12-01:14375|2018-01-01:936|2018-02-01:1652|2018-03-01:2718|2018-04-01:3669|2018-05-01:4727|2018-06-01:5764|2018-07-01:6722|2018-08-01:7986|2018-09-01:9384|2018-10-01:11453|2018-11-01:13132|2018-12-01:14660|2019-01-01:1402|2019-02-01:2510|2019-03-01:3539|2019-04-01:4597|2019-05-01:5710|2019-06-01:6357|2019-07-01:7188|2019-08-01:8517|2019-09-01:10198|2019-10-01:12316|2019-11-01:14464|2019-12-01:15870|2020-01-01:1091|2020-02-01:1935|2020-03-01:3004|2020-04-01:3705|2020-05-01:4505|2020-06-01:5211|2020-07-01:6158|2020-08-01:8050|2020-09-01:10391|2020-10-01:12924|2020-11-01:14937|2020-12-01:16620|2021-01-01:1028|2021-02-01:1786|2021-03-01:2653|2021-04-01:3296|2021-05-01:3997|2021-06-01:4633|2021-07-01:6261|2021-08-01:8765|2021-09-01:10976|2021-10-01:13259|2021-11-01:15063|2021-12-01:16721|2022-01-01:1066|2022-02-01:1961|2022-03-01:2754|2022-04-01:3394|2022-05-01:3887|2022-06-01:4532|2022-07-01:5654|2022-08-01:10745|2022-09-01:14830|2022-10-01:17563|2022-11-01:19491|2022-12-01:21471|2023-01-01:1045|2023-02-01:2217|2023-03-01:3673|2023-04-01:4471|2023-05-01:5219|2023-06-01:6980|2023-07-01:10357|2023-08-01:14376|2023-09-01:18204|2023-10-01:22553|2023-11-01:25286|2023-12-01:27557|2024-01-01:1736|2024-02-01:3238|2024-03-01:4837|2024-04-01:6277|2024-05-01:7782|2024-06-01:9809|2024-07-01:12192|2024-08-01:17360|2024-09-01:21330|2024-10-01:25541|2024-11-01:29605|2024-12-01:35065|2025-01-01:3104|2025-02-01:4919|2025-03-01:6499|2025-04-01:8249|2025-05-01:10885|2025-06-01:13923|2025-07-01:16974|2025-08-01:21398|2025-09-01:24942|2025-10-01:28749|2025-11-01:31664|2025-12-01:36679|2026-01-01:2590|2026-02-01:5784|2026-03-01:9111|2026-04-01:11609|2026-05-01:13735|2026-06-01:17509","7419":"1999-01-01:63|1999-02-01:63|1999-03-01:65|1999-04-01:66|1999-05-01:67|1999-06-01:76|1999-07-01:112|1999-08-01:150|1999-09-01:176|1999-10-01:178|1999-11-01:180|1999-12-01:258|2000-01-01:2|2000-02-01:4|2000-03-01:8|2000-04-01:11|2000-05-01:13|2000-06-01:17|2000-07-01:19|2000-08-01:56|2000-09-01:58|2000-10-01:96|2000-11-01:102|2000-12-01:121|2001-01-01:4|2001-02-01:13|2001-03-01:18|2001-04-01:20|2001-05-01:23|2001-06-01:26|2001-07-01:48|2001-08-01:55|2001-09-01:60|2001-10-01:75|2001-11-01:80|2001-12-01:396|2002-01-01:20|2002-02-01:22|2002-03-01:55|2002-04-01:63|2002-05-01:69|2002-06-01:82|2002-07-01:98|2002-08-01:103|2002-09-01:202|2002-10-01:208|2002-11-01:219|2002-12-01:250|2003-01-01:14|2003-02-01:18|2003-03-01:38|2003-04-01:44|2003-05-01:52|2003-06-01:62|2003-07-01:74|2003-08-01:82|2003-09-01:88|2003-10-01:93|2003-11-01:142|2003-12-01:157|2004-01-01:10|2004-02-01:31|2004-03-01:37|2004-04-01:79|2004-05-01:84|2004-06-01:157|2004-07-01:163|2004-08-01:167|2004-09-01:194|2004-10-01:206|2004-11-01:214|2004-12-01:243|2005-01-01:11|2005-02-01:20|2005-03-01:26|2005-04-01:58|2005-05-01:70|2005-06-01:99|2005-07-01:170|2005-08-01:194|2005-09-01:231|2005-10-01:242|2005-11-01:328|2005-12-01:338|2006-01-01:11|2006-02-01:18|2006-03-01:62|2006-04-01:110|2006-05-01:179|2006-06-01:256|2006-07-01:324|2006-08-01:367|2006-09-01:390|2006-10-01:477|2006-11-01:524|2006-12-01:1458|2007-01-01:524|2007-02-01:534|2007-03-01:553|2007-04-01:628|2007-05-01:651|2007-06-01:666|2007-07-01:688|2007-08-01:699|2007-09-01:718|2007-10-01:788|2007-11-01:804|2007-12-01:1050|2008-01-01:12|2008-02-01:118|2008-03-01:134|2008-04-01:818|2008-05-01:927|2008-06-01:945|2008-07-01:1761|2008-08-01:1791|2008-09-01:2035|2008-10-01:2177|2008-11-01:2255|2008-12-01:3311|2009-01-01:106|2009-02-01:136|2009-03-01:160|2009-04-01:822|2009-05-01:1427|2009-06-01:1842|2009-07-01:1866|2009-08-01:1891|2009-09-01:1926|2009-10-01:1959|2009-11-01:3189|2009-12-01:3219|2010-01-01:43|2010-02-01:156|2010-03-01:223|2010-04-01:317|2010-05-01:371|2010-06-01:424|2010-07-01:473|2010-08-01:847|2010-09-01:1085|2010-10-01:1184|2010-11-01:1256|2010-12-01:1514|2011-01-01:147|2011-02-01:745|2011-03-01:800|2011-04-01:889|2011-05-01:979|2011-06-01:1496|2011-07-01:1539|2011-08-01:2192|2011-09-01:2258|2011-10-01:2619|2011-11-01:2841|2011-12-01:3579|2012-01-01:50|2012-02-01:93|2012-03-01:289|2012-04-01:385|2012-05-01:510|2012-06-01:777|2012-07-01:912|2012-08-01:1018|2012-09-01:1157|2012-10-01:1223|2012-11-01:1319|2012-12-01:1825|2013-01-01:173|2013-02-01:267|2013-03-01:377|2013-04-01:526|2013-05-01:633|2013-06-01:930|2013-07-01:1018|2013-08-01:1391|2013-09-01:1560|2013-10-01:1654|2013-11-01:2377|2013-12-01:4056|2014-01-01:75|2014-02-01:204|2014-03-01:309|2014-04-01:683|2014-05-01:733|2014-06-01:809|2014-07-01:1008|2014-08-01:1426|2014-09-01:1619|2014-10-01:2474|2014-11-01:2690|2014-12-01:3027|2015-01-01:56|2015-02-01:512|2015-03-01:1080|2015-04-01:1114|2015-05-01:1270|2015-06-01:1608|2015-07-01:1622|2015-08-01:1642|2015-09-01:1668|2015-10-01:1693|2015-11-01:1711|2015-12-01:1725|2016-01-01:23|2016-02-01:34|2016-03-01:52|2016-04-01:333|2016-05-01:346|2016-06-01:763|2016-07-01:772|2016-08-01:785|2016-09-01:1049|2016-10-01:1056|2016-11-01:1062|2016-12-01:1533|2017-01-01:6|2017-02-01:11|2017-03-01:19|2017-04-01:36|2017-05-01:48|2017-06-01:53|2017-07-01:392|2017-08-01:404|2017-09-01:424|2017-10-01:651|2017-11-01:666|2017-12-01:680|2018-01-01:18|2018-02-01:40|2018-03-01:49|2018-04-01:60|2018-05-01:78|2018-06-01:97|2018-07-01:112|2018-08-01:144|2018-09-01:152|2018-10-01:162|2018-11-01:172|2018-12-01:180|2019-01-01:10|2019-02-01:13|2019-03-01:15|2019-04-01:19|2019-05-01:22|2019-06-01:31|2019-07-01:42|2019-08-01:53|2019-09-01:60|2019-10-01:69|2019-11-01:75|2019-12-01:79|2020-01-01:4|2020-02-01:9|2020-03-01:12|2020-04-01:27|2020-05-01:30|2020-06-01:64|2020-07-01:71|2020-08-01:82|2020-09-01:88|2020-10-01:325|2020-11-01:330|2020-12-01:590|2021-01-01:6|2021-02-01:15|2021-03-01:22|2021-04-01:34|2021-05-01:205|2021-06-01:317|2021-07-01:324|2021-08-01:342|2021-09-01:346|2021-10-01:356|2021-11-01:369|2021-12-01:384|2022-01-01:11|2022-02-01:20|2022-03-01:41|2022-04-01:68|2022-05-01:96|2022-06-01:125|2022-07-01:144|2022-08-01:156|2022-09-01:172|2022-10-01:181|2022-11-01:195|2022-12-01:224|2023-01-01:41|2023-02-01:55|2023-03-01:65|2023-04-01:80|2023-05-01:93|2023-06-01:107|2023-07-01:120|2023-08-01:129|2023-09-01:145|2023-10-01:159|2023-11-01:173|2023-12-01:224|2024-01-01:29|2024-02-01:41|2024-03-01:53|2024-04-01:101|2024-05-01:139|2024-06-01:186|2024-07-01:230|2024-08-01:258|2024-09-01:286|2024-10-01:299|2024-11-01:307|2024-12-01:328|2025-01-01:10|2025-02-01:55|2025-03-01:89|2025-04-01:101|2025-05-01:129|2025-06-01:148|2025-07-01:164|2025-08-01:171|2025-09-01:195|2025-10-01:245|2025-11-01:621|2025-12-01:673|2026-01-01:127|2026-02-01:134|2026-03-01:194|2026-04-01:213|2026-05-01:247|2026-06-01:317","10844":"1999-01-01:0.5|1999-02-01:-0.23|1999-03-01:0.25|1999-04-01:0.14|1999-05-01:0.12|1999-06-01:-0.01|1999-07-01:0.02|1999-08-01:0.08|1999-09-01:-0.07|1999-10-01:0|1999-11-01:0.13|1999-12-01:0.39|2000-01-01:0.66|2000-02-01:0.43|2000-03-01:-0.07|2000-04-01:1.27|2000-05-01:0.02|2000-06-01:0.09|2000-07-01:-0.01|2000-08-01:0.25|2000-09-01:0.15|2000-10-01:0.15|2000-11-01:0.11|2000-12-01:0.19|2001-01-01:0.41|2001-02-01:0.71|2001-03-01:0.19|2001-04-01:0.61|2001-05-01:0.46|2001-06-01:0.42|2001-07-01:0.84|2001-08-01:0.58|2001-09-01:0.36|2001-10-01:0.34|2001-11-01:0.3|2001-12-01:0.34|2002-01-01:0.29|2002-02-01:1.15|2002-03-01:0.32|2002-04-01:0.4|2002-05-01:0.48|2002-06-01:0.12|2002-07-01:0.65|2002-08-01:0.46|2002-09-01:0.44|2002-10-01:0.31|2002-11-01:0.86|2002-12-01:1.04|2003-01-01:0.99|2003-02-01:1.38|2003-03-01:0.66|2003-04-01:0.38|2003-05-01:0.51|2003-06-01:0.58|2003-07-01:0.59|2003-08-01:0.64|2003-09-01:0.37|2003-10-01:0.47|2003-11-01:0.42|2003-12-01:0.54|2004-01-01:0.61|2004-02-01:1.62|2004-03-01:0.61|2004-04-01:0.33|2004-05-01:0.32|2004-06-01:0.34|2004-07-01:0.53|2004-08-01:0.74|2004-09-01:0.24|2004-10-01:0.41|2004-11-01:0.4|2004-12-01:0.72|2005-01-01:0.53|2005-02-01:1.68|2005-03-01:0.59|2005-04-01:0.39|2005-05-01:0.35|2005-06-01:0.43|2005-07-01:0.57|2005-08-01:0.4|2005-09-01:0.47|2005-10-01:0.43|2005-11-01:0.5|2005-12-01:0.25|2006-01-01:0.79|2006-02-01:1.33|2006-03-01:0.36|2006-04-01:0.36|2006-05-01:0.37|2006-06-01:0.22|2006-07-01:0.31|2006-08-01:0.35|2006-09-01:0.31|2006-10-01:0.49|2006-11-01:0.24|2006-12-01:0.32|2007-01-01:0.53|2007-02-01:1.2|2007-03-01:0.37|2007-04-01:0.27|2007-05-01:0.34|2007-06-01:0.35|2007-07-01:0.21|2007-08-01:0.55|2007-09-01:0.28|2007-10-01:0.41|2007-11-01:0.49|2007-12-01:0.63|2008-01-01:0.57|2008-02-01:1.28|2008-03-01:0.42|2008-04-01:0.48|2008-05-01:0.73|2008-06-01:0.62|2008-07-01:0.59|2008-08-01:0.61|2008-09-01:0.65|2008-10-01:0.51|2008-11-01:0.46|2008-12-01:0.52|2009-01-01:0.69|2009-02-01:1.68|2009-03-01:0.19|2009-04-01:0.59|2009-05-01:0.54|2009-06-01:0.42|2009-07-01:0.34|2009-08-01:0.52|2009-09-01:0.37|2009-10-01:0.2|2009-11-01:0.45|2009-12-01:0.5|2010-01-01:0.69|2010-02-01:1.48|2010-03-01:0.68|2010-04-01:0.52|2010-05-01:0.69|2010-06-01:0.48|2010-07-01:0.32|2010-08-01:0.42|2010-09-01:0.43|2010-10-01:0.6|2010-11-01:0.65|2010-12-01:0.9|2011-01-01:0.91|2011-02-01:1.93|2011-03-01:0.86|2011-04-01:0.59|2011-05-01:0.67|2011-06-01:0.55|2011-07-01:0.53|2011-08-01:0.54|2011-09-01:0.52|2011-10-01:0.53|2011-11-01:0.63|2011-12-01:0.73|2012-01-01:1.05|2012-02-01:1.25|2012-03-01:0.52|2012-04-01:0.76|2012-05-01:0.21|2012-06-01:0.52|2012-07-01:0.79|2012-08-01:0.49|2012-09-01:0.51|2012-10-01:0.51|2012-11-01:0.82|2012-12-01:0.98|2013-01-01:0.92|2013-02-01:1.3|2013-03-01:0.26|2013-04-01:0.54|2013-05-01:0.56|2013-06-01:0.64|2013-07-01:0.64|2013-08-01:0.6|2013-09-01:0.63|2013-10-01:0.52|2013-11-01:0.65|2013-12-01:1.16|2014-01-01:0.47|2014-02-01:1.24|2014-03-01:1.09|2014-04-01:0.44|2014-05-01:0.3|2014-06-01:1.09|2014-07-01:-0.05|2014-08-01:0.59|2014-09-01:0.78|2014-10-01:0.43|2014-11-01:0.46|2014-12-01:1.2|2015-01-01:0.88|2015-02-01:1.07|2015-03-01:0.58|2015-04-01:0.73|2015-05-01:0.2|2015-06-01:0.79|2015-07-01:0.54|2015-08-01:0.32|2015-09-01:0.67|2015-10-01:0.62|2015-11-01:0.46|2015-12-01:0.97|2016-01-01:0.67|2016-02-01:1.05|2016-03-01:0.24|2016-04-01:0.58|2016-05-01:0.37|2016-06-01:0.33|2016-07-01:0.62|2016-08-01:0.58|2016-09-01:0.33|2016-10-01:0.47|2016-11-01:0.41|2016-12-01:0.65|2017-01-01:0.37|2017-02-01:0.84|2017-03-01:0.34|2017-04-01:0.49|2017-05-01:0.05|2017-06-01:0.43|2017-07-01:0.34|2017-08-01:0.01|2017-09-01:0.5|2017-10-01:0.37|2017-11-01:0.12|2017-12-01:0.6|2018-01-01:0.16|2018-02-01:0.74|2018-03-01:0.08|2018-04-01:0.03|2018-05-01:-0.09|2018-06-01:0.26|2018-07-01:0.68|2018-08-01:-0.16|2018-09-01:0.4|2018-10-01:0.17|2018-11-01:0.41|2018-12-01:0.62|2019-01-01:0.51|2019-02-01:0.39|2019-03-01:0.33|2019-04-01:0.32|2019-05-01:-0.11|2019-06-01:0.34|2019-07-01:0.46|2019-08-01:0.07|2019-09-01:0.05|2019-10-01:0.19|2019-11-01:0.2|2019-12-01:0.73|2020-01-01:0.28|2020-02-01:0.68|2020-03-01:-0.14|2020-04-01:0.25|2020-05-01:-0.45|2020-06-01:-0.26|2020-07-01:-0.1|2020-08-01:-0.47|2020-09-01:0.17|2020-10-01:0.55|2020-11-01:0.39|2020-12-01:0.83|2021-01-01:0.07|2021-02-01:0.55|2021-03-01:0.12|2021-04-01:0.05|2021-05-01:-0.15|2021-06-01:0.23|2021-07-01:0.67|2021-08-01:0.39|2021-09-01:0.63|2021-10-01:1.04|2021-11-01:0.27|2021-12-01:0.79|2022-01-01:0.39|2022-02-01:1.36|2022-03-01:0.45|2022-04-01:0.66|2022-05-01:0.85|2022-06-01:0.9|2022-07-01:0.8|2022-08-01:0.28|2022-09-01:0.4|2022-10-01:0.67|2022-11-01:0.13|2022-12-01:0.44|2023-01-01:0.6|2023-02-01:1.41|2023-03-01:0.25|2023-04-01:0.52|2023-05-01:-0.06|2023-06-01:0.62|2023-07-01:0.25|2023-08-01:0.08|2023-09-01:0.5|2023-10-01:0.59|2023-11-01:0.7|2023-12-01:0.6|2024-01-01:0.02|2024-02-01:1.06|2024-03-01:0.1|2024-04-01:0.05|2024-05-01:0.4|2024-06-01:0.04|2024-07-01:0.75|2024-08-01:0.24|2024-09-01:0.15|2024-10-01:0.35|2024-11-01:0.83|2024-12-01:0.66|2025-01-01:0.78|2025-02-01:0.82|2025-03-01:0.62|2025-04-01:0.2|2025-05-01:0.18|2025-06-01:0.4|2025-07-01:0.59|2025-08-01:0.39|2025-09-01:0.13|2025-10-01:0.41|2025-11-01:0.6|2025-12-01:0.72|2026-01-01:0.1|2026-02-01:1.51|2026-03-01:0.53|2026-04-01:0.04|2026-05-01:0.4|2026-06-01:0.33|2026-07-01:0.54|2026-08-01:0.03|2026-09-01:0.61","11752":"1999-01-01:93.04|1999-02-01:115.55|1999-03-01:112.06|1999-04-01:99.7|1999-05-01:98.35|1999-06-01:102.06|1999-07-01:102.97|1999-08-01:108.5|1999-09-01:109.72|1999-10-01:113.32|1999-11-01:108.98|1999-12-01:102.78|2000-01-01:100.17|2000-02-01:97.34|2000-03-01:95.28|2000-04-01:96.02|2000-05-01:97.52|2000-06-01:98.44|2000-07-01:95.77|2000-08-01:93.46|2000-09-01:94.05|2000-10-01:95.61|2000-11-01:99.08|2000-12-01:101.06|2001-01-01:100.36|2001-02-01:105.96|2001-03-01:109.46|2001-04-01:114.17|2001-05-01:119.14|2001-06-01:121.73|2001-07-01:124.71|2001-08-01:128.03|2001-09-01:136.35|2001-10-01:137.79|2001-11-01:126.16|2001-12-01:116.85|2002-01-01:111.75|2002-02-01:111.03|2002-03-01:106.76|2002-04-01:105.39|2002-05-01:112.89|2002-06-01:124.7|2002-07-01:136.62|2002-08-01:142.67|2002-09-01:152.25|2002-10-01:171.03|2002-11-01:158.26|2002-12-01:158.7|2003-01-01:149.36|2003-02-01:160.19|2003-03-01:152.85|2003-04-01:138.14|2003-05-01:133.03|2003-06-01:130.28|2003-07-01:129.2|2003-08-01:132.84|2003-09-01:129.62|2003-10-01:129.03|2003-11-01:130.76|2003-12-01:133.07|2004-01-01:130.93|2004-02-01:137.73|2004-03-01:135.51|2004-04-01:135.1|2004-05-01:142.57|2004-06-01:144.1|2004-07-01:139.4|2004-08-01:136.65|2004-09-01:131.58|2004-10-01:130.98|2004-11-01:129.05|2004-12-01:126.88|2005-01-01:124.02|2005-02-01:120.05|2005-03-01:125.3|2005-04-01:118.26|2005-05-01:111.64|2005-06-01:108.35|2005-07-01:106.38|2005-08-01:106.82|2005-09-01:104.03|2005-10-01:100.88|2005-11-01:97.21|2005-12-01:100.9|2006-01-01:100.68|2006-02-01:95.44|2006-03-01:95.29|2006-04-01:95.14|2006-05-01:99.31|2006-06-01:102.35|2006-07-01:100.12|2006-08-01:99.2|2006-09-01:99.14|2006-10-01:97.72|2006-11-01:98.62|2006-12-01:99.29|2007-01-01:97.85|2007-02-01:95.85|2007-03-01:96.14|2007-04-01:94.59|2007-05-01:92.5|2007-06-01:90.12|2007-07-01:88.84|2007-08-01:92.25|2007-09-01:89.92|2007-10-01:86.17|2007-11-01:86.19|2007-12-01:86.66|2008-01-01:86.19|2008-02-01:85.36|2008-03-01:86.32|2008-04-01:85.97|2008-05-01:84.12|2008-06-01:82.11|2008-07-01:81.06|2008-08-01:80.55|2008-09-01:87.61|2008-10-01:100.24|2008-11-01:100.66|2008-12-01:107.19|2009-01-01:101.33|2009-02-01:99.54|2009-03-01:97.4|2009-04-01:95.38|2009-05-01:89.91|2009-06-01:87.38|2009-07-01:86.38|2009-08-01:82.86|2009-09-01:82.13|2009-10-01:79.15|2009-11-01:79.27|2009-12-01:79.87|2010-01-01:79.59|2010-02-01:81.53|2010-03-01:78.75|2010-04-01:77.18|2010-05-01:77.66|2010-06-01:76.4|2010-07-01:76.44|2010-08-01:76.82|2010-09-01:75.57|2010-10-01:75.18|2010-11-01:75.74|2010-12-01:73.74|2011-01-01:73.19|2011-02-01:74.67|2011-03-01:74.77|2011-04-01:72.21|2011-05-01:73.42|2011-06-01:72.38|2011-07-01:71.76|2011-08-01:73.43|2011-09-01:78.12|2011-10-01:78.22|2011-11-01:78.06|2011-12-01:79.39|2012-01-01:76.75|2012-02-01:75.45|2012-03-01:79|2012-04-01:81.1|2012-05-01:85.53|2012-06-01:87|2012-07-01:85.92|2012-08-01:86.89|2012-09-01:87.63|2012-10-01:87.34|2012-11-01:87.99|2012-12-01:88.5|2013-01-01:86|2013-02-01:83.58|2013-03-01:82.97|2013-04-01:83.3|2013-05-01:84.33|2013-06-01:90.18|2013-07-01:93.45|2013-08-01:98.06|2013-09-01:94.79|2013-10-01:91.47|2013-11-01:94.71|2013-12-01:95.87|2014-01-01:95.6|2014-02-01:94.72|2014-03-01:91.68|2014-04-01:87.63|2014-05-01:86.9|2014-06-01:87.05|2014-07-01:87.49|2014-08-01:88.77|2014-09-01:89.59|2014-10-01:92.87|2014-11-01:94.97|2014-12-01:96.64|2015-01-01:93.33|2015-02-01:98.77|2015-03-01:106.96|2015-04-01:103.69|2015-05-01:104.13|2015-06-01:105.07|2015-07-01:108.32|2015-08-01:116.79|2015-09-01:129.34|2015-10-01:127.47|2015-11-01:121.97|2015-12-01:122.1|2016-01-01:122.64|2016-02-01:120.27|2016-03-01:112.65|2016-04-01:110.04|2016-05-01:108.67|2016-06-01:104.88|2016-07-01:99.55|2016-08-01:98.17|2016-09-01:99.1|2016-10-01:95.95|2016-11-01:98.84|2016-12-01:97.55|2017-01-01:93.08|2017-02-01:91.5|2017-03-01:92.12|2017-04-01:93.26|2017-05-01:95.64|2017-06-01:99.23|2017-07-01:97.45|2017-08-01:97.36|2017-09-01:97.51|2017-10-01:97.91|2017-11-01:99.87|2017-12-01:100.99|2018-01-01:99.48|2018-02-01:101.89|2018-03-01:102.57|2018-04-01:106.74|2018-05-01:110|2018-06-01:110.84|2018-07-01:111.84|2018-08-01:113.82|2018-09-01:116.32|2018-10-01:106.32|2018-11-01:106.72|2018-12-01:109.46|2019-01-01:106.18|2019-02-01:105.64|2019-03-01:107.76|2019-04-01:108.96|2019-05-01:110.69|2019-06-01:107.71|2019-07-01:106.95|2019-08-01:110.62|2019-09-01:112.63|2019-10-01:112.09|2019-11-01:113.51|2019-12-01:111.81|2020-01-01:113.2|2020-02-01:118.06|2020-03-01:131.08|2020-04-01:141.14|2020-05-01:149.83|2020-06-01:139.5|2020-07-01:144.2|2020-08-01:151.32|2020-09-01:148.88|2020-10-01:154.27|2020-11-01:148.41|2020-12-01:141|2021-01-01:147.01|2021-02-01:148.58|2021-03-01:152.43|2021-04-01:150.95|2021-05-01:144.11|2021-06-01:136.74|2021-07-01:139.21|2021-08-01:141|2021-09-01:140.07|2021-10-01:145.35|2021-11-01:144.1|2021-12-01:145.65|2022-01-01:142.57|2022-02-01:134.34|2022-03-01:126.99|2022-04-01:119.52|2022-05-01:122.21|2022-06-01:124.1|2022-07-01:132.68|2022-08-01:128.18|2022-09-01:128.54|2022-10-01:126.82|2022-11-01:128.07|2022-12-01:129.09|2023-01-01:130|2023-02-01:128.63|2023-03-01:128.04|2023-04-01:123.68|2023-05-01:121.49|2023-06-01:117.47|2023-07-01:118.04|2023-08-01:119.48|2023-09-01:118.73|2023-10-01:120.73|2023-11-01:118.13|2023-12-01:116.28|2024-01-01:114.9|2024-02-01:116.82|2024-03-01:117.4|2024-04-01:120.6|2024-05-01:120.73|2024-06-01:126.12|2024-07-01:131.54|2024-08-01:134.29|2024-09-01:133.7|2024-10-01:133.33|2024-11-01:134.64|2024-12-01:139.61|2025-01-01:136.7|2025-02-01:130.95|2025-03-01:131.04|2025-04-01:131.81|2025-05-01:129.87|2025-06-01:127.94|2025-07-01:128.91|2025-08-01:127.44|2025-09-01:124.76|2025-10-01:124.42|2025-11-01:122.71|2025-12-01:125.73|2026-01-01:123.49|2026-02-01:122.4|2026-03-01:121.38|2026-04-01:117.85|2026-05-01:116.2|2026-06-01:118.62|2026-07-01:119.67","11777":"1999-01-01:99.03|1999-02-01:76.51|1999-03-01:73.69|1999-04-01:82.51|1999-05-01:80.02|1999-06-01:76.5|1999-07-01:77.26|1999-08-01:72.39|1999-09-01:72.66|1999-10-01:72.01|1999-11-01:71.76|1999-12-01:73.2|2000-01-01:83.57|2000-02-01:77.32|2000-03-01:82.02|2000-04-01:81.08|2000-05-01:73.36|2000-06-01:74.2|2000-07-01:78.26|2000-08-01:74.68|2000-09-01:76.76|2000-10-01:75.19|2000-11-01:71.48|2000-12-01:65.95|2001-01-01:74.36|2001-02-01:71.1|2001-03-01:67.35|2001-04-01:66.75|2001-05-01:60.03|2001-06-01:61.9|2001-07-01:60.09|2001-08-01:58.19|2001-09-01:58.31|2001-10-01:56.01|2001-11-01:58.68|2001-12-01:63.71|2002-01-01:63.75|2002-02-01:61.51|2002-03-01:64.31|2002-04-01:62.95|2002-05-01:60.12|2002-06-01:57.15|2002-07-01:51.84|2002-08-01:49.13|2002-09-01:46.72|2002-10-01:39.6|2002-11-01:42.66|2002-12-01:40.54|2003-01-01:46.07|2003-02-01:43.91|2003-03-01:47.39|2003-04-01:53.04|2003-05-01:56.01|2003-06-01:60.21|2003-07-01:60.43|2003-08-01:57.47|2003-09-01:56.23|2003-10-01:57.3|2003-11-01:57.85|2003-12-01:53.27|2004-01-01:62.61|2004-02-01:61.49|2004-03-01:59.66|2004-04-01:60.75|2004-05-01:56.37|2004-06-01:56.86|2004-07-01:60.03|2004-08-01:59.97|2004-09-01:62.48|2004-10-01:65.26|2004-11-01:64.56|2004-12-01:62.78|2005-01-01:71.02|2005-02-01:73.89|2005-03-01:71.2|2005-04-01:72.75|2005-05-01:77.39|2005-06-01:77.03|2005-07-01:84|2005-08-01:82.06|2005-09-01:86.82|2005-10-01:90|2005-11-01:88.38|2005-12-01:77.26|2006-01-01:86.06|2006-02-01:91.73|2006-03-01:89.01|2006-04-01:94.15|2006-05-01:86.8|2006-06-01:87.81|2006-07-01:92.82|2006-08-01:91.25|2006-09-01:95.87|2006-10-01:98.87|2006-11-01:91.44|2006-12-01:84.72|2007-01-01:95.61|2007-02-01:99.7|2007-03-01:93.96|2007-04-01:101.85|2007-05-01:98.07|2007-06-01:104.3|2007-07-01:114.5|2007-08-01:102.86|2007-09-01:114.62|2007-10-01:117.76|2007-11-01:116.03|2007-12-01:107.98|2008-01-01:118.02|2008-02-01:120.37|2008-03-01:129.44|2008-04-01:124.59|2008-05-01:128.96|2008-06-01:131.77|2008-07-01:138|2008-08-01:142.23|2008-09-01:127.02|2008-10-01:108.24|2008-11-01:106.97|2008-12-01:103.69|2009-01-01:114.79|2009-02-01:117.06|2009-03-01:108.82|2009-04-01:115.13|2009-05-01:122.01|2009-06-01:125.48|2009-07-01:127.13|2009-08-01:130.98|2009-09-01:135.08|2009-10-01:139.45|2009-11-01:136.24|2009-12-01:119.01|2010-01-01:137.09|2010-02-01:134.26|2010-03-01:131.63|2010-04-01:137.25|2010-05-01:132.04|2010-06-01:138.35|2010-07-01:147.03|2010-08-01:143.15|2010-09-01:153.47|2010-10-01:162.66|2010-11-01:147.7|2010-12-01:134.99|2011-01-01:161.84|2011-02-01:156.45|2011-03-01:160.31|2011-04-01:172.79|2011-05-01:161.78|2011-06-01:173.07|2011-07-01:181.87|2011-08-01:176.72|2011-09-01:170.17|2011-10-01:169.27|2011-11-01:158.85|2011-12-01:138.42|2012-01-01:176.02|2012-02-01:179.9|2012-03-01:169.91|2012-04-01:170.34|2012-05-01:146.69|2012-06-01:153.17|2012-07-01:153.39|2012-08-01:147.73|2012-09-01:158.29|2012-10-01:152.94|2012-11-01:159.32|2012-12-01:145.67|2013-01-01:155.1|2013-02-01:174.1|2013-03-01:170.64|2013-04-01:156.41|2013-05-01:156.83|2013-06-01:152.11|2013-07-01:146.85|2013-08-01:135.02|2013-09-01:147.73|2013-10-01:150.97|2013-11-01:144.34|2013-12-01:136.79|2014-01-01:148.02|2014-02-01:148.7|2014-03-01:156.18|2014-04-01:159.26|2014-05-01:160.12|2014-06-01:168.55|2014-07-01:158.44|2014-08-01:154.11|2014-09-01:150.71|2014-10-01:144.8|2014-11-01:139.48|2014-12-01:127.93|2015-01-01:144.03|2015-02-01:140.52|2015-03-01:123.61|2015-04-01:129.2|2015-05-01:124.25|2015-06-01:125.61|2015-07-01:121.74|2015-08-01:108.75|2015-09-01:100.43|2015-10-01:101.54|2015-11-01:106.04|2015-12-01:97.09|2016-01-01:106.95|2016-02-01:107.56|2016-03-01:119.27|2016-04-01:120.66|2016-05-01:118.95|2016-06-01:119.74|2016-07-01:129.18|2016-08-01:127.62|2016-09-01:135.07|2016-10-01:140.49|2016-11-01:123.3|2016-12-01:109.93|2017-01-01:130.69|2017-02-01:135.34|2017-03-01:139.49|2017-04-01:144.33|2017-05-01:127.94|2017-06-01:127.79|2017-07-01:131.3|2017-08-01:129.83|2017-09-01:134.83|2017-10-01:135.2|2017-11-01:122.29|2017-12-01:107.92|2018-01-01:125.07|2018-02-01:131.48|2018-03-01:134.65|2018-04-01:123.95|2018-05-01:120.04|2018-06-01:107.39|2018-07-01:106.5|2018-08-01:101.53|2018-09-01:106.53|2018-10-01:115.17|2018-11-01:107.22|2018-12-01:100.72|2019-01-01:112.08|2019-02-01:112.81|2019-03-01:123.83|2019-04-01:115.23|2019-05-01:105.6|2019-06-01:114.07|2019-07-01:113.17|2019-08-01:103.33|2019-09-01:107.21|2019-10-01:105.89|2019-11-01:102.03|2019-12-01:95.64|2020-01-01:104.27|2020-02-01:98.94|2020-03-01:106.87|2020-04-01:110.13|2020-05-01:81.21|2020-06-01:87.08|2020-07-01:76.09|2020-08-01:76.53|2020-09-01:78.65|2020-10-01:77.63|2020-11-01:77.4|2020-12-01:71.57|2021-01-01:82.8|2021-02-01:81.68|2021-03-01:84.57|2021-04-01:87.18|2021-05-01:84.94|2021-06-01:91.9|2021-07-01:89.18|2021-08-01:88.08|2021-09-01:92.24|2021-10-01:92.58|2021-11-01:86.65|2021-12-01:75.71|2022-01-01:98.34|2022-02-01:101.11|2022-03-01:111.41|2022-04-01:117.08|2022-05-01:102.73|2022-06-01:104.82|2022-07-01:98.02|2022-08-01:99.69|2022-09-01:106.54|2022-10-01:110.25|2022-11-01:104.14|2022-12-01:97.29|2023-01-01:118.13|2023-02-01:118.37|2023-03-01:122.1|2023-04-01:131.24|2023-05-01:116.99|2023-06-01:126.15|2023-07-01:128.15|2023-08-01:121.35|2023-09-01:131.17|2023-10-01:130.95|2023-11-01:127.21|2023-12-01:118.5|2024-01-01:137.94|2024-02-01:133.42|2024-03-01:150.22|2024-04-01:135.47|2024-05-01:130.97|2024-06-01:125.79|2024-07-01:119.78|2024-08-01:119.59|2024-09-01:129.13|2024-10-01:127.38|2024-11-01:120.57|2024-12-01:107.22|2025-01-01:126.83|2025-02-01:129.64|2025-03-01:143.67|2025-04-01:137.84|2025-05-01:131.11|2025-06-01:141.44|2025-07-01:136.93|2025-08-01:140.22|2025-09-01:149.31|2025-10-01:151.98|2025-11-01:151.63|2025-12-01:137.28|2026-01-01:163.12|2026-02-01:165.28|2026-03-01:172.74|2026-04-01:176.14|2026-05-01:169.88|2026-06-01:171.86|2026-07-01:169.67","13521":"1999-01-01:8|2000-01-01:6|2001-01-01:4|2002-01-01:3.5|2003-01-01:4|2004-01-01:5.5|2005-01-01:4.5|2006-01-01:4.5|2007-01-01:4.5|2008-01-01:4.5|2009-01-01:4.5|2010-01-01:4.5|2011-01-01:4.5|2012-01-01:4.5|2013-01-01:4.5|2014-01-01:4.5|2015-01-01:4.5|2016-01-01:4.5|2017-01-01:4.5|2018-01-01:4.5|2019-01-01:4.25|2020-01-01:4|2021-01-01:3.75|2022-01-01:3.5|2023-01-01:3.25|2024-01-01:3|2025-01-01:3|2026-01-01:3","13522":"1999-01-01:1.65|1999-02-01:2.24|1999-03-01:3.02|1999-04-01:3.35|1999-05-01:3.14|1999-06-01:3.32|1999-07-01:4.57|1999-08-01:5.69|1999-09-01:6.25|1999-10-01:7.5|1999-11-01:8.65|1999-12-01:8.94|2000-01-01:8.85|2000-02-01:7.86|2000-03-01:6.92|2000-04-01:6.77|2000-05-01:6.47|2000-06-01:6.51|2000-07-01:7.06|2000-08-01:7.86|2000-09-01:7.77|2000-10-01:6.65|2000-11-01:5.99|2000-12-01:5.97|2001-01-01:5.92|2001-02-01:6.27|2001-03-01:6.44|2001-04-01:6.61|2001-05-01:7.04|2001-06-01:7.35|2001-07-01:7.05|2001-08-01:6.41|2001-09-01:6.46|2001-10-01:7.19|2001-11-01:7.61|2001-12-01:7.67|2002-01-01:7.62|2002-02-01:7.51|2002-03-01:7.75|2002-04-01:7.98|2002-05-01:7.77|2002-06-01:7.66|2002-07-01:7.51|2002-08-01:7.46|2002-09-01:7.93|2002-10-01:8.45|2002-11-01:10.93|2002-12-01:12.53|2003-01-01:14.47|2003-02-01:15.85|2003-03-01:16.57|2003-04-01:16.77|2003-05-01:17.24|2003-06-01:16.57|2003-07-01:15.43|2003-08-01:15.07|2003-09-01:15.14|2003-10-01:13.98|2003-11-01:11.02|2003-12-01:9.3|2004-01-01:7.71|2004-02-01:6.69|2004-03-01:5.89|2004-04-01:5.26|2004-05-01:5.15|2004-06-01:6.06|2004-07-01:6.81|2004-08-01:7.18|2004-09-01:6.7|2004-10-01:6.86|2004-11-01:7.24|2004-12-01:7.6|2005-01-01:7.41|2005-02-01:7.39|2005-03-01:7.54|2005-04-01:8.07|2005-05-01:8.05|2005-06-01:7.27|2005-07-01:6.57|2005-08-01:6.02|2005-09-01:6.04|2005-10-01:6.36|2005-11-01:6.22|2005-12-01:5.69|2006-01-01:5.7|2006-02-01:5.51|2006-03-01:5.32|2006-04-01:4.63|2006-05-01:4.23|2006-06-01:4.03|2006-07-01:3.97|2006-08-01:3.84|2006-09-01:3.7|2006-10-01:3.26|2006-11-01:3.02|2006-12-01:3.14|2007-01-01:2.99|2007-02-01:3.02|2007-03-01:2.96|2007-04-01:3|2007-05-01:3.18|2007-06-01:3.69|2007-07-01:3.74|2007-08-01:4.18|2007-09-01:4.15|2007-10-01:4.12|2007-11-01:4.19|2007-12-01:4.46|2008-01-01:4.56|2008-02-01:4.61|2008-03-01:4.73|2008-04-01:5.04|2008-05-01:5.58|2008-06-01:6.06|2008-07-01:6.37|2008-08-01:6.17|2008-09-01:6.25|2008-10-01:6.41|2008-11-01:6.39|2008-12-01:5.9|2009-01-01:5.84|2009-02-01:5.9|2009-03-01:5.61|2009-04-01:5.53|2009-05-01:5.2|2009-06-01:4.8|2009-07-01:4.5|2009-08-01:4.36|2009-09-01:4.34|2009-10-01:4.17|2009-11-01:4.22|2009-12-01:4.31|2010-01-01:4.59|2010-02-01:4.83|2010-03-01:5.17|2010-04-01:5.26|2010-05-01:5.22|2010-06-01:4.84|2010-07-01:4.6|2010-08-01:4.49|2010-09-01:4.7|2010-10-01:5.2|2010-11-01:5.63|2010-12-01:5.91|2011-01-01:5.99|2011-02-01:6.01|2011-03-01:6.3|2011-04-01:6.51|2011-05-01:6.55|2011-06-01:6.71|2011-07-01:6.87|2011-08-01:7.23|2011-09-01:7.31|2011-10-01:6.97|2011-11-01:6.64|2011-12-01:6.5|2012-01-01:6.22|2012-02-01:5.84|2012-03-01:5.24|2012-04-01:5.1|2012-05-01:4.99|2012-06-01:4.92|2012-07-01:5.2|2012-08-01:5.24|2012-09-01:5.28|2012-10-01:5.45|2012-11-01:5.53|2012-12-01:5.84|2013-01-01:6.15|2013-02-01:6.31|2013-03-01:6.59|2013-04-01:6.49|2013-05-01:6.5|2013-06-01:6.7|2013-07-01:6.27|2013-08-01:6.09|2013-09-01:5.86|2013-10-01:5.84|2013-11-01:5.77|2013-12-01:5.91|2014-01-01:5.59|2014-02-01:5.68|2014-03-01:6.15|2014-04-01:6.28|2014-05-01:6.37|2014-06-01:6.52|2014-07-01:6.5|2014-08-01:6.51|2014-09-01:6.75|2014-10-01:6.59|2014-11-01:6.56|2014-12-01:6.41|2015-01-01:7.14|2015-02-01:7.7|2015-03-01:8.13|2015-04-01:8.17|2015-05-01:8.47|2015-06-01:8.89|2015-07-01:9.56|2015-08-01:9.53|2015-09-01:9.49|2015-10-01:9.93|2015-11-01:10.48|2015-12-01:10.67|2016-01-01:10.71|2016-02-01:10.36|2016-03-01:9.39|2016-04-01:9.28|2016-05-01:9.32|2016-06-01:8.84|2016-07-01:8.74|2016-08-01:8.97|2016-09-01:8.48|2016-10-01:7.87|2016-11-01:6.99|2016-12-01:6.29|2017-01-01:5.35|2017-02-01:4.76|2017-03-01:4.57|2017-04-01:4.08|2017-05-01:3.6|2017-06-01:3|2017-07-01:2.71|2017-08-01:2.46|2017-09-01:2.54|2017-10-01:2.7|2017-11-01:2.8|2017-12-01:2.95|2018-01-01:2.86|2018-02-01:2.84|2018-03-01:2.68|2018-04-01:2.76|2018-05-01:2.86|2018-06-01:4.39|2018-07-01:4.48|2018-08-01:4.19|2018-09-01:4.53|2018-10-01:4.56|2018-11-01:4.05|2018-12-01:3.75|2019-01-01:3.78|2019-02-01:3.89|2019-03-01:4.58|2019-04-01:4.94|2019-05-01:4.66|2019-06-01:3.37|2019-07-01:3.22|2019-08-01:3.43|2019-09-01:2.89|2019-10-01:2.54|2019-11-01:3.27|2019-12-01:4.31|2020-01-01:4.19|2020-02-01:4.01|2020-03-01:3.3|2020-04-01:2.4|2020-05-01:1.88|2020-06-01:2.13|2020-07-01:2.31|2020-08-01:2.44|2020-09-01:3.14|2020-10-01:3.92|2020-11-01:4.31|2020-12-01:4.52|2021-01-01:4.56|2021-02-01:5.2|2021-03-01:6.1|2021-04-01:6.76|2021-05-01:8.06|2021-06-01:8.35|2021-07-01:8.99|2021-08-01:9.68|2021-09-01:10.25|2021-10-01:10.67|2021-11-01:10.74|2021-12-01:10.06|2022-01-01:10.38|2022-02-01:10.54|2022-03-01:11.3|2022-04-01:12.13|2022-05-01:11.73|2022-06-01:11.89|2022-07-01:10.07|2022-08-01:8.73|2022-09-01:7.17|2022-10-01:6.47|2022-11-01:5.9|2022-12-01:5.79|2023-01-01:5.77|2023-02-01:5.6|2023-03-01:4.65|2023-04-01:4.18|2023-05-01:3.94|2023-06-01:3.16|2023-07-01:3.99|2023-08-01:4.61|2023-09-01:5.19|2023-10-01:4.82|2023-11-01:4.68|2023-12-01:4.62|2024-01-01:4.51|2024-02-01:4.5|2024-03-01:3.93|2024-04-01:3.69|2024-05-01:3.93|2024-06-01:4.23|2024-07-01:4.5|2024-08-01:4.24|2024-09-01:4.42|2024-10-01:4.76|2024-11-01:4.87|2024-12-01:4.83|2025-01-01:4.56|2025-02-01:5.06|2025-03-01:5.48|2025-04-01:5.53|2025-05-01:5.32|2025-06-01:5.35|2025-07-01:5.23|2025-08-01:5.13|2025-09-01:5.17|2025-10-01:4.68|2025-11-01:4.46|2025-12-01:4.26|2026-01-01:4.44|2026-02-01:3.81|2026-03-01:4.14|2026-04-01:4.39|2026-05-01:4.72|2026-06-01:4.64|2026-07-01:4.44|2026-08-01:4.22|2026-09-01:4.58","20622":"1999-01-01:28.45|1999-02-01:28.59|1999-03-01:27.63|1999-04-01:27.21|1999-05-01:27.26|1999-06-01:27.09|1999-07-01:27.17|1999-08-01:27.23|1999-09-01:27.4|1999-10-01:27.66|1999-11-01:27.6|1999-12-01:26.52|2000-01-01:26.31|2000-02-01:25.9|2000-03-01:25.68|2000-04-01:26.09|2000-05-01:27.7|2000-06-01:26.98|2000-07-01:26.94|2000-08-01:26.67|2000-09-01:26.32|2000-10-01:26.43|2000-11-01:26.91|2000-12-01:27.26|2001-01-01:27.02|2001-02-01:27.51|2001-03-01:27.86|2001-04-01:27.95|2001-05-01:28.17|2001-06-01:25.25|2001-07-01:25.5|2001-08-01:25.93|2001-09-01:26.42|2001-10-01:26.46|2001-11-01:26.36|2001-12-01:25.57|2002-01-01:25.48|2002-02-01:25.46|2002-03-01:25.36|2002-04-01:25.37|2002-05-01:25.51|2002-06-01:25.74|2002-07-01:25.94|2002-08-01:25.33|2002-09-01:26.58|2002-10-01:26.05|2002-11-01:25.95|2002-12-01:25.82|2003-01-01:25.6|2003-02-01:25.51|2003-03-01:25.07|2003-04-01:24.5|2003-05-01:24.44|2003-06-01:24.36|2003-07-01:24.17|2003-08-01:24.08|2003-09-01:24.02|2003-10-01:24|2003-11-01:24.32|2003-12-01:24.35|2004-01-01:24.08|2004-02-01:24.12|2004-03-01:23.98|2004-04-01:24.42|2004-05-01:24.72|2004-06-01:24.77|2004-07-01:24.69|2004-08-01:24.76|2004-09-01:25.01|2004-10-01:25.51|2004-11-01:25.51|2004-12-01:25.47|2005-01-01:25.58|2005-02-01:25.64|2005-03-01:25.85|2005-04-01:26.09|2005-05-01:26.05|2005-06-01:26.2|2005-07-01:26.39|2005-08-01:26.58|2005-09-01:26.7|2005-10-01:27.01|2005-11-01:27.43|2005-12-01:27.97|2006-01-01:27.79|2006-02-01:27.89|2006-03-01:28.12|2006-04-01:28.51|2006-05-01:28.99|2006-06-01:28.99|2006-07-01:29.19|2006-08-01:29.12|2006-09-01:29.29|2006-10-01:29.53|2006-11-01:30.04|2006-12-01:30.4|2007-01-01:30.33|2007-02-01:30.44|2007-03-01:30.66|2007-04-01:31.06|2007-05-01:31.16|2007-06-01:31.28|2007-07-01:31.68|2007-08-01:32.34|2007-09-01:32.67|2007-10-01:33.22|2007-11-01:34.05|2007-12-01:34.7|2008-01-01:34.71|2008-02-01:34.84|2008-03-01:35.76|2008-04-01:36.22|2008-05-01:36.81|2008-06-01:37.14|2008-07-01:37.22|2008-08-01:37.63|2008-09-01:38.43|2008-10-01:38.99|2008-11-01:39.36|2008-12-01:39.68|2009-01-01:39.57|2009-02-01:39.42|2009-03-01:39.58|2009-04-01:39.65|2009-05-01:39.88|2009-06-01:40.24|2009-07-01:41.07|2009-08-01:41.51|2009-09-01:41.92|2009-10-01:42.19|2009-11-01:42.36|2009-12-01:42.62|2010-01-01:42.42|2010-02-01:42.23|2010-03-01:42.1|2010-04-01:41.98|2010-05-01:42.3|2010-06-01:42.63|2010-07-01:42.62|2010-08-01:42.96|2010-09-01:43.25|2010-10-01:43.57|2010-11-01:43.88|2010-12-01:44.08|2011-01-01:43.74|2011-02-01:43.78|2011-03-01:43.82|2011-04-01:43.94|2011-05-01:44.08|2011-06-01:44.25|2011-07-01:44.36|2011-08-01:44.69|2011-09-01:45.3|2011-10-01:45.3|2011-11-01:45.83|2011-12-01:46.48|2012-01-01:46.07|2012-02-01:45.88|2012-03-01:46.31|2012-04-01:46.6|2012-05-01:47.04|2012-06-01:47.43|2012-07-01:47.39|2012-08-01:47.52|2012-09-01:47.72|2012-10-01:47.91|2012-11-01:48.28|2012-12-01:49.19|2013-01-01:48.76|2013-02-01:48.81|2013-03-01:49.33|2013-04-01:49.17|2013-05-01:49.55|2013-06-01:50.04|2013-07-01:49.88|2013-08-01:50.17|2013-09-01:50.11|2013-10-01:49.82|2013-11-01:50.22|2013-12-01:50.84|2014-01-01:50.49|2014-02-01:50.17|2014-03-01:50.26|2014-04-01:50.3|2014-05-01:50.42|2014-06-01:50.66|2014-07-01:50.46|2014-08-01:50.67|2014-09-01:50.96|2014-10-01:51.07|2014-11-01:51.47|2014-12-01:52.22|2015-01-01:52.1|2015-02-01:52.2|2015-03-01:52.5|2015-04-01:52.33|2015-05-01:52.6|2015-06-01:52.63|2015-07-01:52.6|2015-08-01:52.87|2015-09-01:53.3|2015-10-01:53.07|2015-11-01:53.27|2015-12-01:53.85|2016-01-01:53.41|2016-02-01:52.95|2016-03-01:52.48|2016-04-01:51.95|2016-05-01:51.85|2016-06-01:51.3|2016-07-01:50.96|2016-08-01:50.7|2016-09-01:50.44|2016-10-01:50.03|2016-11-01:49.92|2016-12-01:49.71|2017-01-01:48.96|2017-02-01:48.76|2017-03-01:48.62|2017-04-01:48.36|2017-05-01:48.01|2017-06-01:48.05|2017-07-01:47.47|2017-08-01:47.26|2017-09-01:47.12|2017-10-01:46.99|2017-11-01:46.96|2017-12-01:47.12|2018-01-01:46.45|2018-02-01:46.14|2018-03-01:46.25|2018-04-01:46.05|2018-05-01:46.16|2018-06-01:46.19|2018-07-01:45.83|2018-08-01:46|2018-09-01:46.01|2018-10-01:45.66|2018-11-01:45.99|2018-12-01:46.59|2019-01-01:46.03|2019-02-01:45.94|2019-03-01:46.22|2019-04-01:46.05|2019-05-01:45.97|2019-06-01:46.03|2019-07-01:45.7|2019-08-01:46.01|2019-09-01:46.24|2019-10-01:46.17|2019-11-01:46.56|2019-12-01:47.04|2020-01-01:46.67|2020-02-01:46.67|2020-03-01:47.78|2020-04-01:48.07|2020-05-01:48.49|2020-06-01:48.8|2020-07-01:49.36|2020-08-01:50.27|2020-09-01:51.13|2020-10-01:51.73|2020-11-01:52.48|2020-12-01:52.85|2021-01-01:52.36|2021-02-01:52.11|2021-03-01:52|2021-04-01:51.16|2021-05-01:50.81|2021-06-01:50.47|2021-07-01:50.43|2021-08-01:50.53|2021-09-01:50.96|2021-10-01:51.19|2021-11-01:51.53|2021-12-01:51.96|2022-01-01:51.7|2022-02-01:51.94|2022-03-01:52.26|2022-04-01:52.15|2022-05-01:52.13|2022-06-01:52.33|2022-07-01:52.12|2022-08-01:52.3|2022-09-01:52.73|2022-10-01:52.68|2022-11-01:52.88|2022-12-01:53.24|2023-01-01:52.85|2023-02-01:52.43|2023-03-01:52.46|2023-04-01:52.08|2023-05-01:51.99|2023-06-01:51.93|2023-07-01:51.73|2023-08-01:52.14|2023-09-01:52.48|2023-10-01:52.39|2023-11-01:52.52|2023-12-01:53.05|2024-01-01:52.56|2024-02-01:52.41|2024-03-01:53.02|2024-04-01:52.77|2024-05-01:52.86|2024-06-01:53.31|2024-07-01:53.09|2024-08-01:53.34|2024-09-01:53.68|2024-10-01:53.76|2024-11-01:54.27|2024-12-01:54.88|2025-01-01:54.58|2025-02-01:54.55|2025-03-01:54.63|2025-04-01:54.59|2025-05-01:54.51|2025-06-01:54.48|2025-07-01:54.38|2025-08-01:54.45|2025-09-01:54.71|2025-10-01:55|2025-11-01:55.35|2025-12-01:56.03|2026-01-01:55.67|2026-02-01:55.64|2026-03-01:55.85|2026-04-01:55.68|2026-05-01:55.73|2026-06-01:55.75|2026-07-01:55.52|2026-08-01:55.45","21082":"2011-03-01:3.17|2011-04-01:3.24|2011-05-01:3.37|2011-06-01:3.32|2011-07-01:3.42|2011-08-01:3.45|2011-09-01:3.46|2011-10-01:3.58|2011-11-01:3.58|2011-12-01:3.54|2012-01-01:3.66|2012-02-01:3.71|2012-03-01:3.67|2012-04-01:3.76|2012-05-01:3.76|2012-06-01:3.71|2012-07-01:3.72|2012-08-01:3.75|2012-09-01:3.72|2012-10-01:3.76|2012-11-01:3.67|2012-12-01:3.55|2013-01-01:3.55|2013-02-01:3.53|2013-03-01:3.46|2013-04-01:3.48|2013-05-01:3.48|2013-06-01:3.26|2013-07-01:3.22|2013-08-01:3.14|2013-09-01:3.15|2013-10-01:3.07|2013-11-01:2.98|2013-12-01:2.87|2014-01-01:2.86|2014-02-01:2.88|2014-03-01:2.91|2014-04-01:2.95|2014-05-01:3.02|2014-06-01:2.93|2014-07-01:2.98|2014-08-01:3.01|2014-09-01:2.94|2014-10-01:2.99|2014-11-01:2.88|2014-12-01:2.76|2015-01-01:2.85|2015-02-01:2.89|2015-03-01:2.85|2015-04-01:2.99|2015-05-01:3.06|2015-06-01:2.96|2015-07-01:3.07|2015-08-01:3.16|2015-09-01:3.16|2015-10-01:3.28|2015-11-01:3.42|2015-12-01:3.42|2016-01-01:3.52|2016-02-01:3.55|2016-03-01:3.58|2016-04-01:3.71|2016-05-01:3.79|2016-06-01:3.57|2016-07-01:3.61|2016-08-01:3.69|2016-09-01:3.74|2016-10-01:3.9|2016-11-01:3.86|2016-12-01:3.75|2017-01-01:3.79|2017-02-01:3.82|2017-03-01:3.91|2017-04-01:4|2017-05-01:4.11|2017-06-01:3.8|2017-07-01:3.75|2017-08-01:3.76|2017-09-01:3.66|2017-10-01:3.69|2017-11-01:3.6|2017-12-01:3.29|2018-01-01:3.48|2018-02-01:3.49|2018-03-01:3.35|2018-04-01:3.38|2018-05-01:3.37|2018-06-01:3.11|2018-07-01:3.08|2018-08-01:3.1|2018-09-01:3.11|2018-10-01:3.11|2018-11-01:3.02|2018-12-01:2.93|2019-01-01:3.01|2019-02-01:2.96|2019-03-01:3.04|2019-04-01:3.07|2019-05-01:3.1|2019-06-01:2.99|2019-07-01:3.1|2019-08-01:3.1|2019-09-01:3.11|2019-10-01:3.09|2019-11-01:3.06|2019-12-01:2.99|2020-01-01:3.06|2020-02-01:3.1|2020-03-01:3.24|2020-04-01:3.36|2020-05-01:3.31|2020-06-01:2.95|2020-07-01:2.82|2020-08-01:2.7|2020-09-01:2.47|2020-10-01:2.4|2020-11-01:2.27|2020-12-01:2.16|2021-01-01:2.19|2021-02-01:2.28|2021-03-01:2.18|2021-04-01:2.24|2021-05-01:2.39|2021-06-01:2.32|2021-07-01:2.36|2021-08-01:2.37|2021-09-01:2.34|2021-10-01:2.33|2021-11-01:2.36|2021-12-01:2.35|2022-01-01:2.51|2022-02-01:2.57|2022-03-01:2.66|2022-04-01:2.72|2022-05-01:2.79|2022-06-01:2.73|2022-07-01:2.84|2022-08-01:2.9|2022-09-01:2.92|2022-10-01:3.04|2022-11-01:3.07|2022-12-01:3.07|2023-01-01:3.24|2023-02-01:3.36|2023-03-01:3.35|2023-04-01:3.54|2023-05-01:3.65|2023-06-01:3.61|2023-07-01:3.63|2023-08-01:3.61|2023-09-01:3.54|2023-10-01:3.56|2023-11-01:3.53|2023-12-01:3.29|2024-01-01:3.38|2024-02-01:3.38|2024-03-01:3.33|2024-04-01:3.37|2024-05-01:3.43|2024-06-01:3.29|2024-07-01:3.3|2024-08-01:3.33|2024-09-01:3.34|2024-10-01:3.3|2024-11-01:3.27|2024-12-01:3.08|2025-01-01:3.34|2025-02-01:3.41|2025-03-01:3.44|2025-04-01:3.67|2025-05-01:3.72|2025-06-01:3.75|2025-07-01:3.96|2025-08-01:4.14|2025-09-01:4.09|2025-10-01:4.18|2025-11-01:4.24|2025-12-01:4.2|2026-01-01:4.44|2026-02-01:4.64|2026-03-01:4.52|2026-04-01:4.64|2026-05-01:4.75|2026-06-01:4.58|2026-07-01:4.88|2026-08-01:5.04","21083":"2011-03-01:1.96|2011-04-01:2.04|2011-05-01:2.15|2011-06-01:2.09|2011-07-01:2.18|2011-08-01:2.15|2011-09-01:2.14|2011-10-01:2.23|2011-11-01:2.2|2011-12-01:2.15|2012-01-01:2.22|2012-02-01:2.27|2012-03-01:2.24|2012-04-01:2.37|2012-05-01:2.29|2012-06-01:2.27|2012-07-01:2.28|2012-08-01:2.35|2012-09-01:2.31|2012-10-01:2.43|2012-11-01:2.38|2012-12-01:2.26|2013-01-01:2.28|2013-02-01:2.28|2013-03-01:2.21|2013-04-01:2.31|2013-05-01:2.28|2013-06-01:2.11|2013-07-01:2.07|2013-08-01:2.01|2013-09-01:2.02|2013-10-01:2.03|2013-11-01:1.95|2013-12-01:1.84|2014-01-01:1.83|2014-02-01:1.88|2014-03-01:1.88|2014-04-01:1.92|2014-05-01:2|2014-06-01:1.97|2014-07-01:2.01|2014-08-01:2.06|2014-09-01:2.03|2014-10-01:2.08|2014-11-01:2|2014-12-01:1.92|2015-01-01:2.02|2015-02-01:2.03|2015-03-01:2.1|2015-04-01:2.28|2015-05-01:2.31|2015-06-01:2.3|2015-07-01:2.41|2015-08-01:2.48|2015-09-01:2.43|2015-10-01:2.53|2015-11-01:2.68|2015-12-01:2.66|2016-01-01:2.77|2016-02-01:2.83|2016-03-01:2.9|2016-04-01:3.1|2016-05-01:3.24|2016-06-01:3.06|2016-07-01:3.09|2016-08-01:3.23|2016-09-01:3.25|2016-10-01:3.58|2016-11-01:3.56|2016-12-01:3.5|2017-01-01:3.53|2017-02-01:3.57|2017-03-01:3.76|2017-04-01:3.89|2017-05-01:4.06|2017-06-01:3.68|2017-07-01:3.47|2017-08-01:3.52|2017-09-01:3.36|2017-10-01:3.42|2017-11-01:3.34|2017-12-01:2.97|2018-01-01:3.13|2018-02-01:3.17|2018-03-01:2.94|2018-04-01:3.03|2018-05-01:3.04|2018-06-01:2.61|2018-07-01:2.51|2018-08-01:2.56|2018-09-01:2.66|2018-10-01:2.72|2018-11-01:2.61|2018-12-01:2.47|2019-01-01:2.53|2019-02-01:2.46|2019-03-01:2.55|2019-04-01:2.63|2019-05-01:2.63|2019-06-01:2.45|2019-07-01:2.57|2019-08-01:2.51|2019-09-01:2.45|2019-10-01:2.41|2019-11-01:2.33|2019-12-01:2.21|2020-01-01:2.26|2020-02-01:2.23|2020-03-01:2.22|2020-04-01:2.35|2020-05-01:2.36|2020-06-01:2.02|2020-07-01:1.92|2020-08-01:1.87|2020-09-01:1.58|2020-10-01:1.51|2020-11-01:1.33|2020-12-01:1.24|2021-01-01:1.25|2021-02-01:1.4|2021-03-01:1.25|2021-04-01:1.33|2021-05-01:1.57|2021-06-01:1.54|2021-07-01:1.58|2021-08-01:1.56|2021-09-01:1.43|2021-10-01:1.43|2021-11-01:1.46|2021-12-01:1.4|2022-01-01:1.46|2022-02-01:1.44|2022-03-01:1.55|2022-04-01:1.57|2022-05-01:1.57|2022-06-01:1.52|2022-07-01:1.6|2022-08-01:1.62|2022-09-01:1.65|2022-10-01:1.77|2022-11-01:1.81|2022-12-01:1.8|2023-01-01:1.94|2023-02-01:2.17|2023-03-01:2.2|2023-04-01:2.45|2023-05-01:2.58|2023-06-01:2.63|2023-07-01:2.73|2023-08-01:2.82|2023-09-01:2.82|2023-10-01:2.92|2023-11-01:2.99|2023-12-01:2.59|2024-01-01:2.77|2024-02-01:2.76|2024-03-01:2.71|2024-04-01:2.76|2024-05-01:2.8|2024-06-01:2.64|2024-07-01:2.52|2024-08-01:2.55|2024-09-01:2.56|2024-10-01:2.52|2024-11-01:2.5|2024-12-01:2.21|2025-01-01:2.43|2025-02-01:2.52|2025-03-01:2.49|2025-04-01:2.72|2025-05-01:2.67|2025-06-01:2.67|2025-07-01:2.79|2025-08-01:2.85|2025-09-01:2.77|2025-10-01:2.82|2025-11-01:2.75|2025-12-01:2.7|2026-01-01:2.87|2026-02-01:3.07|2026-03-01:3.06|2026-04-01:3.15|2026-05-01:3.25|2026-06-01:3.18|2026-07-01:3.32|2026-08-01:3.35","21084":"2011-03-01:4.62|2011-04-01:4.67|2011-05-01:4.82|2011-06-01:4.79|2011-07-01:4.9|2011-08-01:4.97|2011-09-01:5.03|2011-10-01:5.17|2011-11-01:5.22|2011-12-01:5.22|2012-01-01:5.36|2012-02-01:5.4|2012-03-01:5.36|2012-04-01:5.41|2012-05-01:5.51|2012-06-01:5.43|2012-07-01:5.42|2012-08-01:5.4|2012-09-01:5.41|2012-10-01:5.34|2012-11-01:5.21|2012-12-01:5.1|2013-01-01:5.04|2013-02-01:5|2013-03-01:4.95|2013-04-01:4.86|2013-05-01:4.9|2013-06-01:4.62|2013-07-01:4.57|2013-08-01:4.46|2013-09-01:4.45|2013-10-01:4.26|2013-11-01:4.16|2013-12-01:4.09|2014-01-01:4.05|2014-02-01:4.03|2014-03-01:4.08|2014-04-01:4.13|2014-05-01:4.19|2014-06-01:4.01|2014-07-01:4.08|2014-08-01:4.07|2014-09-01:3.97|2014-10-01:4.01|2014-11-01:3.87|2014-12-01:3.7|2015-01-01:3.78|2015-02-01:3.85|2015-03-01:3.71|2015-04-01:3.79|2015-05-01:3.89|2015-06-01:3.7|2015-07-01:3.81|2015-08-01:3.92|2015-09-01:3.99|2015-10-01:4.12|2015-11-01:4.24|2015-12-01:4.27|2016-01-01:4.34|2016-02-01:4.35|2016-03-01:4.3|2016-04-01:4.35|2016-05-01:4.37|2016-06-01:4.1|2016-07-01:4.15|2016-08-01:4.17|2016-09-01:4.23|2016-10-01:4.23|2016-11-01:4.15|2016-12-01:4|2017-01-01:4.04|2017-02-01:4.06|2017-03-01:4.06|2017-04-01:4.09|2017-05-01:4.16|2017-06-01:3.91|2017-07-01:4.01|2017-08-01:3.99|2017-09-01:3.93|2017-10-01:3.93|2017-11-01:3.83|2017-12-01:3.58|2018-01-01:3.78|2018-02-01:3.76|2018-03-01:3.7|2018-04-01:3.68|2018-05-01:3.64|2018-06-01:3.52|2018-07-01:3.56|2018-08-01:3.55|2018-09-01:3.47|2018-10-01:3.43|2018-11-01:3.35|2018-12-01:3.3|2019-01-01:3.39|2019-02-01:3.35|2019-03-01:3.41|2019-04-01:3.41|2019-05-01:3.46|2019-06-01:3.4|2019-07-01:3.49|2019-08-01:3.53|2019-09-01:3.6|2019-10-01:3.58|2019-11-01:3.59|2019-12-01:3.56|2020-01-01:3.63|2020-02-01:3.72|2020-03-01:4|2020-04-01:4.13|2020-05-01:4.04|2020-06-01:3.67|2020-07-01:3.52|2020-08-01:3.35|2020-09-01:3.19|2020-10-01:3.11|2020-11-01:3.02|2020-12-01:2.89|2021-01-01:2.93|2021-02-01:2.97|2021-03-01:2.92|2021-04-01:2.95|2021-05-01:3.01|2021-06-01:2.91|2021-07-01:2.94|2021-08-01:2.96|2021-09-01:3.01|2021-10-01:2.99|2021-11-01:3.01|2021-12-01:3.05|2022-01-01:3.26|2022-02-01:3.38|2022-03-01:3.45|2022-04-01:3.54|2022-05-01:3.65|2022-06-01:3.57|2022-07-01:3.71|2022-08-01:3.78|2022-09-01:3.8|2022-10-01:3.89|2022-11-01:3.92|2022-12-01:3.94|2023-01-01:4.11|2023-02-01:4.16|2023-03-01:4.11|2023-04-01:4.26|2023-05-01:4.35|2023-06-01:4.25|2023-07-01:4.22|2023-08-01:4.12|2023-09-01:4|2023-10-01:3.97|2023-11-01:3.88|2023-12-01:3.75|2024-01-01:3.76|2024-02-01:3.76|2024-03-01:3.71|2024-04-01:3.75|2024-05-01:3.82|2024-06-01:3.71|2024-07-01:3.78|2024-08-01:3.82|2024-09-01:3.83|2024-10-01:3.79|2024-11-01:3.75|2024-12-01:3.63|2025-01-01:3.89|2025-02-01:3.96|2025-03-01:4.03|2025-04-01:4.25|2025-05-01:4.36|2025-06-01:4.41|2025-07-01:4.66|2025-08-01:4.92|2025-09-01:4.89|2025-10-01:4.99|2025-11-01:5.12|2025-12-01:5.12|2026-01-01:5.38|2026-02-01:5.56|2026-03-01:5.39|2026-04-01:5.51|2026-05-01:5.63|2026-06-01:5.42|2026-07-01:5.8|2026-08-01:6.03","21776":"1999-01-01:3499.37|2000-01-01:3753.42|2001-01-01:3161.3|2002-01-01:2834.94|2003-01-01:3084.53|2004-01-01:3648.23|2005-01-01:4808.33|2006-01-01:5903.6|2007-01-01:7372.56|2008-01-01:8849.11|2009-01-01:8658.64|2010-01-01:11346.64|2011-01-01:13328.41|2012-01-01:12462.9|2013-01-01:12390.19|2014-01-01:12224.65|2015-01-01:8874.19|2016-01-01:8829.73|2017-01-01:10053.94|2018-01-01:9278.18|2019-01-01:9008.17|2020-01-01:7054.38|2021-01-01:7950.8|2022-01-01:9255.17|2023-01-01:10349.75|2024-01-01:10277.47|2025-01-01:10687.3","21777":"1999-01-01:40752.02|2000-01-01:41702.64|2001-01-01:41730.98|2002-01-01:42471.46|2003-01-01:42446.94|2004-01-01:44380.01|2005-01-01:45295.31|2006-01-01:46583.52|2007-01-01:48909.35|2008-01-01:50896.82|2009-01-01:50348.9|2010-01-01:53701.36|2011-01-01:55434.53|2012-01-01:56067.35|2013-01-01:57301|2014-01-01:57135.38|2015-01-01:54675.89|2016-01-01:52503.88|2017-01-01:52851.15|2018-01-01:53450.68|2019-01-01:53746.4|2020-01-01:51670.91|2021-01-01:53889.93|2022-01-01:55315.7|2023-01-01:56884.35|2024-01-01:58583.5|2025-01-01:59687.49","23070":"1999-01-01:270.9|1999-02-01:182.5|1999-03-01:113.1|1999-04-01:97.7|1999-05-01:105.3|1999-06-01:99.7|1999-07-01:90.2|1999-08-01:78.9|1999-09-01:82.8|1999-10-01:61.7|1999-11-01:65.2|1999-12-01:79.5|2000-01-01:86.5|2000-02-01:126.8|2000-03-01:176.7|2000-04-01:175|2000-05-01:153.4|2000-06-01:143|2000-07-01:177.9|2000-08-01:176.6|2000-09-01:186.9|2000-10-01:170.9|2000-11-01:177.2|2000-12-01:151.4|2001-01-01:156.8|2001-02-01:142.8|2001-03-01:142|2001-04-01:142.4|2001-05-01:119.5|2001-06-01:102.2|2001-07-01:104.1|2001-08-01:106.9|2001-09-01:94.8|2001-10-01:91.3|2001-11-01:82.1|2001-12-01:76.7|2002-01-01:72.7|2002-02-01:66.8|2002-03-01:62.1|2002-04-01:58.4|2002-05-01:60.6|2002-06-01:61.4|2002-07-01:52.8|2002-08-01:45.5|2002-09-01:43.7|2002-10-01:43.3|2002-11-01:42.3|2002-12-01:33.4|2003-01-01:30.1|2003-02-01:32.6|2003-03-01:28.9|2003-04-01:34.6|2003-05-01:38.1|2003-06-01:50.4|2003-07-01:56.9|2003-08-01:61.1|2003-09-01:73.1|2003-10-01:76.9|2003-11-01:80.5|2003-12-01:99.6|2004-01-01:113.5|2004-02-01:117.7|2004-03-01:114.7|2004-04-01:105.4|2004-05-01:102.5|2004-06-01:87.4|2004-07-01:78.5|2004-08-01:71.5|2004-09-01:63.7|2004-10-01:66.2|2004-11-01:62.5|2004-12-01:60.1|2005-01-01:56|2005-02-01:52.2|2005-03-01:54.3|2005-04-01:52.4|2005-05-01:49.5|2005-06-01:58.1|2005-07-01:59.2|2005-08-01:59.5|2005-09-01:65.2|2005-10-01:62.5|2005-11-01:69.4|2005-12-01:73.3|2006-01-01:80.6|2006-02-01:99.4|2006-03-01:105.7|2006-04-01:112.2|2006-05-01:120|2006-06-01:106.2|2006-07-01:119.7|2006-08-01:135.9|2006-09-01:141.4|2006-10-01:269.4|2006-11-01:301.1|2006-12-01:184.2|2007-01-01:133.7|2007-02-01:121.7|2007-03-01:124.3|2007-04-01:115.5|2007-05-01:116.3|2007-06-01:125.8|2007-07-01:134.4|2007-08-01:138.5|2007-09-01:135|2007-10-01:83|2007-11-01:76.8|2007-12-01:97.6|2008-01-01:136|2008-02-01:141.2|2008-03-01:137.5|2008-04-01:160.8|2008-05-01:160.3|2008-06-01:154.7|2008-07-01:135.4|2008-08-01:123.8|2008-09-01:127.2|2008-10-01:131.6|2008-11-01:112.9|2008-12-01:108.7|2009-01-01:92.3|2009-02-01:87.5|2009-03-01:76.8|2009-04-01:74.1|2009-05-01:64.9|2009-06-01:72.8|2009-07-01:64.6|2009-08-01:68.6|2009-09-01:66.2|2009-10-01:71.4|2009-11-01:86.3|2009-12-01:87.4|2010-01-01:111.8|2010-02-01:114.4|2010-03-01:115.3|2010-04-01:138.9|2010-05-01:169.9|2010-06-01:159.2|2010-07-01:181.3|2010-08-01:181.5|2010-09-01:186.7|2010-10-01:201.4|2010-11-01:202.5|2010-12-01:241.5|2011-01-01:228.5|2011-02-01:247.2|2011-03-01:291.3|2011-04-01:326|2011-05-01:337.5|2011-06-01:387.9|2011-07-01:453.3|2011-08-01:444.2|2011-09-01:458.2|2011-10-01:446.1|2011-11-01:464.8|2011-12-01:465|2012-01-01:491.2|2012-02-01:484.6|2012-03-01:449.3|2012-04-01:368.3|2012-05-01:307.8|2012-06-01:288.3|2012-07-01:240.8|2012-08-01:233.6|2012-09-01:256.3|2012-10-01:215.4|2012-11-01:204.5|2012-12-01:190.5|2013-01-01:185.4|2013-02-01:194.8|2013-03-01:195.1|2013-04-01:195.4|2013-05-01:193.9|2013-06-01:174|2013-07-01:149.3|2013-08-01:121.8|2013-09-01:111.5|2013-10-01:111.3|2013-11-01:109.5|2013-12-01:97.1|2014-01-01:96.4|2014-02-01:92.3|2014-03-01:94.8|2014-04-01:102.8|2014-05-01:104.3|2014-06-01:114.8|2014-07-01:114.7|2014-08-01:126.5|2014-09-01:129.1|2014-10-01:138.8|2014-11-01:140.9|2014-12-01:154.7|2015-01-01:153.2|2015-02-01:142|2015-03-01:130.4|2015-04-01:120.2|2015-05-01:112.8|2015-06-01:105.2|2015-07-01:108|2015-08-01:114.7|2015-09-01:116.8|2015-10-01:108.2|2015-11-01:96.9|2015-12-01:93.3|2016-01-01:83.7|2016-02-01:77.2|2016-03-01:66.4|2016-04-01:63.3|2016-05-01:62.4|2016-06-01:61.8|2016-07-01:58.7|2016-08-01:59|2016-09-01:56.6|2016-10-01:54.8|2016-11-01:63.2|2016-12-01:60.4|2017-01-01:68.6|2017-02-01:71.5|2017-03-01:80.3|2017-04-01:81.8|2017-05-01:88.6|2017-06-01:86|2017-07-01:88.9|2017-08-01:82.8|2017-09-01:82.9|2017-10-01:87.3|2017-11-01:81.3|2017-12-01:87.5|2018-01-01:86.1|2018-02-01:84.3|2018-03-01:85.4|2018-04-01:85.4|2018-05-01:83.6|2018-06-01:83.5|2018-07-01:86.1|2018-08-01:91.4|2018-09-01:94|2018-10-01:91.6|2018-11-01:93.5|2018-12-01:92.1|2019-01-01:89.8|2019-02-01:91.9|2019-03-01:92.5|2019-04-01:90.9|2019-05-01:87.9|2019-06-01:96.8|2019-07-01:96.6|2019-08-01:98.7|2019-09-01:101.9|2019-10-01:105.1|2019-11-01:99.1|2019-12-01:79.9|2020-01-01:85.1|2020-02-01:92.2|2020-03-01:102.1|2020-04-01:97.1|2020-05-01:92.9|2020-06-01:81.5|2020-07-01:75.4|2020-08-01:68.9|2020-09-01:60.8|2020-10-01:60.7|2020-11-01:66|2020-12-01:91.1|2021-01-01:87.6|2021-02-01:83.7|2021-03-01:77.7|2021-04-01:84.6|2021-05-01:90.5|2021-06-01:100.8|2021-07-01:111.8|2021-08-01:114.7|2021-09-01:127|2021-10-01:133.4|2021-11-01:132.6|2021-12-01:115|2022-01-01:113.9|2022-02-01:115|2022-03-01:116.6|2022-04-01:114.2|2022-05-01:114.4|2022-06-01:101.1|2022-07-01:98.6|2022-08-01:100.8|2022-09-01:95.9|2022-10-01:93.4|2022-11-01:89.2|2022-12-01:89.2|2023-01-01:89.5|2023-02-01:87.8|2023-03-01:84.1|2023-04-01:80.3|2023-05-01:81|2023-06-01:90.3|2023-07-01:94.5|2023-08-01:95.1|2023-09-01:95.2|2023-10-01:96.3|2023-11-01:101.3|2023-12-01:100|2024-01-01:97.7|2024-02-01:101.3|2024-03-01:102.2|2024-04-01:107.5|2024-05-01:107|2024-06-01:109.1|2024-07-01:107|2024-08-01:106.5|2024-09-01:107.4|2024-10-01:103.8|2024-11-01:99.5|2024-12-01:103|2025-01-01:104.6|2025-02-01:98.3|2025-03-01:96.3|2025-04-01:97.2|2025-05-01:96.1|2025-06-01:92.4|2025-07-01:90.8|2025-08-01:90|2025-09-01:92.2|2025-10-01:91.8|2025-11-01:93.4|2025-12-01:92.5","23079":"1999-01-01:-4.18|1999-02-01:-4.23|1999-03-01:-4.29|1999-04-01:-4.38|1999-05-01:-4.46|1999-06-01:-4.65|1999-07-01:-4.74|1999-08-01:-4.94|1999-09-01:-4.57|1999-10-01:-4.35|1999-11-01:-4.44|1999-12-01:-4.47|2000-01-01:-4.2|2000-02-01:-4.19|2000-03-01:-4.14|2000-04-01:-4.18|2000-05-01:-4.16|2000-06-01:-4.05|2000-07-01:-3.98|2000-08-01:-3.88|2000-09-01:-3.91|2000-10-01:-4.05|2000-11-01:-4.08|2000-12-01:-4.05|2001-01-01:-4.29|2001-02-01:-4.43|2001-03-01:-4.59|2001-04-01:-4.54|2001-05-01:-4.68|2001-06-01:-4.7|2001-07-01:-4.87|2001-08-01:-4.88|2001-09-01:-4.82|2001-10-01:-4.71|2001-11-01:-4.58|2001-12-01:-4.45|2002-01-01:-4.29|2002-02-01:-4.2|2002-03-01:-3.94|2002-04-01:-3.9|2002-05-01:-3.89|2002-06-01:-3.76|2002-07-01:-3.51|2002-08-01:-3.26|2002-09-01:-2.88|2002-10-01:-2.43|2002-11-01:-2.17|2002-12-01:-1.85|2003-01-01:-1.6|2003-02-01:-1.43|2003-03-01:-1.2|2003-04-01:-0.99|2003-05-01:-0.44|2003-06-01:-0.1|2003-07-01:0.15|2003-08-01:0.33|2003-09-01:0.33|2003-10-01:0.34|2003-11-01:0.33|2003-12-01:0.39|2004-01-01:0.47|2004-02-01:0.52|2004-03-01:0.59|2004-04-01:0.61|2004-05-01:0.69|2004-06-01:0.92|2004-07-01:1.06|2004-08-01:1.12|2004-09-01:1.16|2004-10-01:1.28|2004-11-01:1.25|2004-12-01:1.34|2005-01-01:1.34|2005-02-01:1.3|2005-03-01:1.42|2005-04-01:1.6|2005-05-01:1.44|2005-06-01:1.3|2005-07-01:1.37|2005-08-01:1.22|2005-09-01:1.27|2005-10-01:1.22|2005-11-01:1.41|2005-12-01:1.31|2006-01-01:1.15|2006-02-01:1.18|2006-03-01:1.09|2006-04-01:1.01|2006-05-01:0.97|2006-06-01:0.89|2006-07-01:0.92|2006-08-01:1.03|2006-09-01:1.01|2006-10-01:1.05|2006-11-01:1|2006-12-01:0.97|2007-01-01:0.95|2007-02-01:0.91|2007-03-01:0.81|2007-04-01:0.93|2007-05-01:0.86|2007-06-01:0.82|2007-07-01:0.48|2007-08-01:0.4|2007-09-01:0.25|2007-10-01:0.1|2007-11-01:-0.12|2007-12-01:-0.2|2008-01-01:-0.5|2008-02-01:-0.66|2008-03-01:-0.96|2008-04-01:-1.26|2008-05-01:-1.28|2008-06-01:-1.46|2008-07-01:-1.56|2008-08-01:-1.68|2008-09-01:-1.85|2008-10-01:-1.93|2008-11-01:-1.92|2008-12-01:-2.1|2009-01-01:-2.05|2009-02-01:-2|2009-03-01:-1.86|2009-04-01:-1.68|2009-05-01:-1.75|2009-06-01:-1.62|2009-07-01:-1.59|2009-08-01:-1.56|2009-09-01:-1.51|2009-10-01:-1.57|2009-11-01:-1.65|2009-12-01:-1.75|2010-01-01:-1.96|2010-02-01:-2.2|2010-03-01:-2.5|2010-04-01:-2.77|2010-05-01:-2.88|2010-06-01:-3.14|2010-07-01:-3.42|2010-08-01:-3.6|2010-09-01:-3.78|2010-10-01:-3.89|2010-11-01:-4.05|2010-12-01:-3.92|2011-01-01:-3.95|2011-02-01:-3.83|2011-03-01:-3.68|2011-04-01:-3.59|2011-05-01:-3.56|2011-06-01:-3.44|2011-07-01:-3.33|2011-08-01:-3.28|2011-09-01:-3.17|2011-10-01:-3.12|2011-11-01:-3.11|2011-12-01:-3.2|2012-01-01:-3.27|2012-02-01:-3.26|2012-03-01:-3.25|2012-04-01:-3.3|2012-05-01:-3.34|2012-06-01:-3.45|2012-07-01:-3.49|2012-08-01:-3.48|2012-09-01:-3.49|2012-10-01:-3.58|2012-11-01:-3.65|2012-12-01:-3.76|2013-01-01:-3.82|2013-02-01:-3.89|2013-03-01:-3.91|2013-04-01:-3.91|2013-05-01:-3.89|2013-06-01:-3.74|2013-07-01:-3.9|2013-08-01:-3.96|2013-09-01:-3.94|2013-10-01:-3.92|2013-11-01:-3.77|2013-12-01:-3.58|2014-01-01:-3.61|2014-02-01:-3.72|2014-03-01:-3.79|2014-04-01:-3.86|2014-05-01:-3.87|2014-06-01:-3.91|2014-07-01:-3.83|2014-08-01:-3.83|2014-09-01:-3.96|2014-10-01:-4.08|2014-11-01:-4.27|2014-12-01:-4.5|2015-01-01:-4.47|2015-02-01:-4.49|2015-03-01:-4.5|2015-04-01:-4.49|2015-05-01:-4.46|2015-06-01:-4.5|2015-07-01:-4.42|2015-08-01:-4.4|2015-09-01:-4.29|2015-10-01:-4.2|2015-11-01:-3.98|2015-12-01:-3.53|2016-01-01:-3.26|2016-02-01:-2.97|2016-03-01:-2.73|2016-04-01:-2.44|2016-05-01:-2.15|2016-06-01:-2.11|2016-07-01:-1.98|2016-08-01:-1.86|2016-09-01:-1.75|2016-10-01:-1.63|2016-11-01:-1.44|2016-12-01:-1.7|2017-01-01:-1.71|2017-02-01:-1.6|2017-03-01:-1.47|2017-04-01:-1.45|2017-05-01:-1.4|2017-06-01:-1.26|2017-07-01:-1.25|2017-08-01:-1.23|2017-09-01:-1.22|2017-10-01:-1.16|2017-11-01:-1.3|2017-12-01:-1.22|2018-01-01:-1.26|2018-02-01:-1.52|2018-03-01:-1.67|2018-04-01:-1.75|2018-05-01:-1.92|2018-06-01:-2.03|2018-07-01:-2.24|2018-08-01:-2.45|2018-09-01:-2.53|2018-10-01:-2.57|2018-11-01:-2.6|2018-12-01:-2.81|2019-01-01:-2.91|2019-02-01:-2.76|2019-03-01:-2.81|2019-04-01:-2.84|2019-05-01:-2.92|2019-06-01:-2.93|2019-07-01:-3.07|2019-08-01:-3.13|2019-09-01:-3.18|2019-10-01:-3.51|2019-11-01:-3.53|2019-12-01:-3.42|2020-01-01:-3.51|2020-02-01:-3.65|2020-03-01:-3.69|2020-04-01:-3.51|2020-05-01:-3.4|2020-06-01:-3.14|2020-07-01:-2.56|2020-08-01:-2.16|2020-09-01:-1.96|2020-10-01:-1.48|2020-11-01:-1.39|2020-12-01:-1.64|2021-01-01:-1.49|2021-02-01:-1.44|2021-03-01:-1.77|2021-04-01:-1.61|2021-05-01:-1.41|2021-06-01:-1.42|2021-07-01:-1.57|2021-08-01:-1.72|2021-09-01:-1.89|2021-10-01:-2.14|2021-11-01:-2.44|2021-12-01:-2.36|2022-01-01:-2.27|2022-02-01:-2.11|2022-03-01:-1.69|2022-04-01:-1.79|2022-05-01:-2.11|2022-06-01:-2.17|2022-07-01:-2.28|2022-08-01:-2.52|2022-09-01:-2.68|2022-10-01:-2.59|2022-11-01:-2.19|2022-12-01:-2.15|2023-01-01:-2.17|2023-02-01:-2.31|2023-03-01:-2.29|2023-04-01:-2.43|2023-05-01:-2.23|2023-06-01:-2.32|2023-07-01:-2.18|2023-08-01:-1.87|2023-09-01:-1.59|2023-10-01:-1.34|2023-11-01:-1.31|2023-12-01:-1.23|2024-01-01:-1.02|2024-02-01:-0.97|2024-03-01:-1.18|2024-04-01:-1.21|2024-05-01:-1.31|2024-06-01:-1.47|2024-07-01:-1.62|2024-08-01:-1.91|2024-09-01:-2.19|2024-10-01:-2.53|2024-11-01:-2.74|2024-12-01:-2.99|2025-01-01:-3.26|2025-02-01:-3.58|2025-03-01:-3.58|2025-04-01:-3.66|2025-05-01:-3.73|2025-06-01:-3.73|2025-07-01:-3.71|2025-08-01:-3.53|2025-09-01:-3.57|2025-10-01:-3.39|2025-11-01:-3.31|2025-12-01:-2.96|2026-01-01:-2.93|2026-02-01:-2.69|2026-03-01:-2.61|2026-04-01:-2.47|2026-05-01:-2.46|2026-06-01:-2.37|2026-07-01:-2.45|2026-08-01:-2.5|2026-09-01:-2.33","23080":"1999-01-01:3.46|1999-02-01:3.95|1999-03-01:4.06|1999-04-01:4.19|1999-05-01:4.3|1999-06-01:4.32|1999-07-01:4.58|1999-08-01:4.47|1999-09-01:4.63|1999-10-01:4.56|1999-11-01:4.66|1999-12-01:4.74|2000-01-01:5|2000-02-01:4.47|2000-03-01:4.53|2000-04-01:4.38|2000-05-01:4.41|2000-06-01:4.59|2000-07-01:4.8|2000-08-01:4.73|2000-09-01:4.55|2000-10-01:4.52|2000-11-01:5.08|2000-12-01:5.03|2001-01-01:4.86|2001-02-01:4.81|2001-03-01:4.84|2001-04-01:4.98|2001-05-01:5.09|2001-06-01:4.79|2001-07-01:4.39|2001-08-01:4.27|2001-09-01:4.32|2001-10-01:4.25|2001-11-01:3.7|2001-12-01:4.15|2002-01-01:4.16|2002-02-01:4.17|2002-03-01:4.27|2002-04-01:4.29|2002-05-01:4.23|2002-06-01:4.34|2002-07-01:4.07|2002-08-01:4.01|2002-09-01:3.99|2002-10-01:3.99|2002-11-01:3.82|2002-12-01:3.26|2003-01-01:3.17|2003-02-01:3.17|2003-03-01:2.76|2003-04-01:2.52|2003-05-01:2.32|2003-06-01:2.03|2003-07-01:2.06|2003-08-01:2.07|2003-09-01:1.94|2003-10-01:1.74|2003-11-01:1.86|2003-12-01:1.81|2004-01-01:1.79|2004-02-01:1.79|2004-03-01:1.81|2004-04-01:1.72|2004-05-01:1.65|2004-06-01:1.72|2004-07-01:1.76|2004-08-01:2.55|2004-09-01:2.51|2004-10-01:2.64|2004-11-01:2.5|2004-12-01:2.71|2005-01-01:2.7|2005-02-01:2.62|2005-03-01:2.69|2005-04-01:3.01|2005-05-01:3|2005-06-01:3|2005-07-01:2.98|2005-08-01:2.27|2005-09-01:2.14|2005-10-01:2.03|2005-11-01:1.97|2005-12-01:1.73|2006-01-01:1.73|2006-02-01:1.69|2006-03-01:1.68|2006-04-01:1.42|2006-05-01:1.47|2006-06-01:1.42|2006-07-01:1.36|2006-08-01:1.35|2006-09-01:1.5|2006-10-01:1.56|2006-11-01:1.66|2006-12-01:1.75|2007-01-01:2.33|2007-02-01:2.34|2007-03-01:2.4|2007-04-01:2.59|2007-05-01:2.47|2007-06-01:3.17|2007-07-01:3.29|2007-08-01:3.32|2007-09-01:3.27|2007-10-01:3.34|2007-11-01:3.35|2007-12-01:3.19|2008-01-01:2.97|2008-02-01:2.86|2008-03-01:2.83|2008-04-01:2.82|2008-05-01:2.83|2008-06-01:2.33|2008-07-01:2.26|2008-08-01:2.36|2008-09-01:2.58|2008-10-01:2.62|2008-11-01:2.57|2008-12-01:3|2009-01-01:2.79|2009-02-01:2.92|2009-03-01:2.87|2009-04-01:2.86|2009-05-01:2.97|2009-06-01:2.9|2009-07-01:2.83|2009-08-01:2.7|2009-09-01:2.43|2009-10-01:2.19|2009-11-01:2.06|2009-12-01:1.88|2010-01-01:1.88|2010-02-01:2.02|2010-03-01:2.17|2010-04-01:2.1|2010-05-01:2.25|2010-06-01:2.2|2010-07-01:2.37|2010-08-01:2.46|2010-09-01:2.74|2010-10-01:3.1|2010-11-01:3.33|2010-12-01:3.73|2011-01-01:3.8|2011-02-01:3.92|2011-03-01:4.04|2011-04-01:4.17|2011-05-01:4.1|2011-06-01:4.32|2011-07-01:4.38|2011-08-01:4.34|2011-09-01:4.33|2011-10-01:4.35|2011-11-01:4.26|2011-12-01:3.92|2012-01-01:4.02|2012-02-01:3.82|2012-03-01:4.01|2012-04-01:3.9|2012-05-01:3.82|2012-06-01:3.81|2012-07-01:3.86|2012-08-01:3.87|2012-09-01:3.74|2012-10-01:3.66|2012-11-01:3.84|2012-12-01:3.76|2013-01-01:3.58|2013-02-01:3.5|2013-03-01:3.18|2013-04-01:3.22|2013-05-01:3.53|2013-06-01:3.65|2013-07-01:3.46|2013-08-01:3.36|2013-09-01:3.28|2013-10-01:3.19|2013-11-01:3.17|2013-12-01:3.05|2014-01-01:3.24|2014-02-01:3.34|2014-03-01:3.36|2014-04-01:3.38|2014-05-01:3.2|2014-06-01:2.98|2014-07-01:3.15|2014-08-01:3.36|2014-09-01:3.45|2014-10-01:3.48|2014-11-01:3.36|2014-12-01:3.57|2015-01-01:3.44|2015-02-01:3.36|2015-03-01:3.25|2015-04-01:3.19|2015-05-01:3.17|2015-06-01:3.22|2015-07-01:3.12|2015-08-01:3.03|2015-09-01:3.13|2015-10-01:3.17|2015-11-01:3.32|2015-12-01:3.6|2016-01-01:3.83|2016-02-01:4.07|2016-03-01:4.35|2016-04-01:4.59|2016-05-01:4.64|2016-06-01:4.55|2016-07-01:4.19|2016-08-01:4.29|2016-09-01:4.14|2016-10-01:4.17|2016-11-01:4.13|2016-12-01:4.13|2017-01-01:4.34|2017-02-01:4.14|2017-03-01:4.15|2017-04-01:3.99|2017-05-01:3.78|2017-06-01:3.74|2017-07-01:3.9|2017-08-01:3.78|2017-09-01:3.95|2017-10-01:3.97|2017-11-01:3.83|2017-12-01:3.34|2018-01-01:3.13|2018-02-01:3.25|2018-03-01:3.18|2018-04-01:3.03|2018-05-01:3.03|2018-06-01:3.18|2018-07-01:3.2|2018-08-01:3.49|2018-09-01:3.45|2018-10-01:3.46|2018-11-01:3.71|2018-12-01:4.08|2019-01-01:3.83|2019-02-01:3.89|2019-03-01:3.76|2019-04-01:3.92|2019-05-01:4.26|2019-06-01:3.98|2019-07-01:4.06|2019-08-01:4.11|2019-09-01:3.99|2019-10-01:3.99|2019-11-01:3.99|2019-12-01:3.69|2020-01-01:3.71|2020-02-01:3.51|2020-03-01:3.79|2020-04-01:3.69|2020-05-01:3.47|2020-06-01:3.78|2020-07-01:3.84|2020-08-01:3.37|2020-09-01:3.26|2020-10-01:3.05|2020-11-01:2.68|2020-12-01:2.59|2021-01-01:2.67|2021-02-01:3.13|2021-03-01:3.22|2021-04-01:3.4|2021-05-01:3.23|2021-06-01:2.82|2021-07-01:2.96|2021-08-01:3.16|2021-09-01:3.09|2021-10-01:3.03|2021-11-01:3.16|2021-12-01:2.78|2022-01-01:2.82|2022-02-01:2.84|2022-03-01:2.64|2022-04-01:2.95|2022-05-01:3.02|2022-06-01:3.2|2022-07-01:3.14|2022-08-01:3.3|2022-09-01:3.63|2022-10-01:3.64|2022-11-01:3.67|2022-12-01:3.87|2023-01-01:3.87|2023-02-01:3.73|2023-03-01:3.9|2023-04-01:3.58|2023-05-01:3.64|2023-06-01:3.56|2023-07-01:3.49|2023-08-01:3.31|2023-09-01:3.11|2023-10-01:3.01|2023-11-01:2.97|2023-12-01:2.97|2024-01-01:3.07|2024-02-01:2.92|2024-03-01:2.89|2024-04-01:2.96|2024-05-01:2.94|2024-06-01:3.12|2024-07-01:3.2|2024-08-01:3.28|2024-09-01:3.2|2024-10-01:3.37|2024-11-01:3.36|2024-12-01:3.39|2025-01-01:3.29|2025-02-01:3.5|2025-03-01:3.35|2025-04-01:3.42|2025-05-01:3.77|2025-06-01:3.73|2025-07-01:3.69|2025-08-01:3.64|2025-09-01:3.87|2025-10-01:3.98|2025-11-01:4.01|2025-12-01:3.73|2026-01-01:3.84|2026-02-01:3.73|2026-03-01:3.65|2026-04-01:3.65|2026-05-01:3.43|2026-06-01:3.53|2026-07-01:3.44|2026-08-01:3.39|2026-09-01:3.43","24369":"2012-03-01:8|2012-04-01:7.8|2012-05-01:7.7|2012-06-01:7.6|2012-07-01:7.5|2012-08-01:7.3|2012-09-01:7.1|2012-10-01:6.9|2012-11-01:6.8|2012-12-01:6.9|2013-01-01:7.2|2013-02-01:7.8|2013-03-01:8|2013-04-01:7.9|2013-05-01:7.6|2013-06-01:7.5|2013-07-01:7.4|2013-08-01:7.2|2013-09-01:7|2013-10-01:6.8|2013-11-01:6.5|2013-12-01:6.2|2014-01-01:6.5|2014-02-01:6.8|2014-03-01:7.2|2014-04-01:7.2|2014-05-01:7|2014-06-01:6.9|2014-07-01:7|2014-08-01:7|2014-09-01:6.8|2014-10-01:6.7|2014-11-01:6.6|2014-12-01:6.6|2015-01-01:6.9|2015-02-01:7.5|2015-03-01:8|2015-04-01:8.1|2015-05-01:8.2|2015-06-01:8.4|2015-07-01:8.6|2015-08-01:8.8|2015-09-01:9|2015-10-01:9.1|2015-11-01:9.1|2015-12-01:9.1|2016-01-01:9.6|2016-02-01:10.3|2016-03-01:11|2016-04-01:11.3|2016-05-01:11.3|2016-06-01:11.4|2016-07-01:11.7|2016-08-01:11.9|2016-09-01:11.9|2016-10-01:11.9|2016-11-01:12|2016-12-01:12.1|2017-01-01:12.7|2017-02-01:13.3|2017-03-01:13.9|2017-04-01:13.7|2017-05-01:13.4|2017-06-01:13.1|2017-07-01:12.9|2017-08-01:12.7|2017-09-01:12.5|2017-10-01:12.3|2017-11-01:12.1|2017-12-01:11.9|2018-01-01:12.3|2018-02-01:12.7|2018-03-01:13.2|2018-04-01:13|2018-05-01:12.8|2018-06-01:12.6|2018-07-01:12.4|2018-08-01:12.2|2018-09-01:12|2018-10-01:11.8|2018-11-01:11.7|2018-12-01:11.7|2019-01-01:12.2|2019-02-01:12.5|2019-03-01:12.8|2019-04-01:12.6|2019-05-01:12.4|2019-06-01:12.1|2019-07-01:11.9|2019-08-01:11.9|2019-09-01:11.9|2019-10-01:11.7|2019-11-01:11.3|2019-12-01:11.1|2020-01-01:11.3|2020-02-01:11.7|2020-03-01:12.4|2020-04-01:12.7|2020-05-01:13.1|2020-06-01:13.6|2020-07-01:14.1|2020-08-01:14.8|2020-09-01:14.9|2020-10-01:14.6|2020-11-01:14.3|2020-12-01:14.2|2021-01-01:14.4|2021-02-01:14.6|2021-03-01:14.9|2021-04-01:14.8|2021-05-01:14.7|2021-06-01:14.2|2021-07-01:13.7|2021-08-01:13.2|2021-09-01:12.7|2021-10-01:12.1|2021-11-01:11.6|2021-12-01:11.1|2022-01-01:11.2|2022-02-01:11.2|2022-03-01:11.1|2022-04-01:10.5|2022-05-01:9.8|2022-06-01:9.3|2022-07-01:9.1|2022-08-01:8.9|2022-09-01:8.7|2022-10-01:8.3|2022-11-01:8.1|2022-12-01:7.9|2023-01-01:8.4|2023-02-01:8.6|2023-03-01:8.8|2023-04-01:8.5|2023-05-01:8.3|2023-06-01:8|2023-07-01:7.9|2023-08-01:7.8|2023-09-01:7.7|2023-10-01:7.6|2023-11-01:7.5|2023-12-01:7.4|2024-01-01:7.6|2024-02-01:7.8|2024-03-01:7.9|2024-04-01:7.5|2024-05-01:7.1|2024-06-01:6.9|2024-07-01:6.8|2024-08-01:6.6|2024-09-01:6.4|2024-10-01:6.2|2024-11-01:6.1|2024-12-01:6.2|2025-01-01:6.5|2025-02-01:6.8|2025-03-01:7|2025-04-01:6.6|2025-05-01:6.2|2025-06-01:5.8|2025-07-01:5.6|2025-08-01:5.6|2025-09-01:5.6|2025-10-01:5.4|2025-11-01:5.2|2025-12-01:5.1|2026-01-01:5.4|2026-02-01:5.8|2026-03-01:6.1|2026-04-01:5.8|2026-05-01:5.6|2026-06-01:5.4|2026-07-01:5.3|2026-08-01:5.3","27863":"1999-01-01:0.46|1999-02-01:0.93|1999-03-01:1.1|1999-04-01:1.26|1999-05-01:1.27|1999-06-01:0.59|1999-07-01:0.46|1999-08-01:0.43|1999-09-01:0.43|1999-10-01:2.09|1999-11-01:0.55|1999-12-01:0.17|2000-01-01:0.47|2000-02-01:0.47|2000-03-01:0.17|2000-04-01:0.47|2000-05-01:0.37|2000-06-01:0.51|2000-07-01:0.51|2000-08-01:0.42|2000-09-01:0.3|2000-10-01:0.32|2000-11-01:0.15|2000-12-01:0.21|2001-01-01:0.33|2001-02-01:0.43|2001-03-01:0.35|2001-04-01:0.19|2001-05-01:0.3|2001-06-01:0.12|2001-07-01:0.37|2001-08-01:0.46|2001-09-01:0.11|2001-10-01:0.67|2001-11-01:0.9|2001-12-01:1.2|2002-01-01:0.68|2002-02-01:0.55|2002-03-01:0.53|2002-04-01:0.62|2002-05-01:0.57|2002-06-01:0.18|2002-07-01:0.34|2002-08-01:0.33|2002-09-01:0.76|2002-10-01:1.13|2002-11-01:1.48|2002-12-01:2.24|2003-01-01:1.76|2003-02-01:0.63|2003-03-01:1.55|2003-04-01:1.21|2003-05-01:0.61|2003-06-01:0.45|2003-07-01:0.18|2003-08-01:0.12|2003-09-01:0.35|2003-10-01:0.29|2003-11-01:0.35|2003-12-01:0.72|2004-01-01:0.67|2004-02-01:0.43|2004-03-01:1.07|2004-04-01:1.09|2004-05-01:1.06|2004-06-01:0.71|2004-07-01:0.4|2004-08-01:0.38|2004-09-01:0.54|2004-10-01:0.69|2004-11-01:0.73|2004-12-01:0.62|2005-01-01:0.58|2005-02-01:0.24|2005-03-01:0.25|2005-04-01:1|2005-05-01:0.78|2005-06-01:0.3|2005-07-01:0.18|2005-08-01:0.12|2005-09-01:0.13|2005-10-01:0.32|2005-11-01:0.07|2005-12-01:0.36|2006-01-01:0.95|2006-02-01:0.06|2006-03-01:0.7|2006-04-01:0.08|2006-05-01:-0.47|2006-06-01:-0.56|2006-07-01:-0.06|2006-08-01:-0.14|2006-09-01:0.13|2006-10-01:0.08|2006-11-01:0.22|2006-12-01:0.37|2007-01-01:0.28|2007-02-01:-0.3|2007-03-01:0.06|2007-04-01:0.33|2007-05-01:0.33|2007-06-01:0.06|2007-07-01:-0.11|2007-08-01:0.12|2007-09-01:0.21|2007-10-01:0.37|2007-11-01:0.21|2007-12-01:0.52|2008-01-01:0.21|2008-02-01:-0.07|2008-03-01:0.28|2008-04-01:0.59|2008-05-01:0.61|2008-06-01:0.44|2008-07-01:0.12|2008-08-01:0.36|2008-09-01:0.6|2008-10-01:0.51|2008-11-01:0.23|2008-12-01:0.06|2009-01-01:-0.29|2009-02-01:-0.16|2009-03-01:0.33|2009-04-01:0.58|2009-05-01:0.6|2009-06-01:0.2|2009-07-01:0.07|2009-08-01:-0.05|2009-09-01:0.33|2009-10-01:0.53|2009-11-01:0.39|2009-12-01:0.37|2010-01-01:0.41|2010-02-01:0.02|2010-03-01:0.19|2010-04-01:0.33|2010-05-01:0.51|2010-06-01:0.3|2010-07-01:0.02|2010-08-01:-0.02|2010-09-01:0.23|2010-10-01:0.48|2010-11-01:0.48|2010-12-01:0.45|2011-01-01:0.32|2011-02-01:0.24|2011-03-01:0.44|2011-04-01:0.58|2011-05-01:0.1|2011-06-01:0.41|2011-07-01:0.2|2011-08-01:0.28|2011-09-01:0.33|2011-10-01:0.28|2011-11-01:0.18|2011-12-01:0.12|2012-01-01:-0.04|2012-02-01:-0.13|2012-03-01:-0.19|2012-04-01:0.64|2012-05-01:0.31|2012-06-01:-0.91|2012-07-01:-0.02|2012-08-01:0.27|2012-09-01:0.23|2012-10-01:0.45|2012-11-01:0.41|2012-12-01:0.75|2013-01-01:0.8|2013-02-01:0.58|2013-03-01:0.41|2013-04-01:0.35|2013-05-01:0.35|2013-06-01:0.01|2013-07-01:-0.04|2013-08-01:0.25|2013-09-01:0.39|2013-10-01:0.72|2013-11-01:0.53|2013-12-01:0.7|2014-01-01:0.62|2014-02-01:0.49|2014-03-01:0.58|2014-04-01:0.35|2014-05-01:0.58|2014-06-01:0.23|2014-07-01:0.1|2014-08-01:0.11|2014-09-01:0.29|2014-10-01:0.41|2014-11-01:0.08|2014-12-01:0.41|2015-01-01:0.31|2015-02-01:0.68|2015-03-01:0.57|2015-04-01:0.46|2015-05-01:0.49|2015-06-01:0.51|2015-07-01:0.19|2015-08-01:0.31|2015-09-01:0.38|2015-10-01:0.65|2015-11-01:0.79|2015-12-01:0.71|2016-01-01:0.57|2016-02-01:0.92|2016-03-01:0.71|2016-04-01:0.2|2016-05-01:0.71|2016-06-01:0.25|2016-07-01:0.1|2016-08-01:0.45|2016-09-01:-0.06|2016-10-01:0.2|2016-11-01:0.26|2016-12-01:0.36|2017-01-01:0.12|2017-02-01:0.08|2017-03-01:-0.15|2017-04-01:-0.03|2017-05-01:0.07|2017-06-01:-0.12|2017-07-01:-0.25|2017-08-01:0.26|2017-09-01:0.18|2017-10-01:0.32|2017-11-01:0.08|2017-12-01:0.46|2018-01-01:0.01|2018-02-01:0.05|2018-03-01:0.13|2018-04-01:0.06|2018-05-01:0.13|2018-06-01:0.19|2018-07-01:-0.23|2018-08-01:0.2|2018-09-01:0.37|2018-10-01:0.46|2018-11-01:-0.63|2018-12-01:0.38|2019-01-01:-0.13|2019-02-01:0.09|2019-03-01:0.49|2019-04-01:0.42|2019-05-01:0.03|2019-06-01:0.02|2019-07-01:-0.33|2019-08-01:0.27|2019-09-01:0.1|2019-10-01:0.29|2019-11-01:0.14|2019-12-01:0.24|2020-01-01:-0.23|2020-02-01:0.24|2020-03-01:-0.06|2020-04-01:-0.74|2020-05-01:0.02|2020-06-01:0.29|2020-07-01:0.28|2020-08-01:0.24|2020-09-01:0.56|2020-10-01:0.97|2020-11-01:0.67|2020-12-01:0.89|2021-01-01:0.61|2021-02-01:0.8|2021-03-01:0.81|2021-04-01:0.52|2021-05-01:1.27|2021-06-01:0.8|2021-07-01:0.68|2021-08-01:1.03|2021-09-01:1.04|2021-10-01:1.39|2021-11-01:0.96|2021-12-01:1.41|2022-01-01:1.22|2022-02-01:1.1|2022-03-01:1.2|2022-04-01:1.21|2022-05-01:1.05|2022-06-01:0.57|2022-07-01:-0.11|2022-08-01:0.8|2022-09-01:0.07|2022-10-01:0.77|2022-11-01:0.09|2022-12-01:1.19|2023-01-01:0.18|2023-02-01:0.53|2023-03-01:0.26|2023-04-01:0.39|2023-05-01:0.31|2023-06-01:-0.57|2023-07-01:0.12|2023-08-01:0.32|2023-09-01:-0.2|2023-10-01:0.02|2023-11-01:-0.54|2023-12-01:0.28|2024-01-01:0.36|2024-02-01:0.21|2024-03-01:-0.12|2024-04-01:0.21|2024-05-01:0.29|2024-06-01:0.13|2024-07-01:0.33|2024-08-01:0.18|2024-09-01:0.16|2024-10-01:0.25|2024-11-01:0.18|2024-12-01:0.65|2025-01-01:0.45|2025-02-01:0.4|2025-03-01:0.38|2025-04-01:0.62|2025-05-01:0.06|2025-06-01:0.04|2025-07-01:-0.04|2025-08-01:0.18|2025-09-01:0.06|2025-10-01:0.03|2025-11-01:-0.29|2025-12-01:0.48|2026-01-01:0.61|2026-02-01:0.34|2026-03-01:0.31|2026-04-01:0.62|2026-05-01:0.32|2026-06-01:0.11|2026-07-01:-0.1|2026-08-01:0.43|2026-09-01:0.17","27864":"1999-01-01:1.04|1999-02-01:3.57|1999-03-01:2.66|1999-04-01:-0.5|1999-05-01:-1.21|1999-06-01:-1.42|1999-07-01:-0.32|1999-08-01:0.17|1999-09-01:0.42|1999-10-01:2.3|1999-11-01:1.66|1999-12-01:1.55|2000-01-01:0.94|2000-02-01:-0.5|2000-03-01:-0.63|2000-04-01:-0.54|2000-05-01:-0.98|2000-06-01:0.07|2000-07-01:2.38|2000-08-01:2.58|2000-09-01:0.61|2000-10-01:0.1|2000-11-01:-0.16|2000-12-01:-0.73|2001-01-01:0.82|2001-02-01:-0.11|2001-03-01:1.27|2001-04-01:2.15|2001-05-01:0.51|2001-06-01:-0.17|2001-07-01:0.53|2001-08-01:0.89|2001-09-01:0.19|2001-10-01:1.37|2001-11-01:1.31|2001-12-01:0.48|2002-01-01:0.86|2002-02-01:0.01|2002-03-01:0.21|2002-04-01:-0.39|2002-05-01:-0.94|2002-06-01:0.11|2002-07-01:1.23|2002-08-01:2.28|2002-09-01:2.36|2002-10-01:3.32|2002-11-01:6.68|2002-12-01:4.24|2003-01-01:2.37|2003-02-01:1.47|2003-03-01:1.74|2003-04-01:1.06|2003-05-01:0.45|2003-06-01:-0.68|2003-07-01:-1.07|2003-08-01:-0.54|2003-09-01:0.93|2003-10-01:0.4|2003-11-01:0.18|2003-12-01:0.27|2004-01-01:0.96|2004-02-01:0.06|2004-03-01:0.23|2004-04-01:-0.57|2004-05-01:0.19|2004-06-01:0.73|2004-07-01:0.68|2004-08-01:0.72|2004-09-01:-0.31|2004-10-01:-0.48|2004-11-01:-0.15|2004-12-01:0.49|2005-01-01:0.77|2005-02-01:0.29|2005-03-01:0.07|2005-04-01:0.9|2005-05-01:0.65|2005-06-01:-0.92|2005-07-01:-1.13|2005-08-01:-1.02|2005-09-01:-0.5|2005-10-01:0.38|2005-11-01:0.89|2005-12-01:0.24|2006-01-01:-0.23|2006-02-01:-0.52|2006-03-01:-0.38|2006-04-01:-0.51|2006-05-01:-0.22|2006-06-01:-0.92|2006-07-01:0.08|2006-08-01:-0.09|2006-09-01:0.1|2006-10-01:0.98|2006-11-01:1.38|2006-12-01:0.22|2007-01-01:0.94|2007-02-01:0.87|2007-03-01:1.3|2007-04-01:-0.24|2007-05-01:-0.07|2007-06-01:1.28|2007-07-01:1.93|2007-08-01:1.71|2007-09-01:0.39|2007-10-01:0.46|2007-11-01:0.66|2007-12-01:2.52|2008-01-01:1.76|2008-02-01:0.53|2008-03-01:0.94|2008-04-01:1.44|2008-05-01:2.27|2008-06-01:2.48|2008-07-01:0.89|2008-08-01:-0.64|2008-09-01:-0.88|2008-10-01:0.64|2008-11-01:0.73|2008-12-01:0.08|2009-01-01:0.71|2009-02-01:-0.11|2009-03-01:0.15|2009-04-01:0.03|2009-05-01:0.46|2009-06-01:0.78|2009-07-01:-0.37|2009-08-01:-0.38|2009-09-01:-0.42|2009-10-01:-0.21|2009-11-01:0.41|2009-12-01:-0.16|2010-01-01:1.25|2010-02-01:1.18|2010-03-01:2.06|2010-04-01:1.92|2010-05-01:-0.06|2010-06-01:-1.71|2010-07-01:-1.3|2010-08-01:-0.61|2010-09-01:1.4|2010-10-01:2.4|2010-11-01:2.76|2010-12-01:1.03|2011-01-01:1.24|2011-02-01:-0.15|2011-03-01:0.67|2011-04-01:0.48|2011-05-01:0.47|2011-06-01:-0.62|2011-07-01:-0.96|2011-08-01:0.74|2011-09-01:0.68|2011-10-01:0.36|2011-11-01:1.25|2011-12-01:1.15|2012-01-01:0.68|2012-02-01:-0.03|2012-03-01:0.21|2012-04-01:0.62|2012-05-01:0.83|2012-06-01:0.67|2012-07-01:0.79|2012-08-01:0.89|2012-09-01:1.7|2012-10-01:1.55|2012-11-01:0.52|2012-12-01:1.17|2013-01-01:2.49|2013-02-01:1.63|2013-03-01:1.36|2013-04-01:1.1|2013-05-01:0.05|2013-06-01:-0.36|2013-07-01:-0.73|2013-08-01:-0.34|2013-09-01:-0.03|2013-10-01:1.07|2013-11-01:0.41|2013-12-01:0.79|2014-01-01:0.9|2014-02-01:0.22|2014-03-01:2.43|2014-04-01:1.52|2014-05-01:0.41|2014-06-01:-0.6|2014-07-01:-0.51|2014-08-01:-0.61|2014-09-01:0.76|2014-10-01:0.48|2014-11-01:0.97|2014-12-01:0.96|2015-01-01:1.74|2015-02-01:0.74|2015-03-01:1.17|2015-04-01:0.97|2015-05-01:1.61|2015-06-01:0.7|2015-07-01:0.59|2015-08-01:-0.32|2015-09-01:-0.05|2015-10-01:0.68|2015-11-01:2.46|2015-12-01:1.96|2016-01-01:2.89|2016-02-01:1.28|2016-03-01:1.61|2016-04-01:1.14|2016-05-01:0.87|2016-06-01:0.71|2016-07-01:1.75|2016-08-01:0.36|2016-09-01:-0.6|2016-10-01:-0.45|2016-11-01:-0.47|2016-12-01:-0.05|2017-01-01:0.17|2017-02-01:-0.75|2017-03-01:0.31|2017-04-01:0.68|2017-05-01:-0.56|2017-06-01:-0.93|2017-07-01:-0.81|2017-08-01:-1.84|2017-09-01:-0.74|2017-10-01:-0.17|2017-11-01:-0.72|2017-12-01:0.42|2018-01-01:1.12|2018-02-01:-0.61|2018-03-01:-0.18|2018-04-01:0.27|2018-05-01:0.36|2018-06-01:3.09|2018-07-01:-0.59|2018-08-01:-0.72|2018-09-01:0|2018-10-01:0.91|2018-11-01:0.34|2018-12-01:0.5|2019-01-01:0.97|2019-02-01:1.24|2019-03-01:2.07|2019-04-01:0.62|2019-05-01:-0.89|2019-06-01:-0.39|2019-07-01:-0.06|2019-08-01:-0.84|2019-09-01:-0.7|2019-10-01:-0.03|2019-11-01:1.01|2019-12-01:4.69|2020-01-01:0.2|2020-02-01:0.06|2020-03-01:1.4|2020-04-01:2.24|2020-05-01:0.33|2020-06-01:0.45|2020-07-01:0.14|2020-08-01:1.15|2020-09-01:2.89|2020-10-01:2.57|2020-11-01:3.33|2020-12-01:2.12|2021-01-01:1.06|2021-02-01:0.28|2021-03-01:-0.17|2021-04-01:0.47|2021-05-01:0.23|2021-06-01:0.33|2021-07-01:0.78|2021-08-01:1.63|2021-09-01:1.19|2021-10-01:1.32|2021-11-01:0.04|2021-12-01:0.79|2022-01-01:1.44|2022-02-01:1.65|2022-03-01:3.09|2022-04-01:2.59|2022-05-01:0.43|2022-06-01:0.63|2022-07-01:1.47|2022-08-01:0.01|2022-09-01:-0.86|2022-10-01:0.8|2022-11-01:0.58|2022-12-01:0.71|2023-01-01:0.6|2023-02-01:0.04|2023-03-01:-0.14|2023-04-01:0.73|2023-05-01:0|2023-06-01:-1.07|2023-07-01:-0.72|2023-08-01:-1.26|2023-09-01:-1.02|2023-10-01:0.27|2023-11-01:0.75|2023-12-01:1.34|2024-01-01:1.81|2024-02-01:1.12|2024-03-01:0.59|2024-04-01:0.81|2024-05-01:0.66|2024-06-01:0.47|2024-07-01:-1.51|2024-08-01:-0.73|2024-09-01:0.56|2024-10-01:1.22|2024-11-01:1.81|2024-12-01:1.17|2025-01-01:1.07|2025-02-01:0.79|2025-03-01:1.31|2025-04-01:0.83|2025-05-01:0.02|2025-06-01:-0.43|2025-07-01:-0.69|2025-08-01:-0.83|2025-09-01:-0.41|2025-10-01:-0.16|2025-11-01:-0.2|2025-12-01:0.14|2026-01-01:0.1|2026-02-01:0.23|2026-03-01:1.94|2026-04-01:1.64|2026-05-01:1.65|2026-06-01:-0.39|2026-07-01:-1.14|2026-08-01:-0.61|2026-09-01:0.96","28473":"2000-01-01:50.14|2000-02-01:50.66|2000-03-01:50.98|2000-04-01:50.95|2000-05-01:51.28|2000-06-01:51.13|2000-07-01:51.33|2000-08-01:50.78|2000-09-01:50.98|2000-10-01:50.22|2000-11-01:51.03|2000-12-01:51.3|2001-01-01:51.12|2001-02-01:50.96|2001-03-01:50.75|2001-04-01:50.53|2001-05-01:50|2001-06-01:50|2001-07-01:49.7|2001-08-01:49.91|2001-09-01:50.08|2001-10-01:50.31|2001-11-01:49.7|2001-12-01:50.18|2002-01-01:50.32|2002-02-01:50.27|2002-03-01:50.45|2002-04-01:50.24|2002-05-01:50.42|2002-06-01:49.5|2002-07-01:50.08|2002-08-01:50.61|2002-09-01:49.97|2002-10-01:50.42|2002-11-01:49.27|2002-12-01:48.16|2003-01-01:47.71|2003-02-01:48.45|2003-03-01:47.07|2003-04-01:47.17|2003-05-01:46.81|2003-06-01:47.14|2003-07-01:47.72|2003-08-01:48.16|2003-09-01:48.28|2003-10-01:48.8|2003-11-01:49.71|2003-12-01:49.29|2004-01-01:49.98|2004-02-01:50.83|2004-03-01:51.23|2004-04-01:51.76|2004-05-01:52.42|2004-06-01:52.68|2004-07-01:52.9|2004-08-01:52.25|2004-09-01:52.38|2004-10-01:53.06|2004-11-01:53.09|2004-12-01:54.58|2005-01-01:53.55|2005-02-01:53.37|2005-03-01:53.95|2005-04-01:54.13|2005-05-01:54.32|2005-06-01:55.22|2005-07-01:55.89|2005-08-01:55.37|2005-09-01:55.07|2005-10-01:55.45|2005-11-01:55.6|2005-12-01:56.94|2006-01-01:57.38|2006-02-01:56.67|2006-03-01:56.48|2006-04-01:57.55|2006-05-01:57.66|2006-06-01:57.41|2006-07-01:57.56|2006-08-01:58.79|2006-09-01:59.93|2006-10-01:60.06|2006-11-01:60.56|2006-12-01:60.93|2007-01-01:61.28|2007-02-01:61.69|2007-03-01:62.43|2007-04-01:62.76|2007-05-01:63.56|2007-06-01:63.46|2007-07-01:63.85|2007-08-01:64.52|2007-09-01:65.33|2007-10-01:65.2|2007-11-01:66.8|2007-12-01:67.32|2008-01-01:67.92|2008-02-01:66.91|2008-03-01:68.63|2008-04-01:69.02|2008-05-01:69.94|2008-06-01:70.07|2008-07-01:70.26|2008-08-01:70.88|2008-09-01:71.71|2008-10-01:71.22|2008-11-01:70.37|2008-12-01:70.37|2009-01-01:70.81|2009-02-01:71.87|2009-03-01:71.52|2009-04-01:72.34|2009-05-01:72.69|2009-06-01:73.67|2009-07-01:74.18|2009-08-01:74.53|2009-09-01:75.06|2009-10-01:76.67|2009-11-01:77.21|2009-12-01:77.05|2010-01-01:78.5|2010-02-01:80.48|2010-03-01:81.66|2010-04-01:79.05|2010-05-01:80.88|2010-06-01:81.8|2010-07-01:81.59|2010-08-01:83.28|2010-09-01:83.89|2010-10-01:84.07|2010-11-01:84.19|2010-12-01:84.93|2011-01-01:84.93|2011-02-01:85.18|2011-03-01:86.41|2011-04-01:86.55|2011-05-01:87.31|2011-06-01:87.59|2011-07-01:88.03|2011-08-01:87.7|2011-09-01:88.14|2011-10-01:87.97|2011-11-01:89.16|2011-12-01:90.17|2012-01-01:92.11|2012-02-01:92.86|2012-03-01:93.74|2012-04-01:93.95|2012-05-01:93.57|2012-06-01:95.15|2012-07-01:95.8|2012-08-01:95.89|2012-09-01:96.01|2012-10-01:96.06|2012-11-01:95.62|2012-12-01:96.31|2013-01-01:96.12|2013-02-01:95.78|2013-03-01:96.81|2013-04-01:97.09|2013-05-01:97.63|2013-06-01:97.92|2013-07-01:100.7|2013-08-01:101.12|2013-09-01:101.32|2013-10-01:100.72|2013-11-01:100.64|2013-12-01:101.53|2014-01-01:101.68|2014-02-01:101.45|2014-03-01:100.82|2014-04-01:101.11|2014-05-01:101.49|2014-06-01:100.05|2014-07-01:99.56|2014-08-01:101.26|2014-09-01:101.34|2014-10-01:102.36|2014-11-01:102.21|2014-12-01:101.26|2015-01-01:101.35|2015-02-01:100.13|2015-03-01:100.21|2015-04-01:97.49|2015-05-01:97.97|2015-06-01:96.63|2015-07-01:95.42|2015-08-01:94.78|2015-09-01:94.71|2015-10-01:95.81|2015-11-01:94.44|2015-12-01:94.13|2016-01-01:91.46|2016-02-01:92.71|2016-03-01:91.61|2016-04-01:91.81|2016-05-01:90.83|2016-06-01:91.16|2016-07-01:90.14|2016-08-01:89.7|2016-09-01:88.92|2016-10-01:89.43|2016-11-01:89.12|2016-12-01:88.87|2017-01-01:91.96|2017-02-01:92.26|2017-03-01:90.37|2017-04-01:92.44|2017-05-01:92.35|2017-06-01:93.57|2017-07-01:93.16|2017-08-01:92.43|2017-09-01:93.56|2017-10-01:92.94|2017-11-01:93.54|2017-12-01:93.66|2018-01-01:94.31|2018-02-01:93.78|2018-03-01:94.98|2018-04-01:96.4|2018-05-01:94.73|2018-06-01:93.91|2018-07-01:92.9|2018-08-01:95.49|2018-09-01:94.54|2018-10-01:94.04|2018-11-01:97.07|2018-12-01:95.24|2019-01-01:96.3|2019-02-01:95.51|2019-03-01:95.79|2019-04-01:95.62|2019-05-01:95.28|2019-06-01:94.71|2019-07-01:95.53|2019-08-01:95.6|2019-09-01:97.61|2019-10-01:97.78|2019-11-01:98.84|2019-12-01:99.61|2020-01-01:97.78|2020-02-01:98.13|2020-03-01:93.88|2020-04-01:78.83|2020-05-01:88.23|2020-06-01:95.35|2020-07-01:99.65|2020-08-01:102.57|2020-09-01:103.47|2020-10-01:104.57|2020-11-01:104.39|2020-12-01:100.62|2021-01-01:97.95|2021-02-01:98.69|2021-03-01:94.89|2021-04-01:97.3|2021-05-01:102.51|2021-06-01:100.75|2021-07-01:104.17|2021-08-01:99.32|2021-09-01:97.71|2021-10-01:98.11|2021-11-01:99.38|2021-12-01:98.44|2022-01-01:97.26|2022-02-01:99.33|2022-03-01:99.57|2022-04-01:100.41|2022-05-01:103.14|2022-06-01:100.2|2022-07-01:99.25|2022-08-01:99.95|2022-09-01:100.63|2022-10-01:101.17|2022-11-01:100.4|2022-12-01:99.33|2023-01-01:101.16|2023-02-01:100.93|2023-03-01:101.51|2023-04-01:101.54|2023-05-01:100.71|2023-06-01:101.53|2023-07-01:102.18|2023-08-01:102.32|2023-09-01:103|2023-10-01:102.4|2023-11-01:102.8|2023-12-01:102.61|2024-01-01:104.23|2024-02-01:104.3|2024-03-01:103.82|2024-04-01:105.23|2024-05-01:106.75|2024-06-01:105.21|2024-07-01:106.36|2024-08-01:106.02|2024-09-01:107|2024-10-01:107.25|2024-11-01:106.37|2024-12-01:106.41|2025-01-01:106.73|2025-02-01:107|2025-03-01:107.7|2025-04-01:107.93|2025-05-01:107.55|2025-06-01:107.1|2025-07-01:107.52|2025-08-01:107.6|2025-09-01:107.29|2025-10-01:107.9|2025-11-01:109.05|2025-12-01:108.27|2026-01-01:108.8|2026-02-01:109.61|2026-03-01:110.14|2026-04-01:108.9|2026-05-01:109.11|2026-06-01:109.45|2026-07-01:108.54|2026-08-01:108.69","28503":"2002-01-01:90.8|2002-02-01:92.7|2002-03-01:92.4|2002-04-01:92.6|2002-05-01:92.6|2002-06-01:92.8|2002-07-01:93.2|2002-08-01:92.2|2002-09-01:92.9|2002-10-01:93.2|2002-11-01:93|2002-12-01:92.8|2003-01-01:93|2003-02-01:92.6|2003-03-01:92.4|2003-04-01:92.3|2003-05-01:90.9|2003-06-01:91.4|2003-07-01:90.6|2003-08-01:91.7|2003-09-01:94.8|2003-10-01:95|2003-11-01:95.9|2003-12-01:94.7|2004-01-01:96.4|2004-02-01:97.8|2004-03-01:98.5|2004-04-01:99.2|2004-05-01:100.1|2004-06-01:100.5|2004-07-01:101.2|2004-08-01:102.2|2004-09-01:102.8|2004-10-01:102.1|2004-11-01:102.1|2004-12-01:102.8|2005-01-01:103.2|2005-02-01:101.8|2005-03-01:102.8|2005-04-01:102.9|2005-05-01:106.4|2005-06-01:104.1|2005-07-01:103.5|2005-08-01:103.7|2005-09-01:103|2005-10-01:102.5|2005-11-01:103.4|2005-12-01:105.2|2006-01-01:105.6|2006-02-01:106.4|2006-03-01:105.8|2006-04-01:106.3|2006-05-01:107.1|2006-06-01:105.7|2006-07-01:106.6|2006-08-01:106.4|2006-09-01:105.3|2006-10-01:106.2|2006-11-01:107.5|2006-12-01:108.2|2007-01-01:108.1|2007-02-01:109.3|2007-03-01:110.8|2007-04-01:111.9|2007-05-01:112.2|2007-06-01:112.9|2007-07-01:112.5|2007-08-01:114.1|2007-09-01:112.8|2007-10-01:116.2|2007-11-01:114.9|2007-12-01:115.3|2008-01-01:117.2|2008-02-01:116.9|2008-03-01:117.1|2008-04-01:117.3|2008-05-01:118.1|2008-06-01:119.6|2008-07-01:120.2|2008-08-01:118.8|2008-09-01:120.3|2008-10-01:116.9|2008-11-01:109.7|2008-12-01:97.7|2009-01-01:99.7|2009-02-01:102|2009-03-01:102.5|2009-04-01:103.9|2009-05-01:105.1|2009-06-01:106.7|2009-07-01:108|2009-08-01:109.7|2009-09-01:111.2|2009-10-01:113.7|2009-11-01:115.1|2009-12-01:115.6|2010-01-01:117.2|2010-02-01:117.1|2010-03-01:119.8|2010-04-01:120.2|2010-05-01:119.9|2010-06-01:119.4|2010-07-01:118.6|2010-08-01:118.3|2010-09-01:118.6|2010-10-01:118.2|2010-11-01:119.1|2010-12-01:119.6|2011-01-01:120|2011-02-01:121.4|2011-03-01:121.8|2011-04-01:118.8|2011-05-01:122.4|2011-06-01:120|2011-07-01:119.8|2011-08-01:119|2011-09-01:117.1|2011-10-01:115.7|2011-11-01:116.3|2011-12-01:119.4|2012-01-01:114.3|2012-02-01:115.2|2012-03-01:114.7|2012-04-01:114.6|2012-05-01:115.2|2012-06-01:115.5|2012-07-01:117|2012-08-01:119.5|2012-09-01:117.1|2012-10-01:118.9|2012-11-01:117.3|2012-12-01:118.1|2013-01-01:119.2|2013-02-01:115.7|2013-03-01:118.1|2013-04-01:120.1|2013-05-01:119.8|2013-06-01:120.2|2013-07-01:119.6|2013-08-01:119.9|2013-09-01:120.4|2013-10-01:119.1|2013-11-01:119.8|2013-12-01:115.6|2014-01-01:117.5|2014-02-01:118|2014-03-01:117.5|2014-04-01:116.6|2014-05-01:115.5|2014-06-01:112.1|2014-07-01:115|2014-08-01:115.4|2014-09-01:115.7|2014-10-01:115.7|2014-11-01:114.7|2014-12-01:111.7|2015-01-01:112.1|2015-02-01:111|2015-03-01:110.7|2015-04-01:108.5|2015-05-01:107.3|2015-06-01:106.5|2015-07-01:104.6|2015-08-01:105|2015-09-01:102.7|2015-10-01:102.4|2015-11-01:100.7|2015-12-01:99.3|2016-01-01:100|2016-02-01:99|2016-03-01:99.6|2016-04-01:99.6|2016-05-01:100|2016-06-01:98.6|2016-07-01:99.3|2016-08-01:97.5|2016-09-01:98.5|2016-10-01:97|2016-11-01:98.1|2016-12-01:99.8|2017-01-01:100.5|2017-02-01:101.5|2017-03-01:100|2017-04-01:99.9|2017-05-01:100.4|2017-06-01:101.3|2017-07-01:101.5|2017-08-01:101.6|2017-09-01:101.9|2017-10-01:102.8|2017-11-01:103.3|2017-12-01:106.1|2018-01-01:103.7|2018-02-01:103|2018-03-01:104.6|2018-04-01:104.9|2018-05-01:93.4|2018-06-01:105.1|2018-07-01:104.7|2018-08-01:103.8|2018-09-01:100.8|2018-10-01:102.3|2018-11-01:102.2|2018-12-01:102|2019-01-01:101.5|2019-02-01:101.8|2019-03-01:101.2|2019-04-01:101.9|2019-05-01:101.8|2019-06-01:100.8|2019-07-01:100.4|2019-08-01:101.4|2019-09-01:101.3|2019-10-01:103.6|2019-11-01:101.2|2019-12-01:99.8|2020-01-01:101.1|2020-02-01:101.9|2020-03-01:94|2020-04-01:75.4|2020-05-01:81.3|2020-06-01:89.7|2020-07-01:97.7|2020-08-01:100.6|2020-09-01:103.4|2020-10-01:105|2020-11-01:105.4|2020-12-01:104.9|2021-01-01:105.5|2021-02-01:104.1|2021-03-01:101.9|2021-04-01:100|2021-05-01:101.2|2021-06-01:100.9|2021-07-01:99.4|2021-08-01:99.4|2021-09-01:99.1|2021-10-01:98.6|2021-11-01:98.7|2021-12-01:100.2|2022-01-01:100|2022-02-01:100.9|2022-03-01:100.1|2022-04-01:100.7|2022-05-01:100.2|2022-06-01:100.2|2022-07-01:101.2|2022-08-01:99.8|2022-09-01:98.2|2022-10-01:99.8|2022-11-01:99.8|2022-12-01:100|2023-01-01:99.7|2023-02-01:99.6|2023-03-01:100.3|2023-04-01:99.8|2023-05-01:100.5|2023-06-01:100.2|2023-07-01:99.5|2023-08-01:100.1|2023-09-01:99.7|2023-10-01:100.1|2023-11-01:101.3|2023-12-01:103.1|2024-01-01:101.7|2024-02-01:101.7|2024-03-01:102|2024-04-01:101.7|2024-05-01:100.2|2024-06-01:105.2|2024-07-01:103.6|2024-08-01:103.4|2024-09-01:104.4|2024-10-01:104.4|2024-11-01:103.9|2024-12-01:103.7|2025-01-01:103.6|2025-02-01:103.1|2025-03-01:104.7|2025-04-01:104|2025-05-01:103.2|2025-06-01:104.1|2025-07-01:103.8|2025-08-01:104.7|2025-09-01:104.3|2025-10-01:104.4|2025-11-01:104.2|2025-12-01:102.1|2026-01-01:104.3|2026-02-01:105.2|2026-03-01:105.4|2026-04-01:106.6|2026-05-01:105.5|2026-06-01:103.8|2026-07-01:103.9|2026-08-01:103.3","28763":"1999-01-01:19789890|1999-02-01:19711860|1999-03-01:19635548|1999-04-01:19693091|1999-05-01:19790273|1999-06-01:19848382|1999-07-01:19856439|1999-08-01:19869745|1999-09-01:19876952|1999-10-01:19894391|1999-11-01:19878221|1999-12-01:19635100|2000-01-01:19666298|2000-02-01:19754473|2000-03-01:19794420|2000-04-01:19919491|2000-05-01:20082328|2000-06-01:20225212|2000-07-01:20331054|2000-08-01:20409899|2000-09-01:20502577|2000-10-01:20518019|2000-11-01:20518485|2000-12-01:20292696|2001-01-01:20341492|2001-02-01:20421735|2001-03-01:20456219|2001-04-01:20596216|2001-05-01:20758114|2001-06-01:20866685|2001-07-01:20938071|2001-08-01:20985398|2001-09-01:21065426|2001-10-01:21142613|2001-11-01:21137698|2001-12-01:20883775|2002-01-01:20928003|2002-02-01:21010016|2002-03-01:21100276|2002-04-01:21275366|2002-05-01:21431179|2002-06-01:21564525|2002-07-01:21625752|2002-08-01:21703774|2002-09-01:21871086|2002-10-01:21907454|2002-11-01:21895703|2002-12-01:21646189|2003-01-01:21681674|2003-02-01:21765703|2003-03-01:21786964|2003-04-01:21940988|2003-05-01:22081301|2003-06-01:22207096|2003-07-01:22244329|2003-08-01:22324101|2003-09-01:22485866|2003-10-01:22556736|2003-11-01:22591540|2003-12-01:22291622|2004-01-01:22419719|2004-02-01:22584795|2004-03-01:22711714|2004-04-01:22922230|2004-05-01:23243827|2004-06-01:23479779|2004-07-01:23713033|2004-08-01:23968056|2004-09-01:24204992|2004-10-01:24354569|2004-11-01:24449996|2004-12-01:24088157|2005-01-01:24239213|2005-02-01:24338522|2005-03-01:24468802|2005-04-01:24772612|2005-05-01:25019975|2005-06-01:25243684|2005-07-01:25388551|2005-08-01:25548277|2005-09-01:25777934|2005-10-01:25912359|2005-11-01:25940884|2005-12-01:25649690|2006-01-01:25768129|2006-02-01:25977571|2006-03-01:26081877|2006-04-01:26354540|2006-05-01:26588932|2006-06-01:26776333|2006-07-01:26960101|2006-08-01:27118303|2006-09-01:27327995|2006-10-01:27475073|2006-11-01:27522674|2006-12-01:27199292|2007-01-01:27339967|2007-02-01:27515702|2007-03-01:27687459|2007-04-01:28027785|2007-05-01:28272579|2007-06-01:28481921|2007-07-01:28637783|2007-08-01:28802305|2007-09-01:29094389|2007-10-01:29327221|2007-11-01:29471038|2007-12-01:29142342|2008-01-01:29319214|2008-02-01:29553502|2008-03-01:29780627|2008-04-01:30106498|2008-05-01:30334682|2008-06-01:30679650|2008-07-01:30912047|2008-08-01:31180865|2008-09-01:31491870|2008-10-01:31572367|2008-11-01:31544993|2008-12-01:30849632|2009-01-01:30782555|2009-02-01:30830362|2009-03-01:30899225|2009-04-01:31040331|2009-05-01:31209239|2009-06-01:31360617|2009-07-01:31534316|2009-08-01:31815732|2009-09-01:32115838|2009-10-01:32391960|2009-11-01:32673802|2009-12-01:32247477|2010-01-01:32487617|2010-02-01:32746092|2010-03-01:33068602|2010-04-01:33417963|2010-05-01:33767693|2010-06-01:34024669|2010-07-01:34244794|2010-08-01:34602578|2010-09-01:34898210|2010-10-01:35140146|2010-11-01:35297177|2010-12-01:34877304|2011-01-01:35079512|2011-02-01:35426582|2011-03-01:35552688|2011-04-01:35870131|2011-05-01:36158880|2011-06-01:36414298|2011-07-01:36591580|2011-08-01:36822199|2011-09-01:37073504|2011-10-01:37233632|2011-11-01:37306299|2011-12-01:36903911|2012-01-01:37084541|2012-02-01:37284920|2012-03-01:37450812|2012-04-01:37714422|2012-05-01:37910196|2012-06-01:38073423|2012-07-01:38257419|2012-08-01:38410907|2012-09-01:38613246|2012-10-01:38703389|2012-11-01:38779546|2012-12-01:38276505|2013-01-01:38352119|2013-02-01:38520967|2013-03-01:38703985|2013-04-01:38960210|2013-05-01:39071434|2013-06-01:39229503|2013-07-01:39302720|2013-08-01:39464880|2013-09-01:39722548|2013-10-01:39853413|2013-11-01:39922774|2013-12-01:39415067|2014-01-01:39478305|2014-02-01:39779699|2014-03-01:39814804|2014-04-01:39947519|2014-05-01:40034191|2014-06-01:40084764|2014-07-01:40115947|2014-08-01:40246851|2014-09-01:40415677|2014-10-01:40398645|2014-11-01:40417993|2014-12-01:39835757|2015-01-01:39773932|2015-02-01:39787105|2015-03-01:39823170|2015-04-01:39738389|2015-05-01:39629025|2015-06-01:39530163|2015-07-01:39380806|2015-08-01:39303486|2015-09-01:39215731|2015-10-01:39049063|2015-11-01:38915161|2015-12-01:38300768|2016-01-01:38208495|2016-02-01:38112161|2016-03-01:37997639|2016-04-01:37941817|2016-05-01:37875431|2016-06-01:37787711|2016-07-01:37703471|2016-08-01:37681385|2016-09-01:37649116|2016-10-01:37570351|2016-11-01:37452317|2016-12-01:36974210|2017-01-01:36943135|2017-02-01:36992764|2017-03-01:36935170|2017-04-01:37009552|2017-05-01:37054396|2017-06-01:37071247|2017-07-01:37122028|2017-08-01:37171470|2017-09-01:37220753|2017-10-01:37307678|2017-11-01:37302877|2017-12-01:36962246|2018-01-01:37053313|2018-02-01:37130344|2018-03-01:37205462|2018-04-01:37336922|2018-05-01:37379984|2018-06-01:37388381|2018-07-01:37446526|2018-08-01:37570270|2018-09-01:37721276|2018-10-01:37787881|2018-11-01:37851049|2018-12-01:37508691|2019-01-01:37553357|2019-02-01:37745860|2019-03-01:37707248|2019-04-01:37843632|2019-05-01:37884306|2019-06-01:37943836|2019-07-01:37995461|2019-08-01:38123292|2019-09-01:38285326|2019-10-01:38359484|2019-11-01:38460081|2019-12-01:38152770|2020-01-01:38267044|2020-02-01:38489146|2020-03-01:38131533|2020-04-01:37150202|2020-05-01:36752044|2020-06-01:36698667|2020-07-01:36807184|2020-08-01:37021815|2020-09-01:37321543|2020-10-01:37687567|2020-11-01:38063960|2020-12-01:37907718|2021-01-01:38162273|2021-02-01:38560116|2021-03-01:38714345|2021-04-01:38804651|2021-05-01:39071385|2021-06-01:39389518|2021-07-01:39696530|2021-08-01:40084367|2021-09-01:40414503|2021-10-01:40667384|2021-11-01:40981540|2021-12-01:40690220|2022-01-01:40857624|2022-02-01:41211077|2022-03-01:41310214|2022-04-01:41515688|2022-05-01:41793401|2022-06-01:42078636|2022-07-01:42303989|2022-08-01:42592887|2022-09-01:42871461|2022-10-01:43031969|2022-11-01:43159943|2022-12-01:42705233|2023-01-01:42795336|2023-02-01:43047793|2023-03-01:43242833|2023-04-01:43424731|2023-05-01:43580915|2023-06-01:43736746|2023-07-01:43879131|2023-08-01:44099047|2023-09-01:44303823|2023-10-01:44491077|2023-11-01:44612582|2023-12-01:44161013|2024-01-01:44334269|2024-02-01:44642071|2024-03-01:44887714|2024-04-01:45128050|2024-05-01:45267852|2024-06-01:45474479|2024-07-01:45666244|2024-08-01:45905621|2024-09-01:46157910|2024-10-01:46289414|2024-11-01:46395354|2024-12-01:45840107|2025-01-01:45994796|2025-02-01:46435317|2025-03-01:46515365|2025-04-01:46753538|2025-05-01:46906581|2025-06-01:47068521|2025-07-01:47202305|2025-08-01:47356988|2025-09-01:47571676|2025-10-01:47664273|2025-11-01:47745741|2025-12-01:47110663|2026-01-01:47228450|2026-02-01:47496606|2026-03-01:47724739|2026-04-01:47804347|2026-05-01:47885995|2026-06-01:48022954|2026-07-01:48078869|2026-08-01:48244696","3546":"1999-01-01:36136|1999-02-01:35457|1999-03-01:33848|1999-04-01:44315|1999-05-01:44310|1999-06-01:41346|1999-07-01:42156|1999-08-01:41918|1999-09-01:42562|1999-10-01:40053|1999-11-01:42175|1999-12-01:36342|2000-01-01:37560|2000-02-01:38364|2000-03-01:39200|2000-04-01:28721|2000-05-01:28570|2000-06-01:28265|2000-07-01:29214|2000-08-01:31385|2000-09-01:31431|2000-10-01:30393|2000-11-01:32533|2000-12-01:33011|2001-01-01:35598|2001-02-01:35413|2001-03-01:34407|2001-04-01:34653|2001-05-01:35459|2001-06-01:37318|2001-07-01:35552|2001-08-01:36299|2001-09-01:40054|2001-10-01:37492|2001-11-01:37234|2001-12-01:35866|2002-01-01:36167|2002-02-01:35906|2002-03-01:36721|2002-04-01:33008|2002-05-01:32889|2002-06-01:41999|2002-07-01:39060|2002-08-01:37643|2002-09-01:38381|2002-10-01:35855|2002-11-01:35592|2002-12-01:37823|2003-01-01:38772|2003-02-01:38530|2003-03-01:42335|2003-04-01:41500|2003-05-01:43373|2003-06-01:47956|2003-07-01:47645|2003-08-01:47793|2003-09-01:52675|2003-10-01:54093|2003-11-01:54427|2003-12-01:49296|2004-01-01:53261|2004-02-01:52960|2004-03-01:51612|2004-04-01:50498|2004-05-01:50540|2004-06-01:49805|2004-07-01:49666|2004-08-01:49594|2004-09-01:49496|2004-10-01:49416|2004-11-01:50133|2004-12-01:52935|2005-01-01:54022|2005-02-01:59017|2005-03-01:61960|2005-04-01:61591|2005-05-01:60709|2005-06-01:59885|2005-07-01:54688|2005-08-01:55076|2005-09-01:57008|2005-10-01:60245|2005-11-01:64277|2005-12-01:53799|2006-01-01:56924|2006-02-01:57415|2006-03-01:59824|2006-04-01:56552|2006-05-01:63381|2006-06-01:62670|2006-07-01:66819|2006-08-01:71478|2006-09-01:73393|2006-10-01:78171|2006-11-01:83114|2006-12-01:85839|2007-01-01:91086|2007-02-01:101070|2007-03-01:109531|2007-04-01:121830|2007-05-01:136419|2007-06-01:147101|2007-07-01:155910|2007-08-01:161097|2007-09-01:162962|2007-10-01:167867|2007-11-01:177060|2007-12-01:180334|2008-01-01:187507|2008-02-01:192902|2008-03-01:195232|2008-04-01:195767|2008-05-01:197906|2008-06-01:200827|2008-07-01:203562|2008-08-01:205116|2008-09-01:206494|2008-10-01:197229|2008-11-01:194668|2008-12-01:193783|2009-01-01:188102|2009-02-01:186880|2009-03-01:190388|2009-04-01:190546|2009-05-01:195264|2009-06-01:201467|2009-07-01:207363|2009-08-01:215744|2009-09-01:221629|2009-10-01:231123|2009-11-01:236660|2009-12-01:238520|2010-01-01:240484|2010-02-01:241082|2010-03-01:243762|2010-04-01:247292|2010-05-01:249846|2010-06-01:253114|2010-07-01:257299|2010-08-01:261320|2010-09-01:275206|2010-10-01:284930|2010-11-01:285461|2010-12-01:288575|2011-01-01:297696|2011-02-01:307516|2011-03-01:317146|2011-04-01:328062|2011-05-01:333017|2011-06-01:335775|2011-07-01:346144|2011-08-01:353397|2011-09-01:349708|2011-10-01:352928|2011-11-01:352073|2011-12-01:352012|2012-01-01:355075|2012-02-01:356330|2012-03-01:365216|2012-04-01:374272|2012-05-01:372409|2012-06-01:373910|2012-07-01:376154|2012-08-01:377221|2012-09-01:378726|2012-10-01:377753|2012-11-01:378560|2012-12-01:373147|2013-01-01:373417|2013-02-01:373742|2013-03-01:376934|2013-04-01:378665|2013-05-01:374417|2013-06-01:369402|2013-07-01:371966|2013-08-01:367002|2013-09-01:368654|2013-10-01:364505|2013-11-01:362410|2013-12-01:358808|2014-01-01:360936|2014-02-01:362691|2014-03-01:363914|2014-04-01:366717|2014-05-01:368752|2014-06-01:373516|2014-07-01:376792|2014-08-01:379157|2014-09-01:375513|2014-10-01:375833|2014-11-01:375426|2014-12-01:363551|2015-01-01:361767|2015-02-01:362547|2015-03-01:362744|2015-04-01:364473|2015-05-01:366647|2015-06-01:368668|2015-07-01:368252|2015-08-01:368159|2015-09-01:361370|2015-10-01:361230|2015-11-01:357016|2015-12-01:356464|2016-01-01:357507|2016-02-01:359368|2016-03-01:357698|2016-04-01:362201|2016-05-01:363447|2016-06-01:364152|2016-07-01:369340|2016-08-01:369541|2016-09-01:370417|2016-10-01:367528|2016-11-01:365556|2016-12-01:365016|2017-01-01:367708|2017-02-01:368981|2017-03-01:370111|2017-04-01:374945|2017-05-01:376491|2017-06-01:377175|2017-07-01:381029|2017-08-01:381843|2017-09-01:381244|2017-10-01:380351|2017-11-01:381056|2017-12-01:373972|2018-01-01:375701|2018-02-01:377035|2018-03-01:379577|2018-04-01:379979|2018-05-01:382549|2018-06-01:379500|2018-07-01:379444|2018-08-01:381393|2018-09-01:380738|2018-10-01:380290|2018-11-01:379722|2018-12-01:374715|2019-01-01:376984|2019-02-01:378448|2019-03-01:384165|2019-04-01:383799|2019-05-01:386162|2019-06-01:388092|2019-07-01:385730|2019-08-01:386478|2019-09-01:376434|2019-10-01:369836|2019-11-01:366376|2019-12-01:356884|2020-01-01:359394|2020-02-01:362460|2020-03-01:343165|2020-04-01:339317|2020-05-01:345706|2020-06-01:348781|2020-07-01:354664|2020-08-01:356092|2020-09-01:356606|2020-10-01:354546|2020-11-01:356004|2020-12-01:355620|2021-01-01:355416|2021-02-01:356070|2021-03-01:347413|2021-04-01:350996|2021-05-01:353448|2021-06-01:352486|2021-07-01:355671|2021-08-01:370395|2021-09-01:368886|2021-10-01:367927|2021-11-01:367772|2021-12-01:362204|2022-01-01:358398|2022-02-01:357740|2022-03-01:353169|2022-04-01:345097|2022-05-01:346415|2022-06-01:341958|2022-07-01:346403|2022-08-01:339664|2022-09-01:327580|2022-10-01:325546|2022-11-01:331505|2022-12-01:324703|2023-01-01:331122|2023-02-01:328098|2023-03-01:341158|2023-04-01:345725|2023-05-01:343489|2023-06-01:343620|2023-07-01:345476|2023-08-01:344177|2023-09-01:340324|2023-10-01:340247|2023-11-01:348406|2023-12-01:355034|2024-01-01:355066|2024-02-01:352705|2024-03-01:355008|2024-04-01:351599|2024-05-01:355560|2024-06-01:357827|2024-07-01:363282|2024-08-01:369214|2024-09-01:372016|2024-10-01:366096|2024-11-01:363003|2024-12-01:329730|2025-01-01:328303|2025-02-01:332508|2025-03-01:336157|2025-04-01:340789|2025-05-01:341459|2025-06-01:344440|2025-07-01:345111|2025-08-01:350767|2025-09-01:356582|2025-10-01:357103|2025-11-01:360578|2025-12-01:358234|2026-01-01:364367|2026-02-01:371074|2026-03-01:362002|2026-04-01:366913|2026-05-01:371137|2026-06-01:367558|2026-07-01:369742|2026-08-01:372616|2026-09-01:362821","13762":"2006-12-01:55.48|2007-01-01:56.17|2007-02-01:56.9|2007-03-01:57.24|2007-04-01:57.17|2007-05-01:57.91|2007-06-01:58.23|2007-07-01:58.32|2007-08-01:58.46|2007-09-01:57.88|2007-10-01:57.49|2007-11-01:57.26|2007-12-01:56.72|2008-01-01:57.51|2008-02-01:57.04|2008-03-01:57.09|2008-04-01:56.52|2008-05-01:55.82|2008-06-01:55.6|2008-07-01:55.53|2008-08-01:54.95|2008-09-01:54.83|2008-10-01:55.05|2008-11-01:54.64|2008-12-01:55.98|2009-01-01:56.87|2009-02-01:57.18|2009-03-01:57.47|2009-04-01:56.8|2009-05-01:57.07|2009-06-01:58.34|2009-07-01:59.68|2009-08-01:60.77|2009-09-01:60.8|2009-10-01:61|2009-11-01:60.22|2009-12-01:59.21|2010-01-01:59.76|2010-02-01:59.03|2010-03-01:56.24|2010-04-01:56.05|2010-05-01:55.96|2010-06-01:55.78|2010-07-01:55.53|2010-08-01:54.98|2010-09-01:54.89|2010-10-01:55.07|2010-11-01:54.65|2010-12-01:51.77|2011-01-01:52.4|2011-02-01:52.37|2011-03-01:52.61|2011-04-01:52.61|2011-05-01:52.22|2011-06-01:52.35|2011-07-01:52.52|2011-08-01:52.29|2011-09-01:52.11|2011-10-01:51.7|2011-11-01:51.76|2011-12-01:51.27|2012-01-01:51.83|2012-02-01:52.22|2012-03-01:52.72|2012-04-01:53.22|2012-05-01:53.27|2012-06-01:53.42|2012-07-01:53.6|2012-08-01:53.33|2012-09-01:54.05|2012-10-01:54.52|2012-11-01:54.65|2012-12-01:53.67|2013-01-01:53.98|2013-02-01:54.03|2013-03-01:54.05|2013-04-01:53.78|2013-05-01:53.92|2013-06-01:53.61|2013-07-01:53.7|2013-08-01:53.44|2013-09-01:52.95|2013-10-01:53.1|2013-11-01:52.73|2013-12-01:51.54|2014-01-01:52.63|2014-02-01:51.84|2014-03-01:51.79|2014-04-01:52|2014-05-01:52.18|2014-06-01:52.75|2014-07-01:53.17|2014-08-01:53.81|2014-09-01:55.11|2014-10-01:55.43|2014-11-01:56.01|2014-12-01:56.28|2015-01-01:57.16|2015-02-01:58.28|2015-03-01:59.49|2015-04-01:59.11|2015-05-01:60.21|2015-06-01:60.75|2015-07-01:62.17|2015-08-01:62.97|2015-09-01:63.65|2015-10-01:63.94|2015-11-01:64.29|2015-12-01:65.5|2016-01-01:66.5|2016-02-01:66.66|2016-03-01:66.33|2016-04-01:66.62|2016-05-01:67.58|2016-06-01:67.51|2016-07-01:68.7|2016-08-01:69.34|2016-09-01:69.98|2016-10-01:69.78|2016-11-01:70.84|2016-12-01:69.84|2017-01-01:69.82|2017-02-01:70.39|2017-03-01:71.24|2017-04-01:71.37|2017-05-01:72.34|2017-06-01:72.74|2017-07-01:73.18|2017-08-01:73.61|2017-09-01:73.71|2017-10-01:74.11|2017-11-01:74.02|2017-12-01:73.72|2018-01-01:74.04|2018-02-01:74.5|2018-03-01:74.6|2018-04-01:74.96|2018-05-01:76.12|2018-06-01:76.13|2018-07-01:75.95|2018-08-01:76.02|2018-09-01:75.99|2018-10-01:75.29|2018-11-01:75.69|2018-12-01:75.27|2019-01-01:75.44|2019-02-01:75.52|2019-03-01:76.71|2019-04-01:77.12|2019-05-01:76.55|2019-06-01:76.67|2019-07-01:76.83|2019-08-01:77.55|2019-09-01:76.6|2019-10-01:75.79|2019-11-01:76.2|2019-12-01:74.44|2020-01-01:74.75|2020-02-01:75.15|2020-03-01:76.78|2020-04-01:78.03|2020-05-01:79.95|2020-06-01:82.87|2020-07-01:83.5|2020-08-01:85.83|2020-09-01:87.42|2020-10-01:87.66|2020-11-01:86.96|2020-12-01:86.94|2021-01-01:86.91|2021-02-01:86.87|2021-03-01:85.1|2021-04-01:82.62|2021-05-01:81.44|2021-06-01:80.6|2021-07-01:80.25|2021-08-01:79.64|2021-09-01:79.62|2021-10-01:79.52|2021-11-01:78.22|2021-12-01:77.31|2022-01-01:77|2022-02-01:76.92|2022-03-01:76.4|2022-04-01:76.33|2022-05-01:75.68|2022-06-01:75.61|2022-07-01:75.24|2022-08-01:74.57|2022-09-01:74.15|2022-10-01:73.7|2022-11-01:72.95|2022-12-01:71.68|2023-01-01:71.38|2023-02-01:71.77|2023-03-01:71.54|2023-04-01:71.57|2023-05-01:72.11|2023-06-01:71.97|2023-07-01:72.48|2023-08-01:72.89|2023-09-01:73.01|2023-10-01:73.32|2023-11-01:73.32|2023-12-01:73.83|2024-01-01:74.47|2024-02-01:74.81|2024-03-01:75.02|2024-04-01:75.15|2024-05-01:75.67|2024-06-01:76.68|2024-07-01:77.21|2024-08-01:77.36|2024-09-01:77.09|2024-10-01:77.38|2024-11-01:77.5|2024-12-01:76.27|2025-01-01:75.48|2025-02-01:75.78|2025-03-01:75.55|2025-04-01:75.62|2025-05-01:75.75|2025-06-01:76.3|2025-07-01:77.18|2025-08-01:77.31|2025-09-01:77.84|2025-10-01:78.29|2025-11-01:78.95|2025-12-01:78.64|2026-01-01:78.7|2026-02-01:79.13|2026-03-01:79.88|2026-04-01:80.09|2026-05-01:81.04|2026-06-01:81.95|2026-07-01:82.55|2026-08-01:82.87","20715":"2011-03-01:19.33|2011-04-01:19.86|2011-05-01:19.84|2011-06-01:19.63|2011-07-01:19.64|2011-08-01:19.2|2011-09-01:19.13|2011-10-01:18.91|2011-11-01:18.43|2011-12-01:18.14|2012-01-01:19.06|2012-02-01:18.8|2012-03-01:18.49|2012-04-01:18.04|2012-05-01:16.77|2012-06-01:16.04|2012-07-01:15.7|2012-08-01:15.54|2012-09-01:15.17|2012-10-01:14.7|2012-11-01:14.77|2012-12-01:13.82|2013-01-01:14.57|2013-02-01:14.65|2013-03-01:14.65|2013-04-01:14.61|2013-05-01:14.34|2013-06-01:14.73|2013-07-01:14.96|2013-08-01:15.2|2013-09-01:15.27|2013-10-01:15.39|2013-11-01:15.73|2013-12-01:15.64|2014-01-01:16.52|2014-02-01:16.62|2014-03-01:16.53|2014-04-01:16.68|2014-05-01:16.81|2014-06-01:16.37|2014-07-01:16.66|2014-08-01:16.43|2014-09-01:16.46|2014-10-01:16.67|2014-11-01:16.66|2014-12-01:16.6|2015-01-01:17.54|2015-02-01:18.13|2015-03-01:18.2|2015-04-01:18.64|2015-05-01:18.85|2015-06-01:19.19|2015-07-01:19.74|2015-08-01:20.18|2015-09-01:20.73|2015-10-01:21.18|2015-11-01:21.29|2015-12-01:20.77|2016-01-01:22.49|2016-02-01:22.74|2016-03-01:22.21|2016-04-01:22.01|2016-05-01:21.68|2016-06-01:21.68|2016-07-01:22.19|2016-08-01:22.26|2016-09-01:21.49|2016-10-01:21.8|2016-11-01:21.21|2016-12-01:20.29|2017-01-01:21.4|2017-02-01:20.43|2017-03-01:20.33|2017-04-01:19.48|2017-05-01:19.27|2017-06-01:18.9|2017-07-01:19.11|2017-08-01:18.88|2017-09-01:17.62|2017-10-01:18.37|2017-11-01:17.89|2017-12-01:16.96|2018-01-01:17.81|2018-02-01:17.87|2018-03-01:16.55|2018-04-01:15.95|2018-05-01:15.79|2018-06-01:15.59|2018-07-01:15.86|2018-08-01:15.87|2018-09-01:15.83|2018-10-01:16.19|2018-11-01:15.97|2018-12-01:14.84|2019-01-01:16.26|2019-02-01:15.91|2019-03-01:15.88|2019-04-01:15.97|2019-05-01:15.7|2019-06-01:15.01|2019-07-01:15.11|2019-08-01:14.98|2019-09-01:14.1|2019-10-01:14.02|2019-11-01:13.74|2019-12-01:13.48|2020-01-01:14.95|2020-02-01:13.84|2020-03-01:13.72|2020-04-01:13.07|2020-05-01:12.17|2020-06-01:10.85|2020-07-01:10.65|2020-08-01:10.79|2020-09-01:9.98|2020-10-01:10.68|2020-11-01:10.87|2020-12-01:11.16|2021-01-01:13.53|2021-02-01:12.24|2021-03-01:12.21|2021-04-01:12.95|2021-05-01:12.65|2021-06-01:12.83|2021-07-01:13.76|2021-08-01:14.55|2021-09-01:14.99|2021-10-01:16.71|2021-11-01:17.85|2021-12-01:17.42|2022-01-01:18.57|2022-02-01:18.63|2022-03-01:18.83|2022-04-01:20.52|2022-05-01:19.38|2022-06-01:19.67|2022-07-01:21.44|2022-08-01:18.99|2022-09-01:19.34|2022-10-01:19.66|2022-11-01:20.19|2022-12-01:20.04|2023-01-01:21.8|2023-02-01:20.87|2023-03-01:21.05|2023-04-01:20.87|2023-05-01:20.61|2023-06-01:19.62|2023-07-01:19.46|2023-08-01:19.14|2023-09-01:19.52|2023-10-01:19.52|2023-11-01:19.03|2023-12-01:18.09|2024-01-01:19.47|2024-02-01:18.69|2024-03-01:18.56|2024-04-01:18.22|2024-05-01:17.89|2024-06-01:18.09|2024-07-01:18.13|2024-08-01:18.13|2024-09-01:17.45|2024-10-01:18.64|2024-11-01:19.04|2024-12-01:19.05|2025-01-01:21.18|2025-02-01:20.48|2025-03-01:21.81|2025-04-01:21.49|2025-05-01:20.99|2025-06-01:21.06|2025-07-01:21.59|2025-08-01:21.5|2025-09-01:20.55|2025-10-01:21.66|2025-11-01:20.43|2025-12-01:19.9|2026-01-01:20.99|2026-02-01:20.79|2026-03-01:21.12|2026-04-01:21.72|2026-05-01:21.24|2026-06-01:20.74|2026-07-01:20.81|2026-08-01:19.75","20716":"2011-03-01:36.42|2011-04-01:37.03|2011-05-01:36.89|2011-06-01:36.57|2011-07-01:36.89|2011-08-01:36.12|2011-09-01:36.23|2011-10-01:36.9|2011-11-01:35.79|2011-12-01:34.01|2012-01-01:34.97|2012-02-01:35.3|2012-03-01:35.01|2012-04-01:34.3|2012-05-01:32.34|2012-06-01:31.58|2012-07-01:30.71|2012-08-01:29.84|2012-09-01:29.78|2012-10-01:29.05|2012-11-01:28.47|2012-12-01:27.32|2013-01-01:27.38|2013-02-01:27.96|2013-03-01:27.42|2013-04-01:27.21|2013-05-01:26.93|2013-06-01:27.06|2013-07-01:27.62|2013-08-01:27.73|2013-09-01:28.01|2013-10-01:28.62|2013-11-01:28.71|2013-12-01:28.19|2014-01-01:29.18|2014-02-01:30.14|2014-03-01:30.53|2014-04-01:30.14|2014-05-01:30.34|2014-06-01:30.5|2014-07-01:30.66|2014-08-01:30.67|2014-09-01:29.95|2014-10-01:30.75|2014-11-01:30.87|2014-12-01:30.02|2015-01-01:31.39|2015-02-01:32.23|2015-03-01:32.51|2015-04-01:33.25|2015-05-01:34.19|2015-06-01:34.88|2015-07-01:35.82|2015-08-01:36.37|2015-09-01:36.86|2015-10-01:37.91|2015-11-01:38.26|2015-12-01:37.37|2016-01-01:38.87|2016-02-01:39.47|2016-03-01:40.19|2016-04-01:41.03|2016-05-01:41.4|2016-06-01:41.06|2016-07-01:41.33|2016-08-01:41.43|2016-09-01:42.06|2016-10-01:42.25|2016-11-01:42.29|2016-12-01:41.2|2017-01-01:41.43|2017-02-01:40.73|2017-03-01:40.61|2017-04-01:37.84|2017-05-01:36|2017-06-01:35.8|2017-07-01:36.35|2017-08-01:35.53|2017-09-01:33.58|2017-10-01:33.85|2017-11-01:33.19|2017-12-01:31.57|2018-01-01:31.89|2018-02-01:32.79|2018-03-01:32.54|2018-04-01:32.49|2018-05-01:30.91|2018-06-01:30.48|2018-07-01:30|2018-08-01:29.86|2018-09-01:29.8|2018-10-01:29.95|2018-11-01:29.99|2018-12-01:28.63|2019-01-01:29.99|2019-02-01:30.62|2019-03-01:31.09|2019-04-01:31.09|2019-05-01:30.94|2019-06-01:31.1|2019-07-01:30.8|2019-08-01:30.93|2019-09-01:30.22|2019-10-01:29.45|2019-11-01:29.71|2019-12-01:28.28|2020-01-01:28.12|2020-02-01:28.71|2020-03-01:28.33|2020-04-01:26.8|2020-05-01:26.12|2020-06-01:24.61|2020-07-01:24.27|2020-08-01:23.53|2020-09-01:23.09|2020-10-01:23.58|2020-11-01:23.14|2020-12-01:22.65|2021-01-01:23.81|2021-02-01:24.17|2021-03-01:24.49|2021-04-01:24.76|2021-05-01:24.12|2021-06-01:24.18|2021-07-01:24.15|2021-08-01:24.68|2021-09-01:25.23|2021-10-01:26.51|2021-11-01:27.41|2021-12-01:28.19|2022-01-01:29.1|2022-02-01:29.66|2022-03-01:30.99|2022-04-01:31.45|2022-05-01:32.03|2022-06-01:32.58|2022-07-01:33.67|2022-08-01:33.97|2022-09-01:33.7|2022-10-01:35.22|2022-11-01:36.09|2022-12-01:34.86|2023-01-01:35.27|2023-02-01:35.59|2023-03-01:36.2|2023-04-01:37.2|2023-05-01:37.28|2023-06-01:36.59|2023-07-01:36.03|2023-08-01:35.37|2023-09-01:34.82|2023-10-01:34.18|2023-11-01:34|2023-12-01:33.2|2024-01-01:32.25|2024-02-01:32.34|2024-03-01:32.84|2024-04-01:32.6|2024-05-01:32.53|2024-06-01:32.54|2024-07-01:32.42|2024-08-01:32.12|2024-09-01:32.3|2024-10-01:32.4|2024-11-01:32.94|2024-12-01:33.07|2025-01-01:34.03|2025-02-01:35.33|2025-03-01:35.83|2025-04-01:36.41|2025-05-01:36.63|2025-06-01:36.84|2025-07-01:36.41|2025-08-01:36.6|2025-09-01:36.5|2025-10-01:36.79|2025-11-01:37.89|2025-12-01:37.73|2026-01-01:38.03|2026-02-01:38.34|2026-03-01:38.45|2026-04-01:38.93|2026-05-01:38.56|2026-06-01:38.34|2026-07-01:37.46|2026-08-01:38.18","22110":"1999-01-01:104.97|1999-04-01:105.03|1999-07-01:106.08|1999-10-01:107.94|2000-01-01:107.97|2000-04-01:109.42|2000-07-01:111.31|2000-10-01:112.36|2001-01-01:112.16|2001-04-01:112.79|2001-07-01:109.41|2001-10-01:110.27|2002-01-01:112.31|2002-04-01:113.59|2002-07-01:112.48|2002-10-01:112.02|2003-01-01:112.25|2003-04-01:111.3|2003-07-01:111.69|2003-10-01:112.65|2004-01-01:113.25|2004-04-01:114.8|2004-07-01:117.16|2004-10-01:120.04|2005-01-01:119.32|2005-04-01:120.32|2005-07-01:122.24|2005-10-01:124.01|2006-01-01:125.28|2006-04-01:127.27|2006-07-01:128.61|2006-10-01:130.45|2007-01-01:133.31|2007-04-01:135.07|2007-07-01:135.95|2007-10-01:139.88|2008-01-01:142.89|2008-04-01:144.53|2008-07-01:147.25|2008-10-01:144.86|2009-01-01:146.12|2009-04-01:150.31|2009-07-01:153.8|2009-10-01:154.89|2010-01-01:157.01|2010-04-01:158.5|2010-07-01:161.97|2010-10-01:165.38|2011-01-01:166.94|2011-04-01:169.18|2011-07-01:168.51|2011-10-01:169.4|2012-01-01:171.77|2012-04-01:173.1|2012-07-01:175.35|2012-10-01:177.29|2013-01-01:178.16|2013-04-01:180.48|2013-07-01:181.61|2013-10-01:181.5|2014-01-01:184.46|2014-04-01:183.46|2014-07-01:183.66|2014-10-01:186.42|2015-01-01:183.23|2015-04-01:179.72|2015-07-01:176.42|2015-10-01:175.2|2016-01-01:172.92|2016-04-01:171.89|2016-07-01:171.28|2016-10-01:170.87|2017-01-01:171.97|2017-04-01:174.8|2017-07-01:176.5|2017-10-01:177.04|2018-01-01:178.37|2018-04-01:178.79|2018-07-01:179.8|2018-10-01:180|2019-01-01:182.56|2019-04-01:183.28|2019-07-01:184.33|2019-10-01:185.38|2020-01-01:183.45|2020-04-01:162.8|2020-07-01:174.69|2020-10-01:180.91|2021-01-01:180.92|2021-04-01:178.42|2021-07-01:181.08|2021-10-01:182.48|2022-01-01:184.21|2022-04-01:187.96|2022-07-01:189.37|2022-10-01:191.34|2023-01-01:191.63|2023-04-01:193.52|2023-07-01:195.3|2023-10-01:196.92|2024-01-01:201.49|2024-04-01:203.79|2024-07-01:206.54|2024-10-01:205.27|2025-01-01:205.75|2025-04-01:207.36|2025-07-01:207.24|2025-10-01:207.45|2026-01-01:209.2|2026-04-01:208.27","22111":"1999-01-01:101.93|1999-04-01:103.08|1999-07-01:105.22|1999-10-01:107.18|2000-01-01:105.31|2000-04-01:104.37|2000-07-01:102.96|2000-10-01:104.11|2001-01-01:106.35|2001-04-01:106.64|2001-07-01:106.68|2001-10-01:107.96|2002-01-01:110.8|2002-04-01:110.93|2002-07-01:111.15|2002-10-01:111.05|2003-01-01:110.01|2003-04-01:111.19|2003-07-01:113.38|2003-10-01:116.34|2004-01-01:114.1|2004-04-01:118.31|2004-07-01:118.24|2004-10-01:117.76|2005-01-01:118.35|2005-04-01:119.01|2005-07-01:120.25|2005-10-01:120.22|2006-01-01:121.84|2006-04-01:121.89|2006-07-01:123.32|2006-10-01:127.85|2007-01-01:126.96|2007-04-01:130.02|2007-07-01:129.33|2007-10-01:128.67|2008-01-01:130.76|2008-04-01:130.59|2008-07-01:134.4|2008-10-01:129.82|2009-01-01:134.92|2009-04-01:133.32|2009-07-01:134.79|2009-10-01:137.97|2010-01-01:139.08|2010-04-01:139.94|2010-07-01:141.31|2010-10-01:141.82|2011-01-01:142.93|2011-04-01:144.33|2011-07-01:143.76|2011-10-01:143.44|2012-01-01:146.31|2012-04-01:147.16|2012-07-01:146.42|2012-10-01:147.73|2013-01-01:146.47|2013-04-01:148.79|2013-07-01:149.84|2013-10-01:151.42|2014-01-01:149.62|2014-04-01:150.59|2014-07-01:151.22|2014-10-01:149.97|2015-01-01:149.27|2015-04-01:148.09|2015-07-01:148.36|2015-10-01:147.08|2016-01-01:149.22|2016-04-01:148.8|2016-07-01:148.22|2016-10-01:147.89|2017-01-01:147.01|2017-04-01:147.27|2017-07-01:147.12|2017-10-01:148.69|2018-01-01:148.58|2018-04-01:148.94|2018-07-01:149.56|2018-10-01:147.6|2019-01-01:148.21|2019-04-01:148.14|2019-07-01:147.76|2019-10-01:147.67|2020-01-01:148.28|2020-04-01:136.32|2020-07-01:141.04|2020-10-01:144.28|2021-01-01:145.57|2021-04-01:147.45|2021-07-01:149.4|2021-10-01:151.29|2022-01-01:151.45|2022-04-01:150.13|2022-07-01:153.07|2022-10-01:151.76|2023-01-01:153.87|2023-04-01:157.49|2023-07-01:158.14|2023-10-01:159.86|2024-01-01:159.28|2024-04-01:160.91|2024-07-01:161.69|2024-10-01:160.09|2025-01-01:162.44|2025-04-01:162.41|2025-07-01:164.55|2025-10-01:166.13|2026-01-01:166.74|2026-04-01:167.44","22707":"1999-01-01:-792.7|1999-02-01:38.8|1999-03-01:-325.2|1999-04-01:-66.2|1999-05-01:214.4|1999-06-01:-235|1999-07-01:8.5|1999-08-01:-274.3|1999-09-01:-25.8|1999-10-01:-201.4|1999-11-01:-564.7|1999-12-01:161.4|2000-01-01:-174|2000-02-01:48.7|2000-03-01:-78|2000-04-01:94.3|2000-05-01:307.9|2000-06-01:163.3|2000-07-01:111.9|2000-08-01:32.2|2000-09-01:-453.3|2000-10-01:-695.8|2000-11-01:-863.4|2000-12-01:-282.5|2001-01-01:-557|2001-02-01:-23.9|2001-03-01:-366.6|2001-04-01:28.7|2001-05-01:106.5|2001-06-01:191.4|2001-07-01:20|2001-08-01:548.3|2001-09-01:511.9|2001-10-01:119.8|2001-11-01:201|2001-12-01:756.6|2002-01-01:103.9|2002-02-01:172.8|2002-03-01:514.6|2002-04-01:396.6|2002-05-01:269.3|2002-06-01:569.1|2002-07-01:1105.3|2002-08-01:1501.5|2002-09-01:2410.5|2002-10-01:2088.5|2002-11-01:1160.3|2002-12-01:1711.3|2003-01-01:1059.3|2003-02-01:1022.7|2003-03-01:1437.3|2003-04-01:1616.2|2003-05-01:2434.4|2003-06-01:2262.3|2003-07-01:1964.7|2003-08-01:2585.1|2003-09-01:2558.6|2003-10-01:2424.8|2003-11-01:1567.3|2003-12-01:2643.4|2004-01-01:1507.1|2004-02-01:1897.7|2004-03-01:2462.5|2004-04-01:1841.5|2004-05-01:2995.7|2004-06-01:3668|2004-07-01:3321.6|2004-08-01:3317.9|2004-09-01:3044.2|2004-10-01:2879.3|2004-11-01:1959.7|2004-12-01:3388.5|2005-01-01:2132.4|2005-02-01:2709.5|2005-03-01:3259.8|2005-04-01:3811.4|2005-05-01:3363|2005-06-01:3909.8|2005-07-01:4914.3|2005-08-01:3536.8|2005-09-01:4235.9|2005-10-01:3568|2005-11-01:3962.1|2005-12-01:4318.5|2006-01-01:2758.4|2006-02-01:2711.6|2006-03-01:3582.9|2006-04-01:2957.3|2006-05-01:2884.7|2006-06-01:3959.6|2006-07-01:5518.8|2006-08-01:4504.4|2006-09-01:4326.5|2006-10-01:3835|2006-11-01:3187.7|2006-12-01:4951|2007-01-01:2443.8|2007-02-01:2780.3|2007-03-01:3278.5|2007-04-01:4062.1|2007-05-01:3738.8|2007-06-01:3665.1|2007-07-01:3220.3|2007-08-01:3415.9|2007-09-01:3306.4|2007-10-01:3240.7|2007-11-01:1854|2007-12-01:3492.3|2008-01-01:823.1|2008-02-01:710.7|2008-03-01:853.3|2008-04-01:1597.6|2008-05-01:3947|2008-06-01:2574.7|2008-07-01:3205|2008-08-01:2190.8|2008-09-01:2604|2008-10-01:1259.4|2008-11-01:1480.8|2008-12-01:2260.4|2009-01-01:-541.7|2009-02-01:1724.2|2009-03-01:1727.7|2009-04-01:3672|2009-05-01:2551.3|2009-06-01:4654.8|2009-07-01:2864.4|2009-08-01:3000.7|2009-09-01:1232.8|2009-10-01:1297.8|2009-11-01:490|2009-12-01:2116.2|2010-01-01:-324.4|2010-02-01:259.8|2010-03-01:545.3|2010-04-01:1139.1|2010-05-01:3288.4|2010-06-01:2104.2|2010-07-01:1208.2|2010-08-01:2265.4|2010-09-01:935.9|2010-10-01:1681.2|2010-11-01:122.7|2010-12-01:5132.1|2011-01-01:184.6|2011-02-01:986.3|2011-03-01:1361.5|2011-04-01:1633.5|2011-05-01:3318.5|2011-06-01:4263.7|2011-07-01:2968.3|2011-08-01:3710.3|2011-09-01:2899.3|2011-10-01:2170.1|2011-11-01:372.2|2011-12-01:3656.8|2012-01-01:-1558|2012-02-01:1513.1|2012-03-01:1811.3|2012-04-01:666.9|2012-05-01:2771.9|2012-06-01:610.1|2012-07-01:2682.1|2012-08-01:3018.9|2012-09-01:2362.9|2012-10-01:1357.6|2012-11-01:-375.1|2012-12-01:2046.8|2013-01-01:-4183.8|2013-02-01:-1440.6|2013-03-01:15.4|2013-04-01:-1161.2|2013-05-01:593.8|2013-06-01:2126.9|2013-07-01:-2072.5|2013-08-01:1025.9|2013-09-01:1794.4|2013-10-01:-402.9|2013-11-01:1533.3|2013-12-01:2540.2|2014-01-01:-3890.6|2014-02-01:-2344|2014-03-01:-140|2014-04-01:285.3|2014-05-01:423.9|2014-06-01:2122.5|2014-07-01:1291.1|2014-08-01:903.2|2014-09-01:-1145.1|2014-10-01:-1473.2|2014-11-01:-2707.2|2014-12-01:-65.1|2015-01-01:-2877.8|2015-02-01:-3097.7|2015-03-01:148.9|2015-04-01:272.6|2015-05-01:2449.9|2015-06-01:4309.9|2015-07-01:2625.7|2015-08-01:2366|2015-09-01:2624.1|2015-10-01:1676.4|2015-11-01:898.9|2015-12-01:6048|2016-01-01:1116.2|2016-02-01:2777.9|2016-03-01:4123.3|2016-04-01:4542.3|2016-05-01:6127.1|2016-06-01:3631.6|2016-07-01:4245.1|2016-08-01:3830.9|2016-09-01:3522.7|2016-10-01:2039.4|2016-11-01:4448.4|2016-12-01:4139.2|2017-01-01:2427|2017-02-01:4368.2|2017-03-01:6418.6|2017-04-01:6125.7|2017-05-01:6712.1|2017-06-01:6268.8|2017-07-01:5383.9|2017-08-01:4547.9|2017-09-01:4301.4|2017-10-01:4128.1|2017-11-01:2576.3|2017-12-01:4141.1|2018-01-01:1771|2018-02-01:2021.5|2018-03-01:5419.4|2018-04-01:4586.2|2018-05-01:5039.5|2018-06-01:4675.1|2018-07-01:2717|2018-08-01:1414.9|2018-09-01:3949.4|2018-10-01:4534|2018-11-01:2822.7|2018-12-01:5397.6|2019-01-01:195.7|2019-02-01:1819|2019-03-01:2994.8|2019-04-01:4139.7|2019-05-01:4112.2|2019-06-01:3935.6|2019-07-01:681.4|2019-08-01:1504.3|2019-09-01:2393.6|2019-10-01:954.9|2019-11-01:2102.2|2019-12-01:4734|2020-01-01:-3284.7|2020-02-01:931.5|2020-03-01:2297.1|2020-04-01:4890.9|2020-05-01:3239.3|2020-06-01:6109.4|2020-07-01:6895.9|2020-08-01:5226.2|2020-09-01:4741|2020-10-01:3960.1|2020-11-01:2121.4|2020-12-01:-1464.4|2021-01-01:-2200.5|2021-02-01:28.2|2021-03-01:-158.4|2021-04-01:9337.7|2021-05-01:8132.8|2021-06-01:8146.5|2021-07-01:6844|2021-08-01:6155.4|2021-09-01:2947.9|2021-10-01:1617.5|2021-11-01:-1760.3|2021-12-01:3221.3|2022-01-01:-832|2022-02-01:4044.2|2022-03-01:6681.2|2022-04-01:7522.7|2022-05-01:4269.3|2022-06-01:8032.6|2022-07-01:4624|2022-08-01:3237.8|2022-09-01:2548.4|2022-10-01:2568|2022-11-01:5299.9|2022-12-01:3525.7|2023-01-01:1659.5|2023-02-01:2838.3|2023-03-01:10014.5|2023-04-01:8126.6|2023-05-01:10264.7|2023-06-01:9298.8|2023-07-01:7586.1|2023-08-01:8840.3|2023-09-01:8476.1|2023-10-01:8589.3|2023-11-01:7999.4|2023-12-01:8581.8|2024-01-01:5562.8|2024-02-01:4386.8|2024-03-01:6352.1|2024-04-01:7798.3|2024-05-01:7503.1|2024-06-01:5661.1|2024-07-01:6981.5|2024-08-01:3717.8|2024-09-01:4524.5|2024-10-01:3189.2|2024-11-01:6043|2024-12-01:4121.9|2025-01-01:1396.3|2025-02-01:-1122.8|2025-03-01:7218.6|2025-04-01:6957.2|2025-05-01:6436.8|2025-06-01:5247|2025-07-01:6390.5|2025-08-01:5311.4|2025-09-01:2459.5|2025-10-01:5890.3|2025-11-01:5038.2|2025-12-01:8505.4|2026-01-01:2944.4|2026-02-01:3352|2026-03-01:5672.1|2026-04-01:9806.2|2026-05-01:6537.1|2026-06-01:8076.9|2026-07-01:5503.1|2026-08-01:6136.3|2026-09-01:6868.8","22708":"1999-01-01:2953.5|1999-02-01:3274.6|1999-03-01:3809.3|1999-04-01:3691.3|1999-05-01:4386.3|1999-06-01:4310.9|1999-07-01:4123.4|1999-08-01:4274.2|1999-09-01:4294.2|1999-10-01:4338.4|1999-11-01:4053.1|1999-12-01:4688.1|2000-01-01:3480.5|2000-02-01:4181.7|2000-03-01:4457.3|2000-04-01:4172.6|2000-05-01:5084.2|2000-06-01:4845|2000-07-01:5072.3|2000-08-01:5534.1|2000-09-01:4690.3|2000-10-01:4631.4|2000-11-01:4370.8|2000-12-01:4667.2|2001-01-01:4531.2|2001-02-01:4062.8|2001-03-01:5164|2001-04-01:4722.4|2001-05-01:5343.1|2001-06-01:5034.2|2001-07-01:4958.3|2001-08-01:5724.4|2001-09-01:4758.1|2001-10-01:4957.5|2001-11-01:4500.7|2001-12-01:4349|2002-01-01:3990.3|2002-02-01:3656.4|2002-03-01:4263.8|2002-04-01:4622.4|2002-05-01:4423.6|2002-06-01:4057.2|2002-07-01:6211.2|2002-08-01:5759.6|2002-09-01:6497.9|2002-10-01:6458.4|2002-11-01:5096.4|2002-12-01:5241.3|2003-01-01:4799.3|2003-02-01:4995.8|2003-03-01:5224.3|2003-04-01:5697.7|2003-05-01:6380.8|2003-06-01:5866.2|2003-07-01:6087.4|2003-08-01:6396.7|2003-09-01:7261|2003-10-01:7532.8|2003-11-01:5915.6|2003-12-01:6725.9|2004-01-01:5800.9|2004-02-01:5731.5|2004-03-01:7885.4|2004-04-01:6555.2|2004-05-01:7913.7|2004-06-01:9282.8|2004-07-01:8935|2004-08-01:9026.2|2004-09-01:8879.1|2004-10-01:8811.4|2004-11-01:8120.8|2004-12-01:9155.6|2005-01-01:7482.2|2005-02-01:7781.5|2005-03-01:9258.3|2005-04-01:9235.2|2005-05-01:9825.9|2005-06-01:10167.1|2005-07-01:11062.1|2005-08-01:11321.1|2005-09-01:10637.3|2005-10-01:9895|2005-11-01:10768.4|2005-12-01:10979.6|2006-01-01:9310.7|2006-02-01:8784|2006-03-01:11397.7|2006-04-01:9803.2|2006-05-01:10268.3|2006-06-01:11423.9|2006-07-01:13604|2006-08-01:13716.6|2006-09-01:12534.2|2006-10-01:12665.3|2006-11-01:11948.8|2006-12-01:12252|2007-01-01:11006.8|2007-02-01:10121.1|2007-03-01:12906.5|2007-04-01:12444.8|2007-05-01:13643.2|2007-06-01:13082.3|2007-07-01:14117.1|2007-08-01:15099.4|2007-09-01:14139.4|2007-10-01:15721.9|2007-11-01:14029.8|2007-12-01:14228|2008-01-01:13310.9|2008-02-01:12810.7|2008-03-01:12626.2|2008-04-01:14075.4|2008-05-01:19321.6|2008-06-01:18591.5|2008-07-01:20484.4|2008-08-01:19787.2|2008-09-01:20007.3|2008-10-01:18588.8|2008-11-01:14717.2|2008-12-01:13892.7|2009-01-01:9855.3|2009-02-01:9641.6|2009-03-01:11863.9|2009-04-01:12364.4|2009-05-01:11988.9|2009-06-01:14606.1|2009-07-01:14208.2|2009-08-01:13876.4|2009-09-01:13865.9|2009-10-01:14142.6|2009-11-01:12617.2|2009-12-01:14494.8|2010-01-01:11254.1|2010-02-01:12151.8|2010-03-01:15669.9|2010-04-01:15104.1|2010-05-01:17633.6|2010-06-01:17033.6|2010-07-01:17638.2|2010-08-01:19172.9|2010-09-01:18778.9|2010-10-01:18323.5|2010-11-01:17629.8|2010-12-01:20806.7|2011-01-01:15140.2|2011-02-01:16667|2011-03-01:19227.7|2011-04-01:20092.8|2011-05-01:23146.5|2011-06-01:23663.5|2011-07-01:22215.4|2011-08-01:26106.4|2011-09-01:23241.8|2011-10-01:22056.8|2011-11-01:21719.1|2011-12-01:22125.4|2012-01-01:16026.7|2012-02-01:17961.2|2012-03-01:20843.6|2012-04-01:19519.3|2012-05-01:23190.1|2012-06-01:19313.4|2012-07-01:20971.3|2012-08-01:22314.2|2012-09-01:19959.1|2012-10-01:21739|2012-11-01:20449.1|2012-12-01:19695.4|2013-01-01:15949|2013-02-01:15510.8|2013-03-01:19280.5|2013-04-01:20595.1|2013-05-01:21780.8|2013-06-01:21082.2|2013-07-01:20766.1|2013-08-01:21364.5|2013-09-01:20810.6|2013-10-01:22768.1|2013-11-01:20807.1|2013-12-01:20796.2|2014-01-01:15961.8|2014-02-01:15841.7|2014-03-01:17532.4|2014-04-01:19632.9|2014-05-01:20658|2014-06-01:20374.1|2014-07-01:22936.3|2014-08-01:20373.9|2014-09-01:19538.2|2014-10-01:18227|2014-11-01:15545.9|2014-12-01:17349|2015-01-01:13603.6|2015-02-01:12010.7|2015-03-01:16895.1|2015-04-01:15054.4|2015-05-01:16674.6|2015-06-01:19583.2|2015-07-01:18455.7|2015-08-01:15360.1|2015-09-01:16008.9|2015-10-01:15902.6|2015-11-01:13687.2|2015-12-01:16677.9|2016-01-01:11127.3|2016-02-01:13272.6|2016-03-01:15884.2|2016-04-01:15270.3|2016-05-01:17471.6|2016-06-01:16622.9|2016-07-01:16223|2016-08-01:16925.4|2016-09-01:15744.2|2016-10-01:13663.1|2016-11-01:16156.5|2016-12-01:15905.9|2017-01-01:14879.9|2017-02-01:15497.8|2017-03-01:20107.3|2017-04-01:17694.7|2017-05-01:19809.9|2017-06-01:19803.3|2017-07-01:18786.5|2017-08-01:19500.4|2017-09-01:18690.6|2017-10-01:18886|2017-11-01:16715.4|2017-12-01:17628.8|2018-01-01:17062.4|2018-02-01:17441.4|2018-03-01:20273.2|2018-04-01:19730.7|2018-05-01:19343.4|2018-06-01:20131.1|2018-07-01:22545.5|2018-08-01:21567.8|2018-09-01:19189.5|2018-10-01:21910.7|2018-11-01:20957.3|2018-12-01:19365.2|2019-01-01:18021.3|2019-02-01:15757.3|2019-03-01:17450.9|2019-04-01:19300.8|2019-05-01:20619.9|2019-06-01:18427.1|2019-07-01:20166.2|2019-08-01:19746.4|2019-09-01:20338.5|2019-10-01:19645|2019-11-01:17778.8|2019-12-01:18540.8|2020-01-01:14550.5|2020-02-01:15615.5|2020-03-01:18403.5|2020-04-01:17646.6|2020-05-01:17579.9|2020-06-01:17598.3|2020-07-01:19537.6|2020-08-01:17548.4|2020-09-01:18286|2020-10-01:17805.5|2020-11-01:17522.9|2020-12-01:18595.8|2021-01-01:15097.5|2021-02-01:16498.9|2021-03-01:24561|2021-04-01:26182.6|2021-05-01:26406.9|2021-06-01:29262.2|2021-07-01:25747.1|2021-08-01:27401.4|2021-09-01:24588.6|2021-10-01:22843.2|2021-11-01:20712.5|2021-12-01:24662.6|2022-01-01:19967|2022-02-01:23710.8|2022-03-01:29717.9|2022-04-01:29243|2022-05-01:29949.8|2022-06-01:33121.4|2022-07-01:30164.3|2022-08-01:31142.4|2022-09-01:30231.8|2022-10-01:27536|2022-11-01:28363.7|2022-12-01:27053.1|2023-01-01:23024.1|2023-02-01:21254|2023-03-01:33086.4|2023-04-01:28061.9|2023-05-01:32908|2023-06-01:29869.6|2023-07-01:28501.6|2023-08-01:31355.6|2023-09-01:28912.4|2023-10-01:29809.3|2023-11-01:28089.7|2023-12-01:28946.5|2024-01-01:26961.9|2024-02-01:23587.7|2024-03-01:27959|2024-04-01:30643.3|2024-05-01:30430.6|2024-06-01:29009.7|2024-07-01:31084.1|2024-08-01:28893.9|2024-09-01:28678.7|2024-10-01:29478.8|2024-11-01:28035.1|2024-12-01:25093.7|2025-01-01:25592.4|2025-02-01:22983.7|2025-03-01:28997.5|2025-04-01:30106.2|2025-05-01:30106.8|2025-06-01:29174.3|2025-07-01:32387.4|2025-08-01:29688.2|2025-09-01:30641.8|2025-10-01:31644.4|2025-11-01:28322|2025-12-01:30856.1|2026-01-01:24704.4|2026-02-01:26347.7|2026-03-01:31900.9|2026-04-01:34420.1|2026-05-01:31649.9|2026-06-01:35639.7|2026-07-01:33701.4|2026-08-01:32858.7|2026-09-01:34584","22709":"1999-01-01:3746.2|1999-02-01:3235.9|1999-03-01:4134.5|1999-04-01:3757.4|1999-05-01:4172|1999-06-01:4545.9|1999-07-01:4114.9|1999-08-01:4548.6|1999-09-01:4319.9|1999-10-01:4539.8|1999-11-01:4617.8|1999-12-01:4526.7|2000-01-01:3654.6|2000-02-01:4133.1|2000-03-01:4535.3|2000-04-01:4078.3|2000-05-01:4776.3|2000-06-01:4681.7|2000-07-01:4960.4|2000-08-01:5502|2000-09-01:5143.6|2000-10-01:5327.2|2000-11-01:5234.2|2000-12-01:4949.7|2001-01-01:5088.2|2001-02-01:4086.7|2001-03-01:5530.6|2001-04-01:4693.7|2001-05-01:5236.6|2001-06-01:4842.7|2001-07-01:4938.3|2001-08-01:5176|2001-09-01:4246.2|2001-10-01:4837.7|2001-11-01:4299.7|2001-12-01:3592.5|2002-01-01:3886.4|2002-02-01:3483.6|2002-03-01:3749.1|2002-04-01:4225.8|2002-05-01:4154.3|2002-06-01:3488.1|2002-07-01:5105.9|2002-08-01:4258.1|2002-09-01:4087.3|2002-10-01:4369.9|2002-11-01:3936.1|2002-12-01:3530.1|2003-01-01:3740|2003-02-01:3973.1|2003-03-01:3787|2003-04-01:4081.5|2003-05-01:3946.4|2003-06-01:3603.9|2003-07-01:4122.6|2003-08-01:3811.5|2003-09-01:4702.4|2003-10-01:5108|2003-11-01:4348.3|2003-12-01:4082.6|2004-01-01:4293.7|2004-02-01:3833.8|2004-03-01:5422.8|2004-04-01:4713.7|2004-05-01:4918|2004-06-01:5614.8|2004-07-01:5613.4|2004-08-01:5708.2|2004-09-01:5834.9|2004-10-01:5932.1|2004-11-01:6161.1|2004-12-01:5767|2005-01-01:5349.7|2005-02-01:5072|2005-03-01:5998.5|2005-04-01:5423.9|2005-05-01:6462.9|2005-06-01:6257.3|2005-07-01:6147.8|2005-08-01:7784.3|2005-09-01:6401.4|2005-10-01:6327|2005-11-01:6806.2|2005-12-01:6661.2|2006-01-01:6552.3|2006-02-01:6072.5|2006-03-01:7814.9|2006-04-01:6845.9|2006-05-01:7383.6|2006-06-01:7464.2|2006-07-01:8085.3|2006-08-01:9212.2|2006-09-01:8207.8|2006-10-01:8830.4|2006-11-01:8761.2|2006-12-01:7301|2007-01-01:8563|2007-02-01:7340.9|2007-03-01:9628|2007-04-01:8382.6|2007-05-01:9904.5|2007-06-01:9417.2|2007-07-01:10896.8|2007-08-01:11683.5|2007-09-01:10832.9|2007-10-01:12481.2|2007-11-01:12175.8|2007-12-01:10735.7|2008-01-01:12487.8|2008-02-01:12100|2008-03-01:11772.9|2008-04-01:12477.7|2008-05-01:15374.6|2008-06-01:16016.8|2008-07-01:17279.4|2008-08-01:17596.4|2008-09-01:17403.3|2008-10-01:17329.4|2008-11-01:13236.4|2008-12-01:11632.3|2009-01-01:10397|2009-02-01:7917.3|2009-03-01:10136.2|2009-04-01:8692.5|2009-05-01:9437.6|2009-06-01:9951.3|2009-07-01:11343.8|2009-08-01:10875.7|2009-09-01:12633.1|2009-10-01:12844.7|2009-11-01:12127.2|2009-12-01:12378.5|2010-01-01:11578.5|2010-02-01:11892|2010-03-01:15124.6|2010-04-01:13965|2010-05-01:14345.1|2010-06-01:14929.4|2010-07-01:16430.1|2010-08-01:16907.5|2010-09-01:17843|2010-10-01:16642.3|2010-11-01:17507|2010-12-01:15674.6|2011-01-01:14955.6|2011-02-01:15680.7|2011-03-01:17866.2|2011-04-01:18459.3|2011-05-01:19828|2011-06-01:19399.8|2011-07-01:19247.1|2011-08-01:22396.1|2011-09-01:20342.5|2011-10-01:19886.7|2011-11-01:21346.9|2011-12-01:18468.6|2012-01-01:17584.7|2012-02-01:16448.1|2012-03-01:19032.3|2012-04-01:18852.5|2012-05-01:20418.2|2012-06-01:18703.2|2012-07-01:18289.2|2012-08-01:19295.3|2012-09-01:17596.2|2012-10-01:20381.5|2012-11-01:20824.2|2012-12-01:17648.5|2013-01-01:20132.8|2013-02-01:16951.3|2013-03-01:19265.1|2013-04-01:21756.3|2013-05-01:21187|2013-06-01:18955.3|2013-07-01:22838.7|2013-08-01:20338.6|2013-09-01:19016.2|2013-10-01:23171|2013-11-01:19273.8|2013-12-01:18256|2014-01-01:19852.4|2014-02-01:18185.7|2014-03-01:17672.4|2014-04-01:19347.6|2014-05-01:20234|2014-06-01:18251.6|2014-07-01:21645.2|2014-08-01:19470.7|2014-09-01:20683.3|2014-10-01:19700.2|2014-11-01:18253|2014-12-01:17414.1|2015-01-01:16481.4|2015-02-01:15108.4|2015-03-01:16746.1|2015-04-01:14781.8|2015-05-01:14224.7|2015-06-01:15273.3|2015-07-01:15830|2015-08-01:12994|2015-09-01:13384.8|2015-10-01:14226.2|2015-11-01:12788.3|2015-12-01:10629.9|2016-01-01:10011.1|2016-02-01:10494.7|2016-03-01:11760.9|2016-04-01:10728|2016-05-01:11344.5|2016-06-01:12991.3|2016-07-01:11977.9|2016-08-01:13094.5|2016-09-01:12221.5|2016-10-01:11623.7|2016-11-01:11708.1|2016-12-01:11766.7|2017-01-01:12452.9|2017-02-01:11129.7|2017-03-01:13688.7|2017-04-01:11569|2017-05-01:13097.8|2017-06-01:13534.6|2017-07-01:13402.6|2017-08-01:14952.5|2017-09-01:14389.2|2017-10-01:14757.8|2017-11-01:14139.1|2017-12-01:13487.7|2018-01-01:15291.5|2018-02-01:15419.9|2018-03-01:14853.8|2018-04-01:15144.4|2018-05-01:14303.9|2018-06-01:15456|2018-07-01:19828.5|2018-08-01:20152.9|2018-09-01:15240.1|2018-10-01:17376.7|2018-11-01:18134.6|2018-12-01:13967.6|2019-01-01:17825.5|2019-02-01:13938.3|2019-03-01:14456.1|2019-04-01:15161.1|2019-05-01:16507.7|2019-06-01:14491.5|2019-07-01:19484.8|2019-08-01:18242.1|2019-09-01:17944.9|2019-10-01:18690.1|2019-11-01:15676.6|2019-12-01:13806.8|2020-01-01:17835.2|2020-02-01:14684|2020-03-01:16106.4|2020-04-01:12755.7|2020-05-01:14340.6|2020-06-01:11488.9|2020-07-01:12641.8|2020-08-01:12322.2|2020-09-01:13545.1|2020-10-01:13845.3|2020-11-01:15401.5|2020-12-01:20060.2|2021-01-01:17298|2021-02-01:16470.7|2021-03-01:24719.3|2021-04-01:16844.9|2021-05-01:18274.1|2021-06-01:21115.7|2021-07-01:18903.1|2021-08-01:21246|2021-09-01:21640.7|2021-10-01:21225.7|2021-11-01:22472.8|2021-12-01:21441.4|2022-01-01:20799.1|2022-02-01:19666.5|2022-03-01:23036.7|2022-04-01:21720.3|2022-05-01:25680.5|2022-06-01:25088.7|2022-07-01:25540.4|2022-08-01:27904.6|2022-09-01:27683.4|2022-10-01:24968|2022-11-01:23063.8|2022-12-01:23527.3|2023-01-01:21364.6|2023-02-01:18415.7|2023-03-01:23071.9|2023-04-01:19935.3|2023-05-01:22643.2|2023-06-01:20570.9|2023-07-01:20915.4|2023-08-01:22515.3|2023-09-01:20436.2|2023-10-01:21220.1|2023-11-01:20090.3|2023-12-01:20364.7|2024-01-01:21399.1|2024-02-01:19200.9|2024-03-01:21606.9|2024-04-01:22845|2024-05-01:22927.5|2024-06-01:23348.5|2024-07-01:24102.6|2024-08-01:25176.1|2024-09-01:24154.3|2024-10-01:26289.5|2024-11-01:21992.1|2024-12-01:20971.9|2025-01-01:24196.1|2025-02-01:24106.5|2025-03-01:21778.8|2025-04-01:23149|2025-05-01:23670|2025-06-01:23927.2|2025-07-01:25996.9|2025-08-01:24376.7|2025-09-01:28182.3|2025-10-01:25754.2|2025-11-01:23283.8|2025-12-01:22350.7|2026-01-01:21760|2026-02-01:22995.7|2026-03-01:26228.7|2026-04-01:24613.9|2026-05-01:25112.8|2026-06-01:27562.8|2026-07-01:28198.2|2026-08-01:26722.3|2026-09-01:27715.2","24364":"2003-01-01:70.24531|2003-02-01:71.46538|2003-03-01:71.07428|2003-04-01:70.59064|2003-05-01:69.89636|2003-06-01:70.02837|2003-07-01:69.16061|2003-08-01:69.69307|2003-09-01:71.25295|2003-10-01:71.14404|2003-11-01:71.33106|2003-12-01:71.15629|2004-01-01:72.46781|2004-02-01:73.23679|2004-03-01:74.05002|2004-04-01:74.42501|2004-05-01:74.34675|2004-06-01:74.96272|2004-07-01:75.25478|2004-08-01:75.60415|2004-09-01:76.38245|2004-10-01:75.85434|2004-11-01:76.68709|2004-12-01:76.11373|2005-01-01:76.5966|2005-02-01:77.06792|2005-03-01:77.17541|2005-04-01:77.72032|2005-05-01:77.64183|2005-06-01:77.15793|2005-07-01:77.15552|2005-08-01:77.74555|2005-09-01:77.54981|2005-10-01:77.57804|2005-11-01:78.21058|2005-12-01:78.82313|2006-01-01:79.44816|2006-02-01:79.49449|2006-03-01:79.39037|2006-04-01:79.88261|2006-05-01:80.89115|2006-06-01:79.95656|2006-07-01:81.46512|2006-08-01:81.46473|2006-09-01:81.66473|2006-10-01:82.53161|2006-11-01:83.13138|2006-12-01:84.17153|2007-01-01:83.90426|2007-02-01:84.10166|2007-03-01:83.58701|2007-04-01:84.71261|2007-05-01:85.43675|2007-06-01:85.95573|2007-07-01:86.58222|2007-08-01:86.74322|2007-09-01:87.42248|2007-10-01:88.26435|2007-11-01:88.23773|2007-12-01:89.0241|2008-01-01:89.16193|2008-02-01:88.98523|2008-03-01:88.33949|2008-04-01:89.58433|2008-05-01:90.41734|2008-06-01:91.23219|2008-07-01:91.25862|2008-08-01:91.44644|2008-09-01:91.42262|2008-10-01:89.59985|2008-11-01:87.39099|2008-12-01:85.01123|2009-01-01:84.84237|2009-02-01:85.49744|2009-03-01:86.03184|2009-04-01:86.39949|2009-05-01:87.20008|2009-06-01:87.73188|2009-07-01:87.95206|2009-08-01:89.37255|2009-09-01:90.10757|2009-10-01:90.81965|2009-11-01:90.92106|2009-12-01:92.27926|2010-01-01:93.64187|2010-02-01:94.52748|2010-03-01:95.52947|2010-04-01:96.00255|2010-05-01:95.22069|2010-06-01:94.97797|2010-07-01:95.55855|2010-08-01:96.16115|2010-09-01:97.02013|2010-10-01:96.8665|2010-11-01:97.95902|2010-12-01:96.9412|2011-01-01:98.13988|2011-02-01:98.54156|2011-03-01:98.53888|2011-04-01:98.62492|2011-05-01:98.77708|2011-06-01:99.11656|2011-07-01:99.2609|2011-08-01:99.19098|2011-09-01:99.06633|2011-10-01:99.00237|2011-11-01:99.47551|2011-12-01:98.53093|2012-01-01:97.32318|2012-02-01:98.26796|2012-03-01:98.03022|2012-04-01:98.48053|2012-05-01:99.61968|2012-06-01:100.33214|2012-07-01:100.49686|2012-08-01:100.83752|2012-09-01:100.41614|2012-10-01:101.25404|2012-11-01:101.11214|2012-12-01:100.67568|2013-01-01:101.32838|2013-02-01:100.36236|2013-03-01:101.36541|2013-04-01:102.4885|2013-05-01:102.65358|2013-06-01:102.28874|2013-07-01:102.65015|2013-08-01:102.96936|2013-09-01:103.47923|2013-10-01:103.43001|2013-11-01:103.70965|2013-12-01:103.98675|2014-01-01:103.67518|2014-02-01:103.37654|2014-03-01:103.24975|2014-04-01:102.81576|2014-05-01:102.44956|2014-06-01:100.25894|2014-07-01:101.02246|2014-08-01:101.91418|2014-09-01:102.46299|2014-10-01:101.59399|2014-11-01:101.77306|2014-12-01:102.18533|2015-01-01:101.29644|2015-02-01:100.65261|2015-03-01:100.47001|2015-04-01:99.12565|2015-05-01:98.45531|2015-06-01:97.5131|2015-07-01:96.3637|2015-08-01:96.86001|2015-09-01:96.16581|2015-10-01:96.51541|2015-11-01:95.5374|2015-12-01:95.33539|2016-01-01:94.88253|2016-02-01:94.74729|2016-03-01:94.07561|2016-04-01:94.02556|2016-05-01:93.79556|2016-06-01:93.95735|2016-07-01:93.64214|2016-08-01:93.40534|2016-09-01:93.556|2016-10-01:93.05426|2016-11-01:93.12087|2016-12-01:92.86963|2017-01-01:93.41079|2017-02-01:94.52645|2017-03-01:94.61479|2017-04-01:94.47234|2017-05-01:94.25405|2017-06-01:94.86179|2017-07-01:94.89681|2017-08-01:94.6509|2017-09-01:94.64466|2017-10-01:94.84754|2017-11-01:95.03559|2017-12-01:96.30823|2018-01-01:95.8136|2018-02-01:95.44236|2018-03-01:95.46053|2018-04-01:96.01002|2018-05-01:93.06017|2018-06-01:95.75321|2018-07-01:96.06122|2018-08-01:96.82217|2018-09-01:96.27991|2018-10-01:96.60062|2018-11-01:96.8881|2018-12-01:97.16856|2019-01-01:96.95208|2019-02-01:96.39653|2019-03-01:95.80171|2019-04-01:95.77149|2019-05-01:97.11479|2019-06-01:96.58573|2019-07-01:96.38695|2019-08-01:96.63275|2019-09-01:96.94689|2019-10-01:98.08195|2019-11-01:97.92154|2019-12-01:97.59777|2020-01-01:97.60893|2020-02-01:97.74647|2020-03-01:91.2697|2020-04-01:82.96395|2020-05-01:85.49257|2020-06-01:89.36253|2020-07-01:91.73944|2020-08-01:93.50589|2020-09-01:95.36224|2020-10-01:97.30877|2020-11-01:97.51996|2020-12-01:97.68175|2021-01-01:97.80214|2021-02-01:98.71707|2021-03-01:95.30718|2021-04-01:96.32579|2021-05-01:97.02449|2021-06-01:96.74657|2021-07-01:96.4199|2021-08-01:97.02244|2021-09-01:96.96297|2021-10-01:97.48845|2021-11-01:99.05624|2021-12-01:99.38482|2022-01-01:97.4208|2022-02-01:98.49135|2022-03-01:99.56176|2022-04-01:99.45421|2022-05-01:99.64297|2022-06-01:99.49797|2022-07-01:101.41926|2022-08-01:101.10264|2022-09-01:101.1562|2022-10-01:101.43769|2022-11-01:100.71743|2022-12-01:100.59088|2023-01-01:100.10409|2023-02-01:103.08488|2023-03-01:103.09631|2023-04-01:103.92975|2023-05-01:102.42356|2023-06-01:102.38761|2023-07-01:102.90097|2023-08-01:102.49883|2023-09-01:102.5197|2023-10-01:102.8499|2023-11-01:103.60561|2023-12-01:104.8968|2024-01-01:104.46088|2024-02-01:104.65783|2024-03-01:104.68489|2024-04-01:104.62189|2024-05-01:105.5883|2024-06-01:106.56647|2024-07-01:107.07017|2024-08-01:107.19578|2024-09-01:108.05141|2024-10-01:108.26621|2024-11-01:108.02232|2024-12-01:107.37891|2025-01-01:108.05509|2025-02-01:108.57481|2025-03-01:110.03087|2025-04-01:109.51799|2025-05-01:108.88849|2025-06-01:108.82565|2025-07-01:108.60295|2025-08-01:108.84223|2025-09-01:108.7154|2025-10-01:108.73877|2025-11-01:109.25356|2025-12-01:109.47578|2026-01-01:110.15169|2026-02-01:110.82485|2026-03-01:110.65755|2026-04-01:111.04254|2026-05-01:111.25061|2026-06-01:110.37352|2026-07-01:110.03188|2026-08-01:110.40624","29027":"2003-03-01:340806|2003-04-01:339488|2003-05-01:339255|2003-06-01:338773|2003-07-01:338850|2003-08-01:338022|2003-09-01:336344|2003-10-01:334831|2003-11-01:335212|2003-12-01:336924|2004-01-01:338286|2004-02-01:340804|2004-03-01:342742|2004-04-01:345982|2004-05-01:348632|2004-06-01:350192|2004-07-01:350971|2004-08-01:352739|2004-09-01:353654|2004-10-01:356548|2004-11-01:355127|2004-12-01:356066|2005-01-01:352347|2005-02-01:356037|2005-03-01:354930|2005-04-01:356328|2005-05-01:356552|2005-06-01:359138|2005-07-01:361544|2005-08-01:362540|2005-09-01:363207|2005-10-01:364020|2005-11-01:370567|2005-12-01:368690|2006-01-01:371709|2006-02-01:369735|2006-03-01:370870|2006-04-01:369043|2006-05-01:373195|2006-06-01:376661|2006-07-01:379900|2006-08-01:379947|2006-09-01:386403|2006-10-01:390048|2006-11-01:397594|2006-12-01:391530|2007-01-01:394954|2007-02-01:398314|2007-03-01:404512|2007-04-01:407231|2007-05-01:409935|2007-06-01:409862|2007-07-01:409163|2007-08-01:409947|2007-09-01:413366|2007-10-01:417391|2007-11-01:421167|2007-12-01:425803|2008-01-01:426245|2008-02-01:430347|2008-03-01:425966|2008-04-01:431948|2008-05-01:436609|2008-06-01:441128|2008-07-01:443965|2008-08-01:446668|2008-09-01:449189|2008-10-01:450906|2008-11-01:453592|2008-12-01:455874|2009-01-01:459106|2009-02-01:460507|2009-03-01:462819|2009-04-01:465203|2009-05-01:467382|2009-06-01:468408|2009-07-01:471648|2009-08-01:473273|2009-09-01:474987|2009-10-01:476477|2009-11-01:480673|2009-12-01:485001|2010-01-01:488130|2010-02-01:492070|2010-03-01:496423|2010-04-01:499086|2010-05-01:500838|2010-06-01:500968|2010-07-01:506021|2010-08-01:513049|2010-09-01:518916|2010-10-01:524702|2010-11-01:522895|2010-12-01:521543|2011-01-01:521892|2011-02-01:528997|2011-03-01:530182|2011-04-01:534272|2011-05-01:536564|2011-06-01:543292|2011-07-01:546780|2011-08-01:547503|2011-09-01:545001|2011-10-01:542920|2011-11-01:547910|2011-12-01:550571|2012-01-01:555828|2012-02-01:560028|2012-03-01:563873|2012-04-01:567846|2012-05-01:569859|2012-06-01:572422|2012-07-01:575873|2012-08-01:578719|2012-09-01:580108|2012-10-01:582829|2012-11-01:581806|2012-12-01:581862|2013-01-01:584032|2013-02-01:585947|2013-03-01:591543|2013-04-01:595754|2013-05-01:603803|2013-06-01:609019|2013-07-01:612005|2013-08-01:613281|2013-09-01:615287|2013-10-01:618985|2013-11-01:617290|2013-12-01:612891|2014-01-01:618765|2014-02-01:622559|2014-03-01:624920|2014-04-01:622940|2014-05-01:621926|2014-06-01:622347|2014-07-01:624886|2014-08-01:631192|2014-09-01:635987|2014-10-01:640346|2014-11-01:632965|2014-12-01:624922|2015-01-01:618769|2015-02-01:616214|2015-03-01:618458|2015-04-01:610659|2015-05-01:610897|2015-06-01:608523|2015-07-01:606676|2015-08-01:604549|2015-09-01:597148|2015-10-01:605543|2015-11-01:611280|2015-12-01:622767|2016-01-01:615389|2016-02-01:610275|2016-03-01:602033|2016-04-01:599516|2016-05-01:593369|2016-06-01:592383|2016-07-01:593668|2016-08-01:594038|2016-09-01:592185|2016-10-01:595522|2016-11-01:598166|2016-12-01:604228|2017-01-01:608302|2017-02-01:608338|2017-03-01:610238|2017-04-01:616052|2017-05-01:622234|2017-06-01:624222|2017-07-01:620558|2017-08-01:615903|2017-09-01:610638|2017-10-01:614891|2017-11-01:618302|2017-12-01:622864|2018-01-01:628875|2018-02-01:625371|2018-03-01:625388|2018-04-01:621994|2018-05-01:619301|2018-06-01:614864|2018-07-01:617644|2018-08-01:623964|2018-09-01:622567|2018-10-01:625405|2018-11-01:626015|2018-12-01:626014|2019-01-01:631740|2019-02-01:630305|2019-03-01:633151|2019-04-01:628536|2019-05-01:627232|2019-06-01:607889|2019-07-01:618168|2019-08-01:622153|2019-09-01:640815|2019-10-01:651807|2019-11-01:662870|2019-12-01:670303|2020-01-01:670617|2020-02-01:666992|2020-03-01:643722|2020-04-01:644751|2020-05-01:665791|2020-06-01:682619|2020-07-01:692411|2020-08-01:694312|2020-09-01:684188|2020-10-01:674086|2020-11-01:658240|2020-12-01:651128|2021-01-01:649246|2021-02-01:654429|2021-03-01:653486|2021-04-01:658177|2021-05-01:656677|2021-06-01:657644|2021-07-01:659199|2021-08-01:658327|2021-09-01:642099|2021-10-01:635645|2021-11-01:636631|2021-12-01:639531|2022-01-01:642525|2022-02-01:654534|2022-03-01:666223|2022-04-01:670919|2022-05-01:684124|2022-06-01:678902|2022-07-01:678360|2022-08-01:681449|2022-09-01:688976|2022-10-01:700353|2022-11-01:705589|2022-12-01:706843|2023-01-01:709160|2023-02-01:709412|2023-03-01:713870|2023-04-01:712650|2023-05-01:711646|2023-06-01:715334|2023-07-01:725211|2023-08-01:735764|2023-09-01:735459|2023-10-01:735546|2023-11-01:740173|2023-12-01:757131|2024-01-01:761236|2024-02-01:761859|2024-03-01:756952|2024-04-01:762845|2024-05-01:767484|2024-06-01:766523|2024-07-01:767369|2024-08-01:768327|2024-09-01:774300|2024-10-01:778554|2024-11-01:780266|2024-12-01:776265|2025-01-01:780360|2025-02-01:783852|2025-03-01:786566|2025-04-01:789519|2025-05-01:794333|2025-06-01:801537|2025-07-01:803797|2025-08-01:802837|2025-09-01:803002|2025-10-01:805123|2025-11-01:811029|2025-12-01:814704|2026-01-01:815781|2026-02-01:820257|2026-03-01:829688|2026-04-01:828537|2026-05-01:827132|2026-06-01:824039|2026-07-01:821973|2026-08-01:824634","29034":"2005-03-01:17|2005-04-01:17.2|2005-05-01:17.42|2005-06-01:17.55|2005-07-01:17.71|2005-08-01:17.93|2005-09-01:18.29|2005-10-01:18.55|2005-11-01:18.63|2005-12-01:18.68|2006-01-01:18.68|2006-02-01:18.95|2006-03-01:19.28|2006-04-01:19.53|2006-05-01:19.56|2006-06-01:19.55|2006-07-01:19.5|2006-08-01:19.65|2006-09-01:19.51|2006-10-01:19.43|2006-11-01:19.26|2006-12-01:19.5|2007-01-01:19.39|2007-02-01:19.27|2007-03-01:18.93|2007-04-01:18.75|2007-05-01:18.56|2007-06-01:18.87|2007-07-01:19.23|2007-08-01:19.43|2007-09-01:19.29|2007-10-01:19.28|2007-11-01:19.43|2007-12-01:19.37|2008-01-01:19.62|2008-02-01:19.85|2008-03-01:20.24|2008-04-01:20.41|2008-05-01:20.44|2008-06-01:20.41|2008-07-01:20.47|2008-08-01:20.58|2008-09-01:20.64|2008-10-01:20.77|2008-11-01:20.77|2008-12-01:20.87|2009-01-01:20.89|2009-02-01:21|2009-03-01:21.06|2009-04-01:21.16|2009-05-01:21.34|2009-06-01:21.66|2009-07-01:21.81|2009-08-01:21.89|2009-09-01:21.99|2009-10-01:22.15|2009-11-01:22.22|2009-12-01:22.2|2010-01-01:22.3|2010-02-01:22.27|2010-03-01:22.34|2010-04-01:22.48|2010-05-01:22.72|2010-06-01:23.04|2010-07-01:23.09|2010-08-01:23.13|2010-09-01:23.23|2010-10-01:23.18|2010-11-01:23.54|2010-12-01:23.96|2011-01-01:24.19|2011-02-01:23.96|2011-03-01:23.92|2011-04-01:23.84|2011-05-01:23.77|2011-06-01:23.58|2011-07-01:23.49|2011-08-01:23.7|2011-09-01:24.2|2011-10-01:24.67|2011-11-01:24.62|2011-12-01:24.58|2012-01-01:24.54|2012-02-01:24.49|2012-03-01:24.54|2012-04-01:24.47|2012-05-01:24.53|2012-06-01:24.38|2012-07-01:24.09|2012-08-01:23.8|2012-09-01:23.59|2012-10-01:23.44|2012-11-01:23.46|2012-12-01:23.47|2013-01-01:23.15|2013-02-01:23.09|2013-03-01:22.89|2013-04-01:22.75|2013-05-01:22.33|2013-06-01:22.21|2013-07-01:22.18|2013-08-01:22.24|2013-09-01:22.31|2013-10-01:22.3|2013-11-01:22.44|2013-12-01:22.68|2014-01-01:22.59|2014-02-01:22.58|2014-03-01:22.48|2014-04-01:22.6|2014-05-01:22.71|2014-06-01:22.78|2014-07-01:22.83|2014-08-01:22.67|2014-09-01:22.7|2014-10-01:22.72|2014-11-01:23.11|2014-12-01:23.48|2015-01-01:23.92|2015-02-01:24.08|2015-03-01:24.02|2015-04-01:24.18|2015-05-01:24.18|2015-06-01:24.29|2015-07-01:24.3|2015-08-01:24.37|2015-09-01:24.61|2015-10-01:24.22|2015-11-01:23.75|2015-12-01:22.99|2016-01-01:23.26|2016-02-01:23.37|2016-03-01:23.65|2016-04-01:23.7|2016-05-01:23.97|2016-06-01:24.04|2016-07-01:23.84|2016-08-01:23.79|2016-09-01:23.81|2016-10-01:23.74|2016-11-01:23.57|2016-12-01:23.22|2017-01-01:23.15|2017-02-01:22.96|2017-03-01:22.93|2017-04-01:22.54|2017-05-01:22.18|2017-06-01:22.17|2017-07-01:22.35|2017-08-01:22.66|2017-09-01:22.78|2017-10-01:22.56|2017-11-01:22.34|2017-12-01:22.09|2018-01-01:21.94|2018-02-01:21.89|2018-03-01:21.99|2018-04-01:22.25|2018-05-01:22.48|2018-06-01:22.86|2018-07-01:22.4|2018-08-01:22.1|2018-09-01:22.16|2018-10-01:22.16|2018-11-01:22.31|2018-12-01:22.58|2019-01-01:22.75|2019-02-01:22.96|2019-03-01:22.96|2019-04-01:23.5|2019-05-01:23.85|2019-06-01:25.13|2019-07-01:24.69|2019-08-01:24.73|2019-09-01:23.91|2019-10-01:23.53|2019-11-01:22.99|2019-12-01:22.65|2020-01-01:22.59|2020-02-01:22.64|2020-03-01:23.71|2020-04-01:23.25|2020-05-01:21.83|2020-06-01:20.54|2020-07-01:19.92|2020-08-01:19.77|2020-09-01:20.03|2020-10-01:20.45|2020-11-01:21.25|2020-12-01:21.84|2021-01-01:22.17|2021-02-01:21.97|2021-03-01:22.32|2021-04-01:22.39|2021-05-01:22.78|2021-06-01:22.96|2021-07-01:23.27|2021-08-01:23.63|2021-09-01:24.51|2021-10-01:25.15|2021-11-01:25.45|2021-12-01:25.58|2022-01-01:26.02|2022-02-01:25.65|2022-03-01:25.4|2022-04-01:25.6|2022-05-01:25.45|2022-06-01:25.96|2022-07-01:26.5|2022-08-01:26.91|2022-09-01:27.17|2022-10-01:27.21|2022-11-01:27.32|2022-12-01:27.57|2023-01-01:27.67|2023-02-01:27.69|2023-03-01:27.71|2023-04-01:27.81|2023-05-01:27.96|2023-06-01:27.78|2023-07-01:27.33|2023-08-01:26.89|2023-09-01:26.78|2023-10-01:26.79|2023-11-01:26.49|2023-12-01:25.84|2024-01-01:25.72|2024-02-01:25.83|2024-03-01:26.13|2024-04-01:26.13|2024-05-01:26.02|2024-06-01:26.38|2024-07-01:26.53|2024-08-01:26.73|2024-09-01:26.49|2024-10-01:26.39|2024-11-01:26.39|2024-12-01:26.8|2025-01-01:26.71|2025-02-01:26.85|2025-03-01:26.96|2025-04-01:27.12|2025-05-01:27.19|2025-06-01:27.17|2025-07-01:27.32|2025-08-01:27.55|2025-09-01:27.77|2025-10-01:27.92|2025-11-01:27.89|2025-12-01:28.09|2026-01-01:28.23|2026-02-01:28.27|2026-03-01:28.24|2026-04-01:28.38|2026-05-01:28.47|2026-06-01:28.66|2026-07-01:28.72","29037":"2005-01-01:16.51|2005-02-01:16.84|2005-03-01:17.2|2005-04-01:17.6|2005-05-01:17.96|2005-06-01:18.12|2005-07-01:18.4|2005-08-01:18.85|2005-09-01:19.11|2005-10-01:19.37|2005-11-01:19.61|2005-12-01:19.56|2006-01-01:19.89|2006-02-01:20.11|2006-03-01:20.45|2006-04-01:20.78|2006-05-01:21.07|2006-06-01:21.16|2006-07-01:21.39|2006-08-01:21.65|2006-09-01:21.74|2006-10-01:21.85|2006-11-01:22.07|2006-12-01:21.98|2007-01-01:22.28|2007-02-01:22.48|2007-03-01:22.04|2007-04-01:22.36|2007-05-01:22.88|2007-06-01:23.09|2007-07-01:23.57|2007-08-01:23.77|2007-09-01:23.97|2007-10-01:24.56|2007-11-01:24.88|2007-12-01:24.96|2008-01-01:25.29|2008-02-01:25.5|2008-03-01:25.99|2008-04-01:26.45|2008-05-01:26.8|2008-06-01:26.92|2008-07-01:27.15|2008-08-01:27.25|2008-09-01:27.41|2008-10-01:27.78|2008-11-01:27.46|2008-12-01:27.44|2009-01-01:27.26|2009-02-01:27.26|2009-03-01:27.32|2009-04-01:27.49|2009-05-01:27.85|2009-06-01:28.01|2009-07-01:28.15|2009-08-01:28.42|2009-09-01:28.76|2009-10-01:28.93|2009-11-01:29.12|2009-12-01:29.45|2010-01-01:29.82|2010-02-01:29.95|2010-03-01:30.35|2010-04-01:30.7|2010-05-01:31.19|2010-06-01:31.41|2010-07-01:32.03|2010-08-01:32.34|2010-09-01:32.65|2010-10-01:32.94|2010-11-01:33.46|2010-12-01:33.97|2011-01-01:34.1|2011-02-01:34.23|2011-03-01:34.86|2011-04-01:34.9|2011-05-01:35.11|2011-06-01:35.29|2011-07-01:35.37|2011-08-01:35.98|2011-09-01:36.27|2011-10-01:36.45|2011-11-01:36.5|2011-12-01:36.56|2012-01-01:36.79|2012-02-01:36.78|2012-03-01:36.87|2012-04-01:36.99|2012-05-01:37.21|2012-06-01:37.42|2012-07-01:37.54|2012-08-01:37.71|2012-09-01:37.49|2012-10-01:37.69|2012-11-01:37.88|2012-12-01:38.04|2013-01-01:38.22|2013-02-01:38.27|2013-03-01:38.15|2013-04-01:38.29|2013-05-01:38.4|2013-06-01:38.4|2013-07-01:38.56|2013-08-01:38.69|2013-09-01:38.49|2013-10-01:38.36|2013-11-01:38.36|2013-12-01:38.21|2014-01-01:38.3|2014-02-01:38.25|2014-03-01:38.15|2014-04-01:38.14|2014-05-01:38.3|2014-06-01:38.48|2014-07-01:38.56|2014-08-01:38.63|2014-09-01:38.73|2014-10-01:38.95|2014-11-01:38.95|2014-12-01:39.24|2015-01-01:39.63|2015-02-01:39.64|2015-03-01:39.74|2015-04-01:40.01|2015-05-01:40.02|2015-06-01:40.09|2015-07-01:40.38|2015-08-01:40.57|2015-09-01:40.8|2015-10-01:40.81|2015-11-01:40.54|2015-12-01:40.05|2016-01-01:40.04|2016-02-01:39.7|2016-03-01:39.54|2016-04-01:39.25|2016-05-01:39.16|2016-06-01:39.03|2016-07-01:38.83|2016-08-01:38.72|2016-09-01:38.48|2016-10-01:38.21|2016-11-01:38.24|2016-12-01:38.11|2017-01-01:38|2017-02-01:37.88|2017-03-01:37.8|2017-04-01:37.45|2017-05-01:37.38|2017-06-01:37.32|2017-07-01:37.33|2017-08-01:37.37|2017-09-01:37.25|2017-10-01:37.3|2017-11-01:37.38|2017-12-01:37.22|2018-01-01:37.25|2018-02-01:37.23|2018-03-01:37.26|2018-04-01:37.48|2018-05-01:37.75|2018-06-01:37.84|2018-07-01:37.82|2018-08-01:38|2018-09-01:38.03|2018-10-01:38.28|2018-11-01:38.8|2018-12-01:39.02|2019-01-01:39.27|2019-02-01:39.55|2019-03-01:39.6|2019-04-01:39.83|2019-05-01:40.13|2019-06-01:40.56|2019-07-01:40.72|2019-08-01:41.11|2019-09-01:41.21|2019-10-01:41.33|2019-11-01:41.56|2019-12-01:41.46|2020-01-01:41.55|2020-02-01:41.53|2020-03-01:41.62|2020-04-01:40.91|2020-05-01:40.05|2020-06-01:39.38|2020-07-01:39.21|2020-08-01:39.17|2020-09-01:39.57|2020-10-01:40.2|2020-11-01:41.04|2020-12-01:41.78|2021-01-01:42.11|2021-02-01:42.31|2021-03-01:42.47|2021-04-01:42.89|2021-05-01:43.85|2021-06-01:44.53|2021-07-01:45.2|2021-08-01:46.46|2021-09-01:47.5|2021-10-01:48.19|2021-11-01:48.95|2021-12-01:49.48|2022-01-01:49.67|2022-02-01:49.54|2022-03-01:49.6|2022-04-01:49.67|2022-05-01:49.56|2022-06-01:49.67|2022-07-01:49.89|2022-08-01:49.66|2022-09-01:49.59|2022-10-01:49.76|2022-11-01:49.51|2022-12-01:49.14|2023-01-01:49.11|2023-02-01:48.78|2023-03-01:48.7|2023-04-01:48.6|2023-05-01:48.91|2023-06-01:48.46|2023-07-01:48.06|2023-08-01:48.25|2023-09-01:48.14|2023-10-01:48.2|2023-11-01:48.19|2023-12-01:47.75|2024-01-01:47.96|2024-02-01:47.93|2024-03-01:47.79|2024-04-01:47.66|2024-05-01:47.61|2024-06-01:47.7|2024-07-01:47.93|2024-08-01:48.14|2024-09-01:48.14|2024-10-01:48.19|2024-11-01:48.33|2024-12-01:48.45|2025-01-01:48.64|2025-02-01:48.6|2025-03-01:48.87|2025-04-01:48.93|2025-05-01:48.87|2025-06-01:48.82|2025-07-01:48.78|2025-08-01:48.93|2025-09-01:49.11|2025-10-01:49.46|2025-11-01:49.63|2025-12-01:49.7|2026-01-01:49.92|2026-02-01:49.81|2026-03-01:49.85|2026-04-01:49.88|2026-05-01:49.82|2026-06-01:49.65|2026-07-01:49.86","22113":"1999-01-01:101.47|1999-04-01:100.23|1999-07-01:97.89|1999-10-01:99.88|2000-01-01:100.6|2000-04-01:104.67|2000-07-01:104.7|2000-10-01:108.46|2001-01-01:110.35|2001-04-01:107.5|2001-07-01:105.98|2001-10-01:100.06|2002-01-01:101.3|2002-04-01:103.62|2002-07-01:105.24|2002-10-01:107.47|2003-01-01:104.36|2003-04-01:97.03|2003-07-01:97.69|2003-10-01:102.07|2004-01-01:105.45|2004-04-01:108.94|2004-07-01:111.15|2004-10-01:109.28|2005-01-01:107.29|2005-04-01:112.38|2005-07-01:111.7|2005-10-01:111.89|2006-01-01:117.32|2006-04-01:116.6|2006-07-01:117.61|2006-10-01:121.32|2007-01-01:126.35|2007-04-01:131.44|2007-07-01:133.82|2007-10-01:137.46|2008-01-01:142.08|2008-04-01:149.86|2008-07-01:157.41|2008-10-01:144.59|2009-01-01:128.92|2009-04-01:137.77|2009-07-01:151.16|2009-10-01:162.96|2010-01-01:166.47|2010-04-01:169.4|2010-07-01:174.46|2010-10-01:175.64|2011-01-01:179.73|2011-04-01:183.02|2011-07-01:185.17|2011-10-01:185.44|2012-01-01:184.52|2012-04-01:184.82|2012-07-01:183.21|2012-10-01:186.88|2013-01-01:189.04|2013-04-01:200.25|2013-07-01:197.44|2013-10-01:195.43|2014-01-01:196.1|2014-04-01:187.47|2014-07-01:183.09|2014-10-01:182.75|2015-01-01:177.17|2015-04-01:164.85|2015-07-01:155.61|2015-10-01:147.35|2016-01-01:144|2016-04-01:147.6|2016-07-01:138.65|2016-10-01:136.1|2017-01-01:136.6|2017-04-01:136.5|2017-07-01:137.05|2017-10-01:141.42|2018-01-01:141.26|2018-04-01:142.1|2018-07-01:149.62|2018-10-01:147.18|2019-01-01:145.4|2019-04-01:152.83|2019-07-01:157.07|2019-10-01:148.3|2020-01-01:155.54|2020-04-01:130.7|2020-07-01:143.48|2020-10-01:163.52|2021-01-01:173.67|2021-04-01:165.31|2021-07-01:165.16|2021-10-01:166.27|2022-01-01:163.14|2022-04-01:168.48|2022-07-01:173.79|2022-10-01:171.8|2023-01-01:165.34|2023-04-01:165.72|2023-07-01:161.83|2023-10-01:164.63|2024-01-01:169.44|2024-04-01:174.16|2024-07-01:178.24|2024-10-01:180.48|2025-01-01:184.45|2025-04-01:181.01|2025-07-01:182.35|2025-10-01:175.41|2026-01-01:181.43|2026-04-01:183.6","22114":"1999-01-01:116.38|1999-04-01:119.01|1999-07-01:117.35|1999-10-01:135.93|2000-01-01:133.05|2000-04-01:134.24|2000-07-01:145.94|2000-10-01:141.91|2001-01-01:150.01|2001-04-01:154.71|2001-07-01:150|2001-10-01:147.99|2002-01-01:150.21|2002-04-01:138.18|2002-07-01:176.43|2002-10-01:177.38|2003-01-01:171.22|2003-04-01:177.18|2003-07-01:178.78|2003-10-01:186.12|2004-01-01:194.41|2004-04-01:200.71|2004-07-01:204.33|2004-10-01:211.04|2005-01-01:220.53|2005-04-01:222.98|2005-07-01:226.71|2005-10-01:230.45|2006-01-01:234.96|2006-04-01:218.11|2006-07-01:248.72|2006-10-01:242.53|2007-01-01:249.14|2007-04-01:245.21|2007-07-01:250.38|2007-10-01:252.83|2008-01-01:245.7|2008-04-01:258.78|2008-07-01:253.42|2008-10-01:237.58|2009-01-01:221.59|2009-04-01:232.11|2009-07-01:227.46|2009-10-01:227.72|2010-01-01:252.67|2010-04-01:247.97|2010-07-01:256.85|2010-10-01:258.18|2011-01-01:262.91|2011-04-01:263.84|2011-07-01:269.73|2011-10-01:273.52|2012-01-01:269.72|2012-04-01:259.27|2012-07-01:265.33|2012-10-01:277.63|2013-01-01:264.15|2013-04-01:272.68|2013-07-01:267.85|2013-10-01:289.17|2014-01-01:269.2|2014-04-01:267.2|2014-07-01:280.19|2014-10-01:260.77|2015-01-01:276.96|2015-04-01:290.66|2015-07-01:286.42|2015-10-01:296.52|2016-01-01:298.15|2016-04-01:298.65|2016-07-01:283.72|2016-10-01:277.49|2017-01-01:301.98|2017-04-01:306.06|2017-07-01:311.09|2017-10-01:301.14|2018-01-01:315.67|2018-04-01:298.84|2018-07-01:319.49|2018-10-01:329.98|2019-01-01:314.83|2019-04-01:300.76|2019-07-01:302.95|2019-10-01:313.07|2020-01-01:301.78|2020-04-01:300.75|2020-07-01:298.17|2020-10-01:296.48|2021-01-01:308.61|2021-04-01:338.03|2021-07-01:305.78|2021-10-01:304.36|2022-01-01:333.84|2022-04-01:322.3|2022-07-01:331.43|2022-10-01:346.38|2023-01-01:350.91|2023-04-01:360.79|2023-07-01:369.21|2023-10-01:371.31|2024-01-01:368.84|2024-04-01:377.29|2024-07-01:371.43|2024-10-01:363.13|2025-01-01:379.58|2025-04-01:386.26|2025-07-01:398.97|2025-10-01:414.07|2026-01-01:405.42|2026-04-01:402.36","22115":"1999-01-01:103.76|1999-04-01:102.54|1999-07-01:99.04|1999-10-01:105.98|2000-01-01:105.01|2000-04-01:109.76|2000-07-01:119.23|2000-10-01:123.27|2001-01-01:128.51|2001-04-01:123.64|2001-07-01:113.41|2001-10-01:106.75|2002-01-01:105.45|2002-04-01:102.95|2002-07-01:102.11|2002-10-01:97.83|2003-01-01:99.52|2003-04-01:98.82|2003-07-01:98.46|2003-10-01:108.8|2004-01-01:107.18|2004-04-01:111.26|2004-07-01:111.27|2004-10-01:115.62|2005-01-01:118.52|2005-04-01:121.08|2005-07-01:119.43|2005-10-01:123.7|2006-01-01:133.74|2006-04-01:137.5|2006-07-01:145.89|2006-10-01:150.92|2007-01-01:160.21|2007-04-01:162.3|2007-07-01:173.4|2007-10-01:179.67|2008-01-01:186.25|2008-04-01:200.8|2008-07-01:206.53|2008-10-01:193.86|2009-01-01:165.64|2009-04-01:174.8|2009-07-01:183.5|2009-10-01:205.43|2010-01-01:230.83|2010-04-01:236.28|2010-07-01:254.2|2010-10-01:255.13|2011-01-01:257.2|2011-04-01:268.23|2011-07-01:271.21|2011-10-01:278.59|2012-01-01:267.86|2012-04-01:274.25|2012-07-01:262.87|2012-10-01:279.03|2013-01-01:288.88|2013-04-01:292.52|2013-07-01:287.39|2013-10-01:286.67|2014-01-01:286.42|2014-04-01:281.42|2014-07-01:289.13|2014-10-01:271.91|2015-01-01:269.12|2015-04-01:252.7|2015-07-01:230.52|2015-10-01:218.26|2016-01-01:206.09|2016-04-01:228.24|2016-07-01:213.32|2016-10-01:221.15|2017-01-01:227.78|2017-04-01:227.59|2017-07-01:233.08|2017-10-01:242.41|2018-01-01:242.99|2018-04-01:242.07|2018-07-01:264.24|2018-10-01:248.4|2019-01-01:239.65|2019-04-01:255.13|2019-07-01:265.99|2019-10-01:250.08|2020-01-01:248.91|2020-04-01:218.19|2020-07-01:201.13|2020-10-01:243.87|2021-01-01:275.41|2021-04-01:264.83|2021-07-01:248.07|2021-10-01:254.39|2022-01-01:248.27|2022-04-01:262.13|2022-07-01:275.41|2022-10-01:269.73|2023-01-01:248.9|2023-04-01:262.75|2023-07-01:263.63|2023-10-01:268.81|2024-01-01:277.6|2024-04-01:301.39|2024-07-01:306.94|2024-10-01:309.42|2025-01-01:319.92|2025-04-01:311.9|2025-07-01:313.41|2025-10-01:309.85|2026-01-01:323|2026-04-01:328.82","1619":"1996-01-01:100|1996-02-01:100|1996-03-01:100|1996-04-01:100|1996-05-01:112|1996-06-01:112|1996-07-01:112|1996-08-01:112|1996-09-01:112|1996-10-01:112|1996-11-01:112|1996-12-01:112|1997-01-01:112|1997-02-01:112|1997-03-01:112|1997-04-01:112|1997-05-01:120|1997-06-01:120|1997-07-01:120|1997-08-01:120|1997-09-01:120|1997-10-01:120|1997-11-01:120|1997-12-01:120|1998-01-01:120|1998-02-01:120|1998-03-01:120|1998-04-01:120|1998-05-01:130|1998-06-01:130|1998-07-01:130|1998-08-01:130|1998-09-01:130|1998-10-01:130|1998-11-01:130|1998-12-01:130|1999-01-01:130|1999-02-01:130|1999-03-01:130|1999-04-01:130|1999-05-01:136|1999-06-01:136|1999-07-01:136|1999-08-01:136|1999-09-01:136|1999-10-01:136|1999-11-01:136|1999-12-01:136|2000-01-01:136|2000-02-01:136|2000-03-01:136|2000-04-01:151|2000-05-01:151|2000-06-01:151|2000-07-01:151|2000-08-01:151|2000-09-01:151|2000-10-01:151|2000-11-01:151|2000-12-01:151|2001-01-01:151|2001-02-01:151|2001-03-01:151|2001-04-01:180|2001-05-01:180|2001-06-01:180|2001-07-01:180|2001-08-01:180|2001-09-01:180|2001-10-01:180|2001-11-01:180|2001-12-01:180|2002-01-01:180|2002-02-01:180|2002-03-01:180|2002-04-01:200|2002-05-01:200|2002-06-01:200|2002-07-01:200|2002-08-01:200|2002-09-01:200|2002-10-01:200|2002-11-01:200|2002-12-01:200|2003-01-01:200|2003-02-01:200|2003-03-01:200|2003-04-01:240|2003-05-01:240|2003-06-01:240|2003-07-01:240|2003-08-01:240|2003-09-01:240|2003-10-01:240|2003-11-01:240|2003-12-01:240|2004-01-01:240|2004-02-01:240|2004-03-01:240|2004-04-01:240|2004-05-01:260|2004-06-01:260|2004-07-01:260|2004-08-01:260|2004-09-01:260|2004-10-01:260|2004-11-01:260|2004-12-01:260|2005-01-01:260|2005-02-01:260|2005-03-01:260|2005-04-01:260|2005-05-01:300|2005-06-01:300|2005-07-01:300|2005-08-01:300|2005-09-01:300|2005-10-01:300|2005-11-01:300|2005-12-01:300|2006-01-01:300|2006-02-01:300|2006-03-01:300|2006-04-01:350|2006-05-01:350|2006-06-01:350|2006-07-01:350|2006-08-01:350|2006-09-01:350|2006-10-01:350|2006-11-01:350|2006-12-01:350|2007-01-01:350|2007-02-01:350|2007-03-01:350|2007-04-01:380|2007-05-01:380|2007-06-01:380|2007-07-01:380|2007-08-01:380|2007-09-01:380|2007-10-01:380|2007-11-01:380|2007-12-01:380|2008-01-01:380|2008-02-01:380|2008-03-01:415|2008-04-01:415|2008-05-01:415|2008-06-01:415|2008-07-01:415|2008-08-01:415|2008-09-01:415|2008-10-01:415|2008-11-01:415|2008-12-01:415|2009-01-01:415|2009-02-01:465|2009-03-01:465|2009-04-01:465|2009-05-01:465|2009-06-01:465|2009-07-01:465|2009-08-01:465|2009-09-01:465|2009-10-01:465|2009-11-01:465|2009-12-01:465|2010-01-01:510|2010-02-01:510|2010-03-01:510|2010-04-01:510|2010-05-01:510|2010-06-01:510|2010-07-01:510|2010-08-01:510|2010-09-01:510|2010-10-01:510|2010-11-01:510|2010-12-01:510|2011-01-01:540|2011-02-01:540|2011-03-01:545|2011-04-01:545|2011-05-01:545|2011-06-01:545|2011-07-01:545|2011-08-01:545|2011-09-01:545|2011-10-01:545|2011-11-01:545|2011-12-01:545|2012-01-01:622|2012-02-01:622|2012-03-01:622|2012-04-01:622|2012-05-01:622|2012-06-01:622|2012-07-01:622|2012-08-01:622|2012-09-01:622|2012-10-01:622|2012-11-01:622|2012-12-01:622|2013-01-01:678|2013-02-01:678|2013-03-01:678|2013-04-01:678|2013-05-01:678|2013-06-01:678|2013-07-01:678|2013-08-01:678|2013-09-01:678|2013-10-01:678|2013-11-01:678|2013-12-01:678|2014-01-01:724|2014-02-01:724|2014-03-01:724|2014-04-01:724|2014-05-01:724|2014-06-01:724|2014-07-01:724|2014-08-01:724|2014-09-01:724|2014-10-01:724|2014-11-01:724|2014-12-01:724|2015-01-01:788|2015-02-01:788|2015-03-01:788|2015-04-01:788|2015-05-01:788|2015-06-01:788|2015-07-01:788|2015-08-01:788|2015-09-01:788|2015-10-01:788|2015-11-01:788|2015-12-01:788|2016-01-01:880|2016-02-01:880|2016-03-01:880|2016-04-01:880|2016-05-01:880|2016-06-01:880|2016-07-01:880|2016-08-01:880|2016-09-01:880|2016-10-01:880|2016-11-01:880|2016-12-01:880|2017-01-01:937|2017-02-01:937|2017-03-01:937|2017-04-01:937|2017-05-01:937|2017-06-01:937|2017-07-01:937|2017-08-01:937|2017-09-01:937|2017-10-01:937|2017-11-01:937|2017-12-01:937|2018-01-01:954|2018-02-01:954|2018-03-01:954|2018-04-01:954|2018-05-01:954|2018-06-01:954|2018-07-01:954|2018-08-01:954|2018-09-01:954|2018-10-01:954|2018-11-01:954|2018-12-01:954|2019-01-01:998|2019-02-01:998|2019-03-01:998|2019-04-01:998|2019-05-01:998|2019-06-01:998|2019-07-01:998|2019-08-01:998|2019-09-01:998|2019-10-01:998|2019-11-01:998|2019-12-01:998|2020-01-01:1039|2020-02-01:1045|2020-03-01:1045|2020-04-01:1045|2020-05-01:1045|2020-06-01:1045|2020-07-01:1045|2020-08-01:1045|2020-09-01:1045|2020-10-01:1045|2020-11-01:1045|2020-12-01:1045|2021-01-01:1100|2021-02-01:1100|2021-03-01:1100|2021-04-01:1100|2021-05-01:1100|2021-06-01:1100|2021-07-01:1100|2021-08-01:1100|2021-09-01:1100|2021-10-01:1100|2021-11-01:1100|2021-12-01:1100|2022-01-01:1212|2022-02-01:1212|2022-03-01:1212|2022-04-01:1212|2022-05-01:1212|2022-06-01:1212|2022-07-01:1212|2022-08-01:1212|2022-09-01:1212|2022-10-01:1212|2022-11-01:1212|2022-12-01:1212|2023-01-01:1302|2023-02-01:1302|2023-03-01:1302|2023-04-01:1302|2023-05-01:1320|2023-06-01:1320|2023-07-01:1320|2023-08-01:1320|2023-09-01:1320|2023-10-01:1320|2023-11-01:1320|2023-12-01:1320|2024-01-01:1412|2024-02-01:1412|2024-03-01:1412|2024-04-01:1412|2024-05-01:1412|2024-06-01:1412|2024-07-01:1412|2024-08-01:1412|2024-09-01:1412|2024-10-01:1412|2024-11-01:1412|2024-12-01:1412|2025-01-01:1518|2025-02-01:1518|2025-03-01:1518|2025-04-01:1518|2025-05-01:1518|2025-06-01:1518|2025-07-01:1518|2025-08-01:1518|2025-09-01:1518|2025-10-01:1518|2025-11-01:1518|2025-12-01:1518|2026-01-01:1621|2026-02-01:1621|2026-03-01:1621|2026-04-01:1621|2026-05-01:1621|2026-06-01:1621|2026-07-01:1621|2026-08-01:1621|2026-09-01:1621|2026-10-01:1621","24378":"2012-03-01:95327|2012-04-01:96029|2012-05-01:96461|2012-06-01:96637|2012-07-01:96691|2012-08-01:96848|2012-09-01:96855|2012-10-01:96822|2012-11-01:96767|2012-12-01:96893|2013-01-01:96923|2013-02-01:97046|2013-03-01:97105|2013-04-01:97382|2013-05-01:97590|2013-06-01:97756|2013-07-01:97867|2013-08-01:97807|2013-09-01:97843|2013-10-01:97763|2013-11-01:97933|2013-12-01:97783|2014-01-01:97684|2014-02-01:97858|2014-03-01:98028|2014-04-01:98248|2014-05-01:98270|2014-06-01:98373|2014-07-01:98353|2014-08-01:98339|2014-09-01:98574|2014-10-01:98697|2014-11-01:98760|2014-12-01:98828|2015-01-01:98914|2015-02-01:99103|2015-03-01:99277|2015-04-01:99575|2015-05-01:99669|2015-06-01:99960|2015-07-01:100188|2015-08-01:100306|2015-09-01:100515|2015-10-01:100787|2015-11-01:100707|2015-12-01:100707|2016-01-01:100678|2016-02-01:100929|2016-03-01:101062|2016-04-01:101182|2016-05-01:101326|2016-06-01:101409|2016-07-01:101311|2016-08-01:101226|2016-09-01:100949|2016-10-01:101019|2016-11-01:101357|2016-12-01:101562|2017-01-01:101669|2017-02-01:101783|2017-03-01:102010|2017-04-01:102168|2017-05-01:102332|2017-06-01:102588|2017-07-01:102788|2017-08-01:102966|2017-09-01:103070|2017-10-01:103166|2017-11-01:103415|2017-12-01:103345|2018-01-01:103352|2018-02-01:103236|2018-03-01:103362|2018-04-01:103245|2018-05-01:103165|2018-06-01:103160|2018-07-01:103491|2018-08-01:103785|2018-09-01:104102|2018-10-01:104333|2018-11-01:104466|2018-12-01:104367|2019-01-01:104344|2019-02-01:104327|2019-03-01:104641|2019-04-01:105015|2019-05-01:105341|2019-06-01:105460|2019-07-01:105476|2019-08-01:105584|2019-09-01:105771|2019-10-01:105922|2019-11-01:105759|2019-12-01:105617|2020-01-01:105497|2020-02-01:105468|2020-03-01:104448|2020-04-01:101515|2020-05-01:98076|2020-06-01:95589|2020-07-01:94612|2020-08-01:95172|2020-09-01:96267|2020-10-01:98046|2020-11-01:99260|2020-12-01:99804|2021-01-01:100114|2021-02-01:100357|2021-03-01:100476|2021-04-01:100795|2021-05-01:101491|2021-06-01:102315|2021-07-01:103150|2021-08-01:103667|2021-09-01:104483|2021-10-01:104904|2021-11-01:105368|2021-12-01:105781|2022-01-01:105504|2022-02-01:105281|2022-03-01:105248|2022-04-01:105866|2022-05-01:106143|2022-06-01:106340|2022-07-01:106533|2022-08-01:106685|2022-09-01:106708|2022-10-01:106663|2022-11-01:106415|2022-12-01:105927|2023-01-01:105612|2023-02-01:105321|2023-03-01:105225|2023-04-01:105092|2023-05-01:105301|2023-06-01:105505|2023-07-01:105808|2023-08-01:106000|2023-09-01:106087|2023-10-01:106396|2023-11-01:106635|2023-12-01:106988|2024-01-01:106809|2024-02-01:106708|2024-03-01:106743|2024-04-01:106923|2024-05-01:107016|2024-06-01:107272|2024-07-01:107360|2024-08-01:107687|2024-09-01:107912|2024-10-01:108327|2024-11-01:108548|2024-12-01:108516|2025-01-01:108050|2025-02-01:108011|2025-03-01:108077|2025-04-01:108391|2025-05-01:108553|2025-06-01:108569|2025-07-01:108554|2025-08-01:108502|2025-09-01:108478|2025-10-01:108465|2025-11-01:108662|2025-12-01:108501|2026-01-01:108522|2026-02-01:108388|2026-03-01:108555|2026-04-01:108655|2026-05-01:108768|2026-06-01:108919|2026-07-01:109154|2026-08-01:109262","24379":"2012-03-01:87713|2012-04-01:88535|2012-05-01:89059|2012-06-01:89318|2012-07-01:89445|2012-08-01:89732|2012-09-01:89958|2012-10-01:90099|2012-11-01:90178|2012-12-01:90209|2013-01-01:89898|2013-02-01:89513|2013-03-01:89298|2013-04-01:89682|2013-05-01:90128|2013-06-01:90419|2013-07-01:90663|2013-08-01:90782|2013-09-01:90982|2013-10-01:91139|2013-11-01:91521|2013-12-01:91683|2014-01-01:91374|2014-02-01:91198|2014-03-01:90947|2014-04-01:91175|2014-05-01:91358|2014-06-01:91573|2014-07-01:91503|2014-08-01:91495|2014-09-01:91827|2014-10-01:92098|2014-11-01:92267|2014-12-01:92340|2015-01-01:92109|2015-02-01:91667|2015-03-01:91312|2015-04-01:91507|2015-05-01:91466|2015-06-01:91553|2015-07-01:91523|2015-08-01:91453|2015-09-01:91466|2015-10-01:91636|2015-11-01:91521|2015-12-01:91585|2016-01-01:91014|2016-02-01:90508|2016-03-01:89909|2016-04-01:89737|2016-05-01:89879|2016-06-01:89827|2016-07-01:89472|2016-08-01:89210|2016-09-01:88939|2016-10-01:88985|2016-11-01:89232|2016-12-01:89239|2017-01-01:88798|2017-02-01:88282|2017-03-01:87880|2017-04-01:88171|2017-05-01:88615|2017-06-01:89163|2017-07-01:89535|2017-08-01:89928|2017-09-01:90176|2017-10-01:90484|2017-11-01:90882|2017-12-01:91066|2018-01-01:90684|2018-02-01:90133|2018-03-01:89691|2018-04-01:89844|2018-05-01:89951|2018-06-01:90212|2018-07-01:90632|2018-08-01:91073|2018-09-01:91607|2018-10-01:91973|2018-11-01:92247|2018-12-01:92152|2019-01-01:91658|2019-02-01:91237|2019-03-01:91203|2019-04-01:91773|2019-05-01:92293|2019-06-01:92662|2019-07-01:92875|2019-08-01:92972|2019-09-01:93191|2019-10-01:93479|2019-11-01:93828|2019-12-01:93920|2020-01-01:93524|2020-02-01:93076|2020-03-01:91523|2020-04-01:88585|2020-05-01:85226|2020-06-01:82610|2020-07-01:81285|2020-08-01:81129|2020-09-01:81954|2020-10-01:83767|2020-11-01:85025|2020-12-01:85669|2021-01-01:85648|2021-02-01:85709|2021-03-01:85497|2021-04-01:85880|2021-05-01:86536|2021-06-01:87743|2021-07-01:88992|2021-08-01:90033|2021-09-01:91265|2021-10-01:92230|2021-11-01:93184|2021-12-01:93988|2022-01-01:93679|2022-02-01:93490|2022-03-01:93523|2022-04-01:94729|2022-05-01:95709|2022-06-01:96445|2022-07-01:96833|2022-08-01:97179|2022-09-01:97435|2022-10-01:97821|2022-11-01:97843|2022-12-01:97517|2023-01-01:96788|2023-02-01:96274|2023-03-01:95978|2023-04-01:96176|2023-05-01:96535|2023-06-01:97038|2023-07-01:97463|2023-08-01:97760|2023-09-01:97938|2023-10-01:98302|2023-11-01:98599|2023-12-01:99062|2024-01-01:98677|2024-02-01:98334|2024-03-01:98290|2024-04-01:98877|2024-05-01:99393|2024-06-01:99883|2024-07-01:100081|2024-08-01:100559|2024-09-01:101058|2024-10-01:101628|2024-11-01:101916|2024-12-01:101832|2025-01-01:100988|2025-02-01:100683|2025-03-01:100511|2025-04-01:101260|2025-05-01:101863|2025-06-01:102316|2025-07-01:102437|2025-08-01:102418|2025-09-01:102433|2025-10-01:102555|2025-11-01:103019|2025-12-01:102998|2026-01-01:102671|2026-02-01:102145|2026-03-01:101976|2026-04-01:102333|2026-05-01:102703|2026-06-01:103057|2026-07-01:103335|2026-08-01:103477","24380":"2012-03-01:7613|2012-04-01:7493|2012-05-01:7403|2012-06-01:7319|2012-07-01:7245|2012-08-01:7116|2012-09-01:6897|2012-10-01:6723|2012-11-01:6589|2012-12-01:6684|2013-01-01:7025|2013-02-01:7532|2013-03-01:7807|2013-04-01:7700|2013-05-01:7463|2013-06-01:7338|2013-07-01:7204|2013-08-01:7024|2013-09-01:6861|2013-10-01:6624|2013-11-01:6413|2013-12-01:6100|2014-01-01:6310|2014-02-01:6660|2014-03-01:7081|2014-04-01:7073|2014-05-01:6912|2014-06-01:6801|2014-07-01:6850|2014-08-01:6844|2014-09-01:6747|2014-10-01:6599|2014-11-01:6492|2014-12-01:6488|2015-01-01:6805|2015-02-01:7436|2015-03-01:7965|2015-04-01:8068|2015-05-01:8203|2015-06-01:8408|2015-07-01:8665|2015-08-01:8853|2015-09-01:9048|2015-10-01:9150|2015-11-01:9186|2015-12-01:9122|2016-01-01:9665|2016-02-01:10422|2016-03-01:11153|2016-04-01:11445|2016-05-01:11447|2016-06-01:11583|2016-07-01:11839|2016-08-01:12016|2016-09-01:12010|2016-10-01:12034|2016-11-01:12126|2016-12-01:12323|2017-01-01:12871|2017-02-01:13501|2017-03-01:14130|2017-04-01:13998|2017-05-01:13717|2017-06-01:13425|2017-07-01:13253|2017-08-01:13039|2017-09-01:12894|2017-10-01:12682|2017-11-01:12533|2017-12-01:12279|2018-01-01:12668|2018-02-01:13102|2018-03-01:13671|2018-04-01:13401|2018-05-01:13214|2018-06-01:12948|2018-07-01:12860|2018-08-01:12712|2018-09-01:12495|2018-10-01:12361|2018-11-01:12219|2018-12-01:12215|2019-01-01:12686|2019-02-01:13090|2019-03-01:13439|2019-04-01:13242|2019-05-01:13049|2019-06-01:12797|2019-07-01:12600|2019-08-01:12612|2019-09-01:12581|2019-10-01:12443|2019-11-01:11931|2019-12-01:11698|2020-01-01:11973|2020-02-01:12392|2020-03-01:12925|2020-04-01:12930|2020-05-01:12850|2020-06-01:12979|2020-07-01:13327|2020-08-01:14043|2020-09-01:14313|2020-10-01:14279|2020-11-01:14235|2020-12-01:14135|2021-01-01:14466|2021-02-01:14648|2021-03-01:14979|2021-04-01:14915|2021-05-01:14955|2021-06-01:14572|2021-07-01:14157|2021-08-01:13634|2021-09-01:13218|2021-10-01:12675|2021-11-01:12183|2021-12-01:11793|2022-01-01:11824|2022-02-01:11791|2022-03-01:11725|2022-04-01:11137|2022-05-01:10434|2022-06-01:9895|2022-07-01:9700|2022-08-01:9506|2022-09-01:9273|2022-10-01:8841|2022-11-01:8572|2022-12-01:8410|2023-01-01:8823|2023-02-01:9047|2023-03-01:9247|2023-04-01:8916|2023-05-01:8767|2023-06-01:8468|2023-07-01:8345|2023-08-01:8240|2023-09-01:8150|2023-10-01:8094|2023-11-01:8037|2023-12-01:7926|2024-01-01:8133|2024-02-01:8374|2024-03-01:8453|2024-04-01:8046|2024-05-01:7623|2024-06-01:7388|2024-07-01:7279|2024-08-01:7128|2024-09-01:6854|2024-10-01:6699|2024-11-01:6632|2024-12-01:6684|2025-01-01:7062|2025-02-01:7328|2025-03-01:7566|2025-04-01:7130|2025-05-01:6690|2025-06-01:6253|2025-07-01:6118|2025-08-01:6084|2025-09-01:6045|2025-10-01:5910|2025-11-01:5644|2025-12-01:5503|2026-01-01:5851|2026-02-01:6243|2026-03-01:6579|2026-04-01:6322|2026-05-01:6065|2026-06-01:5861|2026-07-01:5819|2026-08-01:5784"};
const SNAPSHOT_DATE = "2026-10-28";
const PLOTS = MANIFEST.sections.flatMap(section => section.plots);
const GOVERNMENTS = [
  ["FHC I", "1995-01-01", "1999-01-01", "#dceaf6"],
  ["FHC II", "1999-01-01", "2003-01-01", "#b3cde3"],
  ["Lula I", "2003-01-01", "2007-01-01", "#ff9999"],
  ["Lula II", "2007-01-01", "2011-01-01", "#cc0000"],
  ["Dilma I", "2011-01-01", "2015-01-01", "#ffff99"],
  ["Dilma II", "2015-01-01", "2016-09-01", "#cccc00"],
  ["Temer", "2016-09-01", "2019-01-01", "#d9d9d9"],
  ["Bolsonaro", "2019-01-01", "2023-01-01", "#b3ffb3"],
  ["Lula III", "2023-01-01", "2027-01-01", "#660000"]
];
const SEEDS = Object.fromEntries(Object.entries(PACKED_SEEDS).map(([code, text]) => [
  code, text.split("|").filter(Boolean).map(pair => {
    const [date, value] = pair.split(":");
    return [date, Number(value)];
  })
]));

function monthIndex(date) {
  return Number(date.slice(0, 4)) * 12 + Number(date.slice(5, 7)) - 1;
}

function monthDate(index) {
  return `${Math.floor(index / 12)}-${String(index % 12 + 1).padStart(2, "0")}-01`;
}

function clipped(points, start) {
  return points.filter(point => point[0] >= start);
}

function rolling(points, size, operation) {
  const output = [];
  for (let i = size - 1; i < points.length; i++) {
    const window = points.slice(i - size + 1, i + 1);
    if (monthIndex(window.at(-1)[0]) - monthIndex(window[0][0]) !== size - 1) continue;
    const values = window.map(point => point[1]);
    let value;
    if (operation === "compound") value = (values.reduce((p, x) => p * (1 + x / 100), 1) - 1) * 100;
    else value = values.reduce((sum, x) => sum + x, 0) / (operation === "mean" ? size : 1);
    output.push([points[i][0], value]);
  }
  return output;
}

function monthlyFromYTD(points) {
  return points.flatMap((point, i) => {
    if (point[0].slice(5, 7) === "01") return [point];
    const previous = points[i - 1];
    if (!previous || monthIndex(point[0]) - monthIndex(previous[0]) !== 1 ||
        previous[0].slice(0, 4) !== point[0].slice(0, 4)) return [];
    return [[point[0], point[1] - previous[1]]];
  });
}

function buildSeries(plot, raw) {
  return plot.traces.map(spec => {
    const source = raw[spec.code];
    if (!Array.isArray(source) || !source.length) throw new Error(`Missing series ${spec.code}`);
    let points;
    if (spec.op === "compound12") {
      points = rolling(source, 12, "compound");
    } else if (spec.op === "sum12") {
      // Monthly flows are added once; this is not a year-to-date series.
      points = rolling(source, 12, "sum");
    } else if (spec.op === "rebase_year") {
      const reference = source.filter(point => Number(point[0].slice(0, 4)) === spec.baseYear);
      const expected = spec.frequency === "quarterly" ? 4 : 12;
      if (reference.length !== expected) throw new Error(`Incomplete reference year for SGS ${spec.code}`);
      const base = reference.reduce((sum, point) => sum + point[1], 0) / reference.length;
      if (!Number.isFinite(base) || base === 0) throw new Error(`Invalid reference year for SGS ${spec.code}`);
      points = source.map(point => [point[0], 100 * point[1] / base]);
    } else if (spec.op === "net_exports_rebase_year") {
      // A fixed-2019-weight volume-balance proxy, rebased after subtraction.
      // The negative reference balance is valid and its sign is retained.
      const imports = raw[spec.subtractCode];
      if (!Array.isArray(imports) || !imports.length) throw new Error(`Missing series ${spec.subtractCode}`);
      const referenceMean = (values, code) => {
        const reference = values.filter(point => Number(point[0].slice(0, 4)) === spec.baseYear);
        if (reference.length !== 4) throw new Error(`Incomplete reference year for SGS ${code}`);
        const mean = reference.reduce((sum, point) => sum + point[1], 0) / 4;
        if (!Number.isFinite(mean) || mean <= 0) throw new Error(`Invalid reference year for SGS ${code}`);
        return mean;
      };
      const exportsMean = referenceMean(source, spec.code);
      const importsMean = referenceMean(imports, spec.subtractCode);
      const exportsWeight = spec.exportsWeight, importsWeight = spec.importsWeight;
      const baseBalance = exportsWeight - importsWeight;
      if (!(exportsWeight > 0) || !(importsWeight > 0) || !Number.isFinite(baseBalance) || baseBalance === 0) {
        throw new Error("Invalid net-exports reference balance");
      }
      const importsByDate = new Map(imports);
      points = source.filter(point => importsByDate.has(point[0])).map(([date, value]) => [
        date, 100 * (exportsWeight * value / exportsMean -
          importsWeight * importsByDate.get(date) / importsMean) / baseBalance
      ]);
    } else if (spec.op === "mean3") {
      points = rolling(clipped(source, plot.start), 3, "mean");
    } else if (spec.op === "ytd_sum12") {
      points = rolling(clipped(monthlyFromYTD(source), plot.start), 12, "sum");
    } else if (spec.op === "bndes_original_gdp") {
      // Explicit replication of Fig. 3(a): sum 12 original YTD observations.
      const numerator = rolling(clipped(source, plot.start), 12, "sum");
      const denominator = new Map(rolling(clipped(raw[spec.denominator], plot.start), 12, "sum"));
      points = numerator.filter(point => denominator.has(point[0]) && denominator.get(point[0]) !== 0)
        .map(point => [point[0], 100 * point[1] / denominator.get(point[0])]);
    } else if (spec.op === "bndes_gdp") {
      const numerator = rolling(clipped(monthlyFromYTD(source), plot.start), 12, "sum");
      const denominator = new Map(rolling(clipped(raw[spec.denominator], plot.start), 12, "sum"));
      points = numerator.filter(point => denominator.has(point[0]) && denominator.get(point[0]) !== 0)
        .map(point => [point[0], 100 * point[1] / denominator.get(point[0])]);
    } else if (spec.op === "gdp_real" || spec.op === "deflate_ipca") {
      let level = 1;
      const index = new Map(raw[spec.cpi].map(point => {
        level *= 1 + point[1] / 100;
        return [point[0], level];
      }));
      const base = index.get(spec.base);
      if (!Number.isFinite(base)) throw new Error(`The price reference ${spec.base} is unavailable.`);
      points = source.filter(point => index.has(point[0]))
        .map(point => [point[0], point[1] * base / index.get(point[0])]);
    } else {
      points = source;
    }
    const factor = spec.factor ?? 1;
    points = clipped(points, plot.start).map(point => [point[0], point[1] * factor]);
    if (!points.length) throw new Error(`No observations for ${plot.id}`);
    return { spec, points };
  });
}

function dependencies(plot) {
  return [...new Set(plot.traces.flatMap(trace => [trace.code, trace.cpi, trace.denominator, trace.subtractCode].filter(Number.isFinite)))];
}

function axisBounds(spec, series, hardMinimum) {
  if (spec.fixed === true && Number.isFinite(spec.min) && Number.isFinite(spec.max) && spec.max > spec.min) {
    return [spec.min, spec.max];
  }
  const values = series.flatMap(trace => trace.points.map(point => point[1]));
  const minimum = Math.min(...values);
  const maximum = Math.max(...values);
  const padding = Math.max((maximum - minimum) * .05, Math.abs(maximum) * .015, .01);
  let lower = Number.isFinite(spec.min) ? Math.min(spec.min, minimum - padding) : minimum - padding;
  let upper = Number.isFinite(spec.max) ? Math.max(spec.max, maximum + padding) : maximum + padding;
  if (spec.min === 0 && minimum >= 0) lower = 0;
  if (spec.fixedMin === true && Number.isFinite(spec.min)) lower = spec.min;
  if (Number.isFinite(hardMinimum)) {
    lower = hardMinimum;
    upper = Math.max(hardMinimum + 5, Math.ceil(upper / 5) * 5);
  }
  if (Number.isFinite(spec.tickStep) && spec.tickStep > 0) {
    upper = Math.max(lower + spec.tickStep, Math.ceil(upper / spec.tickStep) * spec.tickStep);
  }
  return [lower, upper];
}

function dateLabel(date, frequency = "monthly") {
  if (frequency === true || frequency === "annual") return date.slice(0, 4);
  if (frequency === "quarterly") return `Q${Math.ceil(Number(date.slice(5, 7)) / 3)} ${date.slice(0, 4)}`;
  return new Intl.DateTimeFormat("en-US", { month: "short", year: "numeric", timeZone: "UTC" })
    .format(new Date(date + "T12:00:00Z"));
}

function addGaps(points, frequency) {
  const output = [];
  for (const point of points) {
    const previous = output.at(-1);
    const difference = previous ? monthIndex(point[0]) - monthIndex(previous[0]) : 0;
    const step = frequency === true || frequency === "annual" ? 12 : frequency === "quarterly" ? 3 : 1;
    if (difference > step) output.push([monthDate(monthIndex(previous[0]) + step), null]);
    output.push(point);
  }
  return output;
}

function rgba(hex, alpha) {
  const fullHex = hex.length === 4 ? "#" + [...hex.slice(1)].map(c => c + c).join("") : hex;
  const rgb = [1, 3, 5].map(i => parseInt(fullHex.slice(i, i + 2), 16));
  return `rgba(${rgb.join(",")},${alpha})`;
}

function wrappedTitle(text, width, fontSize) {
  const limit = Math.max(26, Math.floor((width - 24) / (fontSize * .49)));
  const lines = [""];
  for (const word of text.split(/\s+/)) {
    const line = lines.at(-1);
    if (line && line.length + word.length + 1 > limit) lines.push(word);
    else lines[lines.length - 1] += (line ? " " : "") + word;
  }
  return lines.join("<br>");
}

function chooseLegend(series, ranges, count, width) {
  const boxWidth = Math.min(.45, 105 / Math.max(220, width - 70));
  const boxHeight = Math.min(.7, (count * 17 + 24) / 285);
  const candidates = [
    { x: .02, y: .98, xanchor: "left", yanchor: "top", left: 0, top: 0 },
    { x: .98, y: .98, xanchor: "right", yanchor: "top", left: 1 - boxWidth, top: 0 },
    { x: .02, y: .02, xanchor: "left", yanchor: "bottom", left: 0, top: 1 - boxHeight },
    { x: .98, y: .02, xanchor: "right", yanchor: "bottom", left: 1 - boxWidth, top: 1 - boxHeight }
  ];
  const start = Math.min(...series.flatMap(trace => trace.points.map(point => Date.parse(point[0]))));
  const end = Math.max(...series.flatMap(trace => trace.points.map(point => Date.parse(point[0]))));
  const scored = candidates.map(candidate => {
    let score = 0;
    for (const trace of series) {
      const range = ranges[trace.spec.axis || "y"];
      for (const point of trace.points) {
        const x = (Date.parse(point[0]) - start) / Math.max(1, end - start);
        const y = 1 - (point[1] - range[0]) / Math.max(.01, range[1] - range[0]);
        if (x >= candidate.left && x <= candidate.left + boxWidth &&
            y >= candidate.top && y <= candidate.top + boxHeight) score++;
      }
    }
    return { candidate, score };
  }).sort((a, b) => a.score - b.score);
  const { left, top, ...position } = scored[0].candidate;
  return position;
}

/**
 * Place a vertical Presidents legend only where it clears every data mark.
 *
 * `width` and `height` are the logical Plotly canvas dimensions, before PNG
 * scaling. `margins` must be the margins of the figure actually being drawn.
 * `series` is the unchanged buildSeries output: [{spec, points:[[ISO,value]]}].
 * Pass `preferredPosition` to preserve an existing zero-collision position.
 * An external=true result asks the caller to render its external legend.
 *
 * Geometry is rasterized into a conservative two-pixel occupancy grid. A
 * summed-area table then makes every candidate-box collision test O(1).
 */
function chooseLegendPlacement({
  series, ranges, start, end, width, height, margins,
  labels, fontSize = 10, titleSize = 10,
  preferredPosition = null, previousPosition = null
}) {
  const padding = 4;
  const cell = 2;
  const entries = Array.isArray(labels) ? labels.map(String) : [];
  const font = Number.isFinite(fontSize) ? fontSize : 10;
  const titleFont = Number.isFinite(titleSize) ? titleSize : 10;
  const plotWidth = Math.max(0, width - (margins?.l || 0) - (margins?.r || 0));
  const plotHeight = Math.max(0, height - (margins?.t || 0) - (margins?.b || 0));

  // Times-like character advances, calibrated to Plotly 3.1 SVG rectangles:
  // 8 labels => 87x175 @font10/title10; 74x173 @font7/title8.
  function emWidth(text) {
    const widths = {
      " ": .25, i: .278, l: .278, I: .333, j: .278, t: .278,
      f: .333, r: .333, s: .389, a: .444, c: .444, e: .444,
      v: .5, x: .5, y: .5, z: .444, m: .778, w: .722,
      B: .667, F: .556, H: .722, L: .611, P: .556,
      M: .889, W: .944, T: .611
    };
    return [...text].reduce((sum, character) => sum +
      (widths[character] ?? (/[A-Z]/.test(character) ? .667 : .5)), 0);
  }
  const widest = Math.max(0, ...entries.map(label => emWidth(label) * font * 1.04));
  const legendWidth = entries.length ? Math.ceil(Math.max(44 + widest, 12 + emWidth("Presidents") * titleFont * 1.04)) : 0;
  const rowHeight = Math.max(19, Math.ceil(font * 1.25 + 5));
  const legendHeight = entries.length ? entries.length * rowHeight + titleFont + 13 : 0;
  const box = { width: legendWidth, height: legendHeight };
  const defaultPosition = { x: .02, y: .98, xanchor: "left", yanchor: "top" };
  if (!entries.length) return { external: false, position: defaultPosition, box };
  if (plotWidth < legendWidth + padding * 2 || plotHeight < legendHeight + padding * 2) {
    return { external: true, position: defaultPosition, box };
  }

  const columns = Math.ceil(plotWidth / cell);
  const rows = Math.ceil(plotHeight / cell);
  const occupied = new Uint8Array(columns * rows);
  const first = Date.parse(start);
  const last = Date.parse(end);
  if (!Number.isFinite(first) || !Number.isFinite(last) || last <= first) {
    return { external: true, position: defaultPosition, box };
  }

  function rectangle(left, top, right, bottom) {
    if (right < 0 || bottom < 0 || left > plotWidth || top > plotHeight) return;
    const x0 = Math.max(0, Math.floor(left / cell));
    const x1 = Math.min(columns - 1, Math.floor(right / cell));
    const y0 = Math.max(0, Math.floor(top / cell));
    const y1 = Math.min(rows - 1, Math.floor(bottom / cell));
    for (let y = y0; y <= y1; y++) occupied.fill(1, y * columns + x0, y * columns + x1 + 1);
  }

  function point(date, value, range) {
    if (!Number.isFinite(value) || !range || range[1] <= range[0]) return null;
    const stamp = Date.parse(date);
    if (!Number.isFinite(stamp)) return null;
    return [(stamp - first) / (last - first) * plotWidth,
      (range[1] - value) / (range[1] - range[0]) * plotHeight];
  }

  function segment(a, b, thickness) {
    // Sample at no more than one pixel along the longest direction. The
    // occupied cell footprint is conservative relative to the actual stroke.
    const distance = Math.max(Math.abs(b[0] - a[0]), Math.abs(b[1] - a[1]));
    const samples = Math.max(1, Math.ceil(distance));
    const radius = Math.max(.8, thickness / 2);
    for (let i = 0; i <= samples; i++) {
      const t = i / samples;
      const x = a[0] + (b[0] - a[0]) * t;
      const y = a[1] + (b[1] - a[1]) * t;
      rectangle(x - radius, y - radius, x + radius, y + radius);
    }
  }

  const barSeries = series.filter(trace => trace.spec?.type === "bar");
  const barCount = Math.max(1, barSeries.length);
  for (const trace of series) {
    const spec = trace.spec || {};
    const range = ranges[spec.axis || "y"] || ranges.y;
    const values = trace.points || [];
    if (spec.type === "bar") {
      const differences = values.slice(1).map((value, i) => Date.parse(value[0]) - Date.parse(values[i][0]))
        .filter(value => Number.isFinite(value) && value > 0).sort((a, b) => a - b);
      const interval = differences.length ? differences[Math.floor(differences.length / 2)] : 365.25 * 86400000;
      const totalWidth = .8 * interval / (last - first) * plotWidth;
      const barWidth = totalWidth / barCount;
      const offset = (barSeries.indexOf(trace) - (barCount - 1) / 2) * barWidth;
      const zero = point(start, 0, range);
      if (!zero) continue;
      for (const value of values) {
        const p = point(value[0], value[1], range);
        if (p) rectangle(p[0] + offset - barWidth / 2, Math.min(p[1], zero[1]),
          p[0] + offset + barWidth / 2, Math.max(p[1], zero[1]));
      }
    } else {
      let previous = null;
      let previousDate = null;
      for (let i = 0; i < values.length; i++) {
        const value = values[i];
        const p = point(value[0], value[1], range);
        const month = Number(value[0].slice(0, 4)) * 12 + Number(value[0].slice(5, 7));
        const gap = previousDate === null ? 0 : month - previousDate;
        const maximumGap = spec.frequency === "annual" ? 12 : spec.frequency === "quarterly" ? 3 : 1;
        if (p && previous && gap <= maximumGap) segment(previous, p, Math.max(1.3, spec.width || 1));
        if (p && spec.marker && i % (spec.markerEvery || 1) === 0) rectangle(p[0] - 3, p[1] - 3, p[0] + 3, p[1] + 3);
        previous = p;
        previousDate = month;
      }
    }
  }

  const stride = columns + 1;
  const integral = new Uint32Array(stride * (rows + 1));
  for (let y = 0; y < rows; y++) {
    let sum = 0;
    for (let x = 0; x < columns; x++) {
      sum += occupied[y * columns + x];
      integral[(y + 1) * stride + x + 1] = integral[y * stride + x + 1] + sum;
    }
  }

  function collision(left, top) {
    const x0 = Math.max(0, Math.floor((left - padding) / cell));
    const y0 = Math.max(0, Math.floor((top - padding) / cell));
    const x1 = Math.min(columns, Math.ceil((left + legendWidth + padding) / cell));
    const y1 = Math.min(rows, Math.ceil((top + legendHeight + padding) / cell));
    return integral[y1 * stride + x1] - integral[y0 * stride + x1] -
      integral[y1 * stride + x0] + integral[y0 * stride + x0];
  }

  const preference = preferredPosition || previousPosition;
  function pixels(position) {
    if (!position) return null;
    const x = position.x * plotWidth - (position.xanchor === "right" ? legendWidth : position.xanchor === "center" ? legendWidth / 2 : 0);
    const y = (1 - position.y) * plotHeight - (position.yanchor === "bottom" ? legendHeight : position.yanchor === "middle" ? legendHeight / 2 : 0);
    return [x, y];
  }
  function paper(left, top) {
    return { x: left / plotWidth, y: 1 - top / plotHeight, xanchor: "left", yanchor: "top" };
  }
  function fits(left, top) {
    return left >= padding && top >= padding &&
      left + legendWidth <= plotWidth - padding && top + legendHeight <= plotHeight - padding;
  }
  const preferred = pixels(preference);
  if (preferred && fits(...preferred) && collision(...preferred) === 0) {
    return { external: false, position: paper(...preferred), box };
  }

  const right = plotWidth - legendWidth - padding;
  const bottom = plotHeight - legendHeight - padding;
  const xs = [], ys = [];
  for (let x = padding; x < right; x += 8) xs.push(x);
  for (let y = padding; y < bottom; y += 8) ys.push(y);
  xs.push(right); ys.push(bottom);
  let best = null;
  for (const top of ys) for (const left of xs) {
    const count = collision(left, top);
    const distance = preferred ? Math.hypot(left - preferred[0], top - preferred[1]) : left + top;
    if (!best || count < best.count || (count === best.count && distance < best.distance)) {
      best = { left, top, count, distance };
    }
  }
  return {
    external: !best || best.count !== 0,
    position: best ? paper(best.left, best.top) : defaultPosition,
    box
  };
}


/* Place compact legends inside the plotting rectangle without changing data. */
function chooseInsideLegendLayout({
  series, ranges, start, end, width, height, margins,
  labels, fontSize = 10, titleSize = 10, preferredPosition = null,
  hardRanges = false, indicatorPosition = null, _heightSearch = false
}) {
  const pw = Math.max(1, width - margins.l - margins.r);
  const ph = Math.max(1, height - margins.t - margins.b);
  const font = Math.max(1, Number(fontSize) || 10);
  const titleFont = Math.max(1, Number(titleSize) || 10);
  const inset = 5, clearance = 8, gap = 10, cell = 2;
  const original = Object.fromEntries(Object.entries(ranges).map(([axis, range]) => [axis, range.slice()]));
  const presidents = Array.isArray(labels) ? labels.map(String) : [];
  const indicators = series.length > 1 ? series.map(trace => String(trace.spec.legendLabel || trace.spec.label || "Indicator")) : [];
  const first = Date.parse(start), last = Date.parse(end);

  function textWidth(text) {
    const advance = { " ": .25, i: .278, l: .278, I: .333, j: .278, t: .278,
      f: .333, r: .333, s: .389, a: .444, c: .444, e: .444, m: .778, w: .722,
      M: .889, W: .944, B: .667, F: .556, H: .722, L: .611, P: .556, T: .611,
      "—": 1, "–": .5, "%": .833, "/": .278 };
    return Math.ceil([...text].reduce((sum, letter) => sum +
      (advance[letter] ?? (/[A-Z]/.test(letter) ? .667 : .5)), 0) * font * 1.1 + 1);
  }
  function boxes(items, requested, isPresident) {
    if (!items.length) return [];
    const columns = [...new Set(requested.map(n => Math.min(n, items.length)))];
    const columnWidth = Math.max(...items.map(textWidth)) + (isPresident ? 14 : 32);
    const rowHeight = Math.max(12, Math.ceil(font * 1.15) + 3);
    const title = isPresident ? "Presidents" : "Indicators";
    return columns.map(count => {
      const rows = Math.ceil(items.length / count);
      return { box: { width: Math.max(count * columnWidth + (count - 1) * gap, textWidth(title)) + 10,
          height: rows * rowHeight + titleFont + 3 + 10 },
        columns: count, rows, columnWidth, rowHeight, fontSize: font, titleSize: titleFont };
    }).filter(info => info.box.width <= pw - inset * 2 && info.box.height <= ph - inset * 2);
  }
  const presidentBoxes = boxes(presidents, [2, 4], true);
  const indicatorBoxes = boxes(indicators, [1, 2, 4], false);
  const columns = Math.ceil(pw / cell), rows = Math.ceil(ph / cell), stride = columns + 1;
  const occupied = new Uint8Array(columns * rows);
  function paint(left, top, right, bottom) {
    if (right < 0 || bottom < 0 || left > pw || top > ph) return;
    const x0 = Math.max(0, Math.floor(left / cell)), x1 = Math.min(columns - 1, Math.floor(right / cell));
    const y0 = Math.max(0, Math.floor(top / cell)), y1 = Math.min(rows - 1, Math.floor(bottom / cell));
    for (let y = y0; y <= y1; y++) occupied.fill(1, y * columns + x0, y * columns + x1 + 1);
  }
  function point(value, range) {
    if (!value || !Number.isFinite(value[1]) || !range || !(range[1] > range[0])) return null;
    const date = Date.parse(value[0]);
    if (!Number.isFinite(date) || !(last > first)) return null;
    return [(date - first) / (last - first) * pw, (range[1] - value[1]) / (range[1] - range[0]) * ph];
  }
  function line(a, b, thickness) {
    const n = Math.max(1, Math.ceil(Math.max(Math.abs(b[0] - a[0]), Math.abs(b[1] - a[1]))));
    const radius = Math.max(1, thickness / 2);
    for (let k = 0; k <= n; k++) {
      const x = a[0] + (b[0] - a[0]) * k / n, y = a[1] + (b[1] - a[1]) * k / n;
      paint(x - radius, y - radius, x + radius, y + radius);
    }
  }
  const bars = series.filter(trace => trace.spec.type === "bar");
  for (const trace of series) {
    const spec = trace.spec || {}, range = original[spec.axis || "y"], values = trace.points || [];
    if (spec.type === "bar") {
      const differences = values.slice(1).map((value, i) => Date.parse(value[0]) - Date.parse(values[i][0]))
        .filter(value => value > 0).sort((a, b) => a - b);
      const interval = differences.length ? differences[Math.floor(differences.length / 2)] : 365.25 * 86400000;
      const bw = .8 * interval / (last - first) * pw / Math.max(1, bars.length);
      const offset = (bars.indexOf(trace) - (bars.length - 1) / 2) * bw;
      const baseline = point([start, 0], range);
      if (baseline) for (const value of values) {
        const p = point(value, range);
        if (p) paint(p[0] + offset - bw / 2, Math.min(p[1], baseline[1]),
          p[0] + offset + bw / 2, Math.max(p[1], baseline[1]));
      }
    } else {
      let previous = null, previousMonth = null;
      const maximumGap = spec.frequency === "annual" ? 12 : spec.frequency === "quarterly" ? 3 : 1;
      for (let index = 0; index < values.length; index++) {
        const value = values[index], p = point(value, range);
        const month = Number(value[0].slice(0, 4)) * 12 + Number(value[0].slice(5, 7));
        if (p && previous && month - previousMonth <= maximumGap) line(previous, p, Math.max(1.3, spec.width || 1));
        if (p) {
          const radius = spec.marker && index % (spec.markerEvery || 1) === 0 ? 3 : 1;
          paint(p[0] - radius, p[1] - radius, p[0] + radius, p[1] + radius);
        }
        previous = p; previousMonth = month;
      }
    }
  }
  const sat = new Uint32Array(stride * (rows + 1));
  for (let y = 0; y < rows; y++) {
    let sum = 0;
    for (let x = 0; x < columns; x++) {
      sum += occupied[y * columns + x];
      sat[(y + 1) * stride + x + 1] = sat[y * stride + x + 1] + sum;
    }
  }
  function hits(left, top, box) {
    const x0 = Math.max(0, Math.floor((left - clearance) / cell));
    const x1 = Math.min(columns, Math.ceil((left + box.width + clearance) / cell));
    const y0 = Math.max(0, Math.floor((top - clearance) / cell));
    const y1 = Math.min(rows, Math.ceil((top + box.height + clearance) / cell));
    return sat[y1 * stride + x1] - sat[y0 * stride + x1] - sat[y1 * stride + x0] + sat[y0 * stride + x0];
  }
  function preference(info, requested, defaultBottom = false) {
    let position = requested;
    if (typeof requested === "string") {
      const parts = requested.split("-");
      position = { x: parts[1] === "right" ? 1 : parts[1] === "center" ? .5 : 0,
        y: parts[0] === "bottom" ? 0 : parts[0] === "middle" ? .5 : 1,
        xanchor: parts[1] || "left", yanchor: parts[0] === "bottom" ? "bottom" : parts[0] === "middle" ? "middle" : "top" };
    }
    position = position || { x: 0, y: defaultBottom ? 0 : 1, xanchor: "left", yanchor: defaultBottom ? "bottom" : "top" };
    return [position.x * pw - (position.xanchor === "right" ? info.box.width : position.xanchor === "center" ? info.box.width / 2 : 0),
      (1 - position.y) * ph - (position.yanchor === "bottom" ? info.box.height : position.yanchor === "middle" ? info.box.height / 2 : 0)];
  }
  function locations(info, requested, defaultBottom = false) {
    const pref = preference(info, requested, defaultBottom), right = pw - info.box.width - inset, bottom = ph - info.box.height - inset;
    const xs = [inset, right, Math.max(inset, Math.min(right, pref[0]))];
    const ys = [inset, bottom, Math.max(inset, Math.min(bottom, pref[1]))];
    for (let x = inset; x < right; x += 8) xs.push(x);
    for (let y = inset; y < bottom; y += 8) ys.push(y);
    const found = [];
    for (const top of new Set(ys)) for (const left of new Set(xs)) {
      if (!hits(left, top, info.box)) found.push({ left, top, distance: Math.hypot(left - pref[0], top - pref[1]) });
    }
    return found.sort((a, b) => a.distance - b.distance);
  }
  function pack(info, at) {
    return { ...info, position: { x: at.left / pw, y: 1 - at.top / ph, xanchor: "left", yanchor: "top" } };
  }
  function separate(a, ai, b, bi) {
    return a.left + ai.box.width + clearance <= b.left || b.left + bi.box.width + clearance <= a.left ||
      a.top + ai.box.height + clearance <= b.top || b.top + bi.box.height + clearance <= a.top;
  }
  // Prefer a common visual edge before allowing unrelated positions. All
  // candidates use the existing plot ranges and collision map: alignment alone
  // never reserves more space or changes the figure's height.
  const presidentLocationCache = new Map();
  function freePresidents(info) {
    if (!presidentLocationCache.has(info)) presidentLocationCache.set(info, locations(info, preferredPosition));
    return presidentLocationCache.get(info);
  }
  function axisCandidates(maximum, preferred, extra) {
    if (maximum < inset) return [];
    const values = [inset, maximum, Math.max(inset, Math.min(maximum, preferred)), ...extra];
    for (let value = inset; value < maximum; value += 8) values.push(value);
    return [...new Set(values)].filter(value => value >= inset && value <= maximum)
      .sort((a, b) => Math.abs(a - preferred) - Math.abs(b - preferred) || a - b);
  }
  function alignedLocation(anchorInfo, anchor, candidateInfo, edge, requested = null, defaultBottom = false) {
    const pref = preference(candidateInfo, requested, defaultBottom);
    const xmax = pw - candidateInfo.box.width - inset, ymax = ph - candidateInfo.box.height - inset;
    let positions;
    if (edge === "top" || edge === "bottom") {
      const top = edge === "top" ? anchor.top : anchor.top + anchorInfo.box.height - candidateInfo.box.height;
      positions = axisCandidates(xmax, pref[0], [anchor.left - candidateInfo.box.width - clearance,
        anchor.left + anchorInfo.box.width + clearance]).map(left => ({ left, top }));
    } else {
      const left = edge === "left" ? anchor.left : anchor.left + anchorInfo.box.width - candidateInfo.box.width;
      positions = axisCandidates(ymax, pref[1], [anchor.top - candidateInfo.box.height - clearance,
        anchor.top + anchorInfo.box.height + clearance]).map(top => ({ left, top }));
    }
    for (const at of positions) {
      if (at.left < inset || at.top < inset || at.left > xmax || at.top > ymax) continue;
      if (separate(anchor, anchorInfo, at, candidateInfo) && !hits(at.left, at.top, candidateInfo.box)) return at;
    }
    return null;
  }
  function requireMoreHeight(code, message, extra = {}) {
    if (!_heightSearch) {
      const candidates = [...new Set([height + 80, height + 160, height + 320, height + 480, height + 800, Math.max(1600, height + 1000)])];
      for (const nextHeight of candidates) {
        try {
          const result = chooseInsideLegendLayout({ series, ranges: original, start, end, width,
            height: nextHeight, margins, labels, fontSize: font, titleSize: titleFont,
            preferredPosition, hardRanges, indicatorPosition, _heightSearch: true });
          return { ...result, requiredHeight: nextHeight };
        } catch (error) {
          if (!String(error.code || "").startsWith("INSIDE_LEGEND_")) throw error;
          if (error.code === "INSIDE_LEGEND_WIDTH") throw error;
        }
      }
    }
    const error = new Error(message);
    error.code = code;
    Object.assign(error, extra);
    throw error;
  }
  if (indicatorPosition === "top-aligned" && indicators.length) {
    const pairs = [];
    for (const pi of presidentBoxes) for (const ii of indicatorBoxes) {
      const combinedWidth = pi.box.width + clearance + ii.box.width;
      if (combinedWidth <= pw - inset * 2) pairs.push({ pi, ii, combinedWidth });
    }
    if (!pairs.length) {
      const error = new Error("The two aligned legend boxes need a wider plotting area.");
      error.code = "INSIDE_LEGEND_WIDTH";
      error.requiredWidth = margins.l + margins.r + inset * 2 +
        Math.min(...presidentBoxes.map(info => info.box.width)) + clearance +
        Math.min(...indicatorBoxes.map(info => info.box.width));
      throw error;
    }
    // Keep Presidents left of Indicators. Shift the whole top-aligned block
    // toward the right first, leaving the early-2000s Selic peak unobstructed.
    for (const { pi, ii, combinedWidth } of pairs) {
      const right = pw - combinedWidth - inset;
      const lefts = [right, inset];
      for (let left = right; left > inset; left -= 4) lefts.push(left);
      for (const left of new Set(lefts)) {
        const p = { left, top: inset }, i = { left: left + pi.box.width + clearance, top: inset };
        if (!hits(p.left, p.top, pi.box) && !hits(i.left, i.top, ii.box)) return {
          ranges: original, presidents: pack(pi, p), indicators: pack(ii, i), reservedFraction: 0 };
      }
    }
    return requireMoreHeight("INSIDE_LEGEND_TOP_COLLISION",
      "The aligned top legend boxes need a taller plotting area while preserving the requested axis ranges.");
  }
  if (indicatorPosition === "bottom-right" && indicators.length) {
    // Indicators remain exactly five pixels from the lower-right plot corner.
    // First align Presidents with their base or their vertical column.
    for (const edge of ["bottom", "right", "left"]) for (const ii of indicatorBoxes) {
      const i = { left: pw - ii.box.width - inset, top: ph - ii.box.height - inset };
      if (hits(i.left, i.top, ii.box)) continue;
      for (const pi of presidentBoxes) {
        const p = alignedLocation(ii, i, pi, edge, preferredPosition);
        if (p) return { ranges: original, presidents: pack(pi, p), indicators: pack(ii, i),
          reservedFraction: 0, alignment: edge };
      }
    }
    for (const ii of indicatorBoxes) {
      const i = { left: pw - ii.box.width - inset, top: ph - ii.box.height - inset };
      if (hits(i.left, i.top, ii.box)) continue;
      for (const pi of presidentBoxes) for (const p of freePresidents(pi)) {
        if (separate(p, pi, i, ii)) return {
          ranges: original, presidents: pack(pi, p), indicators: pack(ii, i), reservedFraction: 0 };
      }
    }
    return requireMoreHeight("INSIDE_LEGEND_BOTTOM_RIGHT_COLLISION",
      "The bottom-right indicator box needs a taller plotting area to clear the data.");
  }
  if (indicators.length) {
    // Search every permitted column configuration for a side-by-side pair
    // before considering a vertically stacked pair or independent placement.
    for (const edge of ["top", "bottom", "left", "right"]) {
      for (const pi of presidentBoxes) for (const ii of indicatorBoxes) {
        for (const p of freePresidents(pi)) {
          const i = alignedLocation(pi, p, ii, edge, null, true);
          if (i) return { ranges: original, presidents: pack(pi, p), indicators: pack(ii, i),
            reservedFraction: 0, alignment: edge };
        }
      }
    }
  }
  const alternatives = indicatorBoxes.map(info => {
    const places = locations(info, null, true);
    const extremes = places.length ? [places[0],
      places.reduce((a, b) => a.left < b.left ? a : b), places.reduce((a, b) => a.left > b.left ? a : b),
      places.reduce((a, b) => a.top < b.top ? a : b), places.reduce((a, b) => a.top > b.top ? a : b)] : [];
    return { info, places: [...new Set(extremes)] };
  });
  for (const pi of presidentBoxes) for (const p of freePresidents(pi)) {
    if (!indicators.length) return { ranges: original, presidents: pack(pi, p), indicators: null, reservedFraction: 0 };
    for (const alternative of alternatives) for (const i of alternative.places) {
      if (separate(p, pi, i, alternative.info)) return {
        ranges: original, presidents: pack(pi, p), indicators: pack(alternative.info, i), reservedFraction: 0 };
    }
  }
  if (hardRanges) return requireMoreHeight("INSIDE_LEGEND_HARD_RANGE_COLLISION",
    "A taller plotting area is needed to retain the fixed axis ranges without covering data.");
  // A reserved top band guarantees visible legends even for dense line/bar plots.
  const arrangements = [];
  for (const pi of presidentBoxes) {
    if (!indicators.length) arrangements.push({ pi, p: { left: inset, top: inset }, bottom: inset + pi.box.height });
    for (const ii of indicatorBoxes) {
      if (pi.box.width + clearance + ii.box.width <= pw - inset * 2) arrangements.push({ pi, ii,
        p: { left: inset, top: inset }, i: { left: inset + pi.box.width + clearance, top: inset },
        bottom: inset + Math.max(pi.box.height, ii.box.height) });
      if (pi.box.height + clearance + ii.box.height <= ph - inset * 2) arrangements.push({ pi, ii,
        p: { left: inset, top: inset }, i: { left: inset, top: inset + pi.box.height + clearance },
        bottom: inset + pi.box.height + clearance + ii.box.height });
    }
  }
  const fitting = arrangements.filter(item => item.bottom + clearance + cell < ph);
  fitting.sort((a, b) => a.bottom - b.bottom || a.pi.columns - b.pi.columns);
  const chosen = fitting[0];
  if (!chosen) throw new Error("Plot area is too small for the inside legends.");
  const reservedFraction = (chosen.bottom + clearance + cell) / ph;
  const expanded = Object.fromEntries(Object.entries(original).map(([axis, range]) => [axis,
    [range[0], range[0] + (range[1] - range[0]) / (1 - reservedFraction)]]));
  return { ranges: expanded, presidents: pack(chosen.pi, chosen.p),
    indicators: chosen.ii ? pack(chosen.ii, chosen.i) : null, reservedFraction };
}




function belowLegendLayout({ plot, series, ranges, width, height, margins, governments }) {
  // Mobile legends retain the desktop palette, borders and typography while
  // using a dedicated band below a consistently sized data rectangle.
  const fontSize = 10, titleSize = 11, rowHeight = 15, gap = 10;
  const textWidth = text => Math.ceil(String(text).length * fontSize * .58);
  const box = (labels, columns, swatch) => {
    const rows = Math.ceil(labels.length / columns);
    const columnWidth = Math.max(...labels.map(textWidth)) + swatch;
    return { columns, rows, columnWidth, rowHeight, fontSize, titleSize,
      box: { width: columns * columnWidth + (columns - 1) * gap + 10,
        height: rows * rowHeight + titleSize + 13 } };
  };
  const presidentLabels = governments.map(government => government[0]);
  const indicatorLabels = series.length > 1 ? series.map((trace, index) =>
    plot.mobile_legend_labels?.[index] || trace.spec.legendLabel || trace.spec.label) : [];
  const presidents = box(presidentLabels, 2, 14);
  const indicators = indicatorLabels.length ? box(indicatorLabels, 1, 32) : null;
  const stacked = indicators && presidents.box.width + indicators.box.width + gap > width - 10;
  const legendHeight = indicators ? (stacked ? presidents.box.height + gap + indicators.box.height :
    Math.max(presidents.box.height, indicators.box.height)) : presidents.box.height;
  margins.b = 55 + legendHeight + 8;
  const requiredHeight = Math.max(height, margins.t + margins.b + 260);
  const pw = width - margins.l - margins.r;
  const ph = height - margins.t - margins.b;
  const position = (left, top) => ({ x: (left - margins.l) / pw,
    y: 1 - (ph + 55 + top) / ph, xanchor: "left", yanchor: "top" });
  presidents.position = position(5, 0);
  if (indicators) indicators.position = stacked ? position(5, presidents.box.height + gap) :
    position(width - indicators.box.width - 5, 0);
  return { ranges, presidents, indicators, indicatorLabels, reservedFraction: 0, below: true, requiredHeight };
}

function figureFor(plot, series, width = 520, options = {}) {
  const narrow = width < 500;
  const mobile = options.mobile === true;
  const below = mobile && plot.mobile_legend_below === true && !options.forExport;
  const requestedHeight = options.height ?? (mobile ? 320 : 352);
  const height = below ? Math.max(400, requestedHeight) : requestedHeight;
  const legendFont = (narrow ? 9 : 10) - (mobile ? 2 : 0);
  const legendTitleFont = 10 - (mobile ? 2 : 0);
  const margins = options.margins || { l: 60, r: plot.axis2 ? 64 : 14, t: mobile ? 22 : 14, b: 48 };
  const range = axisBounds(plot.axis, series.filter(trace => (trace.spec.axis || "y") === "y"));
  const ranges = { y: range };
  if (plot.axis2) ranges.y2 = axisBounds(plot.axis2, series.filter(trace => trace.spec.axis === "y2"));
  if (Number.isFinite(plot.align_index_base)) {
    // Use symmetric scales so the shared index reference has the same height.
    for (const axis of Object.keys(ranges)) {
      const values = series.filter(trace => (trace.spec.axis || "y") === axis)
        .flatMap(trace => trace.points.map(point => point[1]));
      const spec = axis === "y" ? plot.axis : plot.axis2;
      const step = spec.tickStep || 20;
      const distance = Math.max(...values.map(value => Math.abs(value - plot.align_index_base)));
      const radius = Math.max(step, Math.ceil(distance * 1.1 / step) * step);
      ranges[axis].splice(0, 2, plot.align_index_base - radius, plot.align_index_base + radius);
    }
  }
  const finalDate = series.flatMap(trace => trace.points).map(point => point[0]).sort().at(-1);
  const allAnnual = plot.traces.every(trace => trace.frequency === "annual");
  const allQuarterly = plot.traces.every(trace => trace.frequency === "quarterly");
  const end = allAnnual ? `${Number(finalDate.slice(0, 4)) + 1}-01-01` : monthDate(monthIndex(finalDate) + (allQuarterly ? 3 : 1));
  const governments = GOVERNMENTS.filter(government => government[1] < end && government[2] > plot.start);
  const inside = plot.legend_mode === "inside" ? (below ? belowLegendLayout({
    plot, series, ranges, width, height, margins, governments
  }) : chooseInsideLegendLayout({
    series, ranges, start: plot.start, end, width, height, margins,
    labels: governments.map(government => government[0]), fontSize: legendFont,
    titleSize: legendTitleFont, preferredPosition: plot.president_legend?.position,
    hardRanges: plot.axis.fixed === true || plot.axis2?.fixed === true, indicatorPosition: plot.legend_layout?.indicators
  })) : null;
  if (inside?.requiredHeight > height) {
    return figureFor(plot, series, width, { ...options, height: inside.requiredHeight });
  }
  if (inside) {
    for (const axis of Object.keys(ranges)) ranges[axis].splice(0, 2, ...inside.ranges[axis]);
    if (Number.isFinite(plot.axis.tickStep)) {
      ranges.y[1] = Math.ceil(ranges.y[1] / plot.axis.tickStep) * plot.axis.tickStep;
    }
  }
  const twoColumns = plot.president_legend?.columns === 2;
  const externalColumns = twoColumns && plot.president_legend.position === "external";
  const fixedLegend = !inside && !options.forExport && twoColumns && !externalColumns;
  const placement = inside || options.forExport || fixedLegend || externalColumns ? { external: true } : chooseLegendPlacement({
    series, ranges, start: plot.start, end, width, height, margins,
    labels: governments.map(government => government[0]), fontSize: legendFont,
    titleSize: legendTitleFont,
    preferredPosition: chooseLegend(series, ranges, governments.length, width)
  });
  const shapes = governments.map(government => ({
    type: "rect", xref: "x", yref: "paper", x0: government[1] < plot.start ? plot.start : government[1],
    x1: government[2] > end ? end : government[2], y0: 0, y1: 1,
    fillcolor: government[3], opacity: .3, line: { width: 0 }, layer: "below", showlegend: false
  }));
  if (Number.isFinite(plot.reference_line)) shapes.push({
    type: "line", xref: "paper", yref: "y", x0: 0, x1: 1,
    y0: plot.reference_line, y1: plot.reference_line,
    line: { color: "#777", width: .8, dash: "dot" }, layer: "below", showlegend: false
  });
  if (plot.id === "fig5d") shapes.push({
    type: "line", xref: "paper", yref: "y", x0: 0, x1: 1, y0: 1, y1: 1,
    line: { color: "#777", width: .8, dash: "dash" }, showlegend: false
  });
  const data = series.map(trace => {
    const spec = trace.spec;
    const points = addGaps(trace.points, spec.frequency);
    const item = {
      x: points.map(point => point[0]), y: points.map(point => point[1]),
      customdata: points.map(point => dateLabel(point[0], spec.frequency)),
      name: spec.label, type: spec.type || "scatter", yaxis: spec.axis || "y", showlegend: false,
      legend: "legend2", connectgaps: false,
      hovertemplate: `%{customdata}<br><b>%{y:,.3~f}</b><extra>${spec.label}</extra>`
    };
    if (spec.type === "bar") {
      item.marker = { color: spec.color || "#111", opacity: spec.opacity ?? 1 };
    } else {
      item.mode = spec.marker ? "lines+markers" : "lines";
      item.line = { color: spec.color || "#111", width: Math.max(1.3, spec.width || 1), dash: spec.dash || "solid" };
      item.opacity = spec.opacity ?? 1;
      if (spec.marker) item.marker = {
        symbol: spec.marker, size: points.map((point, i) => i % (spec.markerEvery || 1) === 0 ? 4 : 0),
        color: "#111", line: { width: .8, color: "#111" }
      };
    }
    return item;
  });
  data.push(...governments.map(government => ({
    type: "scatter", mode: "markers", x: [null], y: [null], name: government[0],
    showlegend: !placement.external, hoverinfo: "skip", legend: "legend",
    marker: { symbol: "square", size: 10, color: rgba(government[3], .3), line: { color: "#000", width: 1 } }
  })));
  const annotations = [];
  if (plot.id === "fig2c") annotations.push(
    { xref: "paper", yref: "y", x: .02, y: 0, yshift: 12, text: "Deficit", showarrow: false, font: { size: 12 } },
    { xref: "paper", yref: "y", x: .02, y: 0, yshift: -12, text: "Surplus", showarrow: false, font: { size: 12 } }
  );
  const layout = {
    font: { family: '"Times New Roman", Times, serif', size: narrow ? 11 : 12, color: "#222" },
    separators: ".,", paper_bgcolor: "#fff", plot_bgcolor: "#fff", barmode: "group",
    // Visible page titles are static HTML headings; PNG exports retain theirs.
    title: { text: options.forExport ? wrappedTitle(plot.title, width, narrow ? 12 : 14) +
      (plot.subtitle ? `<br><span style="font-size:11px">${wrappedTitle(plot.subtitle, width, 11)}</span>` : "") : "",
      x: margins.l / width, xanchor: "left", font: { size: narrow ? 12 : 14 } },
    height, margin: margins,
    xaxis: { type: "date", range: [plot.start, end], tick0: plot.start,
      dtick: narrow ? "M48" : "M24", tickformat: "%Y", tickangle: -90,
      showgrid: true, gridcolor: "rgba(0,0,0,.13)", griddash: "dot", fixedrange: true, zeroline: false },
    yaxis: { title: { text: plot.axis.title, standoff: 7 }, range,
      showgrid: true, gridcolor: "rgba(0,0,0,.13)", griddash: "dot", fixedrange: true,
      zeroline: true, zerolinecolor: "#888", zerolinewidth: .8 },
    legend: { title: { text: "Presidents", font: { size: legendTitleFont } },
      ...(placement.position || { x: .02, y: .98, xanchor: "left", yanchor: "top" }),
      font: { size: legendFont }, bgcolor: "rgba(255,255,255,.94)",
      bordercolor: "#000", borderwidth: 1, itemclick: false, itemdoubleclick: false },
    shapes, annotations, showlegend: !placement.external, hovermode: "closest", dragmode: false
  };
  if (plot.axis2) layout.yaxis2 = {
    title: { text: plot.axis2.title, standoff: 7 }, range: ranges.y2,
    overlaying: "y", side: "right", showgrid: false, fixedrange: true, zeroline: false
  };
  if (plot.axis2 && Number.isFinite(plot.axis2.tickStep)) {
    layout.yaxis2.tick0 = Number.isFinite(plot.align_index_base) ? plot.align_index_base : 0;
    layout.yaxis2.dtick = plot.axis2.tickStep;
  }
  if (Number.isFinite(plot.axis.tickStep)) {
    layout.yaxis.tick0 = Number.isFinite(plot.axis.min) ? plot.axis.min : 0;
    layout.yaxis.dtick = plot.axis.tickStep;
  }
  return { data, layout, config: { locale: "en", responsive: true, displayModeBar: false,
    displaylogo: false, scrollZoom: false, doubleClick: false },
    legendInfo: { inside, external: !inside && placement.external && !fixedLegend, overlay: fixedLegend,
      position: plot.president_legend?.position, columns: twoColumns ? 2 : 1,
      width, height, margins, fontSize: legendFont, titleSize: legendTitleFont,
      items: governments.map(government => ({ name: government[0], color: government[3] })) } };
}

let libraryPromise;
function loadPlotly() {
  if (window.Plotly) return Promise.resolve(window.Plotly);
  if (!libraryPromise) libraryPromise = new Promise((resolve, reject) => {
    const script = document.createElement("script");
    script.src = "https://cdn.plot.ly/plotly-basic-3.1.0.min.js";
    script.onload = () => resolve(window.Plotly);
    script.onerror = reject;
    document.head.appendChild(script);
  });
  return libraryPromise;
}

function monthlyUpdateCycle(now = new Date()) {
  const parts = Object.fromEntries(new Intl.DateTimeFormat("en-US", {
    timeZone: "America/Fortaleza", year: "numeric", month: "2-digit", day: "2-digit"
  }).formatToParts(now).filter(part => part.type !== "literal").map(part => [part.type, part.value]));
  let year = Number(parts.year), month = Number(parts.month);
  if (Number(parts.day) < 20) {
    month--;
    if (!month) { month = 12; year--; }
  }
  return `${year}-${String(month).padStart(2, "0")}-20`;
}

function observationMonthLimit(now = new Date()) {
  const parts = Object.fromEntries(new Intl.DateTimeFormat("en-US", {
    timeZone: "America/Fortaleza", year: "numeric", month: "2-digit"
  }).formatToParts(now).filter(part => part.type !== "literal").map(part => [part.type, part.value]));
  return `${parts.year}-${parts.month}-01`;
}

const currentRaw = { ...SEEDS };
const refreshedCycles = new Map();
const CACHE_PREFIX = "brazil-economy-monthly-sgs-";
function cachedSeries(code) {
  // A successful in-memory refresh wins even if browser storage could not be written.
  if (refreshedCycles.get(code) === monthlyUpdateCycle()) return currentRaw[code];
  try {
    const saved = JSON.parse(localStorage.getItem(`${CACHE_PREFIX}${code}`));
    if (saved && saved.retrieved >= SNAPSHOT_DATE && Array.isArray(saved.values) && saved.values.length) {
      const valid = saved.values.every(point => /^\d{4}-\d{2}-01$/.test(point[0]) && Number.isFinite(point[1]));
      const values = valid ? saved.values.filter(point => point[0] <= observationMonthLimit()) : [];
      const seed = SEEDS[code] || [];
      const coverage = values.length && (!seed.length || (values.length >= seed.length &&
        values[0][0] <= seed[0][0] && values.at(-1)[0] >= seed.at(-1)[0]));
      if (valid && coverage) {
        currentRaw[code] = values;
        if (saved.updateCycle === monthlyUpdateCycle()) refreshedCycles.set(code, saved.updateCycle);
      }
    }
  } catch (error) { /* Browser storage is optional. */ }
  return currentRaw[code];
}

const requestQueue = [];
const requestPromises = new Map();
let activeRequests = 0;
function runRequests() {
  while (activeRequests < 2 && requestQueue.length) {
    const task = requestQueue.shift();
    activeRequests++;
    task.run().then(task.resolve, () => task.resolve(null)).finally(() => { activeRequests--; runRequests(); });
  }
}

function freshSeries(code) {
  cachedSeries(code);
  const updateCycle = monthlyUpdateCycle();
  if (refreshedCycles.get(code) === updateCycle) return Promise.resolve(currentRaw[code]);
  const requestKey = `${code}:${updateCycle}`;
  if (!requestPromises.has(requestKey)) requestPromises.set(requestKey, new Promise(resolve => {
    requestQueue.push({ resolve, run: async () => {
      const url = new URL(`https://api.bcb.gov.br/dados/serie/bcdata.sgs.${code}/dados`);
      url.searchParams.set("formato", "json");
      if (code === 1178) {
        const latest = currentRaw[code]?.at(-1)?.[0] || "1999-01-01";
        const now = new Date();
        const start = latest > `${now.getFullYear() - 9}-01-01` ? latest : `${now.getFullYear() - 9}-01-01`;
        url.searchParams.set("dataInicial", `${start.slice(8, 10)}/${start.slice(5, 7)}/${start.slice(0, 4)}`);
        url.searchParams.set("dataFinal", `${String(now.getDate()).padStart(2, "0")}/${String(now.getMonth() + 1).padStart(2, "0")}/${now.getFullYear()}`);
      }
      const controller = new AbortController();
      const timer = setTimeout(() => controller.abort(), 10000);
      try {
        const response = await fetch(url, { signal: controller.signal });
        if (!response.ok) return null;
        const rows = await response.json();
        if (!Array.isArray(rows)) return null;
        const parsed = rows.flatMap(row => {
          const match = /^(\d{2})\/(\d{2})\/(\d{4})$/.exec(row.data || "");
          if (!match || !String(row.valor ?? "").trim()) return [];
          const value = Number(String(row.valor).replace(",", "."));
          return Number.isFinite(value) ? [[`${match[3]}-${match[2]}-${match[1]}`, value]] : [];
        }).sort((a, b) => a[0].localeCompare(b[0]));
        const monthly = new Map();
        for (const point of parsed) {
          const date = point[0].slice(0, 7) + "-01";
          if (code !== 1178 || !monthly.has(date)) monthly.set(date, point[1]);
        }
        if (!monthly.size) return null;
        const merged = code === 1178 ? new Map(currentRaw[code] || []) : new Map();
        for (const point of monthly) merged.set(...point);
        const historyStart = code === 433 || code === 1619 ? "1996-01-01" : "1999-01-01";
        const values = [...merged].filter(point => point[0] >= historyStart && point[0] <= observationMonthLimit())
          .sort((a, b) => a[0].localeCompare(b[0]));
        if (!values.length) return null;
        const previous = currentRaw[code] || [];
        if (code !== 1178 && previous.length && (values.length < previous.length || values[0][0] > previous[0][0] ||
            values.at(-1)[0] < previous.at(-1)[0])) return null;
        currentRaw[code] = values;
        refreshedCycles.set(code, updateCycle);
        try { localStorage.setItem(`${CACHE_PREFIX}${code}`, JSON.stringify({ retrieved: new Date().toISOString().slice(0, 10), updateCycle, values })); }
        catch (error) { /* A full or disabled cache does not affect the chart. */ }
        return values;
      } finally { clearTimeout(timer); }
    } });
    runRequests();
  }));
  return requestPromises.get(requestKey);
}

function fillSidebar(plot, series) {
  const latest = document.getElementById(`latest-${plot.id}`);
  latest.replaceChildren();
  for (const trace of series) {
    const row = document.createElement("p");
    row.textContent = `${trace.spec.label}: ${dateLabel(trace.points.at(-1)[0], trace.spec.frequency)}`;
    latest.appendChild(row);
  }
  const keys = document.getElementById(`keys-${plot.id}`);
  if (!keys || keys.childElementCount) return;
  for (const trace of series) {
    const row = document.createElement("span");
    row.className = "macro-key";
    const sample = document.createElement("span");
    sample.className = "macro-key-sample";
    const spec = trace.spec;
    const color = spec.color || "#111";
    sample.style.opacity = spec.opacity ?? 1;
    sample.style.border = "none";
    if (spec.type === "bar") { sample.style.height = "8px"; sample.style.background = color; }
    else {
      sample.style.height = `${spec.legendWidth ?? 2}px`;
      const patterns = {
        solid: color,
        dash: `repeating-linear-gradient(to right,${color} 0 7px,transparent 7px 11px)`,
        dot: `repeating-linear-gradient(to right,${color} 0 2px,transparent 2px 5px)`,
        dashdot: `repeating-linear-gradient(to right,${color} 0 7px,transparent 7px 10px,${color} 10px 12px,transparent 12px 16px)`
      };
      sample.style.background = patterns[spec.dash || "solid"];
      if (spec.marker) {
        sample.style.position = "relative";
        const cross = document.createElement("span");
        cross.textContent = "×";
        cross.style.cssText = "position:absolute;left:9px;top:-8px;font:14px/1 serif;color:#111";
        sample.appendChild(cross);
      }
    }
    const label = document.createElement("span");
    label.className = "macro-key-label";
    label.textContent = spec.legendLabel || spec.label;
    row.append(sample, label);
    keys.appendChild(row);
  }
}

function fillPresidents(plot, info) {
  const box = document.getElementById(`presidents-${plot.id}`);
  const items = document.getElementById(`president-items-${plot.id}`);
  box.hidden = !(info.external || info.overlay);
  box.classList.toggle("is-overlay", !!info.overlay);
  box.classList.toggle("has-two-columns", info.columns === 2);
  items.classList.toggle("is-two-column", info.columns === 2);
  box.style.left = box.style.top = box.style.transform = "";
  items.style.gridTemplateRows = "";
  if (box.hidden) return;
  if (info.columns === 2) items.style.gridTemplateRows = `repeat(${Math.ceil(info.items.length / 2)}, auto)`;
  if (info.overlay) {
    const horizontal = info.position.split("-")[1];
    const vertical = info.position.split("-")[0];
    const bottom = vertical === "bottom";
    const middle = vertical === "middle";
    const plotWidth = info.width - info.margins.l - info.margins.r;
    const plotHeight = info.height - info.margins.t - info.margins.b;
    const inset = 5;
    const insetX = Math.max(inset, (plot.president_legend?.inset_x ?? 0) * plotWidth);
    const x = horizontal === "left" ? info.margins.l + insetX :
      horizontal === "center" ? info.margins.l + plotWidth / 2 : info.width - info.margins.r - inset;
    const y = bottom ? info.height - info.margins.b - inset : middle ? info.margins.t + plotHeight / 2 : info.margins.t + inset;
    box.style.left = `${x}px`;
    box.style.top = `${y}px`;
    box.style.transform = `translate(${horizontal === "left" ? "0" : horizontal === "center" ? "-50%" : "-100%"},${bottom ? "-100%" : middle ? "-50%" : "0"})`;
  }
  box.style.fontSize = `${info.fontSize}px`;
  box.style.setProperty("--macro-margin-left", `${info.margins.l}px`);
  box.style.setProperty("--macro-margin-right", `${info.margins.r}px`);
  box.querySelector(".macro-presidents-title").style.fontSize = `${info.titleSize}px`;
  items.replaceChildren();
  for (const government of info.items) {
    const item = document.createElement("span");
    item.className = "macro-president-item";
    const swatch = document.createElement("span");
    swatch.className = "macro-president-swatch";
    swatch.style.backgroundColor = rgba(government.color, .3);
    const label = document.createElement("span");
    label.textContent = government.name;
    item.append(swatch, label);
    items.appendChild(item);
  }
}

function fillInsideBoxes(plot, info) {
  const canvas = document.getElementById(`chart-${plot.id}`).parentElement;
  const place = (box, dimensions, title, items) => {
    box.hidden = false;
    const plotWidth = info.width - info.margins.l - info.margins.r;
    const plotHeight = info.height - info.margins.t - info.margins.b;
    const left = info.margins.l + dimensions.position.x * plotWidth;
    const top = info.margins.t + (1 - dimensions.position.y) * plotHeight;
    Object.assign(box.style, { position: "absolute", left: `${left}px`, top: `${top}px`,
      width: `${dimensions.box.width}px`, height: `${dimensions.box.height}px`, maxWidth: "none",
      transform: "none", margin: "0", padding: "4px", fontSize: `${dimensions.fontSize}px` });
    Object.assign(title.style, { margin: "0 0 3px", fontSize: `${dimensions.titleSize}px`,
      lineHeight: `${dimensions.titleSize}px`, fontWeight: "400" });
    Object.assign(items.style, { display: "grid", gridTemplateColumns: `repeat(${dimensions.columns}, ${dimensions.columnWidth}px)`,
      gridTemplateRows: `repeat(${dimensions.rows}, ${dimensions.rowHeight}px)`,
      gridAutoFlow: "column", gap: "0 10px", margin: "0", padding: "0", border: "0" });
  };
  const presidents = document.getElementById(`presidents-${plot.id}`);
  const presidentItems = document.getElementById(`president-items-${plot.id}`);
  presidents.classList.add("is-overlay");
  presidents.classList.remove("has-two-columns");
  presidentItems.classList.remove("is-two-column");
  presidentItems.replaceChildren();
  const dimensions = info.inside.presidents;
  for (const government of info.items) {
    const row = document.createElement("span");
    row.className = "macro-president-item";
    row.style.fontSize = `${dimensions.fontSize}px`;
    row.style.lineHeight = `${dimensions.rowHeight}px`;
    row.style.gap = "4px";
    const swatch = document.createElement("span");
    swatch.className = "macro-president-swatch";
    swatch.style.cssText = `width:10px;height:10px;flex:0 0 10px;background:${rgba(government.color, .3)}`;
    const name = document.createElement("span");
    name.textContent = government.name;
    row.append(swatch, name);
    presidentItems.appendChild(row);
  }
  place(presidents, dimensions, presidents.querySelector(".macro-presidents-title"), presidentItems);
  const keys = document.getElementById(`keys-${plot.id}`);
  if (keys && info.inside.indicators) {
    const indicatorBox = keys.parentElement;
    indicatorBox.classList.add("macro-inset-indicators");
    if (indicatorBox.parentElement !== canvas) canvas.appendChild(indicatorBox);
    place(indicatorBox, info.inside.indicators, indicatorBox.querySelector(".macro-key-title"), keys);
    for (const [index, key] of [...keys.children].entries()) {
      key.querySelector(".macro-key-label").textContent = info.inside.indicatorLabels?.[index] ||
        plot.traces[index].legendLabel || plot.traces[index].label;
      key.style.fontSize = `${info.inside.indicators.fontSize}px`;
      key.style.lineHeight = `${info.inside.indicators.rowHeight}px`;
      key.querySelector(".macro-key-sample").style.cssText += ";width:24px;flex:0 0 24px;margin:0";
      key.querySelector(".macro-key-label").style.fontSize = `${info.inside.indicators.fontSize}px`;
    }
  }
}

function drawInsideExportLegends(figure, series) {
  const { layout, legendInfo } = figure;
  const pw = layout.width - layout.margin.l - layout.margin.r;
  const ph = layout.height - layout.margin.t - layout.margin.b;
  const line = (x1, y1, x2, y2, options = {}) => ({ type: "line", xref: "paper", yref: "paper",
    x0: x1 / pw, x1: x2 / pw, y0: 1 - y1 / ph, y1: 1 - y2 / ph,
    line: { color: "#111", width: 1.5, ...options }, layer: "above" });
  const rectangle = (x, y, w, h, fill) => ({ type: "rect", xref: "paper", yref: "paper",
    x0: x / pw, x1: (x + w) / pw, y0: 1 - (y + h) / ph, y1: 1 - y / ph,
    fillcolor: fill, line: { color: "#000", width: 1 }, layer: "above" });
  const label = (text, x, y, size) => ({ xref: "paper", yref: "paper", x: x / pw, y: 1 - y / ph,
    xanchor: "left", yanchor: "top", showarrow: false, text,
    font: { family: '"Times New Roman", Times, serif', size, color: "#222" } });
  const draw = (dimensions, title, values, presidents) => {
    if (!dimensions) return;
    const left = dimensions.position.x * pw;
    const top = (1 - dimensions.position.y) * ph;
    layout.shapes.push(rectangle(left, top, dimensions.box.width, dimensions.box.height, "rgba(255,255,255,.96)"));
    layout.annotations.push(label(title, left + 4, top + 3, dimensions.titleSize));
    values.forEach((value, index) => {
      const col = Math.floor(index / dimensions.rows), row = index % dimensions.rows;
      const x = left + 5 + col * (dimensions.columnWidth + 10);
      const y = top + 5 + dimensions.titleSize + 3 + row * dimensions.rowHeight;
      if (presidents) {
        layout.shapes.push(rectangle(x, y + (dimensions.rowHeight - 10) / 2, 10, 10, rgba(value.color, .3)));
        layout.annotations.push(label(value.name, x + 14, y + 1, dimensions.fontSize));
      } else {
        const spec = value.spec;
        if (spec.type === "bar") {
          layout.shapes.push(rectangle(x, y + (dimensions.rowHeight - 7) / 2, 24, 7, rgba(spec.color || "#111", spec.opacity ?? 1)));
        } else {
          const sample = line(x, y + dimensions.rowHeight / 2, x + 24, y + dimensions.rowHeight / 2,
            { color: rgba(spec.color || "#111", spec.opacity ?? 1), dash: spec.dash || "solid", width: spec.legendWidth ?? 1.5 });
          layout.shapes.push(sample);
          if (spec.marker) layout.annotations.push(label("×", x + 8, y - 1, dimensions.fontSize + 4));
        }
        layout.annotations.push(label(spec.legendLabel || spec.label, x + 32, y + 1, dimensions.fontSize));
      }
    });
  };
  draw(legendInfo.inside.presidents, "Presidents", legendInfo.items, true);
  draw(legendInfo.inside.indicators, "Indicators", series, false);
}

// PNGs reproduce the requested two-column boxes in plot coordinates.
function fixedExportLegend(plot, figure, series) {
  if (figure.legendInfo.inside) { drawInsideExportLegends(figure, series); return; }
  if (plot.president_legend?.columns !== 2) return;
  const { layout, legendInfo } = figure;
  const pw = layout.width - layout.margin.l - layout.margin.r;
  const ph = layout.height - layout.margin.t - layout.margin.b;
  const rows = Math.ceil(legendInfo.items.length / 2);
  const padding = 6, column = 66, row = 15, title = 15;
  const bw = column * 2 + padding * 2, bh = padding * 2 + title + row * rows;
  const horizontal = plot.president_legend.position.split("-")[1];
  const external = plot.president_legend.position === "external";
  const left = external ? 0 : horizontal === "left" ? Math.max(5, (plot.president_legend?.inset_x ?? 0) * pw) : horizontal === "center" ? (pw - bw) / 2 : pw - bw - 5;
  const top = external ? ph + 52 : plot.president_legend.position.startsWith("bottom-") ? ph - bh - 5 :
    plot.president_legend.position.startsWith("middle-") ? (ph - bh) / 2 : 5;
  const rect = (x, y, w, h, color, border = "#000") => ({
    type: "rect", xref: "paper", yref: "paper", x0: x / pw, x1: (x + w) / pw,
    y0: 1 - (y + h) / ph, y1: 1 - y / ph, fillcolor: color,
    line: { color: border, width: 1 }, layer: "above"
  });
  const label = (text, x, y, size) => ({
    xref: "paper", yref: "paper", x: x / pw, y: 1 - y / ph,
    xanchor: "left", yanchor: "top", showarrow: false,
    text, font: { family: '"Times New Roman", Times, serif', size, color: "#222" }
  });
  layout.shapes.push(rect(left, top, bw, bh, "rgba(255,255,255,.96)"));
  layout.annotations.push(label("Presidents", left + padding, top + padding - 2, 10));
  legendInfo.items.forEach((item, i) => {
    const x = left + padding + Math.floor(i / rows) * column;
    const y = top + padding + title + (i % rows) * row;
    layout.shapes.push(rect(x, y, 10, 10, rgba(item.color, .3)));
    layout.annotations.push(label(item.name, x + 14, y - 2, 10));
  });
}

function buildExportFigure(plot, series) {
  const multiple = series.length > 1;
  const externalColumns = plot.president_legend?.position === "external" && plot.president_legend.columns === 2;
  const insideMode = plot.legend_mode === "inside";
  const margins = { l: 64, r: plot.axis2 ? 68 : 18, t: 62,
    b: insideMode ? 90 : externalColumns ? 225 : multiple ? 175 : 125 };
  const footerLines = [ ...(plot.export_notes || []),
    plot.source_caption || `Source: BCB–SGS · Codes: ${dependencies(plot).join(", ")}. Author’s calculations.` ];
  const footerText = footerLines.map(line => wrappedTitle(line, 1000 - margins.l - margins.r, 9)).join("<br>");
  margins.b += Math.max(0, footerText.split("<br>").length - 1) * 13;
  const figure = figureFor(plot, series, 1000, { height: 650, margins, forExport: true });
  const exportHeight = figure.layout.height;
  figure.data.slice(0, series.length).forEach(trace => { trace.showlegend = !insideMode && multiple; trace.legend = "legend2"; });
  figure.data.slice(series.length).forEach(trace => { trace.showlegend = !insideMode && !plot.president_legend; trace.legend = "legend"; });
  figure.layout.width = 1000;
  figure.layout.height = exportHeight;
  figure.layout.autosize = false;
  figure.layout.margin = margins;
  figure.layout.showlegend = !insideMode;
  figure.layout.legend = { ...figure.layout.legend, orientation: "h", x: 0, y: -.12,
    xanchor: "left", yanchor: "top", bgcolor: "rgba(255,255,255,1)" };
  if (multiple && !insideMode) figure.layout.legend2 = {
    title: { text: "Indicators", font: { size: 10 } }, orientation: "h",
    x: 0, y: externalColumns ? -.43 : -.25, yanchor: "top", font: { size: 10 }, bgcolor: "rgba(255,255,255,1)",
    bordercolor: "#000", borderwidth: 1
  };
  fixedExportLegend(plot, figure, series);
  figure.layout.annotations.push({
    xref: "paper", yref: "paper", x: 0, y: 0, yshift: insideMode ? -62 : externalColumns ? -205 : multiple ? -145 : -95,
    xanchor: "left", yanchor: "top", showarrow: false, font: { size: 9 },
    text: footerText
  });
  return figure;
}

async function initializePlot(plot) {
  const root = document.getElementById(`panel-${plot.id}`);
  const chart = document.getElementById(`chart-${plot.id}`);
  const status = document.getElementById(`status-${plot.id}`);
  const button = document.getElementById(`download-${plot.id}`);
  const codes = dependencies(plot);
  const raw = Object.fromEntries(codes.map(code => [code, cachedSeries(code)]));
  let series;
  let lastDimensions;
  let task = Promise.resolve();
  function enqueue(action) { const next = task.then(action); task = next.catch(() => {}); return next; }
  async function draw(nextSeries) {
    const mobile = window.matchMedia("(max-width: 600px)").matches;
    const width = chart.clientWidth;
    const height = mobile ? 320 : 352;
    const figure = figureFor(plot, nextSeries, width, { mobile, height });
    root.style.setProperty("--macro-plot-top", `${figure.layout.margin.t}px`);
    chart.style.height = `${figure.layout.height}px`;
    await Plotly.react(chart, figure.data, figure.layout, figure.config);
    series = nextSeries;
    lastDimensions = { width, height: figure.layout.height, mobile };
    fillSidebar(plot, series);
    if (figure.legendInfo.inside) fillInsideBoxes(plot, figure.legendInfo);
    else fillPresidents(plot, figure.legendInfo);
    chart.setAttribute("aria-busy", "false");
  }
  try {
    const missing = codes.filter(code => !Array.isArray(raw[code]) || !raw[code].length);
    if (missing.length) {
      status.textContent = "Loading data from the Central Bank of Brazil…";
      status.hidden = false;
      await Promise.all(missing.map(freshSeries));
      for (const code of codes) raw[code] = cachedSeries(code);
    }
    await loadPlotly();
    await enqueue(() => draw(buildSeries(plot, raw)));
    status.hidden = true;
    button.disabled = false;
    button.addEventListener("click", async () => {
      button.disabled = true;
      status.hidden = true;
      try {
        await enqueue(async () => {
          const figure = buildExportFigure(plot, series);
          const exportHeight = figure.layout.height;
          const last = series.flatMap(trace => trace.points).map(point => point[0]).sort().at(-1);
          const downloadFigure = { data: figure.data, layout: figure.layout, config: figure.config };
          await Plotly.downloadImage(downloadFigure, { format: "png", filename: `${plot.id}-sgs-${codes.join("-")}-${last.slice(0, 7)}`,
            width: 1000, height: exportHeight, scale: 2 });
        });
      } catch (error) { status.textContent = "Unable to download the figure. Please try again."; status.hidden = false; }
      finally { button.disabled = false; }
    });
    if (typeof ResizeObserver !== "undefined") {
      let scheduled = false;
      const observer = new ResizeObserver(() => {
        const mobile = window.matchMedia("(max-width: 600px)").matches;
        if (!series || !lastDimensions || (Math.abs(chart.clientWidth - lastDimensions.width) < 1 &&
            Math.abs(chart.clientHeight - lastDimensions.height) < 1 && mobile === lastDimensions.mobile)) return;
        if (scheduled) return;
        scheduled = true;
        requestAnimationFrame(() => {
          scheduled = false;
          void enqueue(() => draw(series)).catch(() => {});
        });
      });
      observer.observe(chart);
    }
    void Promise.all(codes.map(freshSeries)).then(() => enqueue(async () => {
      const nextSeries = buildSeries(plot, currentRaw);
      if (JSON.stringify(nextSeries.map(trace => trace.points)) !== JSON.stringify(series.map(trace => trace.points))) await draw(nextSeries);
    })).catch(() => {});
  } catch (error) {
    chart.setAttribute("aria-busy", "false");
    status.textContent = "Unable to load the chart. Please reload the page.";
    status.hidden = false;
  }
}

function boot() {
  const initialized = new Set();
  function start(plot) {
    if (initialized.has(plot.id)) return;
    initialized.add(plot.id);
    void initializePlot(plot);
  }
  if (typeof IntersectionObserver === "undefined") PLOTS.forEach(start);
  else {
    const observer = new IntersectionObserver(entries => {
      for (const entry of entries) if (entry.isIntersecting) {
        const plot = PLOTS.find(item => `panel-${item.id}` === entry.target.id);
        if (plot) start(plot);
        observer.unobserve(entry.target);
      }
    }, { rootMargin: "650px 0px" });
    PLOTS.forEach(plot => observer.observe(document.getElementById(`panel-${plot.id}`)));
    start(PLOTS[0]);
  }
}

export { buildSeries, figureFor, dependencies, axisBounds, monthlyFromYTD, rolling, chooseLegendPlacement,
  MANIFEST, SEEDS, addGaps, dateLabel, monthlyUpdateCycle, observationMonthLimit, buildExportFigure };
if (typeof document !== "undefined") boot();
</script>
