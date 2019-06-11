---
title: Outils du kit de ressources techniques Lync Server 2013 permanents
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c851be7bb7046021cc2d37c88ef03bdea60c95a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Outils du kit de ressources techniques Lync Server 2013 permanents

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Les outils du kit de ressources techniques Lync Server 2013 persistent pour faciliter les tâches de routine pour les administrateurs informatiques qui déploient et gèrent Lync Server 2013 permanent Chat Server. Outre les instructions d’installation, cette rubrique décrit la finalité de chaque outil et des exemples de son utilisation.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installation des outils du kit de ressources

Pour installer Lync Server 2013, les outils du kit de ressources, téléchargez **PersistentChatReskit. msi**. Exécutez **PersistentChatReskit. msi** pour effectuer une installation simple. Le fichier. msi installe tous les outils dans le chemin d' \\accès suivant: **Program Files\\ Microsoft\\Lync Server 2013 persistent Server Resource Kit**. Les outils exécutables autonomes se trouvent dans ce dossier. Les outils qui comportent également des fichiers se trouvent dans leurs propres sous-dossiers.

<div>


> [!IMPORTANT]  
> Après l’installation des outils de kit de ressources Lync Server 2013, vous devez installer <STRONG>psexec. exe</STRONG> et copier <STRONG>psexec. exe</STRONG> vers le chemin \\d’accès suivant: <STRONG>fichiers programme \ Microsoft Lync Server 2013 \ ressources du serveur de conversation Kit\ChatStressTool </STRONG>. Si vous ne copiez pas <STRONG>psexec. exe</STRONG>, l’outil de contrainte de conversation permanente génère une exception d’erreur et ne fonctionne pas correctement. Assurez-vous de respecter cette exigence préalable avant d’exécuter l’outil. Pour plus d’informations sur l’installation de <STRONG>psexec. exe</STRONG>, voir <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.



</div>

</div>

<div>

## <a name="supported-environments"></a>Environnements pris en charge

Pour des performances optimales, les outils du kit de ressources de Lync Server 2013 doivent être installés dans le même environnement et avec les mêmes spécifications requises pour Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Présentation des outils du kit de ressources

Voici les outils fournis dans le kit de ressources de conversation permanente Lync Server 2013. La section suivante fournit une description de chaque outil, y compris la configuration requise et un exemple d’utilisation.

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

L’outil AffCheck vérifie que la base de données principale de la base de données principale de chat et les enregistrements d’affiliation de groupe correspondent à ceux des services de domaine Active Directory (AD FS).

</div>

<div>

## <a name="requirements"></a>Configuration requise

L’outil est installé avec le programme d’installation PersistentChatResKit sur un ordinateur appartenant à un domaine.

Le compte d’utilisateur sous lequel l’outil est exécuté doit avoir accès en lecture à la base de données principale de chat permanent et aux services de domaine Active Directory.

</div>

<div>

## <a name="usage"></a>Utilisation

Configurez le fichier AffCheck. exe. config conformément aux instructions du fichier de configuration et exécutez l’outil AffCheck sans paramètres de ligne de commande. Voici le contenu de la valeur par défaut AffCheck. exe. config.

**AffCheck. exe. config:**

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

L’outil PersistentChatMonitoringSummary déplace les informations de surveillance des conversations persistantes de la base de données de surveillance dans un fichier journal CSV spécifié.

Le fichier CSV contient une répartition des sessions de conversation persistantes en nombre de sessions totales, de sessions réussies, d’échecs inattendus, d’échecs attendus et de la description des échecs inattendus.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de chat permanent sur un ordinateur appartenant à un domaine ayant accès à la base de données de surveillance.

Le compte d’utilisateur sous lequel l’outil s’exécute doit avoir accès en lecture à la base de données de surveillance.

