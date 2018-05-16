---
title: 'Pierwsze kroki z usługą Cloud Databases'
slug: pierwsze-kroki-z-clouddb
excerpt: 'Dowiedz się, jak rozpocząć korzystanie z rozwiązania CloudDB'
section: 'Pierwsze kroki'
---

**Ostatnia aktualizacja dnia 2018-05-15**

## Wprowadzenie

Rozwiązanie Cloud Databases (w skrócie CloudDB) umożliwia korzystanie z baz danych zainstalowanych na instancji, której zasoby są dedykowane i gwarantowane. Usługa ta oferuje więcej wydajności i elastyczności. Przeznaczona jest dla klientów o specyficznych potrzebach.

**Dowiedz się, jak rozpocząć korzystanie z rozwiązania CloudDB.**

## Wymagania początkowe

- Posiadanie [instancji Cloud Databases](https://www.ovh.pl/cloud/cloud-databases/){.external}
- Dostęp do [Panelu klienta OVH](https://www.ovh.com/auth/?action=gotomanager){.external}

## W praktyce

### Wyświetlanie informacji ogólnych o instancji

W menu usług po lewej stronie [Panelu klienta](https://www.ovh.com/auth/?action=gotomanager){.external}, przejdź do sekcji [Bazy danych](https://www.ovh.com/auth/?action=gotomanager){.external}, a następnie kliknij nazwę instancji. Następnie przejdź do sekcji `Informacje ogólne`{.action}.

> [!primary]
>
> Nazwa usługi CloudDB w Panelu klienta zawiera część Twojego identyfikatora klienta i kończy się trzema cyframi (001 dla pierwszej zainstalowanej usługi CloudDB, 002 dla drugiej, etc.).
>

W zakładce tej znajdziesz ważne informacje dotyczące Twojej instancji. Sprawdź, czy wyświetlające się dane są poprawne i czy są zgodne z poniższymi parametrami.

|Informacja|Szczegóły|
|---|---|
|Status usługi|Pokazuje, czy instancja jest uruchomiona, w trakcie restartu czy zawieszona. Twoja instancja musi być uruchomiona, abyś mógł przeprowadzać na niej działania.|
|Typ|Pokazuje system baz danych używany przez serwer.|
|Wersja|Pokazuje wersję systemu baz danych używanego przez serwer. Upewnij się, czy Twoja strona WWW jest kompatybilna z wybraną wersją.|
|RAM|Pokazuje pamięć operacyjną dostępną dla Twojej instancji oraz ewentualne przekroczenia pamięci. Twoja instancja CloudDB dysponuje dedykowaną i gwarantowaną pamięcią RAM. Jeśli zajdzie taka potrzeba, możesz zwiększyć pamięć RAM. Możesz również ustawić alert o jej całkowitym zużyciu.|
|Infrastruktura|Pokazuje infrastrukturę używaną przez Twoją instancję. Jest to wewnętrzne oznaczenie infrastruktury OVH.|
|Centrum danych|Pokazuje centrum danych, w którym została uruchomiona instancja. Upewnij się, czy Twoja instancja jest uruchomiona w tym samym centrum danych, co hosting, na którym jest (lub zostanie) utworzona Twoja strona WWW.|
|Host|Pokazuje serwer OVH, na którym utworzona została instancja. Jest to wewnętrzne oznaczenie OVH, które może pojawić się w komunikatach dotyczących [prac modernizacyjnych i potencjalnych incydentów OVH](http://travaux.ovh.net/){.external}.|

![cloud databases - bazy danych na instancji](images/clouddb-general-information.png){.thumbnail}

### Utworzenie bazy danych

> [!primary]
>
> Etap ten nie dotyczy systemu baz danych Redis.
>

Aby utworzyć pierwszą bazę danych na Twojej instancji CloudDB, kliknij zakładkę `Bazy danych`{.action}, następnie przycisk `Dodaj bazę danych`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-database.png){.thumbnail}

Wyświetli się okno służące do utworzenia bazy danych. Możesz w nim również:

-  **utworzyć użytkownika**: użytkownik będzie mógł wykonywać zapytania do bazy danych (odczyt, zapis czy usunięcie danych).

- **dodać autoryzowany adres IP**: żądania pochodzące z tego adresu będą uprawnione do uzyskiwania dostępu do bazy danych.

W zależności od dokonanego wyboru, uzupełnij wymagane informacje, po czym kliknij `Zatwierdź`{.action}.

|Informacja|Opis|
|---|---|
|Nazwa bazy danych|Podaj nazwę Twojej przyszłej bazy danych.|
|Nazwa użytkownika|Podaj nazwę użytkownika, który będzie miał uprawnienia do logowania się do bazy i wykonywania zapytań (opcjonalne, jeśli kratka „*Utwórz użytkownika*” nie jest zaznaczona).|
|Uprawnienia|Określ zakres uprawnień powiązanych z użytkownikiem. W przypadku użytku standardowego wybierz opcję `Administrator`{.action} (opcjonalne, jeśli kratka „*Utwórz użytkownika*” nie jest zaznaczona).|
|Hasło|Wybierz hasło, następnie potwierdź je (opcjonalne, jeśli kratka „*Utwórz użytkownika*” nie jest zaznaczona).|
|IP/maska|Wprowadź adres IP lub maskę IP serwera lub serwerów, które będą miały prawo dostępu do Twoich baz danych (opcjonalne, jeśli kratka „*Dodaj autoryzowany adres IP*” nie jest zaznaczona).|

> [!warning]
>
> Przy zapisywaniu informacji zalecamy zastosowanie zwyczajowych zasad bezpieczeństwa.
>

![cloud databases - bazy danych na instancji](images/clouddb-add-database-step2.png){.thumbnail}

### Tworzenie użytkownika

> [!primary]
>
> Etap ten nie dotyczy systemu baz danych Redis.
>

Jeśli utworzyłeś jednocześnie użytkownika i bazę danych podczas poprzedniej operacji, etap ten jest opcjonalny. Należy jednak pamiętać, że w przypadku specyficznego projektu może okazać się konieczne, aby kilku uprawnionych użytkowników wykonywało operacje w Twojej bazie danych. Na przykład jeden z użytkowników może mieć uprawnienia do zapisu i odczytu, podczas gdy inny będzie będzie miał uprawnienia wyłącznie do odczytu.

Jeśli Twój projekt nie wymaga utworzenia dodatkowych użytkowników, możesz przejść do kolejnej operacji. Aby utworzyć nowego użytkownika, kliknij zakładkę `Użytkownicy i uprawnienia`{.action}, następnie przycisk `Dodaj użytkownika`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-user.png){.thumbnail}

Uzupełnij informacje w oknie, które się wyświetli, następnie kliknij `Zatwierdź`{.action}.

|Informacja|Opis|
|---|---|
|Nazwa użytkownika|Podaj nazwę użytkownika, który będzie miał prawo logować się do Twojej instancji. Następnie przypisz mu uprawnienia do wykonywania czynności w Twojej bazie danych.|
|Hasło|Wybierz hasło, a następnie je potwierdź.|

> [!warning]
>
> Przy zapisywaniu informacji zalecamy zastosowanie zwyczajowych zasad bezpieczeństwa.
>

![cloud databases - bazy danych na instancji](images/clouddb-add-user-step2.png){.thumbnail}

Po utworzeniu użytkownika przypisz mu uprawnienia do wykonywania czynności w bazie danych (takie jak uprawnienia do odczytu, zapisu lub usuwania danych). W tym celu kliknij ikonkę koła zębatego, a następnie kliknij `Zarządzaj uprawnieniami`{.action}. Wybierz odpowiednie uprawnienia. W przypadku standardowego użycia wybierz opcję `Administrator`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-rights.png){.thumbnail}

### Import bazy danych OVH

> [!primary]
>
> Etap ten ma zastosowanie, jeśli chcesz zaimportować kopię zapasową już istniejącej bazy danych. Jeśli ten przypadek Cię nie dotyczy, przejdź do kolejnej operacji. 
>

Istnieje kilka metod importu bazy danych. Narzędzie służące do importu dostępne jest w Panelu klienta. Możesz jednak użyć innego narzędzia, zgodnie z Twoimi preferencjami i wiedzą.

Poniższe etapy opisują, jak zaimportować bazę danych przy użyciu narzędzia dostępnego w Panelu klienta.

- **Etap 1: dostęp do interfejsu importu**

Przejdź do zakładki `Bazy danych`{.action}, kliknij ikonkę koła zębatego, a następnie kliknij `Importuj plik`{.action}. W oknie, które się wyświetli zaznacz kratkę `Importuj nowy plik`{.action}, po czym kliknij `Dalej`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-import-step1.png){.thumbnail}

