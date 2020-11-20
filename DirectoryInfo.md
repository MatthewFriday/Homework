# DirectoryInfo class
Mappák és almappák létrehozásához, mozgatásához, listázásához használható metódusokat és funkciókat tartalmaz.

*Ezt az osztályt nem lehet bővíteni. (örökléssel)*

## Használat
Mielőtt használhatnánk az osztály nyújtotta lehetőségeket, használnunk kell a névterét. Ezt könnyedén megtehetjük a fájl elején a `using` direktívával:

     using System.IO;

Ezt követően létrehozunk egy példányt az osztályból:

    DirectoryInfo di = new DirectoryInfo(@"C:\MyDir");

Innentől a létrehozott példány segítségével dolgozhatunk a megadott mappával.

## Tulajdonságok
Egy példány tulajdonságain (property) keresztül információkat tudhatunk meg a megadott mappáról.

\# **Attributes** *(enum)*  
Lekéri vagy beállítja a mappára beállított [attribútumokat](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileattributes?view=net-5.0) (pl.: Hidden - a mappa rejtett).

\# **CreationTime** *(DateTime)*  
Lekéri vagy beállítja a mappa létrehozásának időpontját.

*Példa a mappa létrehozása óta eltelt idő kiírásával:*

    DateTime dirCreatedDt = di.CreationTime;
    TimeSpan timeSince = DateTime.Now - dirCreatedDt;

    Console.WriteLine($"A mappát {timeSince.TotalDays} napja hozták létre.");

\# **CreationTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a mappa létrehozásának időpontját univerzális időzóna alapján.

\# **Exists** *(bool)*  
Ellenőrzi, hogy a mappa létezik-e.

*Példa a felhasználó által megadott mappa létezésének ellenőzésével:*

    if (!di.Exists)
        Console.WriteLine("A megadott mappa nem létezik!");

\# **FullName** *(string)*  
Lekéri a mappa teljes *(abszolút)* útvonalát.

*Hasznos lehet ha a példány létrehozásakor a mappát relatív útvonallal adtuk meg és szükségünk van az abszolút útvonalra.*

\# **LastAccessTime** *(DateTime)*  
Lekéri vagy beállítja a mappához való utolsó hozzáférés időpontját.

\# **LastAccessTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a mappához való utolsó hozzáférés időpontját univerzális időzóna alapján.

\# **LastWriteTime** *(DateTime)*  
Lekéri vagy beállítja a mappa utolsó módosításának időpontját.

\# **LastWriteTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a mappa utolsó módosításának időpontját univerzális időzóna alapján.

\# **Name** *(string)*  
Lekéri a mappa nevét.

\# **Parent** *(DirectoryInfo)*  
Lekéri a mappa szülőkönyvtárának *DirectoryInfo* példányát.

\# **Root** *(DirectoryInfo)*  
Lekéri a meghajtó vagy fájlrendszer gyökérkönyvtárának *DirectoryInfo* példányát, amely a megadott mappát tartalmazza.

## Metódusok
A DirectoryClass metódusai különböző műveleteket hajtanak végre a mappát vagy annak az almappáin.

*Ez a lista csak a fontosabb metódusokat tartalmazza!*

\# **Create()**  
Létrehozza a megadott mappát, ha az nem létezik.

\# **CreateSubdirectory(String path)**  
Létrehoz egy almappát a megadott mappán belül.

*Visszatérési érték:* A létrehozott mappa DirectoryInfo példánya

\# **Delete()**  
Törli a megadott mappát.

\# **GetDirectories()**  
Lekéri a megadott mappa összes almappáját.

*Visszatérési érték:* [DirectoryInfo] tömb

\# **GetFiles()**  
Lekéri a megadott mappában tárolt összes fájlt.

*Visszatérési érték:* [FileInfo] tömb

\# **MoveTo(String path)**  
Áthelyezi a megadott mappát a megadott helyre.
