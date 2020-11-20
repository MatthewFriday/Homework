# FileInfo class
Fájlok létrehozásához, mozgatásához, törléséhez, megnyitásához használható metódusokat és funkciókat tartalmaz.

*Ezt az osztályt nem lehet bővíteni. (örökléssel)*

## Használat
Mielőtt használhatnánk az osztály nyújtotta lehetőségeket, használnunk kell a névterét. Ezt könnyedén megtehetjük a fájl elején a `using` direktívával:

     using System.IO;

Ezt követően létrehozunk egy példányt az osztályból:

    FileInfo fi = new FileInfo(@"C:\MyFile.txt");

Innentől a létrehozott példány segítségével dolgozhatunk a megadott mappával.

## Tulajdonságok
Egy példány tulajdonságain (property) keresztül információkat tudhatunk meg a megadott fájlról.

\# **Attributes** *(enum)*  
Lekéri vagy beállítja a fájlra beállított [attribútumokat](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileattributes?view=net-5.0) (pl.: Hidden - rejtett fájl).

\# **CreationTime** *(DateTime)*  
Lekéri vagy beállítja a fájl létrehozásának időpontját.

*Példa a fájl létrehozása óta eltelt idő kiírásával:*

    DateTime fileCreatedDt = fi.CreationTime;
    TimeSpan timeSince = DateTime.Now - fileCreatedDt;

    Console.WriteLine($"A fájlt {timeSince.TotalDays} napja hozták létre.");

\# **CreationTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a fájl létrehozásának időpontját univerzális időzóna alapján.

\# **Directory** *(DirectoryInfo)*  
Lekéri a fájl szülőkönyvtárának *DirectoryInfo* példányát.

\# **DirectoryName** *(string)*  
Lekéri a fájl szülőkönyvtárának abszolút elérési útvonalát.

\# **Exists** *(bool)*  
Ellenőrzi, hogy a fájl létezik-e.

*Példa a felhasználó által megadott fájl létezésének ellenőzésével:*

    if (!fi.Exists)
        Console.WriteLine("A megadott fájl nem létezik!");

\# **Extension** *(string)*  
Lekéri a fájl kiterjesztését.

\# **FullName** *(string)*  
Lekéri a fájl teljes *(abszolút)* útvonalát.

*Hasznos lehet ha a példány létrehozásakor a fájlt relatív útvonallal adtuk meg és szükségünk van az abszolút útvonalra.*

\# **IsReadOnly** *(bool)*  
Lekéri,, hogy a fájl csak olvasható vagy írható is.

\# **LastAccessTime** *(DateTime)*  
Lekéri vagy beállítja a fájlhoz való utolsó hozzáférés időpontját.

\# **LastAccessTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a fájlhoz való utolsó hozzáférés időpontját univerzális időzóna alapján.

\# **LastWriteTime** *(DateTime)*  
Lekéri vagy beállítja a fájl utolsó módosításának időpontját.

\# **LastWriteTimeUtc** *(DateTime)*  
Lekéri vagy beállítja a fájl utolsó módosításának időpontját univerzális időzóna alapján.

\# **Name** *(string)*  
Lekéri a fájl nevét.

## Metódusok
A FileInfo class metódusai különböző műveleteket hajtanak végre a fájlon.

*Ez a lista csak a fontosabb metódusokat tartalmazza!*

\# **AppendText()**  
Bővíti a megadott fájlt egy *StreamWriter* segítségével.

*Visszatérési érték:* StreamWriter

\# **CopyTo(String path)**  
Másolja a megadott fájlt a megadott helyre.

\# **Create()**  
Létrehozza a megadott fájlt, ha az nem létezik.

\# **Decrypt()**  
Visszafejti az *Encrypt()* metódus által titkosított fájlt.

\# **Delete()**  
Törli a megadott fájlt.

\# **Encrypt()**  
Titkosítja a megadott fájlt, úgy hogy csak az titkosításkor bejelentkezett felhasználó tudja megnyitni.

\# **MoveTo(String path)**  
Áthelyezi a megadott fájlt a megadott helyre.

\# **OpenRead()**  
Megnyitja a fájlt olvasáshoz. (ReadOnly)

*Visszatérési érték:* FileStream

\# **OpenText()**  
Megnyitja a fájlt UTF8 kódolású szöveg olvasásához.

*Visszatérési érték:* StreamReader

\# **OpenWrite()**  
Megnyitja a fájlt íráshoz. (WriteOnly)

*Visszatérési érték:* FileStream
