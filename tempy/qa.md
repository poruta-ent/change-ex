## TESTS

### GENERAL CONSIDERATIONS
#### Po co?
* ustal co chcesz osiągnąć
* zastanów się jaką wartość przyniesie świat idealny:
  * pełne pokrycie automatycznymi testami regresji
  * wykonanie automatów trwa kilka minut
  * możliwość uruchamiania na środowisku developerskim
  * powiązanie z CI

#### Korzyści
* minimalizowanie kosztu stale powiększającego się zestawu testów regresji

#### Problemy do rozważenia
* Dokładność - konieczność daleko większej dokładności/ustalenia szczegółów niż w przypadku manualnych
* Utrzymanie - wrażliwośc na zmianę
* Obsługa niepowodzeń - identyfikowanie kiedy rzeczywiście mamy do czynienia z błędęm, a nie np.uzasadnioną zmianą, planowym przypadkiem (np. wyświetlanie komunikatu o 16:00), zmianą hasła
* Długość przypadku testowego
* Zbieranie dowodów, żeby móc zdiagnozować

___
### ZARZĄDZANIE
#### Kto powinien pisać:
* manualni (+ew programisci), ale:
  * nie będą w stanie ogarnąć frameworku testowego,
  * musza mieć dedykowany konkretny czas
* dedykowany zespół, ale:
  * brak kontekstu biznesowego
  * niewystarczająca współpraca z zespołami dev w zakresie pisania kodu pod testy, czy śledzenia zmianą
* dedykowany dev w zespole, ale:
  * alignment z innymi zespołami
  * ktoś zbierający i dbający o standardy	

#### Mapa drogowa:
* Zacznij od podstawowych testów poprawności - do zastosowania dla każdej PR
  * testy progresji - automatyzuj bieżący development
  * testy regresji- ustal priorytety

#### Co robić z czerwnonymi:
* Zostawiamy tak jak jest do czasu poprawienia błędu, ale:
  * i tak trzeba sprawdzać codziennie bo czerwony noże wynikać z czegoś innego
  * czerwony może być spowodowany pobocznym problemem, a główny cel testu nie jest nawet sprawdzany (a jak poboczny jest naprawiony to test wali się na nastepnym kroku)
  * przyzwyczajenie do czerwonego
* Wykluczanie czerwonych, ale:
  * nie wiemy czy się poprawił inna poprawką
  * nie wiemy czy się bardziej nie popsuł (albo nie był bardziej popsuty)
* Obejścia w teście, ale:
  * dobre: jak pierdoła psuje wiele testów
  * dobre: pozwala przejść do końca i sprawdzić cel
  * złe: utrzymania, pamiętanie, przywracanie
* Wszystkie błędy z testów traktowane jako krytyczne - oszczędzamy czas, działamy na świeżo i elastycznie (można wycofać commit)
* dobre "garażowe" - zastosuj odpowiednie komunikaty błędów i regex - a w raportach odróżniaj na tej podstawie znane od regresji (PILNUJ tylko że to stostuje się do TEGO SAMEGO miejsca wywalenia)

#### Pułapki pełnego pokrycia
* czy w kodzie patrzymy na ścieżki alternatywne
* czy % pokrytych testów odpowiada % całości
* czy fuknkcje w tfs/jira są aktualne

#### Efektywność automatów
* regularne uruchamianie
* bieżąca obsługa błędów