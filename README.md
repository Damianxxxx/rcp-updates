# Punktacja LSO - Rozszerzona Dokumentacja Uzytkownika

Wersja dokumentacji: 2026-03-01

## Spis tresci
1. Wprowadzenie
2. Szybki start (5 minut)
3. Ekran glowny i elementy interfejsu
4. Logi RCP - import i kontrola poprawnosci
5. Presety dyzurow (standardowe)
6. Ministranci: imiona, wykluczenia, usprawiedliwienia
7. Przypisywanie dyzurow (normalne)
8. Dni specjalne - pelny opis
9. Zasady naliczania punktow
10. Szczegoly punktow (diagnostyka)
11. Export do Excel
12. Ustawienia, backup, migracja danych
13. Licencja i aktualizacje
14. Najczestsze scenariusze pracy
15. FAQ i rozwiazywanie problemow
16. Dobre praktyki administracyjne

---

## 1. Wprowadzenie
Program **Punktacja LSO** sluzy do rozliczania punktow ministrantow na podstawie:
- logow wejsc/wyjsc z systemu RCP,
- zdefiniowanych dyzurow tygodniowych,
- konfiguracji dni specjalnych,
- przypisan ministrantow.

Program wspiera:
- wiele sub-dyzurow w jednym dyzurze,
- dyzury obowiazkowe i nadobowiazkowe,
- punktacje dodatnia i ujemna,
- zastapienia wybranych dyzurow standardowych,
- tryb "licz tylko wg dnia specjalnego",
- usprawiedliwienia,
- eksport raportu do Excel,
- diagnostyke dzien po dniu.

---

## 2. Szybki start (5 minut)
Jesli uruchamiasz program pierwszy raz, wykonaj te kroki:

1. Kliknij `Wczytaj log` i wybierz plik TXT z eksportu RCP.
2. W `Presety dyzurow` dodaj minimum jeden preset z sub-dyzurem.
3. Kliknij `Edytuj Imiona` i uzupelnij imiona ministrantow.
4. Kliknij `Przypisywanie dyzurow` i przypisz ministrantow do presetow.
5. Ustaw zakres dat (`Od` i `Do`).
6. Kliknij `Oblicz punkty`.
7. Sprawdz wynik oraz `Szczegoly punktow`.

---

## 3. Ekran glowny i elementy interfejsu
### 3.1 Gorne przyciski
- `Wczytaj log` - import pliku TXT z logami RCP.
- `Oblicz punkty` - przeliczenie punktow dla aktualnego zakresu.
- `Export wynikow` - generowanie pliku Excel.
- `Szczegoly punktow` - raport diagnostyczny dzien po dniu.
- `Sprawdz aktualizacje` - reczna kontrola aktualizacji.
- `Licencja` - aktywacja i status licencji.

### 3.2 Zakres czasu
- `Od` / `Do` - zakres dat do obliczen.
- `Miesiac i rok` - pole pomocnicze przy pracy miesiecznej.

### 3.3 Sekcje robocze
- `Presety dyzurow` - lista i edycja wzorcow.
- `Ministranci i przypisane dyzury` - tabela aktualnych przypisan.
- `Wyniki` - lista punktow po przeliczeniu.

---

## 4. Logi RCP - import i kontrola poprawnosci
### 4.1 Jak importowac
1. Kliknij `Wczytaj log`.
2. Wybierz plik TXT.
3. Po poprawnym imporcie ikona stanu logu zmieni sie na "OK".

### 4.2 Co program robi po imporcie
- ustawia automatycznie minimalna i maksymalna date z logow,
- uzupelnia brakujacych ministrantow po ID,
- aktywuje funkcje zalezne od logow.

### 4.3 Typowe problemy przy imporcie
- zly format pliku,
- pusty/niekompletny eksport,
- plik niepochodzacy z RCP.

W takich przypadkach program pokazuje komunikat bledu i nie uruchamia obliczen.

---

## 5. Presety dyzurow (standardowe)
### 5.1 Czym jest preset
Preset to wzorzec dyzuru przypisany do jednego lub wielu dni tygodnia.

### 5.2 Struktura presetu
Kazdy preset ma:
- nazwe,
- dni tygodnia,
- liste sub-dyzurow.

### 5.3 Sub-dyzur - pola
Dla kazdego sub-dyzuru ustawiasz:
- `Wejscie od` i `Wejscie do`,
- `Wyjscie od` i `Wyjscie do`,
- `Typ`: `obowiazkowy` albo `nadobowiazkowy`,
- `Pkt +` (za zaliczenie),
- `Pkt -` (kara za brak, tylko dla obowiazkowego),
- `Pkt za nadobowiazkowe` (bonus dla innych, tylko dla obowiazkowego).

### 5.4 Zasada typow
- `obowiazkowy`: moze dac +, moze dac -, moze wygenerowac bonus dla innych.
- `nadobowiazkowy`: punktowany jako bonus, bez kary za brak.

### 5.5 Walidacja
Program wykrywa bledy czasu i konflikty nakladajacych sie sub-dyzurow.

---

