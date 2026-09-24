# Energiewacht – journey online

Wat in `main` staat, staat live op https://energiewacht.rbnlrns.nl.
Elke push naar `main` zet `index.html`, `robots.txt` en `.htaccess` via SFTP op de server.

De pagina is niet vindbaar in zoekmachines (noindex + robots.txt). Wie de link heeft, kan hem wel openen.

## Eenmalig instellen

1. Maak een lege repo op GitHub, bijvoorbeeld `energiewacht-journey` (privé).
2. Zet deze map erin en push naar `main`.
3. Ga naar Settings → Secrets and variables → Actions en voeg toe:

| Geheim | Waarde |
|---|---|
| `SFTP_HOST` | `herbp0.ssh.transip.me` |
| `SFTP_USER` | je TransIP-gebruikersnaam |
| `SFTP_REMOTE_DIR` | de map van het subdomein op de server |
| `SFTP_PASSWORD` of `SFTP_KEY` | één van beide; een sleutel is veiliger |
| `SFTP_KNOWN_HOSTS` | aanbevolen: uitvoer van `ssh-keyscan -p 22 herbp0.ssh.transip.me` |

Zet wachtwoorden en sleutels nooit in de repo of in een chat.

4. Ga naar Actions → "Frontend uitrollen" → Run workflow, of push een wijziging.
5. Open https://energiewacht.rbnlrns.nl en kijk of de journey map er staat.

## Bijwerken

Pas `index.html` aan, commit en push. Binnen een minuut staat het live.
