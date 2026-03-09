# Gobuster - brute force subdirectories

- Předchozí page:
    
    [Mr Robot vulnerable hack](../Mr%20Robot%20vulnerable%20hack%2031c7b30bf2e6809c9451ca422ba90f51.md)
    

<aside>

Cílem použití tohoto nástroje je zjistit nějaké užitečné informace a vytvořit si nějakou útočnou plochu

</aside>

- **Co řeším:** Zjištění prvotních informací, se kterými mohu pracovat
- **Cíl / očekávaný výsledek:** Nalezení užitečných subdirectories

## ✅ Postup krok za krokem

1. Použití gobuster nástroje - obrázek výstupu /

```bash
gobuster dir -u http://10.38.1.110 -w /usr/share/wordlists/dirb/common.txt
```

![Snímek obrazovky 2026-03-07 083714.png](Gobuster%20-%20brute%20force%20subdirectories/Snmek_obrazovky_2026-03-07_083714.png)

[Procházení subdirectories](Proch%C3%A1zen%C3%AD%20subdirectories%2031c7b30bf2e6804897c8c73e34382277.md)