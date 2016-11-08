---

copyright:
  years: 2016
lastupdated:  "2016-10-14"
---

#	Developer Pro-Plan verwenden
{: #using_mobilefoundation_p3}

<!--Last updated: 14 October 2016
{: .last-updated}-->

{{site.data.keyword.mobilefoundation_short}}: Developer Pro richtet sich vorallem an die Anwendungsentwicklung im Team und das Testen von Anwendungen; dieser Plan ist nicht für die Produktion gedacht.

Einige Sekunden nach der Erstellung der Serviceinstanz von {{site.data.keyword.mobilefoundation_short}}: Developer Pro können Sie auf die Seite `Übersicht` in {{site.data.keyword.Bluemix_notm}} zugreifen. Dort stehen Lernprogramme und Videos zum Einstieg in die Verwendung des {{site.data.keyword.mobilefoundation_short}}-Service zur Verfügung.

## Voraussetzungen
{: #prerequisites_p3}

Beachten Sie Folgendes, bevor Sie die Serviceinstanz von {{site.data.keyword.mobilefoundation_short}}: Developer Pro konfigurieren.
* {{site.data.keyword.mobilefoundation_short}}: Developer Pro wird nur von {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional (Unterstützung für OLTP) {{site.data.keyword.Bluemix_notm}}-Plänen unterstützt.

* Sie benötigen Zugriff auf die Berechtigungsnachweise der {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz, bevor Sie die Einstellungen für die {{site.data.keyword.mobilefoundation_short}}-Serviceinstanz konfigurieren.

**Hinweis**: Die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz kann sich in jedem `Bereich` in Ihrer {{site.data.keyword.Bluemix_notm}}-`Organisation` bzw. in jeder anderen `Organisation`, auf die Sie zugreifen können, befinden. Stellen Sie sicher, dass Sie über die Berechtigungen für den Zugriff auf den `Bereich` verfügen, in dem sich die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz befindet.


## Datenbankverbindung hinzufügen
{: #configure_dashdb_p3}

###  Erste Schritte
{: #firststeps_p3}

Führen Sie nach der Erstellung der Serviceinstanz von {{site.data.keyword.mobilefoundation_short}}: Developer Pro die nachfolgend beschriebene Prozedur aus, um mit der Verwendung des Service zu beginnen.

### Stellen Sie eine Verbindung zur {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz her.
{: #connect_dashdb_p3}

Nachdem die Serviceinstanz {{site.data.keyword.mobilefoundation_short}}: Developer Pro erstellt wurde, sehen Sie die Seite *Übersicht*, auf der Sie die Verbindungsinformationen für die Serviceinstanz {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional angeben müssen.

1. Wählen Sie die {{site.data.keyword.Bluemix_notm}} `Organisation` aus, in der sich die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz befindet.

+ Wählen Sie den {{site.data.keyword.Bluemix_notm}}-`Bereich`, in dem sich die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz befindet, in der Liste der Bereiche aus, die in der ausgewählten `Organisation` verfügbar sind.

**Hinweis:** Wenn die `Organisation` und der `Bereich`, in denen sich Ihre {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz befindet, nicht aufgeführt sind, prüfen Sie, ob Sie ein Mitglied der betreffenden `Organisation` bzw. des betreffenden `Bereichs` sind.

+ Wählen Sie den `Servicenamen` und die `Berechtigungsnachweise` für {{site.data.keyword.dashdbshort_notm}} aus, um eine Verbindung zur vorhandenen {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz herzustellen.

+  Testen Sie die Verbindung zur angegebenen {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional-Serviceinstanz.

+  Klicken Sie auf **Hinzufügen**. Mit dieser Aktion werden die erforderlichen Tabellen in der konfigurierten {{site.data.keyword.dashdbshort_notm}}-Datenbankserviceinstanz erstellt.

**Hinweis**: Sie können die {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz, die zur Verwendung durch die {{site.data.keyword.mobilefoundation_short}}-Serviceinstanz konfiguriert ist, nicht ändern. Sie können jedoch dieselbe {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz für mehrere {{site.data.keyword.mobilefoundation_short}}-Serviceinstanzen verwenden, da jede {{site.data.keyword.mobilefoundation_short}}-Serviceinstanz ein eigenes Schema in der ausgewählten {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz erstellt.

* Nach einigen Sekunden können Sie auf die Seite `Übersicht` zugreifen, auf der die Lernprogramme und Videos zur Verfügung stehen, die Sie beim Einstieg in die Verwendung des {{site.data.keyword.mobilefoundation_short}}-Service unterstützten.

## {{site.data.keyword.mobilefirst}}-Server starten
{: #start_mobilefoundation_p3}

* Um den {{site.data.keyword.mfserver_short_notm}} mit den Standardeinstellungen zu starten, klicken Sie auf **Basisserver starten**.

* Diese Auswahl stellt einen {{site.data.keyword.mfserver_long_notm}} mit den folgenden Einstellungen bereit:
    - Einzelner Knoten mit 1 GB Hauptspeicher. Diese Größe ist für Entwicklungs- und kleinere Testaktivitäten sowie für kleinere Produktionsworkloads ausreichend.

    -	`Benutzername` und `Kennwort` werden automatisch für Sie generiert. Sie können darauf zugreifen, wenn der Server betriebsbereit ist.

Der Prozess der Bereitstellung Ihres Servers wird gestartet. Dieser Prozess dauert ungefähr 10 Minuten;
in einem Nachrichtenfenster wird der Fortschritt dieser Operation angezeigt. Ist der Vorgang abgeschlossen, wird ein Dashboard mit folgenden
Informationen angezeigt:

  -	Status Ihres Servers, der ausgeführt wird (Zustand, Größe).

  -	Für Sie erstellte Serverroute. Verwenden Sie diese Route in Ihrer mobilen Anwendung, um eine Verbindung zum {{site.data.keyword.mfserver_short_notm}} herzustellen.

  -	Ihr persönlicher `Benutzername` und das `Kennwort` für den Zugriff auf die {{site.data.keyword.mfp_oc_short_notm}}. Das `Kennwort` wird ausgeblendet. Klicken Sie auf das Symbol **Kennwort anzeigen**, um es einzublenden.

*	Klicken Sie auf **Konsole starten**, um die {{site.data.keyword.mfp_oc_short_notm}} zu öffnen.


<!--This console runs inside the container.--> Mit der Konsole können Sie Ihre mobilen Apps, Adapter und Geräte verwalten, Ihren Server als mobiles Back-End verwenden, Push-Benachrichtigungen senden usw.

##  Mobile Analytics-Server hinzufügen
{: #adding_analytics_server_p3}

 Sie können Ihre mobile Anwendung nun auf dem {{site.data.keyword.mobilefirst}}-Server überwachen, indem Sie einen Mobile Analytics-Server zur Instanz des Service {{site.data.keyword.mobilefoundation_short}} hinzufügen.

 Durch den Developer Pro-Plan wird der Mobile Analytics-Server in einer Containergruppe erstellt; der Benutzer kann die Konfiguration durch Auswahl der Anzahl von Containerknoten in der Containergruppe anpassen.

 Benutzer können auch Datenträger an die Container anhängen, um Daten dauerhaft zu speichern. Wird ein Datenträger einmal ausgewählt, kann er nicht mehr geändert werden. 20 GB Speicherplatz für die Dateifreigabe stehen dem Benutzer standardmäßig zur Verfügung. Benötigt der Benutzer zusätzlichen Speicherplatz, um die Analysedaten dauerhaft zu speichern, muss er weiteren Speicherplatz für die Dateifreigabe erwerben und mit dieser Dateifreigabe einen Datenträger erstellen. Anschließend kann er diesen neuen Datenträger auswählen und den Analyseserver bereitstellen.

 Weitere Informationen zum Hinzufügen von Datenträgern zu {{site.data.keyword.containerlong}} finden Sie im Abschnitt zum [Persistenten Speichern von Daten auf einem Datenträger über das {{site.data.keyword.Bluemix_notm}}-Dashboard](https://new-console.ng.bluemix.net/docs/containers/container_volumes_ui.html){: new_window}.

* Klicken Sie auf die Option zum Hinzufügen der Analyse, um den Mobile Analytics-Server zur Instanz des {{site.data.keyword.mobilefoundation_short}}-Service hinzuzufügen.

* Sie können die Mobile Analytics-Serverkonfiguration verwenden; für die Analytics-Serverkonfiguration werden ein Minimum von 1 GB und ein Maximum von 2 GB unterstützt. Der Analytics-Server wird bei diesem Plan nur auf einem einzigen Knoten unterstützt.

Der Prozess der Bereitstellung wird gestartet. Dieser Prozess dauert ungefähr 10 Minuten; in einem Nachrichtenfenster wird der Fortschritt dieser Operation angezeigt.  

* Starten Sie die MobileFirst Analytics Console über die {{site.data.keyword.mfp_oc_short_notm}}.

* Für den {{site.data.keyword.mfserver_short_notm}} und den Mobile Analytics-Server ist Single Sign-on aktiviert. Der Mobile Analytics-Server ist mit denselben LTPA-Schlüsseln und denselben Benutzerberechtigungen konfiguriert wie der {{site.data.keyword.mfserver_short_notm}}. Sie können für die Anmeldung an der Mobile Analytics Console den `Benutzernamen` und das `Kennwort` verwenden, die Sie auch für die Anmeldung bei der {{site.data.keyword.mfp_oc_short_notm}} verwendet haben.

Weitere Informationen zu MobileFirst Analytics finden Sie unter [MobileFirst Foundation Operational Analytics](https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/8.0/analytics/).

**Anmerkung:** Der Mobile Analytics-Server wird entfernt, wenn Sie die Instanz des Service {{site.data.keyword.mobilefoundation_short}} löschen oder wenn Sie versuchen, den {{site.data.keyword.mfserver_short_notm}} erneut zu erstellen.

## {{site.data.keyword.mobilefirst}} Server erneut erstellen
{: #recreate_mobilefoundation_p3}

*	Klicken Sie auf die Schaltfläche **Neu erstellen**, um den Server erneut zu erstellen.

* Diese Aktion stoppt Ihre vorhandenen Server und löscht die Daten. Eine neue Serverinstanz wird mit einer aktualisierten Version erstellt, falls verfügbar. Diese Aktion nimmt einige Minuten in Anspruch.

**Hinweis**: Alle Daten der vorherigen Serverinstanz, einschließlich Informationen zu den Apps und Adaptern, werden in der konfigurierten {{site.data.keyword.dashdbshort_notm}}-Serviceinstanz beibehalten; diese Daten werden zur erneuten Erstellung des Servers verwendet.

##	Erweiterte Konfiguration einrichten
{: #using_mfs_advanced_p3}

Mit der Option **Server mit erweiterter Konfiguration starten** auf der Seite `Übersicht` können Sie einen Server mit erweiterten oder benutzerdefinierten Einstellungen erstellen. Sie können die
Servereinstellungen auch aktualisieren, um Ihre Serverkonfiguration anzupassen; klicken Sie hierfür auf die
Registerkarte **Konfiguration**. {{site.data.keyword.mobilefoundation_short}} bietet Ihnen Zugriff auf einige erweiterte Einstellungen.

*	Auf der Registerkarte **Topologie** können Sie die Servergröße und den Hauptspeicher auswählen, die den jeweiligen Anforderungen entsprechen. Der Standardserver wird mit 1 GB Hauptspeicher erstellt.
  - Sie können den Hauptspeicher für Ihren Server in Abhängigkeit von Ihrem Bedarf auf höchstens 2 GB vergrößern.

  - **Knoten** zeigt die Anzahl der erstellten Knoten an. Dieses Feld kann in {{site.data.keyword.mobilefoundation_short}}: Developer Pro nicht bearbeitet werden. Die Anzahl der Knoten <!--in your {{site.data.keyword.IBM_notm}} container group--> beträgt standardmäßig **1** im Developer Pro-Plan.

Weitere Details finden Sie in der [{{site.data.keyword.mobilefoundation_long}}-Dokumentation](https://www.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html){: new_window}.