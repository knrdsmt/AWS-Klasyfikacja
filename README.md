# Detekcja zmian użytkowania ziemi.
Sprawozdanie z pracy zespołu: Klasyfikacja i rozpoznawanie wzorców. 

### Cel
Celem niniejszej pracy była zaawansowana analiza porównawcza dwóch obrazów satelitarnych w celu zidentyfikowania i wizualizacji różnic między nimi, a następnie sklasyfikowanie zmian na podstawie koloru oraz obliczenie procentowych zmian w różnych kategoriach: woda, las, miasto, pola.

### Metodologia
1. **Wczytanie i Przygotowanie Danych:**
   - Wczytano dwa obrazy satelitarne za pomocą biblioteki `PIL (Pillow)`.
   - Obrazy zostały skonwertowane do tablic `NumPy` w celu ułatwienia dalszych obliczeń.

2. **Przycinanie Obrazów:**
   - Znaleziono minimalne wymiary wspólne dla obu obrazów i przycięto je do tych wymiarów, aby umożliwić bezpośrednie porównanie.

3. **Obliczanie Różnic:**
   - Obliczono różnicę między obrazami poprzez odjęcie wartości pikseli jednego obrazu od drugiego.
   - Różnica została znormalizowana w celu umożliwienia jej wizualizacji.
   - Zastosowano threshold, aby wyświetlić tylko znaczące różnice.

4. **Wyświetlenie Obrazów:**
   - Obrazy przed i po obróbce oraz różnice między nimi zostały wyświetlone obok siebie za pomocą biblioteki `Matplotlib`.

5. **Klasyfikacja Kolorów za Pomocą K-means:**
   - Połączono oba obrazy w celu znalezienia wspólnych centroidów kolorów.
   - Wykorzystano algorytm K-means do znalezienia dominujących kolorów (centroidów) w obrazach.
   - Zdefiniowano kolory reprezentujące woda, las, miasto i pola, a następnie zmapowano centroidy na te kategorie.

6. **Klasyfikacja Pikseli:**
   - Każdy piksel w obrazach został sklasyfikowany do jednej z kategorii na podstawie najbliższego centroidu.

7. **Obliczenie Zmian:**
   - Obliczono zmiany w liczbie pikseli dla każdej kategorii (woda, las, miasto, pola) między dwoma obrazami.
   - Obliczono procentowe zmiany liczby pikseli dla każdej kategorii w stosunku do całkowitego rozmiaru obrazu.

### Wyniki
- **Zmiany w liczbie pikseli dla każdej kategorii:**
  - Woda: `count`
  - Las: `count`
  - Miasto: `count`
  - Pola: `count`

- **Procentowe zmiany względem rozmiaru całego obrazu:**
  - Woda: `+/-value %`
  - Las: `+/-value %`
  - Miasto: `+/-value %`
  - Pola: `+/-value %`
  
- **Przykładowe wyniki**
  ![image](https://github.com/knrdsmt/AWS-Klasyfikacja/assets/97449172/1c49f25b-2f75-4c2b-bbf9-06ecf149c2c6)

- Zmiany w liczbie pikseli dla każdej kategorii: woda: 584802, las: -584802, miasto: 0, pola: 0

- Procentowe zmiany względem rozmiaru całego obrazu: woda: +6.38%, las: -6.38%, miasto: +0.00%, pola: +0.00%

#### Technologie
- **Python**: Język programowania użyty do przetwarzania obrazów i analizy danych.
- **PIL (Pillow)**: Biblioteka do wczytywania i przetwarzania obrazów.
- **NumPy**: Biblioteka do obliczeń numerycznych i manipulacji tablicami pikseli.
- **Matplotlib**: Biblioteka do wizualizacji danych i wyświetlania obrazów.
- **Scikit-learn (K-means)**: Algorytm użyty do grupowania kolorów w obrazie.
