---
layout: page
lang: "en"
permalink: /explore_with_me/
---

<style>
.fiscal-panel {
  margin-bottom: 1.4em;
  font-size: .85em;
  line-height: 1.5;
}

.fiscal-panel * {
  box-sizing: border-box;
}

.explore-analysis-section {
  margin: 0 0 2em;
}

.explore-analysis-section > .explore-analysis-heading {
  margin: 0 0 .7em;
  font-size: 1.7em;
  font-weight: 700;
  line-height: 1.2;
}

.fiscal-panel .nfsp-layout {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 160px;
  gap: 16px;
  align-items: start;
}

.fiscal-panel .nfsp-chart {
  width: 100%;
  min-width: 0;
  height: 400px;
}

.fiscal-panel .nfsp-sidebar {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: .8em;
  min-width: 0;
  padding-top: 65px;
  font-size: .85em;
}

.fiscal-panel button,
.fiscal-panel summary {
  display: inline-block;
  font: inherit;
  color: #333;
  background: #fff;
  border: 1px solid #bbb;
  border-radius: 4px;
  padding: .4em .65em;
  cursor: pointer;
}

.fiscal-panel button:hover,
.fiscal-panel summary:hover {
  background: #f3f3f3;
}

.fiscal-panel button:disabled {
  opacity: .5;
  cursor: wait;
}

.fiscal-panel :focus-visible {
  outline: 2px solid #555;
  outline-offset: 3px;
}

.fiscal-panel details {
  position: relative;
}

.fiscal-panel summary {
  list-style: none;
}

.fiscal-panel summary::-webkit-details-marker {
  display: none;
}

.fiscal-panel summary::after {
  content: " ▾";
}

.fiscal-panel details[open] summary::after {
  content: " ▴";
}

.fiscal-panel .nfsp-info {
  position: absolute;
  z-index: 10;
  top: calc(100% + 8px);
  right: 0;
  width: min(300px, calc(100vw - 48px));
  padding: 1em;
  background: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
  box-shadow: 0 4px 14px #0002;
}

.fiscal-panel .nfsp-info p {
  margin: 0 0 .7em;
}

.fiscal-panel .nfsp-info p:last-child {
  margin: 0;
}

.fiscal-panel .nfsp-source {
  margin: .2em 0 0;
  color: #555;
  font-size: .95em;
  line-height: 1.45;
}

.fiscal-panel .nfsp-status {
  font-size: .85em;
  color: #555;
}

.fiscal-panel .nfsp-status[hidden] {
  display: none;
}

@media (max-width: 600px) {
  .fiscal-panel {
    font-size: .8em;
  }

  .fiscal-panel .nfsp-layout {
    grid-template-columns: minmax(0, 1fr);
    gap: .5em;
  }

  .fiscal-panel .nfsp-chart {
    height: 360px;
  }

  .fiscal-panel .nfsp-sidebar {
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
    padding-top: 0;
  }

  .fiscal-panel .nfsp-source {
    flex-basis: 100%;
  }

  .fiscal-panel .nfsp-info {
    left: 0;
    right: auto;
  }
}
</style>

<section lang="en" class="explore-analysis-section" aria-labelledby="fiscal-heading">
  <h2 id="fiscal-heading" class="explore-analysis-heading">Brazil’s fiscal trajectory</h2>

