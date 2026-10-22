# BLISK / PulseCMS — system tworzenia i optymalizacji stron

**Rodzaj:** własny projekt internetowy · **strona działająca:** [blisk.pl](https://blisk.pl) · **charakter:** system budowy stron rozwijany z użyciem agentów AI.

## Problem

Chciałem tworzyć strony, których działanie nie zależy od ciężkiego zestawu wtyczek i przypadkowej konfiguracji. Ważne były: szybkość w telefonie, spójność mobilnej i desktopowej wersji, powtarzalna publikacja, zarządzanie obrazami i możliwość kontroli zmian.

## Jak zorganizowałem rozwiązanie

- Określałem wymagania biznesowe strony, strukturę informacji, zasady publikacji i kryteria jakości.
- Projektowałem przepływ pracy: **dane i treści → generator → optymalizacja zasobów → build → testy → publikacja**.
- Wymagałem automatycznego tworzenia responsywnych formatów obrazów **WebP / AVIF** i ograniczenia kosztów ich ponownego generowania.
- Testowałem działanie strony i wyniki Lighthouse; identyfikowałem problemy do poprawy i weryfikowałem rezultat kolejnych zmian.
- Korzystałem z **GitHub, testów oraz wdrożeń na Vercel** do organizacji i weryfikacji pracy.

**Moja rola:** projektowałem założenia, zakres i reguły jakości, analizowałem błędy, zatwierdzałem priorytety oraz oceniałem wyniki testów. **Znaczną część implementacji kodu tworzyły agenty AI** pod moją koordynacją — nie opisuję jej jako samodzielnie napisanego przeze mnie frameworka.

## Udokumentowane wyniki

### Performance w pojedynczym teście Lighthouse

**Lighthouse 13.4.0 · 13 lipca 2026 r.**

| Miernik | Mobile | Desktop |
| --- | ---: | ---: |
| Performance | **100/100** | **100/100** |
| LCP | 0,9 s | 0,4 s |
| TBT | 0 ms | 0 ms |
| CLS | 0 | 0 |

Accessibility i Best Practices otrzymały również 100 punktów. W tej próbie SEO był ograniczony świadomym `noindex` — nie twierdzę, że wszystkie kategorie i wszystkie uruchomienia zawsze mają 100.

### Automatyzacja wariantów obrazów

- W udokumentowanej próbie cache zapisano **214 unikalnych wariantów** obrazów.
- Przy kolejnym buildzie bez zmiany źródeł obrazów **0 z 80** wariantów zostało ponownie wygenerowanych.
- Wprowadzono dodatkową ochronę przed duplikacją cache oraz limit **256 MiB**, z testami regresji.

## Co ten projekt pokazuje pracodawcy

To przykład analizy wymagań, organizacji technicznego workflow, kontroli jakości, myślenia o wydajności i pracy z narzędziami AI. Nie jest to dowód, że samodzielnie napisałem cały kod źródłowy ani że obsługiwałem zewnętrznych płacących klientów BLISK.

## Dowody i ograniczenia

- [Działająca witryna BLISK](https://blisk.pl)
- Wewnętrzne repozytorium PulseCMS: scalone PR **#25** (Lighthouse), **#95** (cache AVIF/WebP), **#111** (eliminacja duplikacji), **#112** (limit cache).
- Wartości pochodzą z konkretnych audytów i przebiegów testowych, **nie stanowią SLA** ani gwarancji bieżących parametrów serwisu.
