---
layout: posts
title:  "Nowe przepisy wydawania i aktualizowania aplikacji w sklepie Google Play"
categories : Android
comments: true
---

Na twórców aplikacji w systemie Android, publikujących swoje aplikacje w sklepie Google Play czekają zmiany i o ile dopiero zamierzamy stworzyć taką aplikację - wystarczy mieć świadomość tej zmiany i zgodnie z nią stworzyć nasz projekt. Większe komplikacje pojawią się w przypadku, gdy aplikacja jest już troche starsza i utrzymywana, lub po prostu niepisana pod najnowsze API. Posiadacze już własnych aplikacji w sklepie Google Play, prawodpodobnie otrzymali takiego maila:
![email](/assets/images/posts/2/email_google_play.png){: .center-image}

Każda nowa (od sierpnia 2018) i aktualizowana (od października 2018) aplikacja musi być budowana na poziomie API 26 lub więcej, czyli pod Androida Oreo 8.0. Powstała zmiana ma zapewnić, że wszystkie aplikacje dostępne w sklepie są budowane na najnowszych wersjach API - które są zoptymalizowane pod względem bezpieczeństwa i wydajności. Wkońcu każda nowa werjsa wprowadza jakeiś ulepszenia,a w ten sposób programiści zostaną w jakiś sposób przymuszeni do ich używania. ;)
Pod jakie APi budowana jest nasza aplikacja określa wpis  **"targetSdk"** -  w pliku **build.Gradle** (lub w innym pliku konfiguracyjnym, jeśli posiadamy inny tryb budowania).

# minSdkVersion <= targetSdkVersion <= compileSdkVersion
To reguła według jakich powinno być ustalane budowanie aplikacji, z racji tego że nazwy niejednoznacznie nakreślają czym różnią się od siebie w ramach przypomnienia:
* **minSdkVersion** - minmalna wersja sdk pod którą aplikacja będzie działać
* **targetSdkVersion** - w pełni przetestowana aplikacja na której na pewno będzie działać
* **compileSdkVersion** - najnowsza stabilna dostępna wersja sdk

A więc przykładowa część pliku build.Gradle powinien wyglądać tak:

{% highlight xml %}
android {
  compileSdkVersion 26
  buildToolsVersion “27.0.3”

  defaultConfig {
    applicationId “com.example.ewelinamysiak"
    minSdkVersion 15
    targetSdkVersion 26
    versionCode 1
    versionName “1.0”
  }
}
{% endhighlight xml %}