<section lang="en" id="explore-nfsp" class="fiscal-panel" aria-label="Public sector borrowing requirements">

  <div class="nfsp-layout">
    <div
      id="nfsp-chart"
      class="nfsp-chart"
      aria-label="Public sector borrowing requirements as a percentage of GDP"
      aria-busy="true">
    </div>

    <aside class="nfsp-sidebar" aria-label="Chart information and download">
      <details>
        <summary>About the data</summary>

        <div class="nfsp-info">
          <p>
            <strong>Series code: 5727 (BCB-SGS).</strong>
          </p>

          <p>
            Original name:
            <span lang="pt-BR">
              <em>Necessidade de Financiamento do Setor Público sem desvalorização cambial (% PIB)</em>
            </span>.
          </p>

          <p>
            Public sector borrowing requirements (NFSP), excluding exchange
            rate effects: the consolidated public sector’s nominal balance,
            as a rolling 12-month total (% of GDP).
          </p>

          <p>
            Frequency: monthly.<br>
            Latest observation: <span id="nfsp-latest">—</span>.
          </p>

          <p>
            Colors identify presidential terms. Temer’s band begins in
            September 2016, following his permanent assumption of office.
          </p>
        </div>
      </details>

      <button id="nfsp-png" type="button" disabled>
        Download PNG
      </button>

      <p class="nfsp-source">
        Source:
        <a
          href="https://dadosabertos.bcb.gov.br/dataset/5727-nfsp-sem-desvalorizacao-cambial--pib---fluxo-acumulado-em-12-meses---resultado-nominal---total"
          target="_blank"
          rel="noopener noreferrer">Brazilian Central Bank (BCB)</a>
        –
        <a
          href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries"
          target="_blank"
          rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>,
        code <strong>5727</strong>.
      </p>
    </aside>
  </div>

  <p
    id="nfsp-status"
    class="nfsp-status"
    role="status"
    aria-live="polite"
    hidden>
  </p>

  <noscript>Enable JavaScript to view the chart.</noscript>
</section>

<section lang="en" id="explore-debt" class="fiscal-panel" aria-label="Net public sector debt">

  <div class="nfsp-layout">
    <div
      id="debt-chart"
      class="nfsp-chart"
      aria-label="Net public sector debt as a percentage of GDP"
      aria-busy="true">
    </div>

    <aside class="nfsp-sidebar" aria-label="Chart information and download">
      <details>
        <summary>About the data</summary>

        <div class="nfsp-info">
          <p>
            <strong>Series code: 4513 (BCB-SGS).</strong>
          </p>

          <p>
            Original name:
            <span lang="pt-BR">
              <em>Dívida Líquida do Setor Público (% PIB) – Total – Setor público consolidado</em>
            </span>.
          </p>

          <p>
            The consolidated public sector’s net debt as a percentage of GDP.
            This is a debt stock, measured monthly.
          </p>

          <p>
            Frequency: monthly.<br>
            Latest observation: <span id="debt-latest">—</span>.
          </p>

          <p>
            Colors identify presidential terms. Temer’s band begins in
            September 2016, following his permanent assumption of office.
          </p>
        </div>
      </details>

      <button id="debt-png" type="button" disabled>
        Download PNG
      </button>

      <p class="nfsp-source">
        Source:
        <a
          href="https://dadosabertos.bcb.gov.br/dataset/4513-divida-liquida-do-setor-publico--pib---total---setor-publico-consolidado"
          target="_blank"
          rel="noopener noreferrer">Brazilian Central Bank (BCB)</a>
        –
        <a
          href="https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries"
          target="_blank"
          rel="noopener noreferrer"><em lang="pt-BR">Sistema Gerenciador de Séries Temporais (SGS)</em></a>,
        code <strong>4513</strong>.
      </p>
    </aside>
  </div>

  <p
    id="debt-status"
    class="nfsp-status"
    role="status"
    aria-live="polite"
    hidden>
  </p>

  <noscript>Enable JavaScript to view the chart.</noscript>
</section>
</section>

