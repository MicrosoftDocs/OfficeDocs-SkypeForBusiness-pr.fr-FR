---
title: Outils du kit de ressources de conversation permanente Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80a9116374914c212d305ef2e55d0b8c4fecb782
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533667"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Outils du kit de ressources de conversation permanente Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Les outils du kit de ressources de conversation permanente Lync Server 2013 facilitent les tâches de routine pour les administrateurs qui déploient et gèrent Lync Server 2013 le serveur de conversation permanente. Outre les instructions d’installation, cette rubrique décrit l’objet de chaque outil, ainsi que des exemples de son utilisation.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation des outils du kit de ressources

Pour installer les outils du kit de ressources Lync Server 2013, téléchargez **PersistentChatReskit.msi**. Exécutez **PersistentChatReskit.msi** pour effectuer une installation simple. Le fichier. msi installe tous les outils dans le chemin d’accès suivant : \\ **Program Files \\ Microsoft Lync Server 2013 \\ persistent Server Resource Kit**. Les outils qui sont des fichiers exécutables autonomes se trouvent dans ce dossier. Les outils qui ont également des fichiers se trouvent dans leurs propres sous-dossiers.

<div>


> [!IMPORTANT]  
> Après avoir installé les outils du kit de ressources Lync Server 2013, vous devez installer <STRONG>PsExec.exe</STRONG> et copier <STRONG>PsExec.exe</STRONG> dans le chemin d’accès suivant : \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ persistent Server Resource Kit\ChatStressTool</STRONG>. Si vous ne copiez pas <STRONG>PsExec.exe</STRONG>, l’outil de contrainte de conversation permanente génère une exception d’erreur et ne fonctionne pas correctement. Assurez-vous que vous respectez ces conditions préalables avant d’exécuter l’outil. Pour plus d’informations sur l’installation de <STRONG>PsExec.exe</STRONG>, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .



</div>

</div>

<div>

## <a name="supported-environments"></a>Environnements pris en charge

Pour des performances optimales, les outils du kit de ressources Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications que celles requises pour Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Vue d’ensemble des outils du kit de ressources

Voici les outils fournis dans le kit de ressources de conversation permanente Lync Server 2013. La section suivante fournit une description de chaque outil, notamment les exigences et l’utilisation de l’exemple.

  - AffCheck

  - ChatMonitoringSummary

  - Outil ChatStress

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>Description

L’outil AffCheck confirme que les enregistrements d’appartenance au groupe et à l’utilisateur de la base de données principale de conversation permanente correspondent à ceux des services de domaine Active Directory.

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil est installé avec le programme d’installation PersistentChatResKit sur un ordinateur joint à un domaine.

Le compte d’utilisateur sous lequel l’outil est exécuté doit disposer d’un accès en lecture à la base de données principale de conversation permanente et aux services de domaine Active Directory.

</div>

<div>

## <a name="usage"></a>Utilisation

Configurez le fichier AffCheck.exe.config conformément aux instructions du fichier de configuration et exécutez l’outil AffCheck sans paramètres de ligne de commande. Voici le contenu de la AffCheck.exe.config par défaut.

**AffCheck.exe.config :**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>Description

L’outil PersistentChatMonitoringSummary déplace les informations de surveillance de conversation permanente de la base de données de surveillance dans un fichier CSV spécifié.

Le fichier CSV contiendra une répartition des sessions de conversation permanente en nombre total de sessions, de sessions réussies, d’échecs inattendus, d’échecs attendus et de la répartition des échecs inattendus par ID de diagnostic, le nombre de défaillances et la description de l’échec.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données de surveillance.

Le compte d’utilisateur sous lequel l’outil s’exécute doit disposer d’un accès en lecture à la base de données de surveillance.

Le fichier, PersistentChatMonitoringSummary.exe.config, doit contenir une \<connectionStrings\> section qui définit la chaîne de connexion à la base de données de surveillance. Il doit également contenir une clé pour le PersistentChatEndpointUri pour lequel les données de surveillance seront collectées, et un chemin d’accès de fichier vers un emplacement pour le fichier CSV qui sera généré. Reportez-vous au fichier de configuration installé pour obtenir des exemples. Le fichier doit se trouver dans le même répertoire que l’outil.

</div>

<div>

## <a name="usage"></a>Utilisation

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Ces paramètres définissent la sélection de données :

**StartDateTime :** Spécifie éventuellement la date de début de la période de sélection. Valeur par défaut : 1/1/1753 12:00:00 AM

**EndDateTime :** Spécifie éventuellement la dernière date de la période de sélection. Valeur par défaut : maintenant

</div>

<div>

## <a name="example"></a>Exemple

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Outil de contrainte de conversation permanente

<div>

## <a name="description"></a>Description

L’outil de contrainte de conversation permanente offre un moyen simple de simuler l’utilisation de la conversation permanente pour tester les performances du monde réel, y compris les modèles utilisateur variés afin de mieux répondre aux scénarios d’utilisation attendus.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données principale de conversation permanente.

