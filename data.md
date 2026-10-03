---
layout: default
title: Numbers & Data
permalink: /data/
---

<div class="kicker">Metrics</div>
<h1>Numbers &amp; Data</h1>
<p class="lede">Every hard number this desk has verified about the scheme, as a living table. Rendered live from <a href="https://github.com/ungalsoththu/VetriPayanam/blob/main/data/metrics.csv">data/metrics.csv</a> — the daily watch agent appends rows, and this page reflects them on its next build.</p>

<div id="metrics"><p class="note">Loading metrics…</p></div>
<p class="note">Phases: <b>vidiyal</b> = DMK-era scheme (2021–) · <b>vetri</b> = expanded Magalir Vetri Payanam (Oct 2026–) · <b>context</b> = scheme-adjacent operational figures. Claims vs verified figures are labelled in the note column.</p>

<script>
fetch('https://raw.githubusercontent.com/ungalsoththu/VetriPayanam/main/data/metrics.csv')
  .then(r => r.ok ? r.text() : Promise.reject(r.status))
  .then(t => {
    const rows = t.trim().split('\n').map(l => l.match(/("([^\"]|"")*"|[^,]*)(,|$)/g).map(c => c.replace(/,$/,'').replace(/^\"|\"$/g,'').replace(/\"\"/g,'"')));
    const head = rows.shift();
    const el = document.getElementById('metrics');
    const table = document.createElement('table');
    table.innerHTML = '<thead><tr>' + head.map(h => '<th>' + h + '</th>').join('') + '</tr></thead><tbody>' +
      rows.map(r => '<tr>' + r.map(c => {
        const v = c.replace(/&/g,'&amp;').replace(/</g,'&lt;');
        return /^https?:\/\//.test(c) ? '<td><a href="' + c + '" target="_blank" rel="noopener">source</a></td>' : '<td>' + v + '</td>';
      }).join('') + '</tr>').join('') + '</tbody>';
    el.innerHTML = ''; el.appendChild(table);
  })
  .catch(() => { document.getElementById('metrics').innerHTML = '<p class="note">Couldn\u2019t load metrics right now — see the <a href="https://github.com/ungalsoththu/VetriPayanam/blob/main/data/metrics.csv">CSV on GitHub</a>.</p>'; });
</script>