<script>
(async function () {
  "use strict";

  // Official monthly data retrieved on October 26, 2026.
  const charts = [
    {
      rootId: "explore-nfsp", prefix: "nfsp", seriesCode: 5727,
      title: "Public sector borrowing requirements (% of GDP)<br><sup>Nominal balance · 12-month total  · Excluding exchange rate effects</sup>",
      exportTitle: "Public sector borrowing requirements (% of GDP)<br><sup>Nominal balance · 12-month total · Excluding exchange rate effects</sup>",
      backup: "2003-01:4.93|2003-02:5.12|2003-03:5.38|2003-04:4.97|2003-05:5.15|2003-06:5.39|2003-07:5.91|2003-08:5.92|2003-09:5.97|2003-10:5.55|2003-11:5.64|2003-12:5.18|2004-01:4.60|2004-02:4.33|2004-03:4.00|2004-04:4.29|2004-05:4.01|2004-06:3.70|2004-07:3.34|2004-08:3.11|2004-09:3.05|2004-10:3.10|2004-11:3.00|2004-12:2.88|2005-01:2.78|2005-02:2.93|2005-03:2.98|2005-04:2.74|2005-05:2.89|2005-06:3.10|2005-07:3.13|2005-08:3.14|2005-09:3.31|2005-10:3.32|2005-11:3.45|2005-12:3.54|2006-01:4.06|2006-02:4.12|2006-03:4.11|2006-04:4.02|2006-05:3.71|2006-06:3.72|2006-07:3.80|2006-08:3.71|2006-09:3.65|2006-10:3.51|2006-11:3.42|2006-12:3.57|2007-01:3.01|2007-02:2.85|2007-03:2.90|2007-04:2.83|2007-05:3.08|2007-06:2.82|2007-07:2.78|2007-08:2.70|2007-09:2.85|2007-10:2.86|2007-11:2.70|2007-12:2.74|2008-01:2.50|2008-02:2.55|2008-03:2.21|2008-04:2.25|2008-05:2.18|2008-06:2.31|2008-07:2.28|2008-08:2.22|2008-09:1.74|2008-10:1.32|2008-11:1.52|2008-12:1.99|2009-01:2.46|2009-02:2.43|2009-03:2.68|2009-04:2.85|2009-05:2.93|2009-06:3.02|2009-07:3.19|2009-08:3.32|2009-09:4.01|2009-10:4.28|2009-11:3.96|2009-12:3.19|2010-01:2.86|2010-02:2.94|2010-03:3.20|2010-04:2.96|2010-05:3.07|2010-06:3.12|2010-07:3.12|2010-08:3.16|2010-09:2.21|2010-10:2.32|2010-11:2.58|2010-12:2.41|2011-01:2.47|2011-02:2.45|2011-03:2.17|2011-04:2.32|2011-05:2.27|2011-06:2.05|2011-07:1.78|2011-08:1.91|2011-09:2.39|2011-10:2.37|2011-11:2.26|2011-12:2.47|2012-01:2.27|2012-02:2.19|2012-03:2.26|2012-04:2.27|2012-05:2.29|2012-06:2.44|2012-07:2.56|2012-08:2.52|2012-09:2.57|2012-10:2.50|2012-11:2.73|2012-12:2.26|2013-01:2.22|2013-02:2.50|2013-03:2.59|2013-04:2.65|2013-05:2.60|2013-06:2.56|2013-07:2.71|2013-08:2.82|2013-09:3.00|2013-10:3.10|2013-11:2.67|2013-12:2.96|2014-01:3.27|2014-02:2.98|2014-03:2.90|2014-04:2.83|2014-05:3.13|2014-06:3.27|2014-07:3.46|2014-08:3.60|2014-09:4.39|2014-10:4.48|2014-11:5.18|2014-12:5.95|2015-01:5.70|2015-02:6.53|2015-03:7.45|2015-04:7.16|2015-05:7.61|2015-06:7.83|2015-07:8.48|2015-08:8.89|2015-09:9.01|2015-10:9.18|2015-11:9.19|2015-12:10.22|2016-01:10.73|2016-02:10.60|2016-03:9.59|2016-04:9.96|2016-05:9.93|2016-06:9.81|2016-07:9.47|2016-08:9.53|2016-09:9.32|2016-10:8.77|2016-11:9.32|2016-12:8.98|2017-01:8.48|2017-02:8.47|2017-03:9.13|2017-04:9.14|2017-05:9.19|2017-06:9.45|2017-07:9.28|2017-08:8.97|2017-09:8.73|2017-10:9.21|2017-11:8.41|2017-12:7.77|2018-01:7.44|2018-02:7.28|2018-03:7.30|2018-04:7.42|2018-05:7.12|2018-06:7.18|2018-07:6.91|2018-08:7.32|2018-09:7.08|2018-10:6.68|2018-11:6.95|2018-12:6.96|2019-01:6.83|2019-02:6.78|2019-03:6.83|2019-04:6.83|2019-05:6.77|2019-06:6.37|2019-07:6.35|2019-08:6.14|2019-09:6.20|2019-10:6.23|2019-11:6.24|2019-12:5.81|2020-01:5.87|2020-02:5.90|2020-03:6.11|2020-04:7.32|2020-05:8.61|2020-06:11.02|2020-07:11.77|2020-08:12.54|2020-09:13.26|2020-10:13.48|2020-11:12.97|2020-12:13.34|2021-01:13.25|2021-02:12.99|2021-03:12.32|2021-04:10.25|2021-05:8.81|2021-06:7.06|2021-07:6.59|2021-08:5.42|2021-09:4.64|2021-10:4.52|2021-11:4.54|2021-12:4.26|2022-01:3.51|2022-02:3.29|2022-03:3.06|2022-04:3.80|2022-05:4.06|2022-06:4.10|2022-07:3.71|2022-08:4.04|2022-09:4.19|2022-10:4.04|2022-11:4.44|2022-12:4.57|2023-01:4.90|2023-02:5.52|2023-03:5.98|2023-04:5.79|2023-05:6.26|2023-06:6.28|2023-07:6.81|2023-08:7.15|2023-09:7.48|2023-10:7.73|2023-11:7.77|2023-12:8.84|2024-01:9.00|2024-02:9.15|2024-03:8.97|2024-04:9.30|2024-05:9.43|2024-06:9.78|2024-07:9.86|2024-08:9.66|2024-09:9.20|2024-10:9.36|2024-11:9.47|2024-12:8.47|2025-01:8.08|2025-02:7.87|2025-03:7.88|2025-04:7.70|2025-05:7.54|2025-06:7.27|2025-07:7.82|2025-08:7.79|2025-09:8.13|2025-10:8.14|2025-11:8.12|2025-12:8.34|2026-01:8.48|2026-02:8.47|2026-03:9.39|2026-04:9.37|2026-05:9.61|2026-06:9.99|2026-07:9.35|2026-08:9.48"
    },
    {
      rootId: "explore-debt", prefix: "debt", seriesCode: 4513,
      title: "Net public sector debt (% of GDP)<br><sup>Consolidated public sector · Total</sup>",
      exportTitle: "Net public sector debt (% of GDP)<br><sup>Consolidated public sector · Total</sup>",
      yMin: 25,
      legendPosition: { x: .98, y: .02, xanchor: "right", yanchor: "bottom" },
      backup: "2003-01:59.97|2003-02:60.26|2003-03:58.46|2003-04:54.44|2003-05:54.96|2003-06:54.42|2003-07:55.11|2003-08:55.49|2003-09:54.73|2003-10:53.80|2003-11:54.22|2003-12:54.26|2004-01:54.05|2004-02:53.80|2004-03:53.19|2004-04:52.91|2004-05:53.45|2004-06:52.83|2004-07:52.07|2004-08:51.44|2004-09:50.86|2004-10:50.75|2004-11:50.05|2004-12:50.19|2005-01:49.56|2005-02:49.30|2005-03:49.31|2005-04:48.32|2005-05:47.94|2005-06:48.04|2005-07:48.14|2005-08:47.95|2005-09:47.65|2005-10:47.53|2005-11:47.42|2005-12:47.92|2006-01:47.82|2006-02:47.78|2006-03:47.66|2006-04:47.14|2006-05:47.02|2006-06:46.96|2006-07:46.83|2006-08:46.62|2006-09:46.57|2006-10:46.17|2006-11:46.01|2006-12:46.49|2007-01:45.95|2007-02:45.86|2007-03:45.81|2007-04:45.08|2007-05:45.23|2007-06:44.80|2007-07:44.73|2007-08:44.09|2007-09:44.59|2007-10:44.60|2007-11:44.11|2007-12:44.55|2008-01:43.71|2008-02:43.79|2008-03:43.00|2008-04:42.82|2008-05:43.03|2008-06:42.89|2008-07:42.74|2008-08:42.02|2008-09:39.96|2008-10:38.30|2008-11:36.95|2008-12:37.57|2009-01:38.05|2009-02:38.02|2009-03:38.04|2009-04:38.65|2009-05:39.66|2009-06:39.98|2009-07:40.64|2009-08:40.63|2009-09:41.56|2009-10:41.42|2009-11:40.94|2009-12:40.88|2010-01:39.59|2010-02:39.82|2010-03:39.91|2010-04:39.47|2010-05:38.97|2010-06:38.89|2010-07:38.99|2010-08:38.76|2010-09:38.22|2010-10:37.89|2010-11:37.77|2010-12:37.98|2011-01:37.57|2011-02:37.49|2011-03:37.53|2011-04:37.42|2011-05:37.25|2011-06:37.08|2011-07:36.82|2011-08:36.55|2011-09:34.67|2011-10:35.65|2011-11:34.76|2011-12:34.47|2012-01:35.00|2012-02:35.15|2012-03:34.26|2012-04:33.50|2012-05:32.77|2012-06:32.78|2012-07:32.51|2012-08:32.60|2012-09:32.62|2012-10:32.44|2012-11:32.08|2012-12:32.19|2013-01:32.17|2013-02:32.59|2013-03:32.40|2013-04:32.14|2013-05:31.51|2013-06:31.19|2013-07:30.80|2013-08:30.58|2013-09:31.51|2013-10:31.62|2013-11:30.58|2013-12:30.50|2014-01:30.01|2014-02:30.36|2014-03:30.78|2014-04:30.78|2014-05:31.10|2014-06:31.48|2014-07:31.60|2014-08:32.14|2014-09:32.07|2014-10:32.22|2014-11:32.18|2014-12:32.59|2015-01:32.50|2015-02:32.30|2015-03:31.59|2015-04:32.35|2015-05:32.39|2015-06:33.23|2015-07:32.91|2015-08:32.46|2015-09:32.02|2015-10:33.07|2015-11:33.90|2015-12:35.64|2016-01:35.33|2016-02:36.28|2016-03:38.33|2016-04:38.87|2016-05:39.08|2016-06:41.35|2016-07:41.93|2016-08:42.81|2016-09:43.63|2016-10:43.88|2016-11:43.99|2016-12:46.14|2017-01:46.46|2017-02:47.26|2017-03:47.53|2017-04:47.47|2017-05:48.01|2017-06:48.44|2017-07:49.69|2017-08:50.10|2017-09:50.76|2017-10:50.54|2017-11:50.85|2017-12:51.37|2018-01:51.43|2018-02:51.58|2018-03:51.83|2018-04:51.22|2018-05:50.67|2018-06:50.71|2018-07:51.30|2018-08:50.33|2018-09:51.32|2018-10:52.42|2018-11:52.20|2018-12:52.77|2019-01:53.11|2019-02:53.11|2019-03:53.04|2019-04:53.06|2019-05:53.24|2019-06:53.82|2019-07:54.26|2019-08:53.31|2019-09:53.64|2019-10:54.11|2019-11:53.79|2019-12:54.70|2020-01:53.18|2020-02:52.54|2020-03:50.63|2020-04:51.57|2020-05:53.71|2020-06:56.24|2020-07:58.12|2020-08:58.67|2020-09:59.30|2020-10:59.14|2020-11:60.57|2020-12:61.37|2021-01:59.71|2021-02:59.50|2021-03:58.53|2021-04:57.70|2021-05:57.54|2021-06:58.43|2021-07:57.77|2021-08:57.18|2021-09:56.17|2021-10:55.21|2021-11:54.98|2021-12:55.11|2022-01:54.82|2022-02:55.45|2022-03:56.66|2022-04:56.40|2022-05:56.91|2022-06:56.03|2022-07:55.59|2022-08:56.05|2022-09:56.03|2022-10:55.98|2022-11:55.81|2022-12:56.13|2023-01:55.21|2023-02:55.71|2023-03:55.98|2023-04:55.92|2023-05:56.59|2023-06:57.78|2023-07:58.34|2023-08:58.68|2023-09:58.87|2023-10:58.85|2023-11:59.08|2023-12:60.43|2024-01:59.55|2024-02:60.32|2024-03:60.59|2024-04:60.55|2024-05:61.23|2024-06:61.28|2024-07:60.91|2024-08:61.08|2024-09:61.46|2024-10:61.12|2024-11:60.99|2024-12:61.30|2025-01:60.96|2025-02:61.13|2025-03:61.30|2025-04:61.25|2025-05:61.71|2025-06:62.60|2025-07:63.41|2025-08:64.05|2025-09:64.57|2025-10:64.68|2025-11:65.18|2025-12:65.24|2026-01:64.94|2026-02:65.46|2026-03:66.67|2026-04:67.13|2026-05:67.88|2026-06:68.49|2026-07:69.11|2026-08:69.27"
    }
  ];

  // Exclusive end dates prevent overlapping presidential terms.
  const govs = [
    ["Lula I", "2003-01-01", "2007-01-01", "#ff9999"],
    ["Lula II", "2007-01-01", "2011-01-01", "#cc0000"],
    ["Dilma I", "2011-01-01", "2015-01-01", "#ffff99"],
    ["Dilma II", "2015-01-01", "2016-09-01", "#cccc00"],
    ["Temer", "2016-09-01", "2019-01-01", "#d9d9d9"],
    ["Bolsonaro", "2019-01-01", "2023-01-01", "#b3ffb3"],
    ["Lula III", "2023-01-01", "2027-01-01", "#990000"]
  ];

  const monthLabel = iso => new Intl.DateTimeFormat("en-US", {
    month: "long",
    year: "numeric",
    timeZone: "UTC"
  }).format(new Date(iso + "T12:00:00Z"));

  function normalize(rows) {
    if (!Array.isArray(rows)) {
      throw new Error("Data unavailable.");
    }

    const points = rows.map(row => {
      const match = /^(\d{2})\/(\d{2})\/(\d{4})$/.exec(row.data || "");

      if (!match || !String(row.valor ?? "").trim()) {
        return null;
      }

      return {
        date: `${match[3]}-${match[2]}-${match[1]}`,
        value: Number(String(row.valor).replace(",", "."))
      };
    }).filter(point =>
      point &&
      point.date >= "2003-01-01" &&
      Number.isFinite(point.value)
    );

    points.sort((a, b) => a.date.localeCompare(b.date));

    if (!points.length) {
      throw new Error("Data unavailable.");
    }

    return points;
  }

  async function loadData(seriesCode) {
    const api = `https://api.bcb.gov.br/dados/serie/bcdata.sgs.${seriesCode}/dados?formato=json`;
    const controller = new AbortController();
    const timer = setTimeout(() => controller.abort(), 15000);

    try {
      const response = await fetch(api, {
        signal: controller.signal
      });

      if (!response.ok) {
        throw new Error("Data unavailable.");
      }

      return normalize(await response.json());
    } catch (error) {
      // Keep the displayed data if the background request fails.
      return null;
    } finally {
      clearTimeout(timer);
    }
  }

  async function loadPlotly() {
    if (window.Plotly) return;

    await new Promise((resolve, reject) => {
      const script = document.createElement("script");

      script.src = "https://cdn.plot.ly/plotly-basic-3.1.0.min.js";
      script.onload = resolve;
      script.onerror = reject;

      document.head.appendChild(script);
    });
  }

  async function initializeChart(config) {
    const root = document.getElementById(config.rootId);
    const chart = root.querySelector(".nfsp-chart");
    const status = root.querySelector(".nfsp-status");
    const seriesCode = config.seriesCode;
    try {
      // Render saved data first; the BCB response never delays the first chart.
      let points = normalize(config.backup.split("|").map(pair => {
        const [month, value] = pair.split(":");

        return {
          data: `01/${month.slice(5, 7)}/${month.slice(0, 4)}`,
          valor: value
        };
      }));

      // Serialize redraws and exports so each file matches the displayed series.
      let chartTask = Promise.resolve();

      function enqueue(action) {
        const nextTask = chartTask.then(action);
        chartTask = nextTask.catch(() => {});
        return nextTask;
      }

      async function render(nextPoints) {
        const x0 = nextPoints[0].date;

        const last = new Date(
          nextPoints[nextPoints.length - 1].date + "T12:00:00Z"
        );

        const x1 = new Date(
          Date.UTC(last.getUTCFullYear(), last.getUTCMonth() + 1, 1)
        ).toISOString().slice(0, 10);

        const narrow = chart.clientWidth < 500;

        const shapes = govs
          .filter(government => government[1] < x1 && government[2] > x0)
          .map(government => ({
            type: "rect",
            xref: "x",
            yref: "paper",
            x0: government[1] < x0 ? x0 : government[1],
            x1: government[2] > x1 ? x1 : government[2],
            y0: 0,
            y1: 1,
            fillcolor: government[3],
            opacity: .3,
            line: { width: 0 },
            layer: "below",
            name: government[0],
            showlegend: false
          }));

        // Separate legend markers keep the black border off the shaded bands.
        const legendItems = shapes.map(band => {
          const hex = band.fillcolor.slice(1);

          const rgb = [0, 2, 4].map(index =>
            parseInt(hex.slice(index, index + 2), 16)
          );

          return {
            type: "scatter",
            mode: "markers",
            x: [null],
            y: [null],
            name: band.name,
            showlegend: true,
            hoverinfo: "skip",
            marker: {
              symbol: "square",
              size: 11,
              color: `rgba(${rgb.join(",")},0.3)`,
              line: {
                color: "#000",
                width: 1
              }
            }
          };
        });

        const yaxis = {
          title: { text: "% of GDP", standoff: 8 },
          rangemode: "tozero", showgrid: true,
          gridcolor: "rgba(0,0,0,.13)", griddash: "dot",
          zeroline: true, zerolinecolor: "#888", zerolinewidth: 1,
          fixedrange: true
        };

        if (Number.isFinite(config.yMin)) {
          const maximum = Math.max(...nextPoints.map(point => point.value));
          const padding = Math.max(1, (maximum - config.yMin) * .05);
          const upper = Math.max(config.yMin + 5, Math.ceil((maximum + padding) / 5) * 5);
          yaxis.rangemode = "normal";
          yaxis.range = [config.yMin, upper];
          yaxis.autorange = false;
          yaxis.tick0 = config.yMin;
          yaxis.dtick = 5;
        }

        await Plotly.react(chart, [
          {
            x: nextPoints.map(point => point.date),
            y: nextPoints.map(point => point.value),
            customdata: nextPoints.map(point => monthLabel(point.date)),
            type: "scatter",
            mode: nextPoints.length === 1 ? "markers" : "lines",
            showlegend: false,
            line: {
              color: "#111",
              width: 1.8
            },
            marker: {
              color: "#111",
              size: 6
            },
            hovertemplate:
              "%{customdata}<br><b>%{y:.2f}% of GDP</b><extra></extra>"
          },
          ...legendItems
        ], {
          font: {
            family: '"Times New Roman", Times, serif',
            size: narrow ? 11 : 12,
            color: "#222"
          },

          separators: ".,",
          paper_bgcolor: "#fff",
          plot_bgcolor: "#fff",

          title: {
            text: config.title,
            font: {
              size: narrow ? 12 : 14
            },
            x: .5,
            xanchor: "center"
          },

          margin: {
            l: 52,
            r: 14,
            t: 68,
            b: 48
          },

          showlegend: true,

          legend: {
            title: { text: "Presidents", font: { size: narrow ? 10 : 11 } },
            x: .02,
            y: .98,
            bgcolor: "rgba(255,255,255,.85)",
            font: {
              size: narrow ? 10 : 11
            },
            itemclick: false,
            itemdoubleclick: false,
            ...(config.legendPosition || {})
          },

          annotations: [],

          xaxis: {
            type: "date",
            range: [x0, x1],
            tick0: "2003-01-01",
            dtick: narrow && nextPoints.length > 180 ? "M24" : "M12",
            tickformat: "%Y",
            tickangle: -90,
            showgrid: true,
            gridcolor: "rgba(0,0,0,.13)",
            griddash: "dot",
            zeroline: false,
            fixedrange: true
          },

          yaxis,

          shapes,
          hovermode: "closest",
          dragmode: false
        }, {
          locale: "en",
          responsive: true,
          displayModeBar: false,
          displaylogo: false,
          scrollZoom: false,
          doubleClick: false
        });

        points = nextPoints;

        root.querySelector(`#${config.prefix}-latest`).textContent =
          monthLabel(points[points.length - 1].date);

        chart.setAttribute("aria-busy", "false");
      }

      await enqueue(() => render(points));

      ["png"].forEach(format => {
        const button = root.querySelector(`#${config.prefix}-${format}`);
        button.disabled = false;

        button.addEventListener("click", async () => {
          button.disabled = true;
          status.hidden = true;

          try {
            await enqueue(async () => {
              const period =
                `${points[0].date.slice(0, 7)}-` +
                `${points[points.length - 1].date.slice(0, 7)}`;

              // Preserve the source in the PNG without a footer on the page.
              const figure = {
                data: chart.data,

                layout: {
                  ...chart.layout,

                  width: 1000,
                  height: 650,
                  autosize: false,

                  title: {
                    ...chart.layout.title,
                    text: config.exportTitle,
                    font: {
                      size: 14
                    }
                  },

                  margin: {
                    l: 52,
                    r: 14,
                    t: 60,
                    b: 90
                  },

                  annotations: [
                    {
                      xref: "paper",
                      yref: "paper",
                      x: 0,
                      y: 0,
                      yshift: -66,
                      xanchor: "left",
                      yanchor: "top",
                      showarrow: false,
                      text:
                        "Source: Brazilian Central Bank (BCB) – " +
                        "<i>Sistema Gerenciador de Séries Temporais (SGS)</i>, " +
                        `code ${seriesCode}.`,
                      font: {
                        size: 9
                      }
                    }
                  ]
                },

                config: {
                  locale: "en"
                }
              };

              await Plotly.downloadImage(figure, {
                format,
                filename: `${config.prefix}-${seriesCode}-${period}`,
                width: 1000,
                height: 650,
                scale: 2
              });
            });
          } catch (error) {
            status.textContent =
              "Unable to download the figure. Please try again.";

            status.hidden = false;
          } finally {
            button.disabled = false;
          }
        });
      });

      // Refresh silently after the first chart is visible.
      void loadData(seriesCode).then(freshPoints => {
        if (!freshPoints) return;

        return enqueue(async () => {
          const unchanged =
            freshPoints.length === points.length &&
            freshPoints.every((point, index) =>
              point.date === points[index].date &&
              point.value === points[index].value
            );

          if (!unchanged) {
            await render(freshPoints);
          }
        });
      }).catch(() => {});

    } catch (error) {
      chart.setAttribute("aria-busy", "false");

      status.textContent =
        "Unable to load the chart. Please reload the page.";

      status.hidden = false;
    }
  }

  // Load the plotting library once and initialize both charts independently.
  try {
    await loadPlotly();
    charts.forEach(config => { void initializeChart(config); });
  } catch (error) {
    charts.forEach(config => {
      const root = document.getElementById(config.rootId);
      root.querySelector(".nfsp-chart").setAttribute("aria-busy", "false");
      const status = root.querySelector(".nfsp-status");
      status.textContent = "Unable to load the chart. Please reload the page.";
      status.hidden = false;
    });
  }
})();
</script>