En plus de cet ordinateur *contrôleur* , vous aurez besoin de plusieurs machines de *chargeur* . Pour tous les 10 000 utilisateurs de votre modèle utilisateur, vous aurez besoin d’au moins 4 Go de RAM libre sur un ordinateur chargeur. Par exemple, une exécution avec des utilisateurs de 80K nécessite environ 32 Go de RAM répartis sur tous les ordinateurs de chargement. Nous vous recommandons d’avoir au moins trois machines de chargeur, quelle que soit la charge attendue.

Les machines de chargeur doivent disposer de l’infrastructure .NET 4,5 et de la version redistribuable de Visual C++ 2012.

</div>

<div>

## <a name="configuration"></a>Configuration

Copiez les fichiers ChatStressTool dans un dossier partagé accessible à partir de tous les ordinateurs de chargement.

Créez des utilisateurs et des canaux à utiliser dans l’exécution de contrainte :

  - Créez autant d’utilisateurs que vous appelez votre modèle utilisateur, activez-les pour Lync et définissez leur stratégie de conversation permanente sur activé.

  - Créez une catégorie pour vos canaux de stress, puis créez autant de salles que nécessaire sous cette catégorie. La catégorie doit avoir tous les utilisateurs de stress dans sa liste **autorisée** (par le biais de l’ajout de leur unité d’organisation) et les salles de stress doivent avoir le paramètre de confidentialité « **ouvert**».

  - Nous vous recommandons de créer des salles de contrainte supplémentaires. Vous pouvez créer 50 000 salles à l’aide de la commande d’interface de ligne de commande Windows PowerShell suivante :
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Modifiez les fichiers de configuration pour qu’ils s’ajustent à votre topologie :

Dans **LoaderProcess.exe.config**, remplacez « Controller.contoso.com » par le nom de domaine complet (FQDN) de l’ordinateur contrôleur.

Dans **StressLauncher.exe.config :**

1.  Remplacez la valeur du paramètre « LoaderBinary » par le chemin d’accès du dossier partagé.

2.  Remplacez « AdminUser »/« AdminPassword » par les informations d’identification qui disposent d’un accès administrateur aux machines de chargeur.

3.  Remplacez « ChannelCategory » par le nom de la catégorie dans laquelle les canaux de contrainte ont été créés.

4.  Remplacez « UserNamePattern » et « UserPasswordPattern » par un modèle qui correspond aux informations d’identification de votre utilisateur de stress. {0} est remplacé par le numéro d’index de l’utilisateur.

5.  Remplacez « Domain » par « Domain » par le domaine SIP de votre topologie de test.

6.  Remplacez « ConnectionString » par une chaîne de connexion pour votre base de données principale de conversation permanente.

7.  Remplacez « UserIndexStart » par l’index du premier utilisateur à contrainte.

8.  Remplacez « LyncFQDN » par le nom de domaine complet (FQDN) de votre pool frontal.

9.  Modifiez la liste « machines » pour inclure les noms de machine de tous les ordinateurs de chargement.

10. Modifiez le paramètre baseAddress du point de terminaison du service (par défaut, « controller.contoso.com ») sur le nom de domaine complet de votre ordinateur contrôleur.

</div>

<div>

## <a name="usage"></a>Utilisation

Une fois la configuration terminée, ouvrez StressLauncher.exe sur l’ordinateur contrôleur. Vous pouvez lancer StressLauncher comme n’importe quel utilisateur. Les informations d’identification sous lesquelles les processus de chargeur démarrent sur les ordinateurs de chargeur doivent être spécifiées dans le fichier de configuration. Vous devez également donner une chaîne de connexion qui dispose d’un accès en lecture à la base de données principale de conversation permanente. Si cette chaîne de connexion utilise l’authentification Windows intégrée, vous devez lancer StressLauncher en tant qu’utilisateur disposant de cet accès.

Modifiez les paramètres du modèle utilisateur selon vos besoins. Cliquez sur **Démarrer la charge** pour lancer une exécution. Après une minute ou par conséquent, les utilisateurs commencent à se connecter et la barre de progression commence à se remplir. À ce stade, vous pouvez peut-être utiliser l’ordinateur contrôleur et prendre des mesures de performances.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Description

ChatUpgradeVerifier est un outil de comparaison de base de données spécifique à une conversation permanente. L’outil compare la base de données Group chat 2007 R2 ou Group chat 2010 (2007/2010Db) à la base de données de conversation permanente 2013 (2013Db).

L’outil vérifie, une par une, chaque catégorie, la salle de conversation permanente et le complément dans la version 2007/2010Db pour voir s’il apparaît dans le 2013Db. La comparaison inclut la vérification de tous les paramètres de la catégorie, de la salle de conversation ou du complément, de tous les principaux de l’étendue de la catégorie et de n’importe quel principal d’un rôle sur la catégorie ou la salle de conversation. Si une catégorie ou une salle de conversation ne s’affiche pas correctement dans le 2013Db, les différences seront générées dans un fichier de conflits. Si, après la mise à niveau, la version 2007/2010Db est modifiée et que cet outil est exécuté, il y aura une différence de sortie dans le fichier de conflits. Notez que cette application est uniquement un outil de comparaison de bases de données et ne valide pas le processus de mise à niveau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès aux bases de données principales de conversation permanente (versions précédentes et actuelles pour la conversation permanente).