Le fichier PersistentChatMonitoringSummary. exe. config doit contenir une \<section connectionStrings\> qui définit la chaîne de connexion à la base de données de surveillance. Elle doit également contenir une clé pour le PersistentChatEndpointUri pour lequel les données d’analyse seront collectées et un chemin d’accès de fichier vers un emplacement pour le fichier CSV qui sera généré. Pour obtenir des exemples, consultez le fichier de configuration installé. Le fichier doit se trouver dans le même répertoire que l’outil.

</div>

<div>

## <a name="usage"></a>Utilisation

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Ces paramètres définissent la sélection de données:

**StartDateTime:** Éventuellement, spécifiez la date de début de la période de sélection. Par défaut: 1/1/1753 12:00:00 AM

**EndDateTime:** Spécifie éventuellement la dernière date de la période de sélection. Par défaut: désormais

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

## <a name="persistent-chat-stress-tool"></a>Outil de stress permanent de conversation

<div>

## <a name="description"></a>Description

L’outil de contraintes Permanentles de conversation fournit un moyen facile de simuler l’utilisation de la messagerie instantanée pour tester les performances du monde réel, y compris des modèles utilisateur variés pour mieux s’adapter à vos scénarios d’utilisation prévus.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de chat permanent sur un ordinateur appartenant à un domaine ayant accès à la base de données principale de conversation permanente.

En plus de cet ordinateur *contrôleur* , vous aurez besoin de plusieurs machines de *chargement* . Pour chaque 10K d’utilisation de votre modèle utilisateur, vous avez besoin d’au moins 4 Go de RAM libre sur un ordinateur de chargement. Par exemple, une opération d’exécution avec des utilisateurs de 80K nécessite environ 32 Go de mémoire vive (RAM) sur tous les ordinateurs de chargement. Nous vous recommandons d’avoir au moins trois machines de charge, quelle que soit la charge attendue.

Les machines de chargeur doivent disposer de l’infrastructure .NET 4,5 ainsi que de l’infrastructure Visual C++ 2012 installée.

</div>

<div>

## <a name="configuration"></a>Configuration

Copiez les fichiers ChatStressTool dans un dossier partagé accessible à partir de tous les ordinateurs de chargement.

Créer des utilisateurs et des canaux à utiliser dans le stress:

  - Créez autant d’utilisateurs que vous le souhaitez, vous pouvez les activer pour Lync et définir leur stratégie de discussion persistante sur activé.

  - Créez une catégorie pour vos canaux de stress, puis créez autant de salles que nécessaire dans cette catégorie. La catégorie doit avoir tous les utilisateurs de stress dans sa liste **autorisée** (par le biais de l’ajout de leur UO) et les salles de stress doivent avoir un paramètre de confidentialité d' **Open**.

  - Nous vous recommandons de créer des salles de stress supplémentaires. Vous pouvez créer des salles 50 000 à l’aide de la commande d’interface de ligne de commande Windows PowerShell suivante:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Modifiez les fichiers de configuration pour qu’ils s’intègrent à votre topologie:

Dans **LoaderProcess. exe. config**, remplacez «Controller.contoso.com» par le nom de domaine complet (FQDN) de l’ordinateur contrôleur.

Dans **StressLauncher. exe. config:**

1.  Remplacez la valeur de paramètre «LoaderBinary» par le chemin d’accès du dossier partagé.

2.  Changez «AdminUser»/«AdminPassword» en informations d’identification disposant d’un accès administrateur aux machines de chargeur.

3.  Remplacez «ChannelCategory» par le nom de la catégorie sous laquelle les canaux de stress ont été créés.

4.  Remplacez «UserNamePattern» et «UserPasswordPattern» par un modèle qui correspond à vos informations d’identification de l’utilisateur stress. {0}est remplacé par le numéro d’index de l’utilisateur.

5.  Remplacez «Domain» par le domaine SIP de votre topologie de test.

6.  Changez «ConnectionString» en chaîne de connexion pour votre base de données principale de conversation permanente.

7.  Changez «UserIndexStart» en index du premier utilisateur de stress.

