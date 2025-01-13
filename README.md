# Projekt: Sieć Neuronowa do Rekomendacji Filmów

## Opis projektu

Ten projekt wykorzystuje dane z bazy **MovieLens 100k** do budowy i trenowania prostej sieci neuronowej, która rekomenduje filmy użytkownikom na podstawie ich wcześniejszych ocen. Model uczy się reprezentacji użytkowników i filmów przy użyciu embeddingów, a następnie przewiduje oceny dla niezauważonych dotąd filmów.

---

## Dane wejściowe

Używamy dwóch głównych plików z MovieLens 100k:

1. **`u.data`** - Zawiera oceny użytkowników dla filmów.
2. **`u.item`** - Zawiera szczegóły dotyczące filmów, takie jak tytuł i gatunki.

Przykładowe dane:

- **Tabele ocen (********`u.data`********)**:

  | user\_id | item\_id | rating | timestamp |
  | -------- | -------- | ------ | --------- |
  | 196      | 242      | 3      | 881250949 |

- **Tabele filmów (********`u.item`********)**:

  | item\_id | title            |
  | -------- | ---------------- |
  | 1        | Toy Story (1995) |
  | 2        | GoldenEye (1995) |

---

## Struktura Modelu

Model składa się z następujących warstw:

- **Wejściowe**: ID użytkownika i ID filmu.
- **Embeddingi**: Warstwy embeddingowe dla użytkowników i filmów, które reprezentują je w przestrzeni latentnej (50 wymiarów).
- **Warstwy ukryte**: Dwie w pełni połączone warstwy z 128 i 64 neuronami oraz Dropout (0.3).
- **Wyjście**: Przewidywana ocena w skali od 1 do 5.

Schemat modelu:

- Parametry łączne: **152,599**
- Wymiary embeddingów: 50 dla użytkowników i filmów

---

## Wyniki

1. **Uczenie modelu**:
   Wykresy strat i średnich błędów absolutnych (MAE) dla treningu i walidacji:





1. **Embeddingi użytkowników**:
   Wizualizacja przestrzeni embeddingów użytkowników za pomocą t-SNE:



1. **Rekomendacje filmów**:
   Przykład rekomendacji dla użytkownika o ID `1`:

   | item\_id | title                | predicted\_rating |
   | -------- | -------------------- | ----------------- |
   | 242      | Star Wars (1977)     | 4.8               |
   | 300      | The Godfather (1972) | 4.7               |

---

## Jak uruchomić projekt

1. **Zainstaluj wymagane biblioteki**:

   ```bash
   pip install tensorflow pandas matplotlib scikit-learn
   ```

2. **Uruchom skrypt**:

   - Skrypt ładuje dane, buduje model, trenuje go i generuje rekomendacje.

3. **Zobacz wyniki**:

   - Wykresy uczenia, wizualizacje embeddingów i rekomendacje filmów są generowane automatycznie.

---

## Możliwe ulepszenia

1. **Zwiększenie wymiarów embeddingów**: Ulepszenie reprezentacji użytkowników i filmów.
2. **Dodanie więcej danych**: Użycie większych zbiorów danych MovieLens (np. MovieLens 1M).
3. **Zaawansowane techniki modelowania**: Zastosowanie bardziej złożonych architektur, takich jak Transformers lub metody hybrydowe.

---

## Autor

Projekt przygotowany w celu demonstracji zastosowania sieci neuronowych w systemach rekomendacji.

