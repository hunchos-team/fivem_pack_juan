<div align="center">
	<img src="logo.gif" alt="Hunchos">
	<br>
	<h4>
		<a href="https://hunchos.store/">Dokumentacja</a>
	</h4>
</div>

### Instalacja

Aby zacząć korzystać z naszej paczki pierwsze co musisz posiadać to wygenerowany klucz hunchos. Aby to zrobić stwórz ticket na naszym discordzie (https://dc.hunchos.store/) i podaj tam adres ip na który mamy ją wygenerować. Po otrzymaniu klucza koniecznie go zapisz!

Następnie wygeneruj klucz steam web api key (https://steamcommunity.com/dev/apikey), oraz klucz licencyjny fivem (https://keymaster.fivem.net/)

Wszystkie klucze wpisujesz w pliku server.cfg :
> - klucz hunchos - set hunchos_key "klucz" 
> - steam web api key - set steam_webApiKey "klucz" 
> - keymaster fivem - sv_licenseKey klucz 

Ostatnią rzeczą jaką musisz ustawić w server.cfg to połączenie z bazą danych. Aby to zrobić znajdź linijkę `set mysql_connection_string`  i uzupełnij ją w następujący sposób : `"server=adres_ip_twojej_bazy;database=nazwa_twojej_bazy;userid=nazwa_uzytkownika;password=hasło"`

Cała linijka powinna wyglądać mniej więcej tak:
```
set mysql_connection_string "server=123.123.123;database=bazadanych_1;userid=uzytkownik_1;password=tajne_haslo" #[Połączenie z bazą]#
```

### Nadawanie permisji
Aby nadać sobie, lub komuś innemu permisje wejdź do pliku server.cfg i odszukaj następującą linijkę:
```
##############################################################
#                     ADMINISTRATORZY                        #
##############################################################

///Admin1///
add_principal identifier.steam:TWÓJ_HEX group.god  
add_principal identifier.steam:TWÓJ_HEX group.admin
```
Teraz wystarczy, że pole `TWÓJ_HEX` podmienisz na hexa osoby, której chcesz nadać permisje. Po restarcie serwera, będzie ona mogła korzystac z komend administracyjnych i EasyAdmina.

(Hexa najlepiej brać ze strony http://vacbanned.com/)

### Jaki skrypt za co odpowiada?
- recoil, driveby - 'strzelanie'
- ruch na mieście - 'traffic'
- hud - 'route68'
- wygląd hudu - 'esx_menu_default', 'esx_menu_dialog', 'esx_menu_list'
- narkotyki - 'esx_drugs', 'dragi'
- sprzedawanie narkotyków - 'menu'
- wybór postaci - 'postacie'

### Podstawowe komendy administracyjne
- /setjob id_gracza nazwa_pracy numer_rangi - Nadawanie pracy dla konkretnego gracza | przykład: /setjob 2 police 3
- /car nazwa_modelu - Respienie wybranego pojazdu | przykład: /car t20
- /setmoney id_gracza ilość_pieniędzy - Dawanie określonej ilości gotówki dla gracza | przykład: /setmoney 2 10000
- /dv - Usuwa pojazd w którym siedzimy
- /revive id_gracza - Ożywia wybranego gracza | przykład: /revive 2
- /heal id_gracza - Odnawia zdrowie wybranego gracza | przykład: /heal 2
- /giveweapon id_gracza nazwa_broni ilość_amunicji | Nazwy broni należy brać ze strony https://wiki.rage.mp/index.php?title=Weapons | przykład: /giveweapon 2 weapon_pistol 200

### Nazwy wszystkich prac

Aby zdobyć nazwę danej pracy należy w pierwszej kolejności wejść w tabele `jobs` następnie kliknąc w checkbox'a "Pokaż wszystko" i wyszukać nazwy pracy, która Ciebie interesuje.
> Ważne: Aby nadać komuś tą pracę musisz brać nazwę z kolumny `name`, czyli przykładowo `police`, a nie `Policja`

Aby wyszukać nazwę i numer odpowiadający za daną rangę wejdź do tabeli `job_grades` i tak jak poprzednio zaznacz checkbox'a "Pokaż wszystko". Następnie wyszukaj nazwę pracy z poprzedniej tabeli i będziesz miał wszystkie rangi, wraz z ich numerami :)
> Ważne: Numer rangi odpowiada danym z kolumny `grade`

### Klawiszologia
- f1 - menu postaci
- f2 - ekwipunek
- f3 - telefon
- f5 - zmiana zasięgu rozmowy
- f6 - menu frakcyjne/gangowe
- delete - tablet policyjny


# Potrzebuje pomocy z paczką - co mam zrobić?
- Najważniejsze - "Kto pyta nie bładzi!", dlatego jeżeli nie wiesz jak coś edytować, lub boisz się, że coś zepsujesz to dopytaj się kogoś, lub nas na tickecie - Bez problemu pomożemy z naprawą błędów, lub zmianą skryptów.

# Jak powinno wyglądać zgłoszenie błędu?
- Przykład poprawnego zgłoszenia: `Cześć, dzisiaj po edycji skryptu esx_shops wywaliło mi błąd w konsoli serwera: [HypeSQL] Tabela `shop_inventory` nie istnieje. [SCREEN Z KONSOLI]. Pod f8 nie występują żadne błędy. Co mam zrobić?`
