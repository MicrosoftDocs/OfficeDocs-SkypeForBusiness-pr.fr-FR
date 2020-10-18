---
title: 'Lync Server 2013 : installation des rapports de surveillance de Lync Server 2013'
description: 'Lync Server 2013 : installation des rapports de surveillance de Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12405f786cbaf095e97f526fae2e1c2d3cb45c32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573930"
---
# <a name="installing-lync-server-2013-monitoring-reports"></a>Installation des rapports de surveillance Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-02-27_

Les rapports de surveillance Microsoft Lync Server 2013 fournissent une mine d’informations sur la qualité et la quantité des sessions de communication qui ont lieu dans votre organisation. Toutefois, les rapports de surveillance ne sont pas installés automatiquement lors de l’installation de Lync Server 2013 ; au lieu de cela, vous devez installer les rapports de surveillance séparément et uniquement après l’installation de Lync Server sur l’ordinateur.

<div>


> [!NOTE]  
> Il est recommandé d’installer les rapports de surveillance sur le même ordinateur que celui sur lequel la base de données de surveillance est installée. Cela simplifie le processus d’attribution des autorisations d’accès aux rapports : l’installation des rapports de surveillance sur l’ordinateur qui héberge le magasin d’analyse signifie qu’il n’est pas nécessaire de configurer les autorisations qui permettent à une base de données sur un premier ordinateur d’interagir avec le service Reporting Services exécuté sur un autre ordinateur.



</div>

Les rapports de surveillance de Lync Server incluent plus de 30 rapports conçus pour fournir des informations détaillées sur les conférences, les sessions de messagerie instantanée d’égal à égal, les inscriptions des utilisateurs, l’application Response Group, et bien plus encore. Pour la version 2013, les rapports de surveillance de Lync Server incluent un certain nombre d’améliorations :

  - **Nouveaux rapports de qualité de la voix**. Ces nouveaux rapports incluent le [rapport comparatif de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), qui compare la qualité entre différents types d’appels (par exemple, entre les appels câblés et les appels sans fil); et le [rapport de temps de participation aux conférences dans Lync Server 2013](lync-server-2013-conference-join-time-report.md), qui fournit des informations sur le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence.

  - **Rapports améliorés pour l’analyse et la résolution des problèmes des sessions de partage vidéo et d’application.** Le [rapport de synthèse de la qualité des médias dans Lync server 2013](lync-server-2013-media-quality-summary-report.md) permet d’analyser les appels de partage vidéo et d’application, tandis que le [rapport de performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md) détaille les performances des serveurs qui génèrent ces appels. Les mesures de partage vidéo et d’application sont désormais communiquées par le [rapport détaillé de session P2P dans Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) et le [rapport détaillé de conférence dans Lync Server 2013](lync-server-2013-conference-detail-report.md).

  - **Performances améliorées des rapports**. Ces améliorations incluent un temps de réponse et d’extraction des données plus court, ainsi qu’une navigation plus rapide et plus facile dans les rapports.

D’autres informations sur chaque rapport sont disponibles dans la documentation des rapports de surveillance.

<div>


> [!NOTE]  
> Il existe un autre nouveau rapport : sous-rapport de détails des appels QoE – inclus dans Lync Server 2013. Toutefois, ce rapport est principalement destiné à un usage interne et non à un accès direct.



</div>

Il existe deux façons d’installer les rapports de surveillance Lync Server : vous pouvez utiliser l’Assistant Déploiement de Lync Server ou vous pouvez utiliser un script Windows PowerShell inclus avec les fichiers d’installation de Lync Server 2013. Quelle que doit la méthode utilisée pour installer les rapports, vous devez d’abord vous assurer que vous :

  - avez le droit d’ajouter un rôle de base de données à un compte d’utilisateur dans la base de données de surveillance ;

  - détenez le rôle Gestionnaire de contenu dans SQL Server Reporting Services. Ce rôle vous donne le droit de déployer des rapports sur SQL Server Reporting Services.

Pour installer les rapports de surveillance à l’aide de l’Assistant Déploiement, procédez comme suit :

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement Lync Server**.

2.  Dans l’Assistant Déploiement, cliquez sur **Déployer les rapports de surveillance** afin de démarrer l’Assistant Déploiement des rapports de surveillance.

3.  Dans l’Assistant Déploiement des rapports de surveillance, dans la page **Spécifier une base de données de surveillance**, vérifiez que le nom de domaine complet de l’ordinateur qui héberge votre magasin d’analyse apparaît dans la liste déroulante **Base de données de surveillance**. (Si vous avez plusieurs magasins d’analyse, vous devez sélectionner le serveur approprié dans la liste déroulante.) Vérifiez que l’instance SQL Server correcte apparaît dans la zone **Instance SQL Server Reporting Services (SSRS)** (par exemple, **atl-sql-001.litwareinc.com/archinst**), puis cliquez sur **Suivant**.

