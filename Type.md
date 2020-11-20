# Type class
Típus deklarációkat reprezentál: osztály típus, interfész típus, tömb típus, érték típus, lista típus, típus paraméter, általános típus definíciók;

## Használat
Ha egy objektum típusát akarjuk lekérni a `typeof()` operátort használjuk:

     Type t = typeof(String);


## Tulajdonságok
Egy példány tulajdonságain (property) keresztül információkat tudhatunk meg a megadott típusról.

*Ez a lista csak a fontosabb property-ket tartalmazza!*

\# **Is\<category\>** *(bool)*  
Lekéri hogy a megadott típus besorolható-e a metódus nevében leírt kategóriába.
*Kategóriák példul:* Array, Class, Abstract, Enum

\# **IsVisible** *(bool)*  
Lekéri hogy a megadott típus elérhető-e a jelenlegi Assembly-n kívüli kódból.

\# **Module** *(string)*  
Lekéri a megadott típust tartalmazó modul (DLL vagy EXE fájl) nevét.

\# **Namespace** *(string)*  
Lekéri a megadott típus névterét.

## Metódusok
A FileInfo class metódusai különböző műveleteket hajtanak végre a fájlon.

*Ez a lista csak a fontosabb metódusokat tartalmazza!*

\# **GetConstructors()**  
Visszaadja a megadott típus publikus konstruktorait.

*Visszatérési érték:* ConstructorInfo[] tömb

\# **GetEnumNames()**  
Visszaadja a megadott enum típus neveit.

*Visszatérési érték:* String[] tömb

\# **GetEnumValues()**  
Visszaadja a megadott enum típus értékeit.

*Visszatérési érték:* Array

\# **GetInterfaces()**  
Visszaadja a megadott típus által használt interface-eket.

*Visszatérési érték:* Típe[] tömb

\# **GetMethods()**  
Visszaadja a megadott típus metódusait.

*Visszatérési érték:* MethodInfo[] tömb

\# **GetProperty()**  
Visszaadja a megadott típus tulajdonságait.

*Visszatérési érték:* PropertyInfo[] tömb
