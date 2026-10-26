---
layout: page
title: "Explore with me"
lang: "en"
permalink: /explore_with_me/
---

<style>
#explore-nfsp { font-size: .85em; line-height: 1.5; }
#explore-nfsp * { box-sizing: border-box; }
#explore-nfsp .nfsp-header { display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: .7em; }
#explore-nfsp h2 { margin: 0; font-size: 1.35em; }
#explore-nfsp .nfsp-actions { display: flex; flex-wrap: wrap; align-items: center; gap: .5em; font-size: .85em; }
#explore-nfsp button, #explore-nfsp summary { display: inline-block; font: inherit; color: #333; background: #fff; border: 1px solid #bbb; border-radius: 4px; padding: .4em .65em; cursor: pointer; }
#explore-nfsp button:hover, #explore-nfsp summary:hover { background: #f3f3f3; }
#explore-nfsp button:disabled { opacity: .5; cursor: wait; }
#explore-nfsp :focus-visible { outline: 2px solid #555; outline-offset: 3px; }
#explore-nfsp details { position: relative; }
#explore-nfsp summary { list-style: none; }
#explore-nfsp summary::-webkit-details-marker { display: none; }
#explore-nfsp summary::after { content: " ▾"; }
#explore-nfsp details[open] summary::after { content: " ▴"; }
#explore-nfsp .nfsp-info { position: absolute; z-index: 10; top: calc(100% + 8px); right: 0; width: min(300px, calc(100vw - 48px)); padding: 1em; background: #fff; border: 1px solid #ddd; border-radius: 4px; box-shadow: 0 4px 14px #0002; }
#explore-nfsp .nfsp-info p { margin: 0 0 .7em; }
#explore-nfsp .nfsp-info p:last-child { margin: 0; }
#explore-nfsp .nfsp-chart { width: 100%; height: 440px; margin-top: .6em; }
#explore-nfsp .nfsp-status { font-size: .85em; color: #555; }
#explore-nfsp .nfsp-status[hidden] { display: none; }
@media (max-width: 600px) {
  #explore-nfsp { font-size: .8em; }
  #explore-nfsp .nfsp-chart { height: 400px; }
  #explore-nfsp .nfsp-info { left: 0; right: auto; }
}
</style>

<section lang="en" id="explore-nfsp" aria-labelledby="nfsp-heading">
  <div class="nfsp-header">
    <h2 id="nfsp-heading">Brazil’s fiscal trajectory</h2>
    <div class="nfsp-actions">
      <details>
        <summary>About the data</summary>
        <div class="nfsp-info">
          <p><strong>Brazilian Central Bank series code: 5727 (BCB-SGS).</strong></p>
          <p>Original name: <span lang="pt-BR">NFSP sem desvalorização cambial</span>.</p>
          <p>Public sector borrowing requirements <em>(Necessidade de financiamento do setor público – NFSP)</em>, excluding exchange rate effects: the consolidated public sector’s nominal balance, as a rolling 12-month total (% of GDP).</p>
          <p>Frequency: monthly.<br>Latest observation: <span id="nfsp-latest">—</span>.</p>
          <p>Colors identify presidential terms. Temer’s band begins in September 2016, following his permanent assumption of office.</p>
          <p>Source: <a href="https://dadosabertos.bcb.gov.br/dataset/5727-nfsp-sem-desvalorizacao-cambial--pib---fluxo-acumulado-em-12-meses---resultado-nominal---total" target="_blank" rel="noopener noreferrer">Brazilian Central Brank</a>.</p>
        </div>
      </details>
      <button id="nfsp-png" type="button" disabled>Download PNG</button>
    </div>
  </div>
  <div id="nfsp-chart" class="nfsp-chart" aria-label="Public sector borrowing requirements as a percentage of GDP" aria-busy="true"></div>
  <p id="nfsp-status" class="nfsp-status" role="status" aria-live="polite" hidden></p>
  <noscript>Enable JavaScript to view the chart.</noscript>
</section>

