---
title: 'Hosting www: .htaccess - Generowanie adresów za pomocą mod_rewrite'
excerpt: Mod_rewrite jest dostępny na wszystkich hostingach www OVH (z wyjątkiem 20gp).
id: '1971'
slug: hosting_www_htaccess_-_generowanie_adresow_za_pomoca_mod_rewrite
section: Przekierowania i uprawnienia dostępu
---


## Przekierowanie proste

- Edytuj plik .htaccess:


```
RewriteEngine On
RewriteRule .* testing.php
```



Ta formuła przekieruje każde zapytanie na skrypt testing.php.


- lub:


```
RewriteEngine On
RewriteRule letstest /test_wslash/testing.php
```



Ta formuła przekieruje każde zapytanie /letstest na skrypt /test_wslash/testing.php.


## Przekierowanie exemple.com na www.exemple.com

- Ta formuła wymusza adres strony typu www.exemple.com, co jest użyteczne w zakresie pozycjonowania:


```
RewriteEngine on
Rewritecond %{HTTP_HOST} ^exemple.com$
Rewriterule ^(.*) http://www.exemple.com/$1 [QSA,L,R=301]
```





## Przekierowanie na określony katalog bez wyświetlania nazwy katalogu

- Jeśli Twoja strona znajduje się w katalogu docelowym, formuła ta wymusza adres strony typu www.exemple.com, podczas gdy prawidłowy adres strony to: www.exemple.com/MonSite.


```
RewriteEngine on
Rewritecond %{HTTP_HOST} ^exemple.com
Rewritecond %{REQUEST_URI} !^/MonSite
Rewriterule ^(.*)$ /MonSite/
```





## Generowanie adresów
Moduł mod_rewrite pozwala na generowanie adresów URL.


- .htaccess:


```
RewriteEngine On
RewriteCond %{REQUEST_URI} !testing.php
RewriteRule (.*) testing.php?var=$1
```



Reguły te uruchamiają skrypt testing.php ze zmienną GET zawierającą URL podany przez użytkownika.


- php:


```
<?
print("testing server <br/>\n");
print("var: {$_GET['var']}\n");
?>
```





## Automatyczne przekierowanie użytkownika na stronę z SSL, gdy odwiedza on stronę nie zabezpieczoną.
Moduł mod_rewrite pozwala na generowanie adresów URL.


```
RewriteEngine on
Rewritecond %{HTTP_HOST} ^nom_domaine.tld$
Rewriterule ^(.*) https://ssl5.ovh.net/~login_ftp/$1 [QSA,L,R=301]
```



- Przekierowanie na stronę zabezpieczoną tylko w przypadku odwiedzania określonej strony:


```
RewriteEngine on
RewriteCond %{HTTP_HOST} ^nom_domaine.tld$
RewriteCond %{REQUEST_URI} ~094/page.php
RewriteRule ^(.*) https://ssl5.ovh.net/~login_ftp/$1 [QSA,L,R=301]
```




## Uwaga:
Aby poznać zabezpieczony adres Twojej oferty, [kliknij tutaj](https://www.ovh.pl/g1594.certyfikat-ssl-ovh).


## 
Aby przejść do przewodnika z ogólnymi informacjami o pliku .htaccess, [kliknij tutaj](https://www.ovh.pl/g1967.hosting_www_plik_htaccess)

