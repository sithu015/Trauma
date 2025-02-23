# Stellen Sie Trojan mithilfe einer serverlosen CF-Arbeiter und Seiten ein

🇮🇷[persisch](README.fa.md)  
🇹🇷[Türkisch](README.tr.md)  
🇬🇧[Englisch](README.md)  
🇩🇪[Deutschland](README.de.md)

Dies ist ein Skript, das auf der CloudFlare Worker -Plattform basiert. Basierend auf der Originalversion wird es so geändert, dass die Trojan -Konfigurationsinformationen angezeigt und in Abonnementinhalte umwandelt werden. Mit diesem Skript können Sie die Trojan -Konfigurationsinformationen einfach in Tools wie Clash oder Singbox mithilfe der Online -Konfiguration konvertieren.

[TG -Kanal](https://t.me/F_NiREvil)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Inhaltsverzeichnis

-   [Arbeitnehmer -Bereitstellungsmethode](#Workers-deployment-method)
-   [Seiten für die Bereitstellungsmethode](#Pages-deployment-method)
-   [Proxyip](#proxyIP)
-   [Umgebungsvariable Beschreibung](#Environment-variables-description)
-   [Video -Tutorials](#Video-tutorials)![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<details>
<summary> Use </summary>

-   Dieses Projekt wurde nur für Lern-, Forschungs- und Sicherheitstestzwecke entwickelt und entwickelt. Ziel ist es, Sicherheitsforscher, Akademikern und Technologie -Enthusiasten mit einem Tool zum Verständnis und zu praktizieren, um Netzwerkkommunikationstechnologie zu verstehen und zu praktizieren.
    </details>

<details>
<summary> Legality </summary>
  
  - Users must comply with local laws and regulations when downloading and using this project.
  - Users are responsible for ensuring that their actions comply with the laws, regulations and other applicable requirements of their region

</details>

<details>
<summary> Risk warning </summary>
  - Avoid leaking node configuration information by submitting false node configurations to the subscription service 
</details>

## Arbeitnehmer -Bereitstellungsmethode

1.  Cloudflare Worker bereitstellen:

    -   Erstellen Sie einen neuen Arbeiter in der Cloudflare Worker -Konsole.

    -   Wille[Worker.js](_worker.js)Fügen Sie den Inhalt in den Worker -Editor ein.

    -   Zeile ändern 3`password`Ändern Sie es in Ihren eigenen**password**

    -   Alternativ können Sie auf die Schaltfläche unten klicken, um sie direkt bereitzustellen.

    [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/Trauma)

2.  Vorzugsroute hinzufügen:
    -   Geben`addresses`Fügen Sie den bevorzugten Domänennamen/bevorzugten sauberen IP gemäß dem Format hinzu. Wenn es keine Portnummer gibt, beträgt der Standard -TLS -Port 443 und das # Zeichen ist der Bemerkung -Alias, zum Beispiel:
        ```js
        let addresses = [
        // any Domain or clean IPv4/IPv6 addresses from cloudflare is usable, no sweat.
        'cdnjs.com:443#N1',
        'www.wto.org:2053#N2',
        'sky.rethinkdns.com#N3',
        'creativecommons.org#N4',
        '[2606:4700:310c::ac42:2c39]#N5 √IPv6',
        ];
        ```

3.  Zugriff auf Abonnementinhalte:
    -   Zugang`https://[YOUR-WORKERS-URL]/[password]`Holen Sie sich Abonnementinhalte.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto`Dies ist Ihre universelle adaptive Abonnementadresse.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?sub`Base64 -Abonnementformat, geeignet für Passwall, SSR+usw.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?clash`Clash -Abonnementformat, geeignet für OpenClash, etc.
    -   Zum Beispiel`https://vless.trauma.workers.dev/auto?sb`Singbox -Abonnementformat, geeignet für Singbox, etc.

4.  Binden Sie eine benutzerdefinierte Domäne an Arbeiter:
    -   In der Arbeiterkonsole`trigger`Registerkarte, klicken Sie unten`Add a custom domain`。
    -   Füllen Sie den Namen der sekundären Domain ein, den Sie in den CloudFlare -Domain -Namensauflösungsdienst übertragen haben, z. B.:`vless.trauma.com`Nach Klick`Add a custom domain`Warten Sie einfach, bis das Zertifikat wirksam wird.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Seiten für die Bereitstellungsmethode

1.  Bereitstellen von Cloudflare -Seiten:
    -   Gabel[Dieses Projekt auf GitHub](https://github.com/NiREvil/Trauma/fork)
    -   Wählen Sie in der Cloudflare Pages -Konsole aus`Connected to Git`Danach wählen Sie`trauma`Klicken Sie nach dem Artikel nach`Start setting up`。
    -   existieren`Setting up build and deployment`Wählen Sie unten auf der Seite aus`Environment variables (advanced)`später verschmelzen[Fügen Sie Variablen hinzu](#Environment-variables-description),
    -   Füllen Sie den variablen Namen aus**PASSWORT**, der Wert ist Ihr Passwort, dann klicken Sie dann auf`Save and deploy`Das war's.

2.  Vorzugsroute hinzufügen:
    -   Fügen Sie Variablen hinzu`ADD`Lokale statische bevorzugte Zeile, wenn es keine Portnummer gibt, beträgt der Standard -TLS -Port 443, und auf die # Nummer folgt ein Bemerkung -Alias, zum Beispiel:
        ```js
        discord.com#You can just put the domain name as follows
        www.speedtest.net:443#N1
        speed.cloudflare.com#N2
        zula.ir#N3
        creativecommons.org:2053#N4
        sky.rethinkdns.com#N5
        104.17.152.41#IPv4 is available
        [2606:4700:310c::ac42:2c39]#also IPv6
        ```

3.  Zugriff auf Abonnementinhalte:
    -   Zugang`https://[YOUR-PAGES-URL]/[password]`Abonnementinhalte sind verfügbar.
    -   Zum Beispiel`https://trauma.pages.dev/auto`Dies ist Ihre universelle adaptive Abonnementadresse.
    -   Zum Beispiel`https://trauma.pages.dev/auto?sub`Base64 -Abonnementformat, geeignet für Passwall, SSR+usw.
    -   Zum Beispiel`https://trauma.pages.dev/auto?clash`Clash -Abonnementformat, geeignet für OpenClash, etc.
    -   Zum Beispiel`https://trauma.pages.dev/auto?sb`Singbox -Abonnementformat, geeignet für Singbox, etc.

4.  Binden Sie die CNAME -benutzerdefinierte Domäne an Seiten:
    -   In der Seitenkonsole`Custom domains`Registerkarte, klicken Sie unten`Set up a custom domain`.
    -   Geben Sie Ihren benutzerdefinierten Sekundärdomainnamen ein. Achten Sie darauf, dass Sie Ihren Root -Domänennamen nicht verwenden, z. B.:
    -   Der von Ihnen zugewiesene Domain -Name ist`fuck.cloudns.biz`Fügen Sie dann ein benutzerdefiniertes Feld hinzu, um auszufüllen`iran.fuck.cloudns.biz`Das war's;
    -   Nach Anforderungen von CloudFlare wird Ihr Domain -Name DNS -Dienstanbieter zurückgegeben und die benutzerdefinierte Domain hinzugefügt.`trauma`Cname -Aufzeichnung von`trauma.pages.dev`Danach klicken Sie`Activate Domain`Das war's.

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## Proxyip

1.  Wenn Sie auf Cloudflare -Seiten bereitgestellt werden, können Sie Proxyip in der 4. Zeile von festlegen`_worker.js`Datei. oder setzen Sie die Umgebungsvariable, variabler Name ist`PROXYIP`

2.  Wenn Sie in Worker.dev bereitgestellt werden, können Sie Proxyip in der 4. Zeile von festlegen`_worker.js`Datei. oder setzen Sie die Umgebungsvariable, variabler Name ist`proxyIP`

### So finden Sie Proxyip

[Lassen Sie es hier sehen](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)

## Umgebungsvariablen Beschreibung

> [!NOTIZ]Nur zwei von ihnen sind ausreichend, die erste Variable`PASSWORD`und die zweite`PROXYIP`, Variablen, die in der folgenden Tabelle aufgeführt sind, dienen nur zu Bildungszwecken und zusätzlichen Erklärungen.![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

| Variabler Name                                                                                     | Beispiel                                                                                                                    | Bemerkung                                                                                                                               |
| -------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| PASSWORT                                                                                           | Auto                                                                                                                        | Kann jeden Wert nehmen                                                                                                                  |
| Proxyip                                                                                            | `bpb.radically.pro`oder alles andere, was Sie wollen[Siehe hier](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md) | Alternativer Proxyknoten zum Zugriff auf CFCDN -Websites (unterstützt mehrere Proxyips mit 1 oder 2 Zeilenumbrüten zwischen Proxyips))) |
| HINZUFÜGEN                                                                                         | `zula.ir,www.wto.org:2053`                                                                                                  | Lokale bevorzugte Domänenname/bevorzugte IP (unterstützt mehrere Elemente`,`oder Linieneinspeise als Intervall)                         |
| Fügt hinzu                                                                                         | <https://raw.githubusercontent.com/NiREvil/Trauma/main/cleanIPs.txt>                                                        | Keine Notwendigkeit zu erklären, jeder versteht                                                                                         |
| Nachfolgend                                                                                        | SUBAPI.fxxk.dedyn.io                                                                                                        | Clash, Singbox usw. Abonnement Conversion Backend                                                                                       |
| Subname                                                                                            | Revil                                                                                                                       | Abonnementname                                                                                                                          |
| ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256) | ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)                          | ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)                                      |

* * *

## Video -Tutorials

<https://github.com/NiREvil/Trauma/assets/126243832/92a430c3-4884-4831-bf8c-e328cfd78af8>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f20a0215-bd75-4302-89dd-90a5bdd75cbc>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f63c74c9-0e86-40a2-8894-e027c06776f5>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/61ce0b14-2c26-4325-a6c0-6f12cfc608d7>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

# dankbar

[ca110us](https://github.com/ca110us/epeius)\|[Sterilisieren Sie es](https://github.com/3Kmfi6HP/EDtunnel/tree/trojan)\|[Zizifn](https://github.com/zizifn/edgetunnel)\|[Jemen 178](https://github.com/emn178/js-sha256)\|[ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)\|[SHEGS1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)
