---

copyright:
  years: 2015, 2018
lastupdated: "2018-2-26"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Toolchains verwenden
{: #toolchains-using}

Offene Toolchains stehen in den öffentlichen und den dedizierten Umgebungen von {{site.data.keyword.Bluemix}} (Public bzw. Dedicated) zur Verfügung. Mithilfe einer Toolchain können Sie Ihre täglichen Entwicklungs-, Bereitstellungs- und Systemaufgaben produktiv abwickeln. Nach dem Einrichten einer Toolchain können Sie Toolintegrationen hinzufügen, löschen oder konfigurieren sowie den Zugriff auf die Toolchain verwalten.
{: shortdesc}

## Toolintegration konfigurieren
{: #configuring_a_tool_integration}

Wenn Sie die Konfiguration einer Toolintegration beim Erstellen einer Toolchain noch nicht vorgenommen haben, wird eine Schaltfläche **Konfigurieren** auf der zugehörigen Karte angezeigt. Wenn Sie beim Erstellen einer Toolchain eine Toolintegration konfiguriert haben, können Sie die Konfigurationseinstellungen aktualisieren.

1. Klicken Sie im DevOps-Dashboard auf der Seite **Toolchains** auf eine Toolchain, um die zugehörige Übersichtsseite anzuzeigen. Alternativ können Sie auf der Übersichtsseite der App auf der Karte für Continuous Delivery auf **Toolchain anzeigen** und dann auf **Übersicht** klicken.
1. Wenn Sie eine Toolintegration erstmalig konfigurieren müssen, klicken Sie auf der zugehörigen Karte auf **Konfigurieren**.

  ![Schaltfläche 'Konfigurieren'](images/toolchain_tile_configure.png)

 Wenn Sie die Konfiguration der Toolintegration abgeschlossen haben, klicken Sie auf **Integration speichern**.

1. Wenn Sie die Konfiguration einer Toolintegration aktualisieren müssen, klicken Sie auf der zugehörigen Karte auf das Menü, um auf die Konfigurationsoptionen zuzugreifen.

  ![Konfigurationsmenü](images/toolchain_tile_menu.png)

 **Tipp**: Einige Toolintegrationen sind vorkonfiguriert und erfordern keinerlei Konfigurationsparameter. Sie können die Konfigurationseinstellungen nur für die von Ihnen konfigurierten Toolintegrationen aktualisieren.

 Wenn Sie die Aktualisierung der Einstellungen abgeschlossen haben, klicken Sie auf **Integration speichern**. Informationen zum Konfigurieren spezifischer Toolintegrationen finden Sie in [Toolintegrationen konfigurieren](/docs/services/ContinuousDelivery/toolchains_integrations.html){: new_window}.

## Toolintegration hinzufügen
{: #adding_a_tool_integration}

Sie können Toolintegrationen für Ihre Toolchain hinzufügen und konfigurieren. Welche Toolintegrationen verfügbar sind, hängt davon ab, ob Sie {{site.data.keyword.Bluemix_notm}} Public oder {{site.data.keyword.Bluemix_notm}} Dedicated verwenden.

1. Klicken Sie im DevOps-Dashboard auf der Seite **Toolchains** auf eine Toolchain, um die zugehörige Übersichtsseite anzuzeigen. Alternativ können Sie auf der Übersichtsseite der App auf der Karte für Continuous Delivery auf **Toolchain anzeigen** und dann auf **Übersicht** klicken.
1. Klicken Sie auf **Tool hinzufügen**, um eine Liste von hinzuzufügenden Toolintegrationen anzuzeigen.
1. Klicken Sie auf eine Toolintegration, die Sie hinzufügen möchten.
1. Geben Sie alle erforderlichen Informationen zum Konfigurieren der Toolintegration ein.
1. Klicken Sie auf **Integration erstellen**, um die Toolintegration zu Ihrer Toolchain hinzuzufügen.

## Toolintegration löschen
{: #deleting_a_tool_integration}

Wenn Sie eine Toolintegration aus Ihrer Toolchain löschen, kann diese Löschung nicht mehr rückgängig gemacht werden.

1. Klicken Sie im DevOps-Dashboard auf der Seite **Toolchains** auf eine Toolchain, um die zugehörige Übersichtsseite anzuzeigen. Alternativ können Sie auf der Übersichtsseite der App auf der Karte für Continuous Delivery auf **Toolchain anzeigen** und dann auf **Übersicht** klicken.
1. Klicken Sie auf der Karte für die Toolintegration, die Sie löschen möchten, auf das Menü, um auf die Konfigurationsoptionen zuzugreifen.
1. Klicken Sie auf **Löschen**, um die Toolintegration aus Ihrer Toolchain zu löschen.
1. Bestätigen Sie dies, indem Sie nochmals auf **Löschen** klicken.  

## Zugriff verwalten
{: #managing_access}

Sie können Benutzern Zugriff auf eine Toolchain gewähren, indem Sie sie sowohl zu der Organisation (org) hinzufügen, der die Toolchain zugeordnet ist, als auch zu der Zugriffssteuerungsliste für die Toolchain. Jede Toolchain ist einer bestimmten Organisation zugeordnet und jeder Benutzer, der Mitglied dieser Organisation ist, kann für jede der zugeordneten Toolchains zu der Zugriffssteuerungsliste hinzugefügt werden. Die Organisation, in der Sie gegenwärtig arbeiten, wird auf der Menüleiste angezeigt. Wenn Sie auf andere Toolchains zugreifen wollen, wechseln Sie zu einer anderen Organisation.

**Tipp:** Sie müssen Benutzer zur Organisation der Toolchain in der Region hinzufügen, in der die Toolchain gehostet wird. Da Toolchains derzeit nur in der Region 'Vereinigte Staaten (Süden)' gehostet werden, müssen Sie der Organisation die Benutzer in der Region 'Vereinigte Staaten (Süden)' hinzufügen. Wenn die Toolchain für die Bereitstellung von Apps in anderen Regionen konfiguriert ist, wird sie auch weiterhin Apps in diesen Regionen bereitstellen.

Wenn Sie {{site.data.keyword.Bluemix_notm}} Dedicated für {{site.data.keyword.ghe_short}} verwenden und Benutzer zu Ihrer {{site.data.keyword.Bluemix_notm}}-Organisation und deren Bereichen hinzufügen, so können sich die Benutzer mit ihrer {{site.data.keyword.Bluemix_notm}}-ID und dem zugehörigen Kennwort bei {{site.data.keyword.ghe_short}} anmelden. Wenn sich die Benutzer anmelden, werden Konten für sie erstellt. Wenn Sie Benutzer zu Ihrer {{site.data.keyword.Bluemix_notm}}-Organisation und deren Bereichen hinzufügen, werden sie nicht automatisch zum {{site.data.keyword.ghe_short}}-Repository hinzugefügt. Ein Benutzer mit Administratorberechtigungen für das Repository muss sie hinzufügen. Weitere Informationen finden Sie im Abschnitt zur Verwendung von [Dedicated GitHub Enterprise](/docs/services/ghededicated/index.html){: new_window}. Wenn Sie Ihre eigene verwaltete Version von {{site.data.keyword.ghe_short}} verwenden, gehen Sie gemäß Ihren eigenen internen Prozeduren vor.

###Tipps für die Verwaltung des Zugriffs auf eine Toolchain

* Wenn Sie den Zugriff auf eine Toolchain verwalten wollen, klicken Sie im DevOps-Dashboard auf der Seite **Toolchains** auf die zu verwaltende Toolchain und klicken Sie dann auf **Verwalten**. Alternativ können Sie auf der Übersichtsseite der App auf der Karte für Continuous Delivery auf **Toolchain anzeigen** und dann auf **Verwalten** klicken.

* Wenn Sie allen Mitgliedern der Organisation der Toolchain Zugriff erteilen wollen, klicken Sie auf **Organisation hinzufügen**. Alle Mitglieder dieser Organisation können nun die Toolchain anzeigen.

* Sie können einer Organisation oder einem Benutzer Administratorberechtigungen erteilen. Administratoren können Änderungen an der Toolchain vornehmen und die Toolchain löschen. Wenn Sie Administratorberechtigungen erteilen wollen, wählen Sie für die betreffende Organisation oder den betreffenden Benutzer das Kontrollkästchen **ADMINISTRATOR** aus.

* Bei Auswahl des Kontrollkästchens **ADMINISTRATOR** für eine Organisation können alle Mitglieder dieser Organisation als Administratoren fungieren. Wenn Sie Mitglieder zu der Organisation hinzufügen, nachdem Sie dieser Organisation Administratorberechtigungen erteilt haben, so erhalten diese Mitglieder denselben Zugriff wie der Rest der Organisation.

* Wenn Sie einem Benutzer, der Mitglied der Organisation der Toolchain ist, Zugriff erteilen wollen, geben Sie die Benutzer-ID des Benutzers ein und klicken Sie auf **Benutzer hinzufügen**. Der Benutzer kann nun die Toolchain anzeigen.

* Führen Sie die folgenden Schritte aus, um einem Benutzer, der nicht Mitglied der Organisation der Toolchain ist, Zugriff zu erteilen:

   a. Klicken Sie in der Menüleiste auf **Verwalten>Sicherheit>Identität und Zugriff**. 

   b. Wählen Sie aus der Zeile für den Benutzer, dem Sie den Zugriff zuweisen möchten, das Menü **Aktionen** aus und klicken Sie auf **Zugriff zuweisen**.

   c. Wählen Sie **Zugriff mit Cloud Foundry zuweisen** aus.

   d. Wählen Sie **Organisation zuweisen** aus.

   e. Gehen Sie wie folgt vor, um den Benutzerzugriff zuzuweisen:

     * Wählen Sie eine Organisation aus, zu der der Benutzer hinzugefügt werden soll.

     * Weisen Sie eine Organisationsrolle zu.

     * Wählen Sie eine Region aus.

     * Wählen Sie einen Bereich aus.

     * Weisen Sie dem ausgewählten Bereich in der Organisation eine Rolle zu.

     **Hinweis:** Standardmäßig verfügen Organisationsmanager über uneingeschränkte Administratorberechtigungen für alle Toolchains, die der Organisation zugeordnet sind. Um einem Benutzer die vollen Administratorberechtigungen zu erteilen, wählen Sie die Rolle **Manager** aus. Die Rollen 'Abrechnungsmanager' und 'Auditor' haben keinerlei Einfluss auf den Zugriff auf Toolchains. Sie können die Rollen später auf der Seite 'Teamverzeichnis' ändern. Weitere Informationen finden Sie in [Cloud Foundry-Rollen](/docs/iam/cfaccess.html#cfaccess){: new_window}.

   Nachdem der Benutzer nun zu einem Mitglied der Organisation geworden ist, kehren Sie zu der Verwaltungsseite der Toolchain zurück und fügen Sie den Benutzer zu der Toolchain hinzu.  


## Toolchain löschen
{: #deleting_a_toolchain}

Sie können eine Toolchain löschen und angeben, welche der zugehörigen Toolintegrationen ebenfalls gelöscht werden sollen. Wenn Sie eine Toolchain löschen, kann diese Löschung nicht mehr rückgängig gemacht werden.

1. Klicken Sie im DevOps-Dashboard auf der Seite **Toolchains** auf die Toolchain, die gelöscht werden soll. Alternativ können Sie auf der Übersichtsseite der App auf der Karte für Continuous Delivery auf **Toolchain anzeigen** klicken.
1. Klicken Sie neben **App anzeigen** auf das Menü **Weitere Aktionen**.
1. Klicken Sie auf **Löschen**. Beim Löschen einer Toolchain werden auch alle zugehörigen Toolintegrationen entfernt, was unter Umständen bewirkt, dass von diesen Integrationen verwaltete Ressourcen ebenfalls gelöscht werden.
1. Bestätigen Sie das Löschen, indem Sie den Namen der Toolchain eingeben und auf **Löschen** klicken.  

 **Tipp**: Wenn Sie eine GitHub-, {{site.data.keyword.ghe_short}}- oder {{site.data.keyword.gitrepos}}-Toolintegration löschen, wird das zugeordnete Repository nicht aus GitHub, {{site.data.keyword.ghe_short}} oder {{site.data.keyword.gitrepos}} gelöscht. Sie müssen das Repository manuell entfernen.

##Relevantes Lernprogramm: Toolchains verwenden
{: #toolchain-tutorial}

Informieren Sie sich in diesen Lernprogrammen zu [IBM&reg; Cloud Garage Method ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/garage){:new_window}:

  * [Erstellen und verwenden Sie Ihre erste Toolchain mithilfe der Toolchain zum Entwickeln einer Cloud Foundry-App ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}.

  * [Toolchain zu einer App hinzufügen ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/garage/tutorials/add-a-toolchain-to-an-app?task=2){:new_window}

  * [Verwenden Sie die Toolchain zum Entwickeln und Testen von Microservices auf Cloud Foundry ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}.
