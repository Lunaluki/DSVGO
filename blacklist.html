<?php
// Datei, in der die Nummern gespeichert werden
$file = 'meldungen.json';

// Wenn das Formular abgeschickt wurde
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $fan = trim($_POST['fanName'] ?? '');
    $number = trim($_POST['badNumber'] ?? '');
    $reason = trim($_POST['reason'] ?? '');

    if (!empty($fan) && !empty($number)) {
        // Bestehende Meldungen laden
        $meldungen = [];
        if (file_exists($file)) {
            $meldungen = json_decode(file_get_contents($file), true) ?? [];
        }

        // Neue Meldung vorne hinzufügen
        array_unshift($meldungen, [
            'fan' => htmlspecialchars($fan),
            'number' => htmlspecialchars($number),
            'reason' => htmlspecialchars($reason ? $reason : 'Kein Grund angegeben'),
            'date' => date('d.m.Y H:i')
        ]);

        // In die Datei speichern
        file_put_contents($file, json_encode($meldungen, JSON_PRETTY_PRINT));
        
        // Seite neu laden, damit der Eintrag sofort in der Tabelle steht
        header("Location: blacklist.php");
        exit;
    }
}

// Meldungen für die Tabelle laden
$meldungen = [];
if (file_exists($file)) {
    $meldungen = json_decode(file_get_contents($file), true) ?? [];
}
?>
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>AGA – Luna Blacklist & Meldeportal</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <style>
        :root {
            --pink-main: #ff4fae;
            --pink-dark: #ff2f9c;
            --pink-light: #ff9dd6;
            --pink-glow: #ff007f;
            --pink-neon: #ff00ff;
        }

        body {
            background: #110515;
            color: white;
            font-family: "Inter", Arial, sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.8;
        }

        header {
            background: linear-gradient(135deg, #ff2f9c, #aa0055);
            padding: 3rem 2rem;
            text-align: center;
            border-bottom: 2px solid var(--pink-light);
            box-shadow: 0 0 30px rgba(255, 47, 156, 0.4);
        }

        header h1 {
            margin: 0;
            font-size: 2.4rem;
            color: white;
            font-weight: 700;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
        }

        header p {
            margin-top: 1rem;
            font-size: 1.1rem;
            color: #ffe6f5;
        }

        .nav-btn {
            display: inline-block;
            margin: 0.5rem;
            padding: 0.7rem 1.4rem;
            background: rgba(255, 255, 255, 0.15);
            color: #ffffff;
            border: 1px solid rgba(255, 255, 255, 0.4);
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s;
            backdrop-filter: blur(5px);
        }

        .nav-btn:hover {
            background: #ffffff;
            color: var(--pink-dark);
            box-shadow: 0 0 15px #ffffff;
        }

        main {
            max-width: 900px;
            margin: 0 auto;
            padding: 2rem;
        }

        h2 {
            margin-top: 2.5rem;
            font-size: 1.7rem;
            color: white;
            border-left: 4px solid var(--pink-light);
            padding-left: 0.7rem;
            font-weight: 600;
            text-shadow: 0 0 10px var(--pink-neon);
        }

        .edge-box {
            position: relative;
            border-radius: 16px;
            padding: 2px;
            background: transparent;
            overflow: hidden;
            margin-top: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }

        .edge-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(
                transparent 0deg,
                transparent 140deg,
                var(--pink-neon) 180deg,
                #ffffff 200deg,
                var(--pink-glow) 220deg,
                transparent 260deg
            );
            animation: rotateEdge 3.5s linear infinite;
        }

        @keyframes rotateEdge {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .edge-box-content {
            position: relative;
            z-index: 1;
            background: #1e0924;
            border-radius: 14px;
            padding: 1.8rem;
        }

        .form-group {
            margin-bottom: 1.2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.4rem;
            font-weight: bold;
            color: var(--pink-light);
        }

        .form-group input, .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border-radius: 8px;
            border: 1px solid rgba(255, 157, 214, 0.4);
            background: rgba(255, 255, 255, 0.05);
            color: white;
            font-size: 1rem;
            box-sizing: border-box;
        }

        .form-group input:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--pink-neon);
            box-shadow: 0 0 10px var(--pink-neon);
        }

        .btn-action {
            display: inline-block;
            width: 100%;
            padding: 0.9rem;
            background: linear-gradient(135deg, var(--pink-main), var(--pink-dark));
            color: #ffffff;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.5);
            transition: 0.2s;
        }

        .btn-action:hover {
            box-shadow: 0 0 25px var(--pink-neon);
            transform: translateY(-2px);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1.5rem;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 8px;
            overflow: hidden;
        }

        th, td {
            padding: 0.9rem;
            text-align: left;
            border-bottom: 1px solid rgba(255, 157, 214, 0.2);
            font-size: 0.95rem;
        }

        th {
            background: rgba(255, 47, 156, 0.25);
            color: var(--pink-light);
        }

        .badge-reported {
            background: #ff2f9c;
            color: white;
            padding: 3px 8px;
            border-radius: 6px;
            font-size: 0.85rem;
            font-weight: bold;
        }

        footer {
            margin-top: 4rem;
            padding: 2rem;
            text-align: center;
            border-top: 1px solid var(--pink-dark);
            color: #ffe6f5;
            font-size: 0.95rem;
        }
    </style>
