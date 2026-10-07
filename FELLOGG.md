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