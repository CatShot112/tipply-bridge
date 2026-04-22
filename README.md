# 🌉 Tipply Bridge by SZABLIX

![Wersja](https://img.shields.io/badge/Wersja-1.0.0-success)
![Platforma](https://img.shields.io/badge/Platforma-Windows%20%7C%20Linux-blue)

**Tipply Bridge** to lekki, niezawodny i nowoczesny program działający w tle, który w czasie rzeczywistym przechwytuje wpłaty z platformy **Tipply** i natychmiastowo przekazuje je do **StreamElements**.

Zbudowany z myślą o streamerach (i serwerach takich jak Ciapongi RP!), którzy chcą mieć wszystkie powiadomienia w jednym miejscu, bez obciążania komputera ukrytymi przeglądarkami w tle.

## ✨ Główne funkcje

* ⚡ **Zero Opóźnień (WebSockets):** Program łączy się bezpośrednio z serwerami Tipply z pominięciem przeglądarki. Powiadomienia wpadają ułamek sekundy po wysłaniu donejta.
* 🪶 **Ekstremalnie lekki:** Zapomnij o starych skryptach używających Selenium i Chromium. Tipply Bridge zużywa ułamek procenta procesora i pamięci RAM.
* 🎨 **Nowoczesny Interfejs (Dark Mode):** Eleganckie, gamingowe GUI zbudowane na CustomTkinter.
* 👻 **Działanie w tle (System Tray):** Kliknij "X", aby ukryć program w zasobniku obok zegarka. Będzie cicho pracował w tle, nie zaśmiecając paska zadań.
* 🛡️ **Bezpieczeństwo:** Twoje wrażliwe tokeny (JWT, Account ID) są zapisywane w bezpiecznym, ukrytym folderze systemowym, a nie w zwykłym pliku tekstowym obok programu.
* 🪄 **Inteligentny Kreator Konfiguracji:** Pierwsze uruchomienie to prosty przewodnik krok po kroku. Wklej cały link z Tipply, a program sam wytnie z niego odpowiedni token!
* ♻️ **Ochrona przed Replayami:** Program pamięta ID przetworzonych płatności. Ponowne odtworzenie alertu w panelu Tipply nie spowoduje wysłania fałszywego powiadomienia do StreamElements.

## 📸 Zrzuty ekranu

*(Tutaj dodaj link do zrzutu ekranu swojego programu, jak już wrzucisz go na GitHuba)*
`![Ekran Główny](link-do-zdjecia.png)`

## 🚀 Jak zacząć? (Dla użytkowników)

Nie musisz znać się na programowaniu ani instalować Pythona!
1. Przejdź do zakładki **[Releases](../../releases)** po prawej stronie.
2. Pobierz najnowszy plik `TipplyBridge_Windows.exe` (lub wersję na Linuxa).
3. Uruchom program i postępuj zgodnie z instrukcjami na ekranie, aby podać swoje tokeny.
4. Kliknij **START** i ciesz się połączonymi systemami!

## 🛠️ Dla programistów (Kompilacja ze źródeł)

Jeśli chcesz zmodyfikować kod lub skompilować go samodzielnie:

```bash
# Sklonuj repozytorium
git clone [https://github.com/TwojaNazwa/tipply-bridge.git](https://github.com/TwojaNazwa/tipply-bridge.git)
cd tipply-bridge

# Stwórz środowisko wirtualne i aktywuj je
python -m venv venv
# Windows: venv\Scripts\activate
# Linux: source venv/bin/activate

# Zainstaluj zależności
pip install customtkinter requests "python-socketio[client]<5" "python-engineio<4" pystray Pillow pyinstaller

# Uruchom testowo
python app.py

# Kompilacja do pliku .exe (Windows)
pyinstaller --onefile --windowed --icon=TwojeLogo.ico --add-data "TwojeLogo.ico;." app.py
