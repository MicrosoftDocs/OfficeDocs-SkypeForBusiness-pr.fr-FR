---
title: 'Lync Server 2013: utilisation de l’application arrêter pour le service de journalisation centralisée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Utiliser le service de journalisation centralisé dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Vous pouvez arrêter une session de journalisation en cours à l’aide de l’applet de commande Stop-CsClsLogging. En général, vous rencontrerez peu de situations vous obligeant à arrêter une session de journalisation. Par exemple, vous n’avez pas à arrêter une séance de journalisation pour effectuer une recherche dans les journaux ou modifier les paramètres. Si deux scénarios sont en cours d’exécution, par exemple AlwaysOn et UserReplicator, alors que vous devez recueillir des informations relatives à l’authentification, vous devez arrêter un de ces deux scénarios (au niveau global, du site, du pool ou de l’ordinateur) avant de pouvoir lancer l’exécution du scénario Authentication. Pour en savoir plus, voir [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Lorsque vous déterminez les scénarios que vous pouvez exécuter sur un déploiement, un pool ou un ordinateur, vous devez vous souvenir que l’exécution de deux scénarios <STRONG>par ordinateur</STRONG>est limitée. Si vous effectuez la journalisation de l’activité d’un pool, vous devrez considérer ce pool globalement. Dans la plupart des cas, il n’est pas judicieux d’exécuter différents scénarios sur chaque ordinateur dans un pool. Il n’est pas non plus logique d’examiner le problème pour lequel vous recherchez des données et vous demander alors quel scénario convient le mieux pour un ordinateur donné dans le déploiement entier. Par exemple, si vous considérez le scénario UserReplicator, il n’y a pas de très grande valeur à exécuter UserReplicator sur un serveur Edge ou un pool de périphériques.<BR>Une fois que vous avez compris l’origine du problème et avez déterminé son impact, vous devez choisir soigneusement les scénarios à exécuter sur quels ordinateurs et pools. Bien qu’il soit judicieux d’exécuter le scénario AlwaysOn pour une application large, car il recueille des informations sur une grande variété de fournisseurs, certains scénarios ne sont utiles que sur certains ordinateurs ou pools. De plus, lorsque vous lancez une session de journalisation vous devez choisir au préalable le scénario offrant les meilleurs résultats. Si vous utilisez un scénario inapproprié, ou si vous utilisez un scénario qui est approprié pour la tâche mais pas adapté au niveau d’application envisagé (global, site, pool ou ordinateur), vous risquez d’obtenir des données inutiles, comme si vous n’aviez pas exécuté de scénario du tout.



</div>

Pour contrôler les fonctions de service de journalisation centralisées à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC), ou un rôle RBAC personnalisé contenant l’un de ces deux groupes. Pour renvoyer la liste de tous les rôles RBAC attribués à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Par exemple :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Pour arrêter une session de service de journalisation centralisée en cours d’exécution

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Interrogez le service de journalisation centralisé pour savoir quels scénarios sont actuellement en cours d’exécution en entrant les éléments suivants:
    
        Show-CsClsLogging
    
    ![Console Windows PowerShell après avoir appelé Show-CsCl] (images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console Windows PowerShell après avoir appelé Show-CsCl")
    
    Show-CsClsLogging affiche une synthèse des scénarios en cours d’exécution et de leur étendue d’application. Pour plus d’informations, voir [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Pour arrêter une session de journalisation en cours avec un scénario spécifique, tapez :
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Exemple :
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Cette commande arrête la journalisation avec le scénario UserReplicatior sur pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > Les journaux créés au cours de cette session de journalisation à l’aide du scénario UserReplicator sont conservés. Vous pouvez continuer à effectuer des recherches avec la journalisation à l’aide de la commande Search-CsClsLogging. Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Faisant pendant à l’applet de commande Start-CsClsLogging, l’applet de commande Stop-CsClsLogging arrête la session de journalisation, définie par des scénarios, et conserve les journaux créés par celle-ci. Vous pouvez exécuter deux scénarios sur un ordinateur donné à tout moment. La méthode d’arrêt d’un scénario pour recueillir des informations à l’aide d’un autre scénario est une tâche courante que vous pouvez effectuer au cours du dépannage de la plupart des charges de travail.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utiliser démarrer pour le service de journalisation centralisé pour capturer les journaux dans Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Présentation du service de journalisation centralisé dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Démarrer-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

