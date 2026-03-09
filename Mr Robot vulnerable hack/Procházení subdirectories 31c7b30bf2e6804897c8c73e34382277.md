# Procházení subdirectories

<aside>

Procházení užitečných subdirectories, které jsme zjistili pomocí nástroje gobuster

- odkaz na gobuster page

[Gobuster - brute force subdirectories](Gobuster%20-%20brute%20force%20subdirectories%2031c7b30bf2e680cabfafee5eb730bf50.md)

</aside>

- **Co řeším:** Procházení užitečných subdirectories zjištěných z nástroje gobuster
- **Cíl / očekávaný výsledek:** Nalezení užitečných informací

## ✅ Postup krok za krokem

1. `/admin` 
    1. po načtení stránky se nic zatím nenachází, stránka se nekontrolovatelně restartuje
2. `/dashboard`
    1. po načtení stránky nás to přesune na wordpress login 
        1. po použití ctrl+u jsem zjistil možnou verzi wordpressu 4.3.1, později na internetu budu hledat nějaké zranitelnosti, které bych mohl použít
3. `/favicon.ico`
    1. rozhodl jsem se zkusit udělat hash favicon.ico a následně hash předat databázi s cílem nalezení užitečné informace (tento krok byl v tomto úkolu nepodstatný)
4. `/licence`
    1. po načtení stránky se zobrazil text: 
    `what you do just pull code from Rapid9 or some s@#% since when did you become a script kitty?`
5. `/phpmyadmin`
    1. po načtení stránky se zobrazil text: 
        
        `For security reasons, this URL is only accessible using localhost (127.0.0.1) as the hostname.`
        
6. `/robots.txt`
    1. po načtení stránky jsme získali první **flag** ze tří a soubor **fsocity.div**, který v sobě skrývá obří wordlist s 850 000 řádky
    
    Díky fsocity.div souboru jsme se mohli posunout dále v další kapitole:
    
    [Hydra ](Hydra%2031d7b30bf2e680f7a4b3e65b4a98e42a.md)
    

```bash
curl http://10.38.1.110/favicon.ico | md5sum
výstup příkazu d41d8cd98f00b204e9800998ecf8427e

výstup databáze: d41d8cd98f00b204e9800998ecf8427e:Zero byte favicon
```

## 💻 Příkazy

```bash
curl http://10.38.1.110/favicon.ico | md5sum
výstup příkazu d41d8cd98f00b204e9800998ecf8427e
```