- **Etap 2: wysyłanie pliku z kopią zapasową**

Wprowadź nazwę pliku, która pozwoli Ci zidentyfikować tę kopię zapasową później, jeśli będziesz chciał odtworzyć z niej bazę. Następnie, obok opcji **Plik**, wybierz plik z kopią zapasową bazy danych na Twoim komputerze, a następnie kliknij `Wyślij`{.action}. Odczekaj, aż interfejs wskaże, że plik został pomyślnie wysłany, następnie kliknij przycisk `Dalej`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-import-step2.png){.thumbnail}

- **Etap 3: import bazy danych**

Wybierz, lub nie, dodatkowe opcje opisane poniżej, a następnie kliknij `Zatwierdź`{.action}.

|Opcje dodatkowe|Opis |
|---|---|
|Opróżnij aktualną bazę danych|Bieżąca zawartość bazy danych zostanie w całości usunięta, a następnie zastąpiona zawartością z kopii zapasowej.|
|Wyślij powiadomienie e-mail po zakończeniu importu|Otrzymasz powiadomienie e-mail, gdy import bazy danych zostanie zakończony.|

![cloud databases - bazy danych na instancji](images/clouddb-add-import-step3.png){.thumbnail} 

### Autoryzacja adresu IP

Aby uzyskać dostęp do instancji CloudDB, należy wskazać adresy IP lub zakresy adresów IP, które mogą się łączyć z Twoimi bazami danych.  Aby to zrobić, przejdź do zakładki `Autoryzowane adresy IP`{.action}, następnie kliknij `Dodaj adres IP/maskę`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-ip.png){.thumbnail}