<script>
(async function () {
  "use strict";

  const root = document.getElementById("explore-nfsp");
  const chart = root.querySelector("#nfsp-chart");
  const status = root.querySelector("#nfsp-status");
  const seriesCode = 5727;
  const api = `https://api.bcb.gov.br/dados/serie/bcdata.sgs.${seriesCode}/dados?formato=json`;

  // Backup of official data retrieved on October 26, 2026.
  const backup = "2003-01:4.93|2003-02:5.12|2003-03:5.38|2003-04:4.97|2003-05:5.15|2003-06:5.39|2003-07:5.91|2003-08:5.92|2003-09:5.97|2003-10:5.55|2003-11:5.64|2003-12:5.18|2004-01:4.60|2004-02:4.33|2004-03:4.00|2004-04:4.29|2004-05:4.01|2004-06:3.70|2004-07:3.34|2004-08:3.11|2004-09:3.05|2004-10:3.10|2004-11:3.00|2004-12:2.88|2005-01:2.78|2005-02:2.93|2005-03:2.98|2005-04:2.74|2005-05:2.89|2005-06:3.10|2005-07:3.13|2005-08:3.14|2005-09:3.31|2005-10:3.32|2005-11:3.45|2005-12:3.54|2006-01:4.06|2006-02:4.12|2006-03:4.11|2006-04:4.02|2006-05:3.71|2006-06:3.72|2006-07:3.80|2006-08:3.71|2006-09:3.65|2006-10:3.51|2006-11:3.42|2006-12:3.57|2007-01:3.01|2007-02:2.85|2007-03:2.90|2007-04:2.83|2007-05:3.08|2007-06:2.82|2007-07:2.78|2007-08:2.70|2007-09:2.85|2007-10:2.86|2007-11:2.70|2007-12:2.74|2008-01:2.50|2008-02:2.55|2008-03:2.21|2008-04:2.25|2008-05:2.18|2008-06:2.31|2008-07:2.28|2008-08:2.22|2008-09:1.74|2008-10:1.32|2008-11:1.52|2008-12:1.99|2009-01:2.46|2009-02:2.43|2009-03:2.68|2009-04:2.85|2009-05:2.93|2009-06:3.02|2009-07:3.19|2009-08:3.32|2009-09:4.01|2009-10:4.28|2009-11:3.96|2009-12:3.19|2010-01:2.86|2010-02:2.94|2010-03:3.20|2010-04:2.96|2010-05:3.07|2010-06:3.12|2010-07:3.12|2010-08:3.16|2010-09:2.21|2010-10:2.32|2010-11:2.58|2010-12:2.41|2011-01:2.47|2011-02:2.45|2011-03:2.17|2011-04:2.32|2011-05:2.27|2011-06:2.05|2011-07:1.78|2011-08:1.91|2011-09:2.39|2011-10:2.37|2011-11:2.26|2011-12:2.47|2012-01:2.27|2012-02:2.19|2012-03:2.26|2012-04:2.27|2012-05:2.29|2012-06:2.44|2012-07:2.56|2012-08:2.52|2012-09:2.57|2012-10:2.50|2012-11:2.73|2012-12:2.26|2013-01:2.22|2013-02:2.50|2013-03:2.59|2013-04:2.65|2013-05:2.60|2013-06:2.56|2013-07:2.71|2013-08:2.82|2013-09:3.00|2013-10:3.10|2013-11:2.67|2013-12:2.96|2014-01:3.27|2014-02:2.98|2014-03:2.90|2014-04:2.83|2014-05:3.13|2014-06:3.27|2014-07:3.46|2014-08:3.60|2014-09:4.39|2014-10:4.48|2014-11:5.18|2014-12:5.95|2015-01:5.70|2015-02:6.53|2015-03:7.45|2015-04:7.16|2015-05:7.61|2015-06:7.83|2015-07:8.48|2015-08:8.89|2015-09:9.01|2015-10:9.18|2015-11:9.19|2015-12:10.22|2016-01:10.73|2016-02:10.60|2016-03:9.59|2016-04:9.96|2016-05:9.93|2016-06:9.81|2016-07:9.47|2016-08:9.53|2016-09:9.32|2016-10:8.77|2016-11:9.32|2016-12:8.98|2017-01:8.48|2017-02:8.47|2017-03:9.13|2017-04:9.14|2017-05:9.19|2017-06:9.45|2017-07:9.28|2017-08:8.97|2017-09:8.73|2017-10:9.21|2017-11:8.41|2017-12:7.77|2018-01:7.44|2018-02:7.28|2018-03:7.30|2018-04:7.42|2018-05:7.12|2018-06:7.18|2018-07:6.91|2018-08:7.32|2018-09:7.08|2018-10:6.68|2018-11:6.95|2018-12:6.96|2019-01:6.83|2019-02:6.78|2019-03:6.83|2019-04:6.83|2019-05:6.77|2019-06:6.37|2019-07:6.35|2019-08:6.14|2019-09:6.20|2019-10:6.23|2019-11:6.24|2019-12:5.81|2020-01:5.87|2020-02:5.90|2020-03:6.11|2020-04:7.32|2020-05:8.61|2020-06:11.02|2020-07:11.77|2020-08:12.54|2020-09:13.26|2020-10:13.48|2020-11:12.97|2020-12:13.34|2021-01:13.25|2021-02:12.99|2021-03:12.32|2021-04:10.25|2021-05:8.81|2021-06:7.06|2021-07:6.59|2021-08:5.42|2021-09:4.64|2021-10:4.52|2021-11:4.54|2021-12:4.26|2022-01:3.51|2022-02:3.29|2022-03:3.06|2022-04:3.80|2022-05:4.06|2022-06:4.10|2022-07:3.71|2022-08:4.04|2022-09:4.19|2022-10:4.04|2022-11:4.44|2022-12:4.57|2023-01:4.90|2023-02:5.52|2023-03:5.98|2023-04:5.79|2023-05:6.26|2023-06:6.28|2023-07:6.81|2023-08:7.15|2023-09:7.48|2023-10:7.73|2023-11:7.77|2023-12:8.84|2024-01:9.00|2024-02:9.15|2024-03:8.97|2024-04:9.30|2024-05:9.43|2024-06:9.78|2024-07:9.86|2024-08:9.66|2024-09:9.20|2024-10:9.36|2024-11:9.47|2024-12:8.47|2025-01:8.08|2025-02:7.87|2025-03:7.88|2025-04:7.70|2025-05:7.54|2025-06:7.27|2025-07:7.82|2025-08:7.79|2025-09:8.13|2025-10:8.14|2025-11:8.12|2025-12:8.34|2026-01:8.48|2026-02:8.47|2026-03:9.39|2026-04:9.37|2026-05:9.61|2026-06:9.99|2026-07:9.35|2026-08:9.48";

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
    month: "long", year: "numeric", timeZone: "UTC"
  }).format(new Date(iso + "T12:00:00Z"));

  function normalize(rows) {
    if (!Array.isArray(rows)) throw new Error("Data unavailable.");
    const points = rows.map(row => {
      const match = /^(\d{2})\/(\d{2})\/(\d{4})$/.exec(row.data || "");
      if (!match || !String(row.valor ?? "").trim()) return null;
      return { date: `${match[3]}-${match[2]}-${match[1]}`,
        value: Number(String(row.valor).replace(",", ".")) };
    }).filter(p => p && p.date >= "2003-01-01" && Number.isFinite(p.value));
    points.sort((a, b) => a.date.localeCompare(b.date));
    if (!points.length) throw new Error("Data unavailable.");
    return points;
  }

  async function loadData() {
    const controller = new AbortController();
    const timer = setTimeout(() => controller.abort(), 15000);
    try {
      const response = await fetch(api, { signal: controller.signal });
      if (!response.ok) throw new Error("Data unavailable.");
      return normalize(await response.json());
    } catch (error) {
      return null; // Keep the displayed data if the background request fails.
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

  try {
    // Render saved data first; the BCB response never delays the first chart.
    let points = normalize(backup.split("|").map(pair => {
      const [month, value] = pair.split(":");
      return { data: `01/${month.slice(5, 7)}/${month.slice(0, 4)}`, valor: value };
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
      const last = new Date(nextPoints[nextPoints.length - 1].date + "T12:00:00Z");
      const x1 = new Date(Date.UTC(last.getUTCFullYear(), last.getUTCMonth() + 1, 1)).toISOString().slice(0, 10);
      const narrow = chart.clientWidth < 500;

      const shapes = govs.filter(g => g[1] < x1 && g[2] > x0).map(g => ({
        type: "rect", xref: "x", yref: "paper", x0: g[1] < x0 ? x0 : g[1],
        x1: g[2] > x1 ? x1 : g[2], y0: 0, y1: 1,
        fillcolor: g[3], opacity: .3, line: { width: 0 }, layer: "below",
        name: g[0], showlegend: true
      }));

      await Plotly.react(chart, [{
        x: nextPoints.map(p => p.date), y: nextPoints.map(p => p.value),
        customdata: nextPoints.map(p => monthLabel(p.date)),
        type: "scatter", mode: nextPoints.length === 1 ? "markers" : "lines", showlegend: false,
        line: { color: "#111", width: 1.8 }, marker: { color: "#111", size: 6 },
        hovertemplate: "%{customdata}<br><b>%{y:.2f}% of GDP</b><extra></extra>"
      }], {
        font: { family: '"Times New Roman", Times, serif', size: narrow ? 11 : 12, color: "#222" },
        separators: ".,", paper_bgcolor: "#fff", plot_bgcolor: "#fff",
        title: { text: "Public sector borrowing requirements (% of GDP)<br><sup>Nominal balance · 12-month total · Excluding exchange rate effects</sup>",
          font: { size: narrow ? 12 : 14 }, x: .5, xanchor: "center" },
        margin: { l: 52, r: 14, t: 60, b: 90 }, showlegend: true,
        legend: { x: .02, y: .98, bgcolor: "rgba(255,255,255,.85)", font: { size: narrow ? 10 : 11 },
          itemclick: false, itemdoubleclick: false },
        annotations: [{ xref: "paper", yref: "paper", x: 0, y: 0, yshift: -66,
          xanchor: "left", yanchor: "top", showarrow: false,
          text: `Source: BCB · SGS code ${seriesCode}. Author’s calculations.`, font: { size: 9 } }],
        xaxis: { type: "date", range: [x0, x1], tick0: "2003-01-01",
          dtick: narrow && nextPoints.length > 180 ? "M24" : "M12", tickformat: "%Y",
          tickangle: -90, showgrid: true, gridcolor: "rgba(0,0,0,.13)", griddash: "dot", zeroline: false, fixedrange: true },
        yaxis: { title: { text: "% of GDP", standoff: 8 }, rangemode: "tozero",
          showgrid: true, gridcolor: "rgba(0,0,0,.13)", griddash: "dot",
          zeroline: true, zerolinecolor: "#888", zerolinewidth: 1, fixedrange: true },
        shapes, hovermode: "closest", dragmode: false
      }, { locale: "en", responsive: true, displayModeBar: false, displaylogo: false, scrollZoom: false, doubleClick: false });
      points = nextPoints;
      root.querySelector("#nfsp-latest").textContent = monthLabel(points[points.length - 1].date);
      chart.setAttribute("aria-busy", "false");
    }

    await loadPlotly();
    await enqueue(() => render(points));

    ["png"].forEach(format => {
      const button = root.querySelector(`#nfsp-${format}`);
      button.disabled = false;
      button.addEventListener("click", async () => {
        button.disabled = true;
        status.hidden = true;
        try {
          await enqueue(async () => {
            const period = `${points[0].date.slice(0, 7)}-${points[points.length - 1].date.slice(0, 7)}`;
            await Plotly.downloadImage(chart, {
              format, filename: `nfsp-${seriesCode}-${period}`,
              width: 1000, height: 650,
              scale: format === "png" ? 2 : 1
            });
          });
        } catch (error) {
          status.textContent = "Unable to download the figure. Please try again.";
          status.hidden = false;
        } finally {
          button.disabled = false;
        }
      });
    });

    // Refresh silently after the first chart is visible.
    void loadData().then(freshPoints => {
      if (!freshPoints) return;
      return enqueue(async () => {
        const unchanged = freshPoints.length === points.length && freshPoints.every((point, i) =>
          point.date === points[i].date && point.value === points[i].value);
        if (!unchanged) await render(freshPoints);
      });
    }).catch(() => {});
  } catch (error) {
    chart.setAttribute("aria-busy", "false");
    status.textContent = "Unable to load the chart. Please reload the page.";
    status.hidden = false;
  }
})();
</script>