8.  Remplacez «LyncFQDN» par le nom de domaine complet (FQDN) du pool frontal.

9.  Modifiez la liste «machines» pour inclure les noms d’ordinateur pour tous les ordinateurs de chargement.

10. Modifiez la valeur de l’option baseAddress du point de terminaison de service (la valeur par défaut est «controller.contoso.com») en nom de domaine complet (FQDN) de votre ordinateur de contrôleur.

</div>

<div>

## <a name="usage"></a>Utilisation

Une fois la configuration terminée, ouvrez StressLauncher. exe sur l’ordinateur contrôleur. Vous pouvez lancer StressLauncher comme n’importe quel utilisateur. Les informations d’identification à partir desquelles les processus de chargeur s’exécutent sur les ordinateurs de chargement doivent être spécifiées dans le fichier de configuration. Vous devez également fournir une chaîne de connexion qui dispose d’un accès en lecture à la base de données principale de conversation permanente. Si cette chaîne de connexion utilise l’authentification Windows intégrée, vous devez lancer StressLauncher en tant qu’utilisateur disposant de cet accès.

Modifiez les paramètres du modèle utilisateur selon vos besoins. Cliquez sur **Démarrer la charge** pour lancer une exécution. Après quelques minutes, les utilisateurs commenceront à se connecter et la barre de progression commencera à remplir. À ce stade, vous pouvez peut-être utiliser l’ordinateur de contrôleur fonctionnant et prendre des mesures de performance.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Description

ChatUpgradeVerifier est un outil de comparaison de base de données spécifique d’une conversation permanente. L’outil compare la base de données de discussion de groupe 2007 R2 ou la base de données de discussion de groupe 2010 (2007/2010Db) à la base de données de conversation 2013 2013Db ().

L’outil vérifie, une par une, chaque catégorie, salle de conversation permanente et complément en 2007/2010Db pour voir s’il apparaît dans le 2013Db. La comparaison inclut la vérification de tous les paramètres d’une catégorie, d’une salle de conversation ou d’un complément, de tout principal sur la catégorie et de n’importe quel principal d’un rôle dans la catégorie ou la salle de conversation. Si une catégorie ou une salle de conversation ne s’affiche pas correctement dans le 2013Db, les différences seront générées dans un fichier de conflits. Si, à l’issue de la mise à niveau, le 2007/2010Db est modifié et que cet outil est exécuté, il y a une différence de sortie dans le fichier de conflits. Notez que cette application est un outil de comparaison de bases de données uniquement et ne valide pas le processus de mise à niveau.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources pour les discussions permanentes sur un ordinateur appartenant à un domaine ayant accès aux bases de données principales de chat permanent (versions précédentes et actuelles pour les discussions permanentes).

Le compte d’utilisateur sous lequel l’outil s’exécute doit disposer d’un accès en lecture aux bases de données de chat permanent.

Le fichier ChatUpgradeVerifier. exe. config doit contenir le paramètre GroupChat2007R2Db ou le paramètre GroupChat2010Db, avec une chaîne de connexion dans la base de données de discussion de groupe appropriée (groupchat 2007R2 ou 2010). Elle doit également contenir un paramètre PersistentChat2013Db, avec une chaîne de connexion à la base de données chat 2013.

</div>

<div>

## <a name="usage"></a>Utilisation

Exécutez **ChatUpgradeVerifier** sans aucun paramètre.

</div>

<div>

## <a name="example"></a>Exemple

