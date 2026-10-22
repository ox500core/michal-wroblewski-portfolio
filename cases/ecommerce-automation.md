# E-commerce — integracja sprzedaży, zamówień i wysyłek

**Rodzaj:** własny, działający sklep internetowy · **okres:** około 2016–2020 · **skala:** niewielki e-commerce, około 50–70 zamówień miesięcznie (szacunek z własnej praktyki).

## Punkt wyjścia

Samodzielnie prowadziłem sprzedaż online. Obsługa zamówienia wymagała przechodzenia między kanałem sprzedaży, danymi towaru, dokumentami, usługą kurierską i komunikacją z klientem. Szczególnym wyzwaniem była kontrola stanów u dostawcy — automatyczne potwierdzanie niedostępnego towaru mogłoby powodować problemy.

## Co rzeczywiście zrobiłem

- Korzystałem z **RedCart** przez około rok, a następnie **samodzielnie przeniosłem sklep na WooCommerce / WordPress**, m.in. w celu ograniczenia kosztów utrzymania.
- Nauczyłem się wykorzystywać integracje z **API hurtowni** do pracy z informacjami produktowymi. Nie oznacza to autorstwa całej warstwy programistycznej integracji.
- Konfigurowałem **BaseLinker (obecnie Base)** do odbierania i organizowania zamówień, w tym z **Allegro**.
- Łączyłem realizację zamówień z **Apaczką**, komunikacją przez **SMSAPI** oraz obiegiem dokumentów sprzedażowych z użyciem **wFirma**.
- Ustawiałem powiadomienia o zamówieniach, numery przesyłek i przypomnienia o przesyłkach nieodebranych.
- Tam, gdzie dane magazynowe nie dawały pewności, utrzymywałem **ręczny punkt kontroli** zamiast pozornego pełnego automatu.

## Logika procesu

```text
Zamówienie (sklep / Allegro)
             ↓
      Organizacja w BaseLinker
             ↓
   Sprawdzenie towaru / wyjątki
             ↓
Dokumenty i przygotowanie przesyłki
             ↓
      Apaczka + powiadomienia
             ↓
   Informacja do kupującego / SMS
```

## Mój wkład i wynik

**Moja rola:** właściciel sklepu i osoba konfigurująca proces w gotowych systemach SaaS. Nie zatrudniałem zespołu wdrożeniowego i nie twierdzę, że zbudowałem własną platformę e-commerce.

**Wynik:** proces działał przy rzeczywistej obsłudze zamówień i pozwalał mi łączyć powtarzalne kroki w jedno workflow, z kontrolą wyjątków.

**Czego to dowodzi:** rozumienia operacji e-commerce, migracji między platformami, zależności między systemami, integracji usług i projektowania reguł biznesowych.

## Granice dowodu

To opis **historycznego doświadczenia operacyjnego**, nie zrzut aktualnego panelu ani niezależny audyt. Nie posiadam obecnie pełnych artefaktów konfiguracyjnych starego sklepu. Nie deklaruję mierzalnego wzrostu przychodu lub oszczędności roboczogodzin bez dokumentacji. Wersje narzędzi od tamtego czasu się zmieniły.