</head>
<body>

<header>
    <h1>Luna Blacklist & Meldeportal</h1>
    <p>Schütze die Community vor Spam, Scannern und Hatern.</p>
    <a class="nav-btn" href="index.html">Zur Hauptseite</a>
</header>

<main>

    <!-- NUMMER MELDEN FORMULAR -->
    <section>
        <h2>1. Nummer an das Luna Team melden</h2>
        <div class="edge-box">
            <div class="edge-box-content">
                <form method="POST" action="">
                    <div class="form-group">
                        <label for="fanName">Dein Luna Fan-Name:</label>
                        <input type="text" id="fanName" name="fanName" placeholder="z. B. LunaFan_Alex" required>
                    </div>

                    <div class="form-group">
                        <label for="badNumber">Telefonnummer (Format: 4917666724481):</label>
                        <input type="text" id="badNumber" name="badNumber" placeholder="4917666724481" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="reason">Grund der Meldung:</label>
                        <textarea id="reason" name="reason" rows="3" placeholder="Z. B. Spam im Chat / Scamming..."></textarea>
                    </div>

                    <button type="submit" class="btn-action">Nummer an Luna Team melden</button>
                </form>
            </div>
        </div>
    </section>

    <!-- ÖFFENTLICHE BLACKLIST -->
    <section>
        <h2>2. Aktuelle Blacklist (Öffentlich)</h2>
        <div class="edge-box">
            <div class="edge-box-content">
                <p>Hier siehst du alle gemeldeten Nummern, welches Luna-Fan-Konto sie gemeldet hat und den Status.</p>
                
                <div style="overflow-x: auto;">
                    <table>
                        <thead>
                            <tr>
                                <th>Luna Fan</th>
                                <th>Gemeldete Nummer</th>
                                <th>Grund</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
                            <?php if (empty($meldungen)): ?>
                                <tr>
                                    <td colspan="4" style="text-align:center; color:var(--pink-light);">Bisher wurden keine Nummern gemeldet.</td>
                                </tr>
                            <?php else: ?>
                                <?php foreach ($meldungen as $m): ?>
                                    <tr>
                                        <td><strong><?php echo $m['fan']; ?></strong></td>
                                        <td><code><?php echo $m['number']; ?></code></td>
                                        <td><?php echo $m['reason']; ?></td>
                                        <td><span class="badge-reported">Gemeldet</span></td>
                                    </tr>
                                <?php endforeach; ?>
                            <?php endif; ?>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>☆『Luna Team』☆ – Schutzsystem für die AGA Community</p>
    </footer>

</main>

</body>
</html>
