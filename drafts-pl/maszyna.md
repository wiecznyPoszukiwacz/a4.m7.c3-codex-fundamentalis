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





