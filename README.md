<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prehistoric 5 – PokeMMO Gym Rerun Guide</title>
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            font-family: Arial, sans-serif;
            background-color: #0d0d0d;
            color: #e0e0e0;
            line-height: 1.6;
            padding: 20px;
        }

        .sticky-div {
            position: sticky;
            top: 0;
            background: #111;
            padding: 14px 20px;
            margin-bottom: 30px;
            border-bottom: 3px solid #c47c00;
            z-index: 100;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .sticky-div h2 {
            color: #c47c00;
            font-size: 1.4rem;
            margin: 0;
        }

        .sticky-div span {
            color: #888;
            font-size: 0.9rem;
        }

        h1 {
            color: #c47c00;
            font-size: 3rem;
            margin: 40px 0 16px;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-weight: 900;
            padding: 18px 0;
            border-top: 4px solid #c47c00;
            border-bottom: 3px solid #e8a000;
        }

        h2 {
            color: #e8a000;
            font-size: 1.6rem;
            margin: 30px 0 12px;
        }

        /* Pokémon name colours */
        .arch   { color: #40b8d8; font-weight: bold; }
        .blast  { color: #4da6ff; font-weight: bold; }
        .typh   { color: #ff6b35; font-weight: bold; }
        .tork   { color: #4caf50; font-weight: bold; }
        .heat   { color: #e8a000; font-weight: bold; }

        /* Team cards */
        .pokemon-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .pokemon-card {
            background: #1a1a1a;
            border: 2px solid #333;
            border-radius: 8px;
            padding: 14px;
            text-align: center;
            font-size: 0.88rem;
            line-height: 1.8;
        }

        .pokemon-card img {
            width: 90px;
            height: 90px;
            image-rendering: pixelated;
            margin-bottom: 6px;
            mix-blend-mode: lighten;
        }

        .pokemon-card .pname {
            font-size: 1rem;
            font-weight: bold;
            margin-bottom: 4px;
        }

        .pokemon-card .item-line {
            color: #e8a000;
            font-weight: bold;
            margin-bottom: 4px;
        }

        .pokemon-card .ivs {
            color: #aaa;
            font-size: 0.78rem;
        }

        /* Caution box */
        .caution-box {
            background: #1f1200;
            border: 2px solid #c47c00;
            border-radius: 8px;
            padding: 18px 20px;
            margin: 20px 0;
            color: #f0d080;
            font-size: 0.95rem;
            line-height: 1.8;
        }

        .caution-box b { color: #ffa500; }

        /* Earnings table */
        .earnings-table {
            width: 100%;
            border-collapse: collapse;
            margin: 16px 0;
            font-size: 0.85rem;
        }

        .earnings-table th {
            background: #222;
            color: #e8a000;
            padding: 8px 12px;
            border: 1px solid #333;
            text-align: left;
        }

        .earnings-table td {
            padding: 7px 12px;
            border: 1px solid #2a2a2a;
            background: #1a1a1a;
            color: #d0d0d0;
        }

        .earnings-table tr:nth-child(even) td { background: #222; color: #d0d0d0; }

        /* Region header */
        .region-header {
            color: #e8a000;
            font-size: 2.4rem;
            text-transform: uppercase;
            letter-spacing: 4px;
            padding: 24px 0;
            border-bottom: 3px solid #e8a000;
            margin: 50px 0 10px;
            text-align: center;
        }

        hr { border: none; border-top: 1px solid #2a2a2a; margin: 20px 0; }

        /* Gym card */
        .gym-card {
            background: #151515;
            border: 2px solid #2a2a2a;
            border-radius: 8px;
            padding: 18px 22px;
            margin: 18px 0;
            display: flex;
            gap: 20px;
            align-items: flex-start;
            box-shadow: 0 3px 12px rgba(0,0,0,0.5);
        }

        .gym-card img.map {
            width: 220px;
            height: auto;
            border-radius: 6px;
            border: 2px solid #c47c00;
            flex-shrink: 0;
        }

        .gym-card .gym-info { flex: 1; }
        .gym-card .gym-info u b { font-size: 1rem; color: #e0e0e0; }

        /* Fight section */
        .fight-section {
            background: #0d0d0d;
            border-left: 4px solid #c47c00;
            padding: 13px 16px;
            margin: 12px 0;
            border-radius: 4px;
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .fight-section img {
            width: 56px;
            height: 56px;
            image-rendering: pixelated;
            margin: 3px 4px;
            vertical-align: middle;
            mix-blend-mode: lighten;
        }

        .fight-section.alt {
            border-left-color: #ff6b35;
        }

        .fight-section.green {
            border-left-color: #4caf50;
        }

        /* Note */
        .note {
            background: #161616;
            border-left: 4px solid #e8a000;
            padding: 10px 14px;
            margin: 10px 0;
            border-radius: 4px;
            font-size: 0.88rem;
            color: #ccc;
            line-height: 1.6;
        }

        /* PC Reset banner */
        .pc-reset {
            background: #1a0d00;
            border: 2px solid #c47c00;
            border-radius: 6px;
            padding: 12px 18px;
            margin: 20px 0;
            color: #ffa500;
            font-weight: bold;
            font-size: 1rem;
            text-align: center;
            letter-spacing: 1px;
        }

        /* Heal banner */
        .heal-banner {
            background: #0d1f0d;
            color: #4caf50;
            padding: 12px;
            text-align: center;
            font-weight: bold;
            font-size: 1rem;
            margin: 18px 0;
            border-radius: 5px;
            border: 1px solid #4caf50;
        }

        /* Credits */
        .credits-section {
            background: #151515;
            border: 2px solid #333;
            border-radius: 8px;
            padding: 20px;
            margin: 40px 0 20px;
            font-size: 0.9rem;
            line-height: 1.8;
        }

        .credits-section .credits-title {
            color: #c47c00;
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 12px;
        }

        .credits-section .credit-item { margin: 8px 0; color: #bbb; }
        .credits-section .credit-item b { color: #e0e0e0; }

        /* Optional gym */
        .optional-gym { border-color: #5588cc !important; }

        /* Bonus section */
        .bonus-box {
            background: #0d1a22;
            border: 2px solid #5588cc;
            border-radius: 8px;
            padding: 16px 20px;
            margin: 20px 0;
            color: #aac8e8;
        }

        .bonus-box b { color: #88bbff; }

        @media (max-width: 768px) {
            .gym-card { flex-direction: column; }
            .gym-card img.map { width: 100%; }
            h1 { font-size: 2rem; }
            .region-header { font-size: 1.6rem; }
        }
    </style>
</head>
<body>

<div class="sticky-div">
    <h2>🦕 Prehistoric 5 – PokeMMO Gym Rerun</h2>
    <span>by JinxedBoon | 28-Gym Route Guide</span>
</div>

<!-- ═══════════════ TEAM ═══════════════ -->
<h2>Requirements</h2>
<p>✓ All 5 regions completed<br>
✓ 5 Pokémon team (Prehistoric lineup)<br>
✓ Recommended: Teleport Ocarina, Ice Heal (~1% chance), Paralyze Heal (optional), Potions (optional)</p>

<h2 style="margin-top:28px;">Team Roster</h2>
<div class="pokemon-container">

    <section class="pokemon-card">
        <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
        <div class="pname typh">Typhlosion</div>
        <div class="item-line">@ Choice Specs</div>
        Ability: Flash Fire (HA)<br>
        Modest / Mild / Rash<br>
        EVs: 252 SpA / 252 Spe<br>
        IVs: 31 SpA / 31 Spe<br>
        <div class="ivs">– Eruption (PP Max)<br>– Lava Plume<br>– Cut (if no Ocarina)</div>
    </section>

    <section class="pokemon-card">
        <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
        <div class="pname heat">Heatran</div>
        <div class="item-line">@ Choice Scarf</div>
        Ability: Flash Fire<br>
        Modest Nature<br>
        EVs: 252 SpA / 252 Spe<br>
        IVs: 31 SpA / 31 Spe / 31 HP / 31 Def / 31 SpD<br>
        <div class="note" style="margin-top:6px; font-size:0.78rem;">Min 15 Def IV — avoids Mach Punch from Breloom at Cianwood</div>
        <div class="ivs">– Eruption (PP Max)<br>– Lava Plume<br>– Earth Power</div>
    </section>

    <section class="pokemon-card">
        <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
        <div class="pname blast">Blastoise</div>
        <div class="item-line">@ Choice Scarf</div>
        Mild / Modest Nature<br>
        EVs: 252 SpA / 252 Spe<br>
        IVs: 31 SpA / 31 Spe<br>
        <span style="color:#aaa; font-size:0.78rem;">Optimal (Mild): 31 SpA / 31 Spe / 10-22 HP / 10-22 Def<br>
        Optimal (Modest): 31 SpA / 31 Spe / 0-9 HP / 0-9 Def</span><br>
        <div class="note" style="margin-top:6px; font-size:0.78rem;">Low Def discourages AI Wild Charge at Striaton Fire (Stoutland team)</div>
        <div class="ivs">– Water Spout (PP Max)</div>
    </section>

    <section class="pokemon-card">
        <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
        <div class="pname arch">Archeops</div>
        <div class="item-line">@ Wide Lens</div>
        Lonely / Adamant Nature<br>
        EVs: 252 Atk / 252 Spe<br>
        IVs: 31 Atk / 31 Spe<br>
        <span style="color:#aaa; font-size:0.78rem;">Optimal (Lonely): 31 Atk / 31 Spe / 0-4 HP / 0-4 Def<br>
        (Low HP/Def = OHKO from Torkoal's Explosion → better AI targeting)</span><br>
        <div class="ivs">– Rock Slide (PP Max)<br>– Tailwind<br>– Fly (if no Ocarina)</div>
    </section>

    <section class="pokemon-card">
        <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal"><br>
        <div class="pname tork">Torkoal</div>
        <div class="item-line">@ Choice Band</div>
        Ability: Drought<br>
        Brave / Adamant Nature<br>
        EVs: 252 Atk / 252 SpD<br>
        IVs: 31 Atk<br>
        <span style="color:#aaa; font-size:0.78rem;">Optimal: 31 Atk / 15+ Def / 20+ SpD / 15+ HP<br>
        High Def IVs: keeps Torkoal alive to Explode when flinched</span><br>
        <div class="ivs">– Explosion<br>– Helping Hand</div>
    </section>

</div>

<!-- ═══════════════ CAUTION ═══════════════ -->
<div class="caution-box">
    <u><b>⚠️ KEY NOTES BEFORE YOU START</b></u><br><br>
    • <b>Poképaste:</b> <a href="https://pokepast.es/61837e2f18d99656" style="color:#e8a000;">https://pokepast.es/61837e2f18d99656</a><br>
    • <b>Earnings Calculator:</b> <a href="https://c4vv.github.io/" style="color:#e8a000;">https://c4vv.github.io/</a><br>
    • <b>Trade Bonus:</b> Applied to any Pokémon not your OT — buy from GTL or trade from alts.<br>
    • <b>Olivine:</b> Cut from route — Shiny War 2025 update causes Full Restore spam on Blastoise.<br>
    • <b>Covert Cloak on Torkoal</b> (optional): Reduces flinch/para chance. Won't always KO Arch — if so, switch into Typhlosion and continue.<br>
    • Optimal HP and Def on <b>Archeops and Blastoise</b> ensure OHKO from Torkoal's Explosion. Improves consistency especially with double Rock Slide flinches.<br>
    • <b>High Def Torkoal</b> keeps it alive to Explode when flinched, encouraging AI to target its partner.
</div>

<!-- ═══════════════ EARNINGS ═══════════════ -->
<h2>Earnings (All 28 Gyms)</h2>
<table class="earnings-table">
    <tr>
        <th>Method</th>
        <th>No Donator</th>
        <th>Donator Status</th>
    </tr>
    <tr><td>No Charm</td><td>$250,120</td><td>$262,626</td></tr>
    <tr><td>Amulet Coin</td><td>$375,180</td><td>$393,939</td></tr>
    <tr><td>Riches 75%</td><td>$437,710</td><td>$459,596</td></tr>
    <tr><td>Riches 100%</td><td>$500,240</td><td>$525,252</td></tr>
    <tr><td>Reamplifier + Trade Bonus</td><td>~$80,000* EXP</td><td>~$92,000* EXP</td></tr>
    <tr><td>Reamplifier</td><td>~$76,000* EXP</td><td>~$85,000* EXP</td></tr>
    <tr><td>EXP Share + Trade Bonus</td><td>~$52,000* EXP</td><td>~$60,000* EXP</td></tr>
    <tr><td>EXP Share</td><td>~$47,000* EXP</td><td>~$55,000* EXP</td></tr>
</table>
<div class="note">*Compared to average price of EXP service at $0.2/exp. Earnings do NOT include the price of Amulet Coin or Riches Charm.</div>

<!-- ═══════════════ HOENN ═══════════════ -->
<div class="region-header">HOENN</div>
<hr>

<h1>1. Lavaridge Town <span style="font-size:1rem; color:#aaa;">(Fire)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/9/93/Hoenn_Lavaridge_Town_Map.png" alt="Lavaridge">
    <div class="gym-info"><u><b>Gym Leader: Flannery</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="arch">Rock Slide</span> + <span class="blast">Water Spout</span>
</div>

<h1>2. Mauville City <span style="font-size:1rem; color:#aaa;">(Electric)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/a/a1/Hoenn_Mauville_City_Map.png" alt="Mauville">
    <div class="gym-info"><u><b>Gym Leader: Wattson</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="heat">Heatran</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="arch">Rock Slide</span> + <span class="heat">Eruption</span>
</div>

<h1>3. Fortree City <span style="font-size:1rem; color:#aaa;">(Flying)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/f/f5/Hoenn_Fortree_City_Map.png" alt="Fortree">
    <div class="gym-info"><u><b>Gym Leader: Winona</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="arch">Rock Slide</span> + <span class="typh">Eruption / Lava Plume</span>
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Rain:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/pelipper.gif" alt="Rain setter"><br>
    Swap <span class="arch">Archeops</span> → <span class="tork">Torkoal (Helping Hand)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
</div>

<div class="note">• Chance of Arch going down — replace Heatran's Plume, continue without PC Heal.<br>
• If Torkoal paralyzed from Thunder: use Paralyze Heal after gym, or PC Heal.</div>

<h1>4. Dewford Town <span style="font-size:1rem; color:#aaa;">(Fighting)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/d/d3/Hoenn_Dewford_Town_Map.png" alt="Dewford">
    <div class="gym-info"><u><b>Gym Leader: Brawly</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="heat">Eruption / Lava Plume</span> + <span class="blast">Water Spout</span>
</div>

<h1>5. Petalburg City <span style="font-size:1rem; color:#aaa;">(Normal)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/4/4b/Hoenn_Petalburg_City_Map.png" alt="Petalburg">
    <div class="gym-info"><u><b>Gym Leader: Norman</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="tork">Explosion</span> + <span class="blast">Water Spout</span><br>
    <b>Send in:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<div class="pc-reset">🔄 PC RESET — (~49 mins on charm)</div>

<!-- ═══════════════ UNOVA ═══════════════ -->
<div class="region-header">UNOVA</div>
<hr>

<h1>6. Castelia City <span style="font-size:1rem; color:#aaa;">(Bug)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/9/96/Unova_Castelia_City_Map.png" alt="Castelia">
    <div class="gym-info"><u><b>Gym Leader: Burgh</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="blast">Blastoise</span> + <span class="heat">Heatran</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="blast">Water Spout</span> + <span class="heat">Eruption / Lava Plume</span>
</div>
<div class="note">If hurt from Accelgor team, heal here.</div>

<h1>7. Nimbasa City <span style="font-size:1rem; color:#aaa;">(Electric)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/1/1b/Unova_Nimbasa_City_Map.png" alt="Nimbasa">
    <div class="gym-info"><u><b>Gym Leader: Elesa</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="blast">Blastoise</span> + <span class="heat">Heatran</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="blast">Water Spout</span> + <span class="heat">Eruption / Lava Plume</span>
</div>
<div class="note">Chance at Heatran getting hurt — continue if so.</div>

<h1>8. Driftveil City <span style="font-size:1rem; color:#aaa;">(Ground)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/2/2f/Unova_Driftveil_City_Map.png" alt="Driftveil">
    <div class="gym-info"><u><b>Gym Leader: Clay</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="arch">Archeops</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="tork">Explosion</span> + <span class="arch">Rock Slide / Tailwind</span><br>
    <b>Send in:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<div class="pc-reset">🔄 PC RESET — (~42 mins on charm)</div>

<h2 style="margin-top:30px; letter-spacing:2px;">STRIATON CITY</h2>

<h1>9. Striaton – Fire <span style="font-size:1rem; color:#aaa;">(Chili)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/d/d7/Unova_Striaton_City_Map.png" alt="Striaton">
    <div class="gym-info"><u><b>Gym Leader: Chili</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="blast">Blastoise</span> + <span class="arch">Archeops</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="blast">Water Spout</span> + <span class="arch">Rock Slide</span>
</div>
<div class="note">If Blastoise is hurt from this gym, PC Reset before Striaton Grass.</div>

<h1>10. Striaton – Grass <span style="font-size:1rem; color:#aaa;">(Cilan)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/d/d7/Unova_Striaton_City_Map.png" alt="Striaton">
    <div class="gym-info"><u><b>Gym Leader: Cilan</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="typh">Typhlosion (Lava Plume)</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="heat">Lava Plume</span> + <span class="typh">Lava Plume</span>
</div>

<h1>11. Striaton – Water <span style="font-size:1rem; color:#aaa;">(Cress)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/d/d7/Unova_Striaton_City_Map.png" alt="Striaton">
    <div class="gym-info"><u><b>Gym Leader: Cress</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="tork">Torkoal (Helping Hand)</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="tork">Helping Hand</span> + <span class="typh">Eruption / Lava Plume</span>
</div>
<div class="note">If Blastoise is hurt from the fire leader, PC Reset.</div>

<h1>12. Mistralton City <span style="font-size:1rem; color:#aaa;">(Flying)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/6/62/Unova_Mistralton_City_Map.png" alt="Mistralton">
    <div class="gym-info"><u><b>Gym Leader: Skyla</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="blast">Blastoise</span> + <span class="heat">Heatran</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="blast">Water Spout</span> + <span class="heat">Lava Plume</span>
</div>
<div class="note">Chance of getting eject-buttoned — attack through it. If <b>Heatran or Typh dies</b>, PC Reset then continue and skip the next PC Reset.</div>

<h1>13. Icirrus City <span style="font-size:1rem; color:#aaa;">(Ice)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/0/04/Unova_Icirrus_City_Map.png" alt="Icirrus">
    <div class="gym-info"><u><b>Gym Leader: Brycen</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="typh">Typhlosion (Lava Plume)</span> + <span class="heat">Heatran (Lava Plume)</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="typh">Lava Plume</span> + <span class="heat">Lava Plume</span>
</div>
<div class="note">⚠️ If frozen from Blizzard, use Ice Heal on the frozen one's turn.</div>

<div class="pc-reset">🔄 PC RESET — (~32 mins on charm)</div>

<h1>14. Opelucid City <span style="font-size:1rem; color:#aaa;">(Dragon)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/3/3d/Unova_Opelucid_City_Map.png" alt="Opelucid">
    <div class="gym-info"><u><b>Gym Leader: Iris / Drayden</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="arch">Archeops (Tailwind)</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="arch">Tailwind</span> + <span class="tork">Explosion</span><br>
    <b>Send in:</b> <span class="typh">Typhlosion</span> + <span class="heat">Heatran (Lava Plume)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
</div>

<!-- ═══════════════ JOHTO ═══════════════ -->
<div class="region-header">JOHTO</div>
<hr>

<h1>15. Violet City <span style="font-size:1rem; color:#aaa;">(Flying)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/2/2c/Johto_Violet_City_Map.png" alt="Violet">
    <div class="gym-info"><u><b>Gym Leader: Falkner</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="heat">Lava Plume</span> + <span class="blast">Water Spout</span>
</div>
<div class="note">Chance at Heatran and Blast getting hurt — continue if so.</div>

<h1>16. Mahogany Town <span style="font-size:1rem; color:#aaa;">(Ice)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/4/46/Johto_Mahogany_Town_Map.png" alt="Mahogany">
    <div class="gym-info"><u><b>Gym Leader: Pryce</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="heat">Lava Plume</span> + <span class="typh">Eruption / Lava Plume</span>
</div>
<div class="note">⚠️ If frozen from Blizzard, use Ice Heal on the frozen one's turn.</div>

<div class="pc-reset">🔄 PC RESET — (~26 mins on charm)</div>

<h1>17. Goldenrod City <span style="font-size:1rem; color:#aaa;">(Normal)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/e/ec/Johto_Goldenrod_City_Map.png" alt="Goldenrod">
    <div class="gym-info"><u><b>Gym Leader: Whitney</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="heat">Eruption / Lava Plume</span> + <span class="blast">Water Spout</span>
</div>
<div class="note">⭐ Put <b>Heatran on the LEFT side</b> (above Blastoise in team order) — Ditto changed transform target after Halloween 2025 update.<br>Chance at Heatran getting hurt — continue if so.</div>

<h1>18. Azalea Town <span style="font-size:1rem; color:#aaa;">(Bug)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/b/b0/Johto_Azalea_Town_Map.png" alt="Azalea">
    <div class="gym-info"><u><b>Gym Leader: Bugsy</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="typh">Typhlosion (Lava Plume)</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="heat">Lava Plume</span> + <span class="typh">Lava Plume</span>
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Sand appears:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/hippowdon.gif" alt="Sand setter"><br>
    Swap <span class="typh">Typhlosion</span> → <span class="tork">Torkoal (Helping Hand)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
</div>
<div class="note">Chance at Heatran getting hurt — continue if so.</div>

<h1 style="color:#5588cc;">[Optional] 19. Olivine City <span style="font-size:1rem; color:#aaa;">(Steel)</span></h1>
<div class="gym-card optional-gym">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/6/65/Johto_Olivine_City_Map.png" alt="Olivine">
    <div class="gym-info"><u><b>Gym Leader: Jasmine</b></u><br>
    <span style="color:#f06030; font-size:0.85rem;">⚠️ Cut from main route — Shiny War 2025 update causes Full Restore spam on Blastoise</span></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Blastoise comes out:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    Swap <span class="heat">Heatran</span> → <span class="tork">Torkoal (Helping Hand)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Rapidash comes out:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/rapidash.gif" alt="Rapidash"><br>
    Swap <span class="heat">Heatran</span> → <span class="tork">Torkoal (Explosion)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal"><br>
    <span style="color:#ccc; font-size:0.88rem;">If you explode here, heal before the next gym or skip it.</span>
</div>

<h1>20. Cianwood City <span style="font-size:1rem; color:#aaa;">(Fighting)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/d/d8/Johto_Cianwood_City_Map.png" alt="Cianwood">
    <div class="gym-info"><u><b>Gym Leader: Chuck</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="tork">Explosion</span> + <span class="blast">Water Spout</span><br>
    <b>Send in:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>
<div class="note">T1 Rock Slide flinches can be annoying here. ⚠️ Heatran needs min 15 Def IV to avoid taking Mach Punch from Breloom.</div>

<div class="pc-reset">🔄 PC RESET — (~18 mins on charm)</div>

<!-- ═══════════════ SINNOH ═══════════════ -->
<div class="region-header">SINNOH</div>
<hr>

<h1>21. Veilstone City <span style="font-size:1rem; color:#aaa;">(Fighting)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/3/32/Sinnoh_Veilstone_City_Map.png" alt="Veilstone">
    <div class="gym-info"><u><b>Gym Leader: Maylene</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="arch">Rock Slide</span> + <span class="typh">Eruption / Lava Plume</span>
</div>
<div class="note">Chance at Arch getting hurt — continue if so, or heal if KO'd.</div>

<h1>22. Eterna City <span style="font-size:1rem; color:#aaa;">(Grass)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/0/0b/Sinnoh_Eterna_City_Map.png" alt="Eterna">
    <div class="gym-info"><u><b>Gym Leader: Gardenia</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="heat">Heatran</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <span class="arch">Rock Slide</span> + <span class="heat">Lava Plume</span>
</div>
<div class="note">If Arch is less than 50% HP, heal after. Replace Typh if needed.</div>

<h1>23. Sunyshore City <span style="font-size:1rem; color:#aaa;">(Electric)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/5/5a/Sinnoh_Sunyshore_City_Map.png" alt="Sunyshore">
    <div class="gym-info"><u><b>Gym Leader: Volkner</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="arch">Archeops</span> + <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise"><br>
    <span class="arch">Rock Slide</span> + <span class="blast">Water Spout</span>
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Lanturn leads:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/lanturn.gif" alt="Lanturn"><br>
    Swap <span class="blast">Blastoise</span> → <span class="tork">Torkoal (Helping Hand)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal"><br>
    Replace Typh when possible.<br>
    <b>Explosion on Torkoal when Galvantula comes out!</b>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/galvantula.gif" alt="Galvantula"><br>
    <span style="color:#ccc; font-size:0.88rem;">Skip the next gym if this happens, or heal and do it if you have time.</span>
</div>

<h1>24. Pastoria City <span style="font-size:1rem; color:#aaa;">(Water)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/b/ba/Sinnoh_Pastoria_City_Map.png" alt="Pastoria">
    <div class="gym-info"><u><b>Gym Leader: Crasher Wake</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="arch">Archeops</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="tork">Explosion</span> + <span class="arch">Rock Slide / Tailwind</span><br>
    <b>Send in:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<!-- ═══════════════ KANTO ═══════════════ -->
<div class="region-header">KANTO</div>
<hr>

<div class="pc-reset">🔄 PC RESET — (~10 mins on charm)</div>

<h1>25. Vermilion City <span style="font-size:1rem; color:#aaa;">(Electric)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/5/54/Kanto_Vermilion_City_Map.png" alt="Vermilion">
    <div class="gym-info"><u><b>Gym Leader: Lt. Surge</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="heat">Lava Plume</span> + <span class="typh">Eruption / Lava Plume</span>
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Rain lead:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/politoed.gif" alt="Politoed"><br>
    Swap <span class="heat">Heatran</span> → <span class="tork">Torkoal (Helping Hand)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Electrode lead:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/electrode.gif" alt="Electrode"><br>
    <span class="heat">Heatran</span> + <span class="typh">Typhlosion (Lava Plume)</span>
</div>

<h1>26. Pewter City <span style="font-size:1rem; color:#aaa;">(Rock)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/8/8e/Kanto_Pewter_City_Map.png" alt="Pewter">
    <div class="gym-info"><u><b>Gym Leader: Brock</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="blast">Blastoise</span> + <span class="arch">Archeops</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/blastoise.gif" alt="Blastoise">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="blast">Water Spout</span> + <span class="arch">Rock Slide</span>
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Arch goes down:</b></u><br>
    Replace with <span class="heat">Heatran</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
</div>

<div class="fight-section alt">
    <u style="color:#ff6b35;"><b>If Toxicroak:</b></u><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/toxicroak.gif" alt="Toxicroak"><br>
    <b>T1:</b> Swap <span class="blast">Blastoise</span> → <span class="heat">Heatran (Lava Plume)</span> — Arch may die<br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran"><br>
    <b>T2:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion (Lava Plume)</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<h1>27. Cerulean City <span style="font-size:1rem; color:#aaa;">(Water)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/2/29/Kanto_Cerulean_City_Map.png" alt="Cerulean">
    <div class="gym-info"><u><b>Gym Leader: Misty</b></u></div>
</div>

<div class="fight-section">
    <b>T1 Lead:</b> <span class="tork">Torkoal</span> + <span class="arch">Archeops</span> or <span class="blast">Blastoise</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/torkoal.gif" alt="Torkoal">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/archeops.gif" alt="Archeops"><br>
    <span class="tork">Explosion</span> + <span class="arch">Rock Slide / Tailwind</span><br>
    <b>Send in:</b> <span class="heat">Heatran (Lava Plume)</span> + <span class="typh">Typhlosion</span>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion">
</div>

<h1>28. Celadon City <span style="font-size:1rem; color:#aaa;">(Grass)</span></h1>
<div class="gym-card">
    <img class="map" src="https://archives.bulbagarden.net/media/upload/b/bd/Kanto_Celadon_City_Map.png" alt="Celadon">
    <div class="gym-info"><u><b>Gym Leader: Erika</b></u></div>
</div>

<div class="fight-section">
    <b>Lead:</b> <span class="heat">Heatran</span> + <span class="typh">Typhlosion (Lava Plume)</span><br>
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/heatran.gif" alt="Heatran">
    <img src="http://play.pokemonshowdown.com/sprites/gen5ani/typhlosion.gif" alt="Typhlosion"><br>
    <span class="heat">Lava Plume</span> + <span class="typh">Lava Plume</span>
</div>

<!-- ═══════════════ BONUS ═══════════════ -->
<div class="bonus-box" style="margin-top:40px;">
    <b>⭐ BONUS (If time permits):</b><br>
    Go to Sinnoh and fight <b>PI Carlos</b> trainer — earns <b>$9,000 on coin</b>.<br>
    Location: South of Veilstone City (Route 214 area — see Sinnoh map X marker).
</div>

<!-- ═══════════════ CREDITS ═══════════════ -->
<div class="credits-section">
    <div class="credits-title">🦕 Credits & Attribution</div>
    <div class="credit-item"><b>Route Creator:</b> JinxedBoon — Original Prehistoric 5 gym rerun strategy.</div>
    <div class="credit-item"><b>Poképaste:</b> <a href="https://pokepast.es/61837e2f18d99656" style="color:#e8a000;">https://pokepast.es/61837e2f18d99656</a></div>
    <div class="credit-item"><b>Earnings Calculator:</b> <a href="https://c4vv.github.io/" style="color:#e8a000;">https://c4vv.github.io/</a></div>
    <div class="credit-item"><b>Video Guide:</b> <a href="https://www.youtube.com" style="color:#e8a000;">The BEST New Gym Rerun Strat in PokeMMO!</a></div>
    <div class="credit-item" style="margin-top:14px; color:#666; font-size:0.82rem;">
        All Pokémon sprites from play.pokemonshowdown.com. Map images from Bulbagarden Archives. Community resource for PokeMMO players.
    </div>
</div>

<script>
// Fallback for any map images that fail to load
document.querySelectorAll('img.map').forEach(img => {
    img.onerror = function() {
        this.onerror = null;
        this.style.display = 'none';
        const ph = document.createElement('div');
        ph.style.cssText = 'width:220px;height:120px;background:#1a1a1a;border:2px solid #c47c00;border-radius:6px;display:flex;align-items:center;justify-content:center;color:#555;font-size:0.8rem;flex-shrink:0;';
        ph.textContent = '📍 ' + this.alt + ' Map';
        this.parentNode.insertBefore(ph, this);
    };
});
</script>
</body>
</html>
