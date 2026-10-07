# Fellogg

En rad per fel. Skriv medan du minns hur du gjorde.

1. Fel nr #1 . I  actions stod det you have an error in your workflow file 
det var fel på indenteringen i uv sync --frozen . Felet låg lokalt i ci.yml filen
Hur löste du det ? : Genom att ta bort det extra mellanslag som fanns , jag räknade de övrigas mellanslag innan. 

2. Fel nr #2. error: Unable to find lockfile at `uv.lock´, but --frozen was provided....
Error: Process completed with exit code 1.
Felet hittade jag först i actions sedan provade jag att köra lokalt med uv sync frozen och det fungerade inte hellet och uv  försökte skapa venv men stoppade då den insåg att det inte fanns uv.lock .
  Hur löste du det ? : genom att köra uv kommando: uv lock , en lock fil skapades sedan körde jag 
  uv sync --frozen och det fungerade lokalt 
3. Fel nr #3 I github actions stod felet att F401 [*] `os` imported but unused
 --> src/miniforecast/baseline.py:3:8, sedan körde jag lokalt,. Jag öppnade filen baseline.py och
 såg att det fanns en import os, koden verkar inte ha behov av import os 
 Hur löste du det ? : Jag tog bort import os och provade köra lokalt först och fick "all checks passed" nästa steg att pusha och se vad nästa fel blir 
 4. fel nr 4# formatfel unformatted: File would be reformatted. 
 Hur löste du det: jag provade att köra uv run ruff format för att rätta formatering automatiskt 
 sedan uv run ruff format --check src test för kontroll 
5. fel nr#5 Import error /Modulenotfounderror " no module named "numpy", samma fel lokalt när jag kör uv run pytest, tittar man i pyproject är dependencies tom . hur löste du det : uv add numpy 