4.  Sur la page **spécifier les informations d’identification** , dans la zone **nom d’utilisateur** , tapez le nom de domaine et le nom d’utilisateur du compte à utiliser lors de l’accès aux rapports de surveillance (par exemple, **litwareinc \\ kenmyer**). Si vous n’utilisez pas ce format ( \\ nom d’utilisateur de domaine), une erreur se produit.
    
    Tapez le mot de passe du compte d’utilisateur dans la zone **Mot de passe**, puis cliquez sur **Suivant**. Notez qu’aucun droit particulier n’est requis pour ce compte. Une fois l’installation terminée, le compte dispose automatiquement des autorisations d’ouverture de session et de base de données requises.

5.  Dans la page **Spécifier un groupe en lecture seule**, entrez le nom d’un groupe de sécurité qui disposera d’un accès en lecture seule à SQL Server Reporting Services dans la zone de groupe Utilisateur. Par exemple, pour octroyer aux administrateurs un accès en lecture seule aux rapports, entrez **RTCUniversalReadOnlyAdmins**. Cliquez sur **Suivant**.

6.  Dans la page de **Exécution de commandes**, cliquez sur **Terminer**.

Les rapports de surveillance peuvent également être installés à partir de Lync Server Management Shell en exécutant le script DeployReports.ps1 ; Ce script Windows PowerShell se trouve sur le support d’installation de Lync Server dans \\ le \\ dossier Setup ReportingSetup Pour installer les rapports de surveillance à l’aide de DeployReports.ps1, tapez une commande similaire à la suivante à l’invite Management Shell :

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

Les paramètres utilisés dans la commande précédente sont décrits dans le tableau suivant :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom du paramètre</th>
<th>Requis</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>Oui</p></td>
<td><p>Compte d’utilisateur (au format domaine\nomUtilisateur) utilisé pour accéder au magasin d’analyse ; par exemple :</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>Ce compte doit posséder les autorisations SQL Server et SQL Server Reporting Services précédemment spécifiées, sans quoi le script échoue.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>Oui</p></td>
<td><p>Mot de passe du compte d’utilisateur utilisé pour accéder au magasin d’analyse.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>Non</p></td>
<td><p>Domaine ou groupe de sécurité local dont les membres disposent d’un accès en lecture seule aux rapports de surveillance. Notez que le script échoue si le groupe spécifié n’existe pas. Si vous décidez ultérieurement de révoquer ces autorisations, ou si vous décidez d’octroyer à d’autres utilisateurs ou groupes des autorisations d’accès, vous pouvez le faire à l’aide du Gestionnaire de rapports SQL Service Reporting Services.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>Non</p></td>
<td><p>Instance SQL Server qui héberge le service de rapport. L’instance de création de rapports doit être spécifiée à l’aide du nom de domaine complet du serveur de rapports ; par exemple :</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>Si ce paramètre n’est pas inclus, le script part du principe que les services de rapport sont hébergés par la même instance SQL Server que celle qui héberge la base de données de surveillance.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>Non</p></td>
<td><p>Identité de service de la base de données de surveillance. Vous pouvez retourner les identités pour vos bases de données de surveillance en exécutant cette commande :</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


Une fois que les rapports de surveillance ont été installés, vous devez utiliser l’applet de commande Set-CsReportingConfiguration pour configurer l’URL utilisée pour accéder à ces rapports. Cette tâche peut être exécutée à partir de Lync Server Management Shell en exécutant la commande Windows PowerShell suivante. Notez qu’il est recommandé, mais pas obligatoire, d’utiliser le protocole HTTPS pour configurer l’URL des rapports :

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

Dans la commande précédente, la propriété ReportingUrl doit avoir la valeur de l’URL du Gestionnaire de rapports utilisé par SQL Server 2008 R2 Reporting Services. Vous pouvez la déterminer en suivant les étapes ci-après sur l’ordinateur sur lequel SQL Server Reporting Services a été installé :

1.  Cliquez sur Démarrer, sur Tous les programmes, sur Microsoft SQL Server 2008 R2, sur Outils de configuration, puis sur Gestionnaire de configuration de Reporting Services.

2.  Dans la boîte de dialogue Connexion relative à la configuration de Reporting Services, vérifiez que le nom de l’ordinateur Reporting Services apparaît dans la zone Nom du serveur. Sélectionnez l’instance SQL Server dans la liste déroulante Instance du serveur de rapports, puis cliquez sur Connecter.

3.  Dans le Gestionnaire de configuration de Reporting Services, cliquez sur URL du Gestionnaire de rapports. Une ou plusieurs URL doivent apparaître dans le volet URL du Gestionnaire de rapports. Chacune de ces URL peut être utilisée en tant qu’URL de rapports, même si, là encore, il est recommandé d’utiliser le protocole HTTPS pour le paramètre ReportingUrl.

Si vous avez configuré une base de données miroir pour votre base de données de surveillance, vous devez également associer les rapports de surveillance à la base de données miroir. Pour plus d’informations, reportez-vous à l’article [Association des rapports de surveillance avec une base de données miroir dans Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .

</div>

<span> </span>

</div>

</div>

</div>