## 6. Ministranci: imiona, wykluczenia, usprawiedliwienia
### 6.1 Edycja imion
Panel `Edytuj Imiona` pozwala ustawic czytelna nazwe dla kazdego ID.

### 6.2 Wykluczenie z sumowania (Admin)
Checkbox `Wyklucz z obliczania (Admin)`:
- dana osoba jest pomijana w sumach glownych,
- nadal mozna analizowac jej dzienne zdarzenia diagnostycznie.

### 6.3 Usprawiedliwienia
Panel `Usprawiedliwienia`:
- dodawanie pojedynczych dat,
- dodawanie zakresow dat,
- usuwanie zaznaczonych dat,
- `Ctrl + A` dziala na listach.

Skutek:
- za usprawiedliwiona date nie nalicza sie kara `Pkt -` za brak.

---

## 7. Przypisywanie dyzurow (normalne)
Panel `Przypisywanie dyzurow`:
- przypisujesz ministrantow do wybranego presetu,
- mozesz filtrowac i zarzadzac przypisaniami hurtowo,
- `Ctrl + A` dziala w listach.

Przypisania standardowe sa baza do obliczen, o ile dany dzien nie jest modyfikowany przez dzien specjalny.

---

## 8. Dni specjalne - pelny opis
Panel: `Admin: Punktacja dnia`.

To najbardziej rozbudowana czesc programu.

### 8.1 Co mozna zrobic w dniach specjalnych
- ustawic inny uklad godzin dla konkretnej daty,
- ustawic ten sam uklad dla wielu dowolnych dat,
- importowac konfiguracje z presetow standardowych,
- laczyc wpisy reczne i importowane w jednej tabeli,
- ustawic zastapienie konkretnego standardowego presetu,
- przypisac osobne osoby do kazdego wpisu,
- wybrac czy dzien ma byc liczony tylko wg specjalnego.

### 8.2 Grupy dat
Lista glowna pokazuje grupy dat o identycznej konfiguracji.
- Edycja grupy otwiera cala grupe, nie pojedyncza date.
- Usuniecie daty z listy w edycji usuwa ja z konfiguracji po zapisie.

### 8.3 Jeden model zapisu
Wpisy reczne i importowane trafiaja do jednej tabeli i tylko ta tabela jest zrodlem zapisu.

#### Reczny wpis
1. Ustaw nazwe wpisu.
2. Dodaj sub-dyzury.
3. Ustaw przypisania osob.
4. Kliknij `Dodaj reczny wpis do tabeli`.

Bez dodania do tabeli wpis nie zostanie zapisany.

#### Import z presetow
1. Zaznacz presety na liscie importu.
2. Kliknij `Wczytaj zaznaczone`.
3. Dla kazdego wpisu mozesz edytowac godziny, nazwe i przypisania.

### 8.4 Zastepowanie standardowego dyzuru
W tabeli wpisu sa kolumny:
- `Zastepuje` (checkbox),
- `Zastepuje dyzur` (docelowy preset standardowy).

Znaczenie:
- ten wpis specjalny podmienia wskazany preset standardowy.
- bez trybu globalnego tylko ten preset jest zastapiony, reszta standardowych dalej dziala.

### 8.5 Tryb globalny dnia
Checkbox:
`Licz tylko wg dnia specjalnego (pomin standardowe dyzury w tym dniu)`

- wlaczony:
  - standardowe dyzury sa pomijane,
  - liczenie idzie tylko po wpisach specjalnych.
- wylaczony:
  - wpisy specjalne sa laczone ze standardowymi,
  - podmiany dzialaja tylko tam, gdzie ustawiono `Zastepuje`.

### 8.6 Przypisania osob per wpis
Kazdy wpis ma osobne przypisania.
Dodatkowo w oknie przypisan mozna importowac przypisania z normalnego presetu.

### 8.7 Wpis tylko nadobowiazkowy
Jesli wpis ma tylko sub-dyzury nadobowiazkowe:
- przypisywanie osob jest zablokowane,
- wpis traktowany jest globalnie jako dodatkowy.

### 8.8 Zachowanie kompatybilnosci
Program obsluguje starsze formaty zapisow i migruje je do aktualnego modelu.

---

## 9. Zasady naliczania punktow
### 9.1 Zaliczenie sub-dyzuru
Sub-dyzur jest zaliczony, gdy logi dnia zawieraja czas wejscia i wyjscia mieszczacy sie w oknach.

### 9.2 Zakresowe zaliczenie miedzy sub-dyzurami
Program obsluguje przypadki, gdzie wejscie i wyjscie wpadaja w dwa sasiednie sub-dyzury i zalicza zakres pomiedzy nimi.

### 9.3 Kary
Kara (`Pkt -`) naliczana jest za **kazdy niespelniony** sub-dyzur obowiazkowy (jesli data nie jest usprawiedliwiona).

### 9.4 Nadobowiazkowe
Bonusy sa naliczane wedlug reguly:
- za obowiazkowy sub-dyzur: z pola `Pkt za nadobowiazkowe`,
- za nadobowiazkowy sub-dyzur: z pola `Pkt +`.