Le compte d’utilisateur sous lequel l’outil s’exécute doit disposer d’un accès en lecture aux bases de données de conversation permanente.

Le fichier ChatUpgradeVerifier.exe.config doit contenir le paramètre GroupChat2007R2Db ou le paramètre GroupChat2010Db, avec une chaîne de connexion à la base de données de conversation de groupe appropriée (soit groupchat 2007R2, soit 2010). Elle doit également contenir un paramètre PersistentChat2013Db, avec une chaîne de connexion à la base de données de conversation permanente 2013.

</div>

<div>

## <a name="usage"></a>Utilisation

Exécutez **ChatUpgradeVerifier** sans aucun paramètre.

</div>

<div>

## <a name="example"></a>Exemple

![Exécutant ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Exécutant ChatUpgradeVerifier.exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Rapport d’utilisation de conversation permanente

<div>

## <a name="description"></a>Description

L’outil ChatUsageReport génère un rapport HTML sur l’utilisation du service de conversation permanente.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de conversation permanente sur un ordinateur joint à un domaine qui a accès à la base de données principale de conversation permanente.

Le compte d’utilisateur sous lequel l’outil est exécuté doit disposer d’un accès en lecture à la base de données principale de conversation permanente.

Le fichier, ChatUsageReport.exe.config, doit contenir une \<connectionStrings\> section définissant la chaîne de connexion à la base de données principale de conversation permanente. Le contenu du fichier de configuration par défaut est inclus ici, à des fins de référence.

</div>

<div>

## <a name="usage"></a>Utilisation

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Ces paramètres définissent la sélection de données :

**StartDate :** Spécifie éventuellement la date de début UTC de la période de sélection. Valeur par défaut : date au plus tôt

**EndDate :** Spécifie éventuellement la date de fin UTC de la période de sélection. Valeur par défaut : maintenant

Ces paramètres définissent la façon dont les données sont affichées :

**TopActiveUsers :** Si cette option est spécifiée, le rapport inclut les utilisateurs les plus actifs en termes de nombre de messages publiés par l’utilisateur dans la salle de conversation pendant la période sélectionnée. Par défaut : 10

**TopActiveRooms :** Si cette option est spécifiée, le rapport inclut les n salles de conversation les plus actives en termes de nombre de messages publiés dans la salle pendant la période sélectionnée. Par défaut : 10

**LeastActiveRooms :** Si cette option est spécifiée, le rapport inclut les salles de conversation les moins actives en termes de nombre de messages publiés dans la salle de conversation pendant la période sélectionnée. Les salles auront au moins un message publié. Par défaut : 10

**RoomsInactiveSince :** Si cette indication est spécifiée, le rapport inclut une liste des salles de conversation qui ont été inactives depuis la date spécifiée. Valeur par défaut : heure entière

**OutputFolder :** Dossier dans lequel les images ChatUsageReport.html et Graph seront placées. Il doit être défini dans le fichier de configuration ou dans la ligne de commande.

Toutes les valeurs de paramètre de ligne de commande peuvent également être spécifiées dans le fichier ChatUsageReport.exe.config qui se trouve dans le même répertoire que l’outil. Si une valeur est spécifiée dans le fichier de configuration et la ligne de commande, la valeur de la ligne de commande remplace la valeur du fichier de configuration.

</div>

<div>

## <a name="output"></a>Output

Le rapport inclut toujours la sortie suivante :

  - N premières salles de conversation les plus actives en nombre de publications de messages pour la période sélectionnée.

  - N premiers utilisateurs les plus actifs en nombre de publications de messages pour la période sélectionnée.

  - N premières salles de conversation actives par nombre de publications de messages pour la période sélectionnée.

  - Salles de conversation inactives pendant toute la durée de vie de la base de données ou depuis la date spécifiée.

  - Tendance quotidienne des publications de messages pour la période sélectionnée.

  - Tendance hebdomadaire des publications de messages pour la période sélectionnée.

  - Tendance mensuelle des publications de messages pour la période sélectionnée.

  - Total des publications de messages pour la période sélectionnée.

  - Nombre total de salles activées.

</div>

<div>

## <a name="example"></a>Exemple

L’exemple suivant génère un rapport d’utilisation pour l’année 2001 entière et place l’État dans le OutputFolder spécifié dans la ChatUsageReport.exe.config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport.exe.config :

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>Description

ScheduleADSyncForPrincipal est un script Microsoft SQL Server 2012 qui doit être exécuté directement à partir de SQL Server Management Studio lorsqu’il est connecté à la base de données principale de conversation permanente. Ce script vous permet de forcer la conversation permanente à synchroniser ses enregistrements d’un utilisateur avec ceux des services de domaine Active Directory, au lieu d’attendre la durée de la synchronisation planifiée.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Le compte d’utilisateur sous lequel le script est exécuté doit disposer d’un accès propriétaire à la base de données principale de conversation permanente.

</div>

<div>

## <a name="usage"></a>Utilisation

Voici le contenu du script par défaut :

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

