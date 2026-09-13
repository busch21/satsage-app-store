# SatSage Umbrel Community App Store

Umbrel Community App Store für **[SatSage](https://github.com/Juniormind1/SatSage)** — *know your sats*.

SatSage analysiert XPUB-Wallets und rekonstruiert, wann Sats sie erreicht oder verlassen haben — die On-Chain-Haltedauer für Steuer und Überblick.

## Hinzufügen

In umbrelOS: **App Store → Community App Stores → Add**, dann diese URL:

```
https://github.com/busch21/satsage-app-store
```

Danach erscheint SatSage im Store und lässt sich wie jede andere App installieren.

## Voraussetzung

**Electrs** muss auf dem Umbrel installiert sein — SatSage nutzt es als Datenquelle und deklariert es als Dependency. Bitcoin Core kommt transitiv mit. Ist die **mempool**-App installiert, holt SatSage Kurse und Block-Links darüber statt aus öffentlichen Quellen.

## Anmeldung

Nach dem Umbrel-Login verlangt SatSage ein eigenes Passwort. Umbrel zeigt es in den App-Details an.

Das ist Absicht: der `app_proxy` schützt nur den Weg über den Browser, während jeder andere Container im Docker-Netz den Dienst direkt erreichen könnte — und dort liegen die XPUBs.

## Hinweis zur App-Identität

umbrelOS präfixt App-IDs aus Community Stores mit der Store-ID, die App heißt hier also `juniormind-satsage`. Erscheint SatSage später im offiziellen Umbrel App Store, ist das dort eine **andere** App-Identität mit eigenem Datenverzeichnis — Wallets und Caches wandern **nicht** automatisch mit.

## Herkunft

Die Paketdateien werden aus [`packaging/umbrel/`](https://github.com/Juniormind1/SatSage/tree/main/packaging/umbrel) im SatSage-Repo abgeleitet (`scripts/build_umbrel_community_store`). Änderungen gehören dorthin, nicht in dieses Repo.

## Lizenz

SatSage steht unter der MIT-Lizenz. Community App Stores werden nicht vom offiziellen Umbrel-Team geprüft.