### 9.5 Anty-duplikaty
Program ma zabezpieczenia, zeby nie dublowac punktow:
- brak podwojenia globalny bonus + wlasny punkt za ten sam sub-dyzur,
- brak dublowania przy identycznych oknach obowiazkowy/nadobowiazkowy,
- poprawna obsluga diagnostyki dla osob wykluczonych adminem.

---

## 10. Szczegoly punktow (diagnostyka)
Panel `Szczegoly punktow` pokazuje:
- daty w zakresie,
- logi z danego dnia,
- zdarzenia punktowe (`zaliczony`, `ukarany`, `nadobowiazkowy`),
- sume dnia,
- sume zakresu.

To podstawowe narzedzie do wyjasniania roznic punktowych.

### 10.1 Jak czytac wpis diagnostyczny
Przyklad:
- `zaliczony ... typ obowiazkowe` - punktacja za realizacje przypisanego obowiazku.
- `ukarany ...` - kara za brak zaliczenia obowiazkowego.
- `zaliczony ... typ nadobowiazkowe` - bonus dodatkowy.

---

## 11. Export do Excel
Przycisk `Export wynikow` tworzy raport do pliku XLSX.
Raport zawiera podsumowanie wynikow i oznacza osoby z najwyzsza liczba punktow (z obsluga remisow).

---

## 12. Ustawienia, backup, migracja danych
### 12.1 Automatyczny zapis
Program zapisuje ustawienia lokalnie (format binarny `.rcpsetb`).

### 12.2 Backup
Wbudowany mechanizm backupu umozliwia przywrocenie poprzedniego stanu konfiguracji.

### 12.3 Migracja
Przy starcie moze pojawic sie komunikat o migracji danych.
Migracja dostosowuje starsze struktury do aktualnego formatu.

---

## 13. Licencja i aktualizacje
### 13.1 Licencja
Panel `Licencja` obsluguje aktywacje i walidacje.

### 13.2 Aktualizacje
- Wersja EXE: obsluga aktualizacji automatycznych/recznych.
- Uruchomienie z Pythona: komunikat o pominieciu update jest normalny.

---

## 14. Najczestsze scenariusze pracy
### 14.1 Standardowy miesiac
1. Wczytaj logi.
2. Zweryfikuj presety i przypisania.
3. Dodaj wyjatki jako dni specjalne.
4. Oblicz punkty.
5. Sprawdz diagnostyke dni granicznych.
6. Eksportuj do Excel.

### 14.2 Dwie niedziele z inna godzina
1. Otworz `Admin: Punktacja dnia`.
2. Wybierz dwie konkretne daty.
3. Dodaj wpis specjalny z nowymi godzinami.
4. Ustaw `Zastepuje` -> wskaz docelowy preset niedzielny.
5. Zapisz.

### 14.3 "Byl na innym dyzurze"
- jesli nie byl na swoim specjalnym i dostaje kare,
- ale byl na innym dyzurze,
- moze dostac nadobowiazkowe zgodnie z konfiguracja i przypisaniami.

---

## 15. FAQ i rozwiazywanie problemow
### 15.1 "Po restarcie znika zastapienie"
Sprawdz, czy wpis ma ustawione:
- `Zastepuje = TAK`,
- `Zastepuje dyzur = konkretny preset`.

### 15.2 "Usunalem date z grupy, ale zostala"
Po usunieciu daty kliknij `OK` w oknie edycji dnia specjalnego i potem `OK` w glownym oknie panelu.

### 15.3 "W diagnostyce mam podwojone nadobowiazkowe"
Zweryfikuj, czy nie ma dwoch wpisow o identycznych oknach i roznych typach.
Aktualna wersja posiada filtry anty-duplikat.

### 15.4 "Nie liczy standardowych po dniu specjalnym"
Sprawdz checkbox:
`Licz tylko wg dnia specjalnego (pomin standardowe dyzury w tym dniu)`.

### 15.5 "Nadal cos sie nie zgadza"
Uzyj `Szczegoly punktow` i porownaj:
- logi dnia,
- liste zdarzen,
- konfiguracje wpisu specjalnego,
- przypisania osob.

---

## 16. Dobre praktyki administracyjne
- Uzywaj jednoznacznych nazw presetow i wpisow.
- Unikaj bardzo podobnych nazw (`Niedziela 18`, `Niedziela 18:00`) bez potrzeby.
- Po kazdej wiekszej zmianie uruchom diagnostyke dla 1-2 dni testowych.
- Trzymaj regularny backup przed przebudowa konfiguracji.
- Przy pracy grupowej ustal jedna osobe odpowiedzialna za finalne zatwierdzenie ustawien.

---

## Zalaczniki
### A. Slownik skrótów
- RCP - rejestracja czasu pracy (zrodlo logow)
- GUI - interfejs graficzny
- XLSX - format Excela

### B. Checklista przed zamknieciem miesiaca
1. Czy wszystkie logi sa wczytane?
2. Czy zakres dat jest poprawny?
3. Czy dni specjalne sa kompletne?
4. Czy sprawdzono diagnostyke trudnych dni?
5. Czy eksport XLSX zostal wykonany?
6. Czy backup jest aktualny?

