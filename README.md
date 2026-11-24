Projekt z wykorzystaniem CIS Benchmarks
Wymagania zaliczenia
Wprowadzenie - znaczenie i rola CIS Benchmarks
CIS Benchmarks są zestawami konkretnych zaleceń dotyczących bezpiecznej konfiguracji systemów; CIS publikuje benchmarki m.in. dla Windows, Windows Server, Ubuntu, Debiana, RHEL, macOS itd.

Można je pobrać z: https://downloads.cisecurity.org/#/

CIS Benchmarks stanowią jedne z najbardziej szanowanych i powszechnie uznawanych na świecie wytycznych dotyczących bezpiecznej konfiguracji systemów IT. Ponieważ są one opracowywane na drodze globalnego konsensusu niezależnych ekspertów, eliminują subiektywizm w ocenie tego, co oznacza "bezpieczny system", dostarczając obiektywny i mierzalny punkt odniesienia. Wykorzystanie tych wytycznych nadaje projektowi wysoce profesjonalny wymiar, udowadniając znajomość standardów, które na co dzień stanowią fundament bezpieczeństwa w największych korporacjach oraz instytucjach rządowych.

Projekt z wykorzystaniem CIS Benchmarks
Oparcie projektu z dziedziny cyberbezpieczeństwa na standardach Center for Internet Security (CIS) to doskonały sposób na połączenie wiedzy akademickiej z najlepszymi praktykami rynkowymi.

Skrajnie można ograniczyć projekt do „przeklikania ustawień”, ale to absolutny minimalizm (niezbyt ciekawy i uciążliwy w wykonaniu). Ciekawy projekt to pokazanie różnicy między systemem przed i po hardeningu oraz automatyczna weryfikacja, które zalecenia zostały spełnione.

Jak mógłby wyglądać projekt
Nie trzeba wymyślać szczegółowego tematu, ale ogólnie brzmiałby on „Analiza i implementacja mechanizmów hardeningu systemu operacyjnego na podstawie CIS Benchmark”. (Można też sformułować go bardziej praktycznie, np. „Automatyzacja bezpiecznej konfiguracji systemu Windows/Linux zgodnie z CIS Benchmark”).

Projekt wyglądałby tak, że:

tworzysz czystą maszynę wirtualną, np. Windows 11 albo Ubuntu;

wybierasz odpowiedni CIS Benchmark;

robisz początkowy audyt konfiguracji;

pokazujesz kilka przykładowych słabości/niezgodności;

wprowadzasz zalecane ustawienia hardeningu;

ponownie wykonujesz audyt;

porównujesz wynik przed/po;

opcjonalnie automatyzujesz cały proces skryptem.

Nie bez znaczenie jest to, że CIS rozróżnia m.in. poziomy Level 1 i Level 2 — Level 1 obejmuje podstawowe ustawienia, które powinny powodować niewielkie ograniczenia funkcjonalności, natomiast Level 2 jest bardziej restrykcyjny.

Pomocne może być to, że w przypadku Windows CIS ma nawet Build Kits, które służą do automatyzacji hardeningu, m.in. poprzez GPO; dla środowisk Unix/Linux wykorzystywane są skrypty Bash. Jednak zdecydowanie warto choć raz pewne rzeczy zrobić samodzielnie - ręcznie. W przeciwnym razie ani się tego dobrze nie zapamięta, ani nie zrozumie.

Ile czasu?
Zależy od ambicji:

Wersja	Zakres	Czas
🟢 Podstawowa	VM + kilkanaście zaleceń + demonstracja	15–25 h
🟡 Dobra praca studencka	pełny benchmark/wybrana sekcja + audyt + hardening + raport	30–50 h
🟠 Bardzo dobra	własne skrypty automatyzujące + raport before/after	50–80 h
🔴 Projekt rozbudowany	narzędzie audytujące, raportowanie, kilka systemów	80–120+ h
Na typowy projekt semestralny 30–60 godzin jest moim zdaniem bardzo rozsądnym zakresem.

Co będzie potrzebne?
Sprzęt
Praktycznie wystarczy zwykły komputer:

16 GB RAM — komfortowo,

8 GB — też da się zrobić przy odpowiednim doborze VM,

kilkadziesiąt GB wolnego miejsca,

