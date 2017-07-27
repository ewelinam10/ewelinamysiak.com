---
layout: post
title:  "Zapisywanie danych aplikacji - TinyDB"
---
{% highlight ruby %}
TinyDB tinyDB = new TinyDB();
tinyDB.putInt("example_of_value",2);
int data = tinyDB.get("example_of_value");
{% endhighlight %}

Wygląda prosto? Poznaj i zakochaj się w świetnej alternatywie przechowywania informacji pomiędzy uruchomieniami aplikacji.

Aby w przechwycić, pobrać lub zapisać dane w trakcie wykonywania się aplikacji, ale nie tylko pomiędzy aktywnościami, ale stale przy każdym kolejnym uruchomieniu się aplikacji, najczęstszymi rozwiązaniami są SharedPreferences lub SQLite , jednak gdy tylko zaczniemy czytać w jaki sposób je wykorzystać lub jeżeli już dobrze je znamy , nie są to szczególnie dla początkujących  najkrótsze  prz najprostsze rozwiązania . A co jeśli można byłoby tak w trzech linijkach kodu - STWORZYĆ, ZAPISAĆ I ODCZYTAĆ dane? Brzmi pięknie , nieprawdaż ? To właśnie umożliwia nam klasa TinyDB.

Największa zaletą jej prostoty, a zatem rozwiązaniem na problem który ja szukałam jest szybki i banalny  zapis danych takich jak obiektów, tablic obiektów. Podczas gdy przy używaniu SharedPreferences musimy iterować po tablicy, parsować obiekty na Jsony ( tak naprawdę to właśnie za nas robi ta napisana klasa) .

A więc :
TinyDB tinydb = new TinyDB(this); // tworzymy baze
tinydb.putInt("wartosc_klucza",6); //zapisujemy w bazie wartosc 6 pod nazwa wartosc_klucza
int wartosc = tinydb.getInt("wartosc_klucza"); //pobieramy za pomoca nazwy klucza zapisana wartosc

Inne możliwe typy do zapisu ( pobieranie analogicznie jak powyżej) :
tinydb.putFloat("jakasNazwaKlucza", 6.6f);
tinydb.putLong("x", 66666L);
tinydb.putString("y", "Tak naprawdę to koty zawsze mają Ale ");
tinydb.putBoolean("z", true);
tinydb.putList("key", jakaśTablica);
tinydb.putImagePNG("zamek", "zamek.png", lunchBitmap);
tinydb.putObject("zamek_blyskawiczny",jakisObiekt);
tinydb.putListObject("a",jakasListaObiektow);

3 kroki które pozwolą Ci używać tej klasy :
