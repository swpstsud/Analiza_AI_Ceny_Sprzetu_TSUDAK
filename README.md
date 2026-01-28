# 📈 Analiza Wpływu AI na Ceny Sprzętu Komputerowego

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Data-Analysis-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 O Projekcie
Projekt zaliczeniowy z zakresu analizy szeregów czasowych (Time Series Analysis). Celem badania była weryfikacja hipotezy o wpływie dynamicznego rozwoju sektora sztucznej inteligencji (AI) na realne ceny producentów sprzętu komputerowego.

Główne pytanie badawcze: **Czy hossa na akcjach spółek AI (reprezentowana przez NVIDIA) jest wskaźnikiem wyprzedzającym dla wzrostu cen sprzętu komputerowego (indeks PPI)?**

## 💾 Źródła Danych
Analiza opiera się na dwóch szeregach czasowych z lat **2018–2025**:

1.  **Sektor AI (Przyczyna):** Historyczne notowania akcji **NVIDIA Corp. (NVDA)**.
    * *Źródło:* Yahoo Finance (`yfinance`)
    * *Charakter:* Dane dzienne (agregowane do średniej miesięcznej).
2.  **Ceny Sprzętu (Skutek):** Indeks Cen Producentów – **PPI: Electronic Computer Manufacturing**.
    * *Źródło:* Federal Reserve Economic Data (FRED)
    * *Seria:* `PCU334111334111`
    * *Charakter:* Dane miesięczne.

## ⚙️ Metodyka i Modele
W projekcie zastosowano zaawansowane techniki ekonometryczne (zgodnie z wymogami akademickimi):

* **Przetwarzanie danych:** Resampling danych do wspólnej częstotliwości miesięcznej, obsługa braków danych.
* **Analiza Stacjonarności:** Przeprowadzono **Rozszerzony Test Dickeya-Fullera (ADF)**. Wykazano niestacjonarność cen surowych i konieczność zastosowania różnicowania (zmiany procentowe).
* **Model VAR (Vector Autoregression):** Zbudowano model wielowymiarowy badający wzajemne zależności między zmiennymi.
    * Dobór opóźnień (Lags) na podstawie kryterium informacyjnego **AIC**.
* **Test Przyczynowości Grangera:** Kluczowy test statystyczny weryfikujący, czy zmiany cen NVIDIA pozwalają prognozować zmiany PPI.
* **Walidacja:** Ocena jakości modelu przy użyciu metryki **MAE (Mean Absolute Error)**.

## 📊 Wnioski
Przeprowadzona analiza doprowadziła do następujących konkluzji:

1.  **Brak przyczynowości Grangera (p-value > 0.05):** Testy statystyczne wykazały brak istotnego wpływu spekulacji giełdowych na realne ceny produkcji sprzętu w badanym okresie.
2.  **Rozdźwięk Rynków (Decoupling):** Zaobserwowano silną dywergencję – wykładniczy wzrost wyceny NVIDIA nie przekłada się na gwałtowny wzrost cen konsumenckich komputerów, które pozostają stabilne.
3.  **Jakość Modelu:** Model VAR osiągnął bardzo niski błąd (MAE ≈ 1%) dla prognozy cen sprzętu, co potwierdza stabilność tego sektora.

## 🛠️ Technologie
Projekt został zrealizowany w języku **Python** z wykorzystaniem bibliotek:
* `pandas` & `numpy` - manipulacja danymi
* `matplotlib` & `seaborn` - wizualizacja danych
* `statsmodels` - modelowanie ekonometryczne (VAR, ADF, Granger)
* `yfinance` & `pandas-datareader` - pobieranie danych API

## 🚀 Jak uruchomić?
Aby odtworzyć wyniki analizy:

1. Sklonuj repozytorium:
   ```bash
   git clone [https://github.com/TwojNick/Analiza-AI-Ceny-Sprzetu.git](https://github.com/TwojNick/Analiza-AI-Ceny-Sprzetu.git)