procesor obsługujący wirtualizację.

Oprogramowanie
Możesz użyć:

VirtualBox, VMware, …, albo dowolnych kontenerów,

system operacyjny dla którego masz CIS Benchmark (Windows 11, Ubuntu, …)

PowerShell w przypadku Windows, pewnie Bash w przypadku Linux,

coś do wersjonowania skryptów (np. git).

Dokumentacja
Najważniejszym źródłem będzie odpowiedni CIS Benchmark. CIS udostępnia benchmarki bezpłatnie do zastosowań niekomercyjnych, choć pobranie wymaga obecnie konta CIS. (Mi nie przysyłają spamu, a jedynie informacje o nowościach co jest dość przydatne). Zwróć uwagę, że przykładowo dla Windows 11 CIS ma obecnie benchmarki dla Windows 11 Enterprise i Standalone.

Co można pokazać na obronie? (Jak rozliczyć realizację projektu?)
To jest chyba największa zaleta tego tematu, że daje coś wymiernego i użytecznego na koniec. Szczegóły demonstracji będą się różnić, ale ideowo można to wyobrazić sobie w następujący sposób.

Możesz uruchomić VM i powiedzieć:

„Przed zastosowaniem hardeningu system spełniał 58% wybranych wymagań.”

Następnie uruchamiasz skrypt i ponownie wykonujesz audyt.

Przed:  58 / 100
Po:     91 / 100
A następnie pokazujesz konkretne ustawienia, np. politykę haseł, blokadę konta po nieudanych próbach logowania, konfigurację audytu zdarzeń, ustawienia zapory itd. To daje bardzo czytelny efekt „przed → zmiana → po”.

Oczywiście trzeba potrafić wytłumaczyć się z wszystkiego, a odpowiedź w stylu “bo tu jest tak napisane” lub “zostało to zrobione w sposób opisany tam” jest głęboko niesatysfakcjonująca.

Czy można jakoś trochę inaczej?
Projekt będzie oceniany przez prowadzącego, więc zdecydowanie nie próbowałbym implementować wszystkich kilkuset zaleceń CIS. To szybko zrobi się żmudne.

Wybrałbym np. 15–25 zaleceń i podzielił je na kategorie:

konta i uwierzytelnianie,

polityka haseł,

audyt i logowanie,

usługi systemowe,

firewall,

uprawnienia,

bezpieczeństwo sieci,

mechanizmy ochrony przed nieautoryzowanym dostępem.

Dla każdego z nich:

stan początkowy (sposób weryfikacji?) → sposób poprawy (CIS) → stan końcowy (sposób weryfikacji?) → wpływ na bezpieczeństwo.

Wtedy projekt jest nie tylko administracyjny, ale ma też część analityczną.

Można też porównać dwa systemy
I spróbować projektem odpowiedzieć na pytanie „Czy proces hardeningu systemów A i B zgodnie z CIS Benchmark można w podobnym stopniu zautomatyzować?”. (W zasadzie to już byłby naprawdę ciekawy temat na pracę z cyber).

Jak to wszystko ocenić?
Sama liczba zaimplementowanych zaleceń byłaby słabą metryką. Można przecież „odhaczyć” 100 prostych rekomendacji i zrobić gorszy projekt niż ktoś, kto dobrze zaimplementuje i zbada 20 trudniejszych.

Projekt może być znacznie ciekawszy niż „zaimplementowano 37 z 50 zaleceń, więc 74%.”

Proponowany model oceny
Załóżmy, że wybierasz np. 25–40 zaleceń CIS dla jednego systemu.

Kryterium	Waga	Jak mierzyć
Pokrycie zaleceń CIS	20%	% wybranych rekomendacji zaimplementowanych
Poprawność implementacji	25%	% zaleceń, które rzeczywiście spełniają wymagania CIS
Automatyzacja	15%	ile czynności można wykonać automatycznie
Weryfikacja / audyt	15%	czy potrafisz automatycznie sprawdzić stan systemu
Wpływ na bezpieczeństwo	10%	zmiana wyniku audytu / liczby niezgodności
Dokumentacja i reprodukowalność	10%	czy inna osoba może odtworzyć eksperyment
Jakość techniczna	5%	jakość skryptów, obsługa błędów, struktura itd.
Kilka wyjaśnień do modelu oceny
Metryka „compliance score”
Dla każdego zalecenia określasz stan:

