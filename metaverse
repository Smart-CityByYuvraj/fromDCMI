

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8" />
  <title>India Works Tracker – Political Map</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <!-- amCharts 5 (free for school/non-commercial use). Loads India states geodata -->
  <script src="https://cdn.amcharts.com/lib/5/index.js"></script>
  <script src="https://cdn.amcharts.com/lib/5/map.js"></script>
  <script src="https://cdn.amcharts.com/lib/5/geodata/indiaLow.js"></script>
  <script src="https://cdn.amcharts.com/lib/5/themes/Animated.js"></script>
  <style>
    :root { --bg:#0b1020; --panel:#121835; --card:#0f1530; --text:#e6ecff; --muted:#b1b8d6; }
    *{box-sizing:border-box}
    body{
      margin:0; background:linear-gradient(180deg,#0b1020 0%,#0b1228 60%,#0a0f24 100%);
      color:var(--text); font-family:system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial;
      min-height:100vh; display:flex; flex-direction:column;
    }
    header{padding:14px 18px; display:flex; gap:14px; align-items:center; border-bottom:1px solid #243067; background:#0a1330aa; backdrop-filter: blur(6px); position:sticky; top:0; z-index:5}
    header h1{font-size:18px; margin:0; font-weight:700}
    header .subtitle{font-size:12px; color:var(--muted)}
    .layout{display:grid; grid-template-columns: 1.2fr 1fr; gap:16px; padding:16px; flex:1; min-height:0}
    #chartdiv{width:100%; height: calc(100vh - 130px); min-height:520px; background:var(--panel); border-radius:16px}
    aside{display:flex; flex-direction:column; gap:12px; height: calc(100vh - 130px); min-height:520px}
    .card{
      background:linear-gradient(180deg,#121a3a 0%,#0f1836 100%);
      border:1px solid #27316b; border-radius:16px; box-shadow: 0 10px 30px rgba(0,0,0,.25);
      padding:12px; overflow:auto; min-height:0
    }
    .card h3{margin:0 0 8px 0; font-size:14px; letter-spacing:.3px}
    .row{display:grid; grid-template-columns: 1fr 1fr; gap:8px}
    label{font-size:12px; color:#c9d2ff; display:block; margin-top:6px}
    input, textarea, select{
      width:100%; padding:8px 10px; border-radius:10px; border:1px solid #2c3870; background:#0b1330; color:var(--text);
      outline:none;
    }
    textarea{resize:vertical; min-height:64px}
    button{
      background:#2b5cff; color:white; padding:10px 12px; border:none; border-radius:12px; cursor:pointer; font-weight:700;
    }
    button.secondary{background:#18224a}
    .list{display:flex; flex-direction:column; gap:8px}
    .item{
      background:var(--card); border:1px solid #25306a; border-radius:12px; padding:10px; display:grid; gap:4px
    }
    .meta{font-size:12px; color:var(--muted)}
    .tag{display:inline-block; padding:2px 8px; border-radius:999px; font-size:11px; background:#1c2658; border:1px solid #2a3872; margin-right:6px}
    .toolbar{display:flex; gap:8px; flex-wrap:wrap; align-items:center}
    .muted{color:var(--muted); font-size:12px}
    .legend{display:flex; gap:8px; flex-wrap:wrap; align-items:center; font-size:12px}
    .legend > span{display:inline-flex; align-items:center; gap:6px}
    .swatch{width:10px; height:10px; border-radius:2px; display:inline-block}
    .danger{color:#ff9c9c}
    .success{color:#9cffb1}
    .hint{font-size:11px; color:#9bb0ff}
    .hr{height:1px; background:#25306a; margin:8px 0}
    footer{padding:8px 16px; text-align:center; font-size:12px; color:#9bb0ff}
  </style>
</head>

<body>

   <nav style="background:#1565c0; padding:20px; display:flex; gap:20px; 
              position:fixed; top:10; left:0; right:0; z-index:1000; width:10000px ;">
       <a href="metaverse website2.html" style="color:#fff; text-decoration:none; font-weight:bold;">Project Info</a>
    <a href="metaverse website3.html" style="color:#fff; text-decoration:none; font-weight:bold;">Material Required</a>
     <a href="metaverse website4.html" style="color:#fff; text-decoration:none; font-weight:bold;">Place Oder</a>

  </nav>

  <!-- Push page content down -->
  <div style="margin-top:60px;">
    <!-- your content starts here -->
  </div>
</body>


  <header>
    <div>
      <h1>India Works Tracker</h1>
      <div class="subtitle">Click a state on the political map to add a “work started” marker. Everything is saved locally.</div>
    </div>
    <div class="legend">
      <span><i class="swatch" style="background:#5570ff"></i> State boundary</span>
      <span><i class="swatch" style="background:#20c997"></i> States with works</span>
      <span><i class="swatch" style="background:#ff6b6b"></i> Selected state</span>
    </div>z
  </header>

  <div class="layout">
    <div id="chartdiv" aria-label="Political map of India showing states"></div>

    <aside>
      <div class="card" id="formCard">
        <h3>Add / Edit Work</h3>
        <div class="toolbar">
          <span class="muted">Click on the map (inside a state) to pre-fill State & coordinates.</span>
        </div>
        <div class="hr"></div>
        <form id="workForm">
          <div class="row">
            <div>
              <label>Title</label>
              <input id="title" placeholder="e.g., Smart Irrigation Pilot" required />
            </div>
            <div>
              <label>Date</label>
              <input id="date" type="date" />
            </div>
          </div>
          <div class="row">
            <div>
              <label>State</label>
              <input id="state" placeholder="Auto-filled on click" required />
            </div>
            <div>
              <label>City / Area</label>
              <input id="city" placeholder="e.g., Nagpur" />
            </div>
          </div>
          <label>Description</label>
          <textarea id="desc" placeholder="What/why/how? Key specs or sensors."></textarea>
          <div class="row">
            <div>
              <label>Latitude</label>
              <input id="lat" placeholder="auto" />
            </div>
            <div>
              <label>Longitude</label>
              <input id="lng" placeholder="auto" />
            </div>
          </div>
          <div class="row" style="margin-top:8px">
            <button type="submit">Save / Update</button>
            <button type="button" class="secondary" id="resetBtn">Reset Form</button>
          </div>
          <div class="hint" style="margin-top:6px">Tip: you can also click on an existing marker to edit it.</div>
        </form>
      </div>

      <div class="card">
        <h3>All Works</h3>
        <div class="toolbar" style="margin-bottom:8px">
          <input id="search" placeholder="Search title/city/state…" />
          <button type="button" id="exportBtn">Export JSON</button>
          <label class="secondary" style="display:inline-flex; gap:8px; align-items:center; padding:8px 12px; border-radius:12px; cursor:pointer">
            Import JSON
            <input id="importFile" type="file" accept="application/json" style="display:none" />
          </label>
          <button type="button" id="clearBtn" class="secondary danger">Clear All</button>
        </div>
        <div id="list" class="list" aria-live="polite"></div>
      </div>
    </aside>
  </div>

  <footer>Built for metaverse project </footer>

  <script>
    // ------------------------- Data store (localStorage) -------------------------
    const STORAGE_KEY = "indiaWorks_v1";
    /** @type {Array<{id:string,title:string,date?:string,state:string,city?:string,desc?:string,lat?:number,lng?:number}>} */
    let WORKS = [];

    function load() {
      try {
        WORKS = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
      } catch { WORKS = []; }
    }
    function save() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(WORKS));
      renderList();
      updateStateFills();
    }
    function uid() { return Math.random().toString(36).slice(2,9); }

    // ------------------------- UI: list render -------------------------
    const listEl = document.getElementById("list");
    const searchEl = document.getElementById("search");

    function renderList() {
      const q = (searchEl.value || "").toLowerCase();
      listEl.innerHTML = "";
      const items = WORKS.filter(w =>
        [w.title,w.city,w.state,w.desc].filter(Boolean).some(s => (s||"").toLowerCase().includes(q))
      );
      if (!items.length) {
        listEl.innerHTML = '<div class="muted">No items yet. Click on the map or use the form to add your first work.</div>';
        return;
      }
      for (const w of items) {
        const el = document.createElement("div");
        el.className = "item";
        el.innerHTML = `
          <div style="display:flex; justify-content:space-between; gap:8px; align-items:center">
            <div style="font-weight:700">${w.title}</div>
            <div class="meta">${w.date ? new Date(w.date).toLocaleDateString() : ""}</div>
          </div>
          <div class="meta">
            <span class="tag">${w.state}</span>
            ${w.city ? `<span class="tag">${w.city}</span>` : ""}
            ${Number.isFinite(w.lat) && Number.isFinite(w.lng) ? `<span class="tag">${w.lat.toFixed(3)}, ${w.lng.toFixed(3)}</span>` : ""}
          </div>
          ${w.desc ? `<div>${w.desc}</div>` : ""}
          <div class="toolbar" style="margin-top:6px">
            <button data-act="zoom" data-id="${w.id}">Zoom</button>
            <button class="secondary" data-act="edit" data-id="${w.id}">Edit</button>
            <button class="secondary danger" data-act="del" data-id="${w.id}">Delete</button>
          </div>
        `;
        listEl.appendChild(el);
      }
    }

    listEl.addEventListener("click", (e) => {
      const btn = e.target.closest("button"); if(!btn) return;
      const id = btn.getAttribute("data-id");
      const act = btn.getAttribute("data-act");
      const w = WORKS.find(x => x.id===id); if(!w) return;

      if (act==="del") {
        if (confirm("Delete this item?")) {
          WORKS = WORKS.filter(x => x.id!==id);
          removeMarker(id);
          save();
        }
      } else if (act==="edit") {
        fillForm(w);
      } else if (act==="zoom") {
        if (Number.isFinite(w.lat) && Number.isFinite(w.lng)) {
          focusOnLatLng(w.lat, w.lng);
        } else {
          selectStateByName(w.state, true);
        }
      }
    });

    document.getElementById("exportBtn").addEventListener("click", () => {
      const blob = new Blob([JSON.stringify(WORKS, null, 2)], {type:"application/json"});
      const url = URL.createObjectURL(blob);
      const a = Object.assign(document.createElement("a"), {href:url, download:"india-works.json"});
      document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
    });

    document.getElementById("importFile").addEventListener("change", async (e) => {
      const file = e.target.files[0]; if (!file) return;
      try {
        const text = await file.text();
        const data = JSON.parse(text);
        if (Array.isArray(data)) {
          WORKS = data.map(d => ({id: d.id || uid(), ...d}));
          rebuildMarkers();
          save();
        } else alert("Invalid JSON.");
      } catch (err) { alert("Failed to import: " + err.message); }
      e.target.value = "";
    });

    document.getElementById("clearBtn").addEventListener("click", () => {
      if (confirm("This will remove all saved works and markers.")) {
        WORKS = [];
        rebuildMarkers();
        save();
      }
    });

    searchEl.addEventListener("input", renderList);

    // ------------------------- Map (amCharts 5) -------------------------
    let root, chart, polygonSeries, pointSeries;

    function initMap() {
      root = am5.Root.new("chartdiv");
      root.setThemes([am5themes_Animated.new(root)]);

      chart = root.container.children.push(am5map.MapChart.new(root, {
        panX: "rotateX",
        panY: "none",
        projection: am5map.geoMercator(),
        wheelY: "zoom"
      }));

      polygonSeries = chart.series.push(am5map.MapPolygonSeries.new(root, {
        geoJSON: am5geodata_indiaLow,
        exclude: [], // keep all
        valueField: "value",
        calculateAggregates: true
      }));

      // Default styling of states
      polygonSeries.mapPolygons.template.setAll({
        tooltipText: "{name}",
        interactive: true
      });
      polygonSeries.mapPolygons.template.states.create("hover", { fill: am5.color(0xff6b6b) });
      polygonSeries.mapPolygons.template.setAll({
        fill: am5.color(0x5570ff),
        stroke: am5.color(0x2a3a8f),
        strokeWidth: 1
      });

      // Click to prefill form with state and coords
      polygonSeries.mapPolygons.template.events.on("click", (ev) => {
        const data = ev.target.dataItem.dataContext;
        const name = data.name;
        const centroid = am5map.getGeoCentroid(data.geometry);
        if (centroid) {
          const p = chart.convert({longitude: centroid[0], latitude: centroid[1]});
          // Prefill form
          document.getElementById("state").value = name;
          document.getElementById("lat").value = centroid[1].toFixed(5);
          document.getElementById("lng").value = centroid[0].toFixed(5);
        }
        // Visually select
        polygonSeries.mapPolygons.each(mp => mp.set("fill", am5.color(0x5570ff)));
        ev.target.set("fill", am5.color(0xff6b6b));
      });

      // Markers (works)
      pointSeries = chart.series.push(am5map.MapPointSeries.new(root, {}));
      const circleTemplate = am5.Template.new({});
      pointSeries.bullets.push((root, dataItem) => {
        const g = am5.Graphics.new(root, {
          themeTags: ["marker"],
          tooltipText: "{title}\n{state}{city}\n{date}\n{desc}",
          cursorOverStyle: "pointer"
        }, circleTemplate);
        g.setAll({
          draw: (display) => {
            display.circle(0,0,6); // simple circle marker
          },
          fill: am5.color(0x20c997)
        });

        g.events.on("click", () => {
          const id = dataItem.dataContext.id;
          const w = WORKS.find(x => x.id===id);
          if (w) fillForm(w); // open in form for edit
        });
        return am5.Bullet.new(root, { sprite: g });
      });

      rebuildMarkers();
      updateStateFills();
    }

    function selectStateByName(name, zoomOnly=false) {
      const item = polygonSeries.dataItems.find(di => (di.dataContext && di.dataContext.name === name));
      if (item) {
        const geo = item.get("mapPolygon").getGeoBounds();
        chart.zoomToGeoBounds(geo, 1, true);
        if (!zoomOnly) {
          polygonSeries.mapPolygons.each(mp => mp.set("fill", am5.color(0x5570ff)));
          item.get("mapPolygon").set("fill", am5.color(0xff6b6b));
        }
      }
    }

    function focusOnLatLng(lat, lng) {
      chart.zoomToGeoPoint({latitude: lat, longitude: lng}, 12, true, 500);
    }

    function rebuildMarkers() {
      if (!pointSeries) return;
      pointSeries.data.setAll([]); // clear
      for (const w of WORKS) {
        if (Number.isFinite(w.lat) && Number.isFinite(w.lng)) {
          pointSeries.data.push({
            id: w.id, title: w.title,
            state: w.state ? "State: " + w.state : "",
            city: w.city ? "\nCity: " + w.city : "",
            date: w.date ? "\nDate: " + new Date(w.date).toLocaleDateString() : "",
            desc: w.desc ? "\n" + w.desc : "",
            geometry: { type: "Point", coordinates: [w.lng, w.lat] }
          });
        }
      }
    }

    function updateStateFills() {
      const statesWithWorks = new Set(WORKS.map(w => w.state).filter(Boolean));
      polygonSeries.mapPolygons.each(mp => {
        const name = mp.dataItem.dataContext.name;
        if (statesWithWorks.has(name)) {
          mp.set("fill", am5.color(0x20c997)); // green if has at least one work
        } else {
          mp.set("fill", am5.color(0x5570ff));
        }
      });
    }

    // ------------------------- Form logic -------------------------
    const form = document.getElementById("workForm");
    const titleEl = document.getElementById("title");
    const dateEl = document.getElementById("date");
    const stateEl = document.getElementById("state");
    const cityEl = document.getElementById("city");
    const descEl = document.getElementById("desc");
    const latEl = document.getElementById("lat");
    const lngEl = document.getElementById("lng");
    const resetBtn = document.getElementById("resetBtn");

    let editingId = null;

    function fillForm(w) {
      editingId = w.id;
      titleEl.value = w.title || "";
      dateEl.value = w.date || "";
      stateEl.value = w.state || "";
      cityEl.value = w.city || "";
      descEl.value = w.desc || "";
      latEl.value = Number.isFinite(w.lat) ? w.lat : "";
      lngEl.value = Number.isFinite(w.lng) ? w.lng : "";
      // zoom/select on map
      if (Number.isFinite(w.lat) && Number.isFinite(w.lng)) {
        focusOnLatLng(w.lat, w.lng);
      } else if (w.state) {
        selectStateByName(w.state);
      }
    }

    function clearForm() {
      editingId = null;
      form.reset();
    }

    form.addEventListener("submit", (e) => {
      e.preventDefault();
      const w = {
        id: editingId || uid(),
        title: titleEl.value.trim(),
        date: dateEl.value || undefined,
        state: stateEl.value.trim(),
        city: cityEl.value.trim() || undefined,
        desc: descEl.value.trim() || undefined,
        lat: latEl.value ? Number(latEl.value) : undefined,
        lng: lngEl.value ? Number(lngEl.value) : undefined
      };
      if (!w.title || !w.state) { alert("Title and State are required."); return; }

      const idx = WORKS.findIndex(x => x.id===w.id);
      if (idx>=0) WORKS[idx] = w; else WORKS.push(w);

      rebuildMarkers();
      save();
      clearForm();
    });

    resetBtn.addEventListener("click", clearForm);

    // ------------------------- Map click to add point -------------------------
    // If user clicks on empty map area (not state), create a point at that lat/lng.
    document.getElementById("chartdiv").addEventListener("click", (ev) => {
      // We rely on polygon click for state & centroid. For generic clicks, try to derive geo coords.
      // amCharts captures events internally; here we just leave form logic to polygon click.
    });

    // ------------------------- Boot -------------------------
    load();
    renderList();
    am5.ready(initMap);
  </script>


</body>
</html>
