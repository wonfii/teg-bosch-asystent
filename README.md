# Asystent i Wyszukiwarka do pralek Bosch

Projekt zaliczeniowy z przedmiotu TEG (PJATK, 2026Z).

Asystent pomaga diagnozować usterki pralek Bosch na podstawie instrukcji w PDF. Użytkownik podaje kod błędu (np. `E:18`) albo opisuje objaw własnymi słowami, a system wskazuje prawdopodobne przyczyny, kroki naprawy i potrzebne części, razem ze źródłem (plik i numer strony). Deterministyczny silnik w Pythonie liczy koszt naprawy i podejmuje decyzję „naprawiać czy kupić nową”.

## Planowane elementy

- ekstrakcja encji i relacji z PDF przez LLM (Pydantic, structured output),
- wyszukiwanie semantyczne w ChromaDB i RAG z odwołaniami do źródeł,
- graf wiedzy w Neo4j (Model, ErrorCode, Symptom, Cause, RepairStep, Part) i zapytania Cypher,
- agent ReAct w LangGraph z narzędziami i pamięcią rozmowy,
- silnik decyzyjny opłacalności naprawy,
- ewaluacja: RAG wektorowy vs GraphRAG,
- opcjonalnie: wyszukiwanie hybrydowe (BM25 + wektory, reranker) i własny serwer MCP.

## Dane

Oficjalne instrukcje obsługi pralek Bosch (PL), pobrane z serwerów producenta. Pliki PDF nie są w repozytorium (`.gitignore`); trafiają do `data/raw/`. Lista źródeł: `data/raw/zrodla_objawy.txt`.

## Uruchomienie

W przygotowaniu.
