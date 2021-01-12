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
Aby nadać sobie, lub komuś innemu permisje wejdź do pliku server.cfg i odszukaj następującej linijki:
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