![Exécution de ChatUpgradeVerifier. exe.] (images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Exécution de ChatUpgradeVerifier. exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Rapport d’utilisation persistante des conversations

<div>

## <a name="description"></a>Description

L’outil ChatUsageReport génère un rapport HTML de l’utilisation du service de chat permanent.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Installez les outils du kit de ressources de chat permanent sur un ordinateur appartenant à un domaine ayant accès à la base de données principale de conversation permanente.

Le compte d’utilisateur sous lequel l’outil est exécuté doit avoir accès en lecture à la base de données principale de conversation permanente.

Le fichier ChatUsageReport. exe. config doit contenir une \<section connectionStrings\> définissant la chaîne de connexion sur la base de données principale de chat. Le contenu du fichier de configuration par défaut est inclus ici, à des fins de référence.

</div>

<div>

## <a name="usage"></a>Utilisation

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Ces paramètres définissent la sélection de données:

**DateDébut:** Le cas échéant, spécifie la date de début UTC de la période de sélection. Par défaut: date au plus tôt

**Date_fin:** Facultatif, spécifie la date de fin UTC de la période de sélection. Par défaut: désormais

Ces paramètres définissent le mode d’affichage des données:

**TopActiveUsers:** Si ce paramètre est spécifié, le rapport inclut les n utilisateurs les plus actifs en fonction du nombre de messages que l’utilisateur a publiés dans la salle de conversation pendant la période sélectionnée. Par défaut: 10

**TopActiveRooms:** Si ce paramètre est spécifié, le rapport inclura les n salles de conversation les plus actives pour le nombre de messages publiés dans la salle pendant la période sélectionnée. Par défaut: 10

**LeastActiveRooms:** Si ce paramètre est spécifié, le rapport inclura le numéro des salles de conversation actives pour le nombre de messages publiés dans la salle de conversation pendant la période sélectionnée. Au moins un message sera publié dans les salles. Par défaut: 10

**RoomsInactiveSince:** Si ce paramètre est spécifié, le rapport inclura une liste des salles de conversation inactives depuis la date spécifiée. Valeur par défaut: heure entière

**OutputFolder:** Le dossier dans lequel se trouve le fichier ChatUsageReport. html et les images graphiques. Cette opération doit être définie dans le fichier de configuration ou la ligne de commande.

Toutes les valeurs de paramètres de ligne de commande peuvent également être spécifiées dans le fichier ChatUsageReport. exe. config qui se trouve dans le même répertoire que l’outil. Si une valeur est spécifiée dans le fichier de configuration et la ligne de commande, la valeur de la ligne de commande remplace la valeur du fichier de configuration.

</div>

<div>

## <a name="output"></a>Sortie

Le rapport inclut toujours la sortie suivante:

  - N premières salles de conversation actives par nombre de publications de messages pour la période sélectionnée.

  - N premiers utilisateurs actifs par nombre de billets de messages pour la période sélectionnée.

  - Top n des salles de conversation actives par nombre de publications de messages pour la période sélectionnée.

  - Des salles de conversation inactives pour toute la durée de vie de la base de données ou depuis la date spécifiée.

  - Tendance quotidienne de publication des messages pour la période sélectionnée.

  - Tendance hebdomadaire des publications de messages pour la période sélectionnée.

  - Tendance mensuelle des publications de messages pour la période sélectionnée.

  - Nombre total de publications de messages pour la période sélectionnée.

  - Nombre total d’espaces activés.

</div>

<div>

## <a name="example"></a>Exemple

L’exemple suivant génère un rapport sur l’utilisation de la 2001 entière et place le rapport dans le OutputFolder spécifié dans ChatUsageReport. exe. config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport. exe. config:

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

ScheduleADSyncForPrincipal est un script Microsoft SQL Server 2012 qui doit être exécuté directement depuis SQL Server Management Studio lorsqu’il est connecté à la base de données principale de conversation permanente. Ce script vous permet de forcer une conversation permanente à synchroniser ses enregistrements d’un utilisateur avec des services de domaine Active Directory, plutôt que d’attendre la durée de la synchronisation planifiée.

</div>

<div>

## <a name="requirements"></a>Configuration requise

Le compte d’utilisateur sous lequel le script est exécuté doit avoir accès au propriétaire de la base de données principale de conversation permanente.

</div>

<div>

## <a name="usage"></a>Utilisation

Le contenu du script par défaut est le suivant:

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

