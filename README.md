# panel-sprzedawcy-docs
Dokumentacja aplikacji — wersja 0.6.4  
Aktualizacja: 23 października 2026 r.

## Przeznaczenie

Panel Sprzedawcy jest niezależnym narzędziem działającym lokalnie na komputerze operatora. Służy do wewnętrznej obsługi własnej sprzedaży na kontach autoryzowanych przez OAuth. Nie jest oficjalnym produktem Allegro ani usługą oferowaną innym sprzedawcom.

## Funkcje

- Synchronizacja własnych ofert i zamówień oraz analiza sprzedaży.
- Odczyt rozliczeń, opłat reklamowych i zwrotów płatności, bez zarządzania kampaniami, zlecania płatności lub zwrotów.
- Audyt tytułów, opisów, zdjęć i parametrów ofert.
- Opcjonalne przygotowywanie propozycji tytułów z AI oraz ich zatwierdzanie i publikacja.
- Uzupełnianie parametrów na podstawie kategorii, katalogu i danych własnej oferty.
- Kalkulacja opłat sprzedażowych, szacunkowej marży i progu rentowności reklam.

Moduł Smart Repricer zawiera operacje reguł cenowych z limitami oraz przywracania ceny. Obecnie pozostaje wstrzymany.

## Dostęp do danych i operacje API

Każde konto jest autoryzowane oddzielnie. Aplikacja nie otrzymuje loginu ani hasła sprzedawcy.

Uprawnienia obejmują odczyt własnych ofert, zamówień, ustawień i profilu oraz kontrolowane zmiany ofert. Odczyt rozliczeń i zwrotów wymaga dodatkowych uprawnień. Aplikacja korzysta również z danych kategorii i katalogu produktów oraz oficjalnego kalkulatora opłat.

Zmiany tytułów i parametrów wymagają zatwierdzenia operatora. Przed zapisem ponownie sprawdzany jest stan oferty. Niepewny wynik zapisu jest weryfikowany odczytem, bez automatycznego ponawiania zmiany.

Synchronizacja odbywa się okresowo podczas działania aplikacji. Wywołania mają ograniczoną częstotliwość; odpowiedź HTTP 429 powoduje przerwę i odroczenie kolejnych zapytań.

## Przechowywanie danych i AI

Dane są przechowywane lokalnie i wykorzystywane do obsługi własnej sprzedaży. Obejmują również pełne odpowiedzi zamówień, które mogą zawierać dane kupujących. Dane pozostają do ich usunięcia przez operatora. Tokeny autoryzacyjne są przechowywane lokalnie w postaci zaszyfrowanej.

Opcjonalne generowanie tytułów korzysta z OpenAI. Do generatora przekazywane są dane produktów i własnych ofert, w tym parametry oraz dane sprzedaży, bez danych kupujących i tokenów autoryzacyjnych. Opcjonalny research WWW służy do sprawdzania nazewnictwa produktów, nie do ustalania oficjalnych wolumenów wyszukiwań.


