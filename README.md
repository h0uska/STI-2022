Dokument Specifikace Požadavků
STI
Semestrální práce
Zadání

Aplikace bude simulovat chování tzv. botů. Bude mít dvě části, klientskou a serverovou.

Klientská část:

    umožnit komunikaci se serverovou částí formou grafického režimu
    Umožnit poslat zprávu serveru a zobrazit odpověď serverové částí
    zobrazovat odpověď ve formátu HTML

Serverová část:

    serverová část zpracovává dotazy chodící z klientské části
        jaký je čas
        jak se jmenuji (bot - serverová část)
        aktuální kurz EUR vůči CZK
    serverová a klientská část běží na jiném hostu

Je možné použít libovolné programovací jazyk a nástroje.
O aplikaci

Celá aplikace je v angličtině. Aplikace je rozdělena na serverovou a klientskou část.
Klientská část bude desktopová aplikace naprogramována v C# a serverová část poběží na
serveru https://www.endora.cz/. Účelem této aplikace je uživateli umožnit posílat zprávy
(dotazy) na server, který uživateli odpovídá a zobrazovat dotazy a odpověď do klientské části
ve formě chatu. Klientská část ukazuje uživateli historii dotazů a odpovědí dokud není
ukončena. Server posílá odpověď pouze uživateli, který se na dotaz zeptal. Uživatel se může
ptát na 4 dotazy a to:

    jaký je čas
    jak se jmenuji (bot - serverová část)
    aktuální kurz EUR vůči CZK
    historie kurzu EUR vůči CZK

Klientská část bude zobrazovat historii otázek a odpovědí, pole pro zápis dotazu a tlačítko
pro odeslání dotazu.
P ožadavky

Pro porovnání kurzu EUR vůči CZK se budou používat data z adres:
https://www.cnb.cz/cs/financni-trhy/devizovy-trh/kurzy-devizoveho-trhu/kurzy-devizoveho-
trhu/denni_kurz.txt;jsessionid=51434B515C33C368A4D0DE79932EF99C?date=DD.MM.R
RRR
Pro bezproblémový chod je nutné, aby struktura stahovaných dat zůstala stejná, jako je
specifikováno níže. Pokud se formát dat změní, není možné garantovat, že aplikace bude
fungovat bez problémů.
Formát dat z ČNB :

Z těchto dat budou použity položky ”datum“ (ve formátu DD.MM.RRRR) a položky řádku
s kódem měny EUR a to:
“množství”, “kód” (kód měny) a “kurz” (kurz měny vůči CZK).
Server si bude ukládat tato data do textového souboru “historie_meny“ ve formátu TXT, kdy
každý řádek bude obsahovat položku ”datum“ (ve formátu DD.MM.RRRR) ), “množství”,
“kód” (kód měny) a “kurz” (kurz měny vůči CZK). Všechna tato data budou oddělena
středníkem. Historie měny se ukládá od té doby, co se spustí server.

    Na dotaz ”jaký je čas” bude klientská část zobrazovat uživateli odpověď ve formátu
    ”the time is hh:mm” (čas serveru).
    Na dotaz ”jak se jmenuji (bot - serverová část)” bude klientská část zobrazovat
    uživateli odpověď ve formátu ”my name is jmenoServeru” (jméno serveru).
    Na dotaz ”aktuální kurz EUR vůči CZK” bude klientská část zobrazovat uživateli
    odpověď ve formátu ”exchange rate of 1 kodMeny to CZK is kurzMenyVuciCZK
    (datumPoslednihoZaznamuKurzu)”.
    Na dotaz ”historie kurzu EUR vůči CZK” bude klientská část zobrazovat uživateli
    data v jednoduché tabulce a to konkrétně:
    ”datum“ (ve formátu DD.MM.RRRR) a “kurz” (kurz měny při množství 1 vůči CZK)

Podmínky:
 Pokud je v jedné zprávě více než jeden dotaz, potom klientská část posílá serveru
pouze první nalezený dotaz ve zprávě.
 Pokud není ve zprávě uveden žádný dotaz, potom klientská část uživateli zobrazí
nápovědu.
 Pokud server neodpoví, potom bude klientská část zobrazovat odpověď “the server is
not answering“.
Aktualizace dat:

Při prvním spuštění serveru se data “historie_meny“ aktualizují okamžitě, aby se do aplikace
dostali data k zobrazení pro ten daný den. Pokud dojde při stahování těchto dat k chybě, nebo
pokud nejsou data pro daný den zatím dostupná, server se je pokusí obnovit každých 60
minut, dokud data pro daný den nejsou nalezena.
Dotazy uživatele :

    Pokud se uživatel ptá na dotaz “jaký je čas“, potom jeho dotaz musí obsahovat slova
    “what“ a “time“ a to přesně jak jsou uvedena.
    Pokud se uživatel ptá na dotaz “jak se jmenuji (bot - serverová část)“, potom jeho
    dotaz musí obsahovat slova “what“ a “name“ a to přesně jak jsou uvedena.
    Pokud se uživatel ptá na dotaz “aktuální kurz EUR vůči CZK“, potom jeho dotaz
    musí obsahovat slova “current“ a “EUR“ a to přesně jak jsou uvedena.
    Pokud se uživatel ptá na dotaz “historie kurzu EUR vůči CZK“, potom jeho dotaz
    musí obsahovat slova, “history“ a “EUR“ a to přesně jak jsou uvedena.

O mezení a jiné specifikace

    Klientská část je vytvořena pro systém WINDOWS 10 (64 bit) a není zaručena
    funkčnost na jiném systému.
    Je dáno, že zařízení, na kterém klientská část poběží bude mít alespoň 8 GB RAM a
    minimálně dvoujádrový CPU.
    Klientská část bude odevzdána v ZIP souboru.
    Maximální velikost klientské části je 5 00 MB.
    Programování a testování serverové a klientské části potrvá přibližně 12 0 hodin.

