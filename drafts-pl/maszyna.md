# Budowa

Każda maszyna składa się z:
* komory przetwarzającej - Processing Chamber - PC
* zera lub więcej buforów wejściowych na materiały składowe - Input Buffers - IB
* zera lub więcej buforów wyjściowych na materiały wynikowe - Output Buffers - OB

Każdy bufor jest dedykowany jednemu materiałowi. 

## Zasada działania

Podstawową jednostką pracy maszyny jest cykl.
Każdy cykl składa się z trzech faz:
* fazy wejściowej - Input Phase - IP
* fazy procesowania/produkcji - Processing Phase - PP
* fazy wyjściowej - Output Phase - OP


### Faza wejściowa

W tej fazie maszyna
1. wykonuje polecenia konfiguracyjne i modyfikuje swoje nastawy
1. sprawdza stan środowiska na zewnątrz (pogoda, temperatura etc.)
1. sprawdza swoje parametry
   - zasilanie - IO Power 
   - uruchomienie
   - uszkodzenia
1. pobiera z zewnątrz materiały wejściowe do buforów wejściowych. Ilość pobranych materiałów jest ograniczona:
   - pojemnością bufora
   - dostępnością
   - prędkością ładowania
   - nastawami dot. zapełnienia buforów

### Faza produkcji

W tej fazie maszyna:
1. sprawdza swoje parametry
   - zasilanie - Processing Power
   - uruchomienie
   - uszkodzenia
   - zadaną moc produkcki
1. sprawdza czy w IB znajduje się wymagana ilość materiałów. NIE są sprawdzane same materiały
1. przenosi porcje materiałów z IB do PC
1. jeżeli wszystkie warunki są spełnione, rozpoczyna proces produkcji
1. proces może zakończyć się w tym samym cyklu, w którym się rozpoczął lub trwać dowolną liczbę cykli
1. jeżeli proces nie zakończył się w poprzednim cyklu, nie rozpoczyna nowego tylko zwiększa postęp trwającego
1. jeżeli postęp procesu dotarł do końca, kończy proces
1. przenosi produkty procesu z PC do OB

#### zasady

* bez względu na etap procesu maszyna może pobierać materiały z IB i przenosić produkty do OB
* pewne sytuacje mogą spowodować Zakłócenie Procesu:
  - brak energii - IO Power
  - brak energii - Processing Power
  - brak materiałów w IB
  - zapełnione OB uniemożliwiające opróżnienie PC
* Zaklócenie procesu może spowodować:
  - wstrzymanie procesu
  - konieczność rozpoczęcia procesu od 0%
  - zniszczenie materiałów wejściowych