0 — niespełnione,

1 — częściowo spełnione,

2 — spełnione.

Przykładowo:

CIS	Zalecenie	Przed	Po
1.1.1	konfiguracja X	0	2
1.1.2	konfiguracja Y	0	2
1.1.3	konfiguracja Z	1	2
2.3.1	konfiguracja A	0	2
2.3.2	konfiguracja B	0	0
Możesz wtedy policzyć “poziom zgodności”, np: przed hardeningiem: 48%, po hardeningu: 91%

To daje konkretny i bardzo łatwy do pokazania wynik eksperymentu.

Zgodność z CIS a jakość projektu
Projekt może osiągnąć np. 95% zgodności z CIS i nadal być kiepski, jeżeli ktoś tylko ręcznie przeklikał ustawienia.

Dla uczciwego systemu oceny potrzebny jest jakiś “quality score” na podstawie:

poprawności,

automatyzacji,

testów,

dokumentacji,

reprodukowalności,

analizy skutków ubocznych.

To daje bardzo uczciwy system oceny.

Metryka automatyzacji implementacji
Można zdefiniować ją jako “liczba zaleceń możliwych do zastosowania automatycznie” przez “liczba wszystkich zastosowanych zaleceń”.

Metryka automatyzacji weryfikacji
Można ją określić podobnie (jak wyżej).

Czy to już projekt inżynierski?
Przykład:

Metryka	Wynik
Zaleceń	40
Automatycznie wdrażanych	34/40 = 85%
Automatycznie weryfikowanych	38/40 = 95%
Spełnionych po hardeningu	36/40 = 90%
To już wygląda jak rzeczywisty projekt inżynierski.

Warto mierzyć regresję
To może być bardzo dobry element projektu, którego często brakuje w prostych demonstracjach hardeningu.

Załóżmy, że zastosowano 40 ustawień.

Potem wykonujesz testy i okazuje się, że:

firewall działa,

logowanie działa,

użytkownik może się zalogować,

wymagania dotyczące haseł działają,

wybrane usługi nadal funkcjonują.

Czyli mamy nie tylko odpowiedź na pytanie „Czy system jest bardziej bezpieczny?”, ale również na pytanie „Czy zwiększenie bezpieczeństwa nie zepsuło funkcjonalności?”

Można więc prowadzić “współczynnik regresji” np.: “ilość testów funkcjonalnych zakończonych niepowodzeniem” przez “liczbę wszystkich testów”.

(Idealnie ten współczynnik powinien być 0% i to byłby bardzo mocny wynik demonstracyjny).

A co z “trudnością” zaleceń?
Nie wszystkie zalecenia są równoważne.

Możesz przypisać im punkty:

Poziom	Punkty
łatwe	1
średnie	2
trudne	3
bardzo trudne	5
Wtedy zamiast

„Zaimplementowałem 30 zaleceń”

raportujesz:

„Zaimplementowano 30 zaleceń o łącznej wadze 74 pkt.”

To jest znacznie bardziej miarodajne.

Możesz również uwzględnić wpływ na bezpieczeństwo. Byłaby to suma po wszystkich zaleceniach: ich trudność pomnożona przez znaczenie dla bezpieczeństwa. Oczywiście trzeba wtedy dobrze uzasadnić sposób przyznawania wag.

Najlepszy wariant to eksperyment porównawczy
Mając np. 80 godzin zrobiłbym projekt mniej więcej tak:

Etap 1 — przygotowanie (VM z czystym systemem, wybór np. 30–40 zaleceń CIS, przygotowanie testów).

Etap 2 — baseline (robisz audyt).

Etap 3 — implementacja (tworzysz własny mechanizm hardeningu).

Etap 4 — weryfikacja (robisz audyt).

Etap 5 — testy regresyjne (sprawdzasz, czy po hardeningu system nadal wykonuje określone funkcje).

Porównujesz:

 	Przed	Po
zgodność z CIS	52%	91%
automatyzacja implementacji	0%	87%
weryfikacja automatyczna	0%	95%
testy funkcjonalne	100%	98%
czas	60 min	8 min
I właśnie te wyniki są sednem projektu.
