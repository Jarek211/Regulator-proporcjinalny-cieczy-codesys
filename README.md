# Regulator proporcjinalny ciceczy
sterowanie napełnianiem zbiornika
# Regulator cieczy (Proportional Liquid Level Controller)  
**CODESYS 3.5.21.0**

## 📌 Opis projektu / Project description

Projekt przedstawia implementację prostego regulatora proporcjonalnego (P-regulatora), który steruje poziomem cieczy w zbiorniku poprzez zawory napełniania i opróżniania.  
Regulator działa na podstawie uchybu (różnicy pomiędzy wartością zadaną a aktualnym poziomem cieczy) i wysterowuje odpowiednio zawory, aby utrzymać poziom cieczy w zadanym zakresie.

---

## ⚙️ Zastosowane komponenty / Used components

- Typy zmiennych: `REAL`, `BOOL`, `WORD`
- Bloki funkcyjne: własny P-regulator
- Wejścia:
  - `wSetPoint`: wartość zadana poziomu cieczy
  - `wLevelMeter`: aktualny poziom cieczy
  - `xStart`, `xStop`, `xReset`: sterowanie startem, zatrzymaniem i resetem regulatora
- Wyjścia:
  - `wFillValve`: sygnał sterujący zaworem napełniania
  - `wDischargeValve`: sygnał sterujący zaworem opróżniania
  - `xAlarm`, `xReady`, `xRunning`: status pracy regulatora
- Parametr `rKp`: wzmocnienie proporcjonalne

---

## 🔄 Zasada działania / Operating principle

- Regulator oblicza uchyb: `SetPoint - LevelMeter`
- Jeśli uchyb jest dodatni, otwierany jest zawór napełniania (`wFillValve`)
- Jeśli ujemny – otwierany jest zawór opróżniania (`wDischargeValve`)
- Działanie proporcjonalne realizowane jest z użyciem współczynnika `Kp`

---

## 🧪 Tryby działania / Operating modes

- `xStart = TRUE` uruchamia regulator
- `xStop = TRUE` zatrzymuje działanie
- `xReset = TRUE` resetuje uchyb, alarmy i stan

---

## 🧰 Użyte biblioteki / Used libraries

- Brak zewnętrznych bibliotek (projekt bazuje na standardowych elementach CODESYS)

---

## 🗂️ Struktura projektu / Project structure

- `PLC_PRG`: główny program uruchamiający regulator
- `P_Regulator`: blok funkcyjny P-regulatora
- `GVL`: zmienne globalne )

---

## 📎 Wersja / Version

- Opracowano w CODESYS 3.5.21.0

---



Projekt stworzony w ramach nauki programowania w środowisku CODESYS.