W oknie, które się wyświetli wskaż adres IP lub maskę, którą chcesz autoryzować w `IP/maska`{.action}. Możesz również dodać opis. Zdecyduj, czy chcesz udzielić dostępu wyłącznie do baz danych czy również do SFTP. Następnie kliknij `Zatwierdź`{.action}.

![cloud databases - bazy danych na instancji](images/clouddb-add-ip-step2.png){.thumbnail}

### Powiązanie strony WWW z bazą danych

Teraz, gdy Twoja baza danych została utworzona, jeden lub więcej użytkowników mają uprawnienia do wykonywania w niej operacji, przynajmniej jeden adres IP ma prawo dostępu do Twojej instancji CloudDB, pozostaje połączyć bazę danych ze stroną WWW. Możesz to zrobić na wiele sposobów, w zależności od Twojej strony WWW lub CMS (WordPress, Joomla!, etc...) czy też od bieżącego etapu tworzenia strony WWW.

Aby pomyślnie zakończyć tę operację, potrzebne Ci będą następujące informacje:

|Informacja|Opis |
|---|---|
|Nazwa bazy danych|Jest to nazwa, którą określiłeś podczas tworzenia bazy danych. Listę wszystkich baz danych utworzonych w instancji CloudDB znajdziesz w zakładce `Bazy danych`{.action}.|
|Nazwa użytkownika|Jest to nazwa, którą określiłeś podczas tworzenia bazy danych lub ewentualnie nazwa użytkownika dodatkowego, którego utworzyłeś. Listę wszystkich użytkowników utworzonych w instancji CloudDB znajdziesz w zakładce `Użytkownicy i uprawnienia`{.action}.|
|Hasło użytkownika|Jest to hasło przypisane podczas tworzenia użytkownika.|
|Nazwa hosta|Jest to nazwa serwera, którą należy wprowadzić, aby Twoja strona WWW mogła się łączyć z Twoją bazą danych. Informacja ta jest dostępna w Panelu klienta w zakładce `Informacje ogólne`{.action} w części **Informacje o dostępie**.|
|Port serwera|Jest to port do połączenia z Twoją instancją CloudDB, dzięki czemu twoja strona WWW może połączyć się z Twoją bazą danych. Informacja ta jest dostępna w Panelu klienta w zakładce `Informacje ogólne`{.action} w części **Informacje o dostępie**.|

> [!warning]
>
> W rzadkich przypadkach pole `port`{.action} może się nie pojawić w konfiguracji Twojej strony WWW. Jeśli taki przypadek wystąpi, pole to należy dodać po nazwie hosta. Dane te muszą być oddzielone dwukropkiem *:* (na przykład: nazwahosta: port).
>

![cloud databases - bazy danych na instancji](images/clouddb-login-information.png){.thumbnail}

## Sprawdź również

Przyłącz się do społeczności naszych użytkowników na stronie <https://community.ovh.com/en/>.