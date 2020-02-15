---
title: Présentation des paramètres de configuration du service de journalisation centralisée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bda4fe432841cd005671b18a163df57bd6e0bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5ae2d-102">Présentation des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ae2d-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ae2d-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5ae2d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5ae2d-104">Le service de journalisation centralisée est configuré pour définir ce que le service de journalisation doit collecter, le mode de collecte, l’emplacement à partir duquel il sera collecté et les paramètres de journalisation.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="5ae2d-105">Vous définissez ces paramètres globalement (c’est-à-dire pour l’ensemble du déploiement) ou pour un site (autrement dit, un site nommé dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="5ae2d-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="5ae2d-106">La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="5ae2d-107">Pour afficher la configuration actuelle du service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="5ae2d-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="5ae2d-108">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5ae2d-109">Tapez ce qui suit dans une invite de ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="5ae2d-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="5ae2d-110">Vous pouvez réduire ou développer l’étendue des paramètres de configuration qui sont renvoyés par <CODE>-Identity</CODE> la définition et une étendue, telle que « site : Redmond » pour renvoyer uniquement le CsClsConfiguration pour le site Redmond.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="5ae2d-111">Si vous souhaitez obtenir des détails sur une partie donnée de la configuration, vous pouvez rediriger la sortie vers une autre cmdlet Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="5ae2d-112">Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site "Redmond", tapez :<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="5ae2d-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="5ae2d-113">![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="5ae2d-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="5ae2d-114">Le résultat de l’applet de commande affiche la configuration actuelle du service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5ae2d-115">Paramètre de configuration</span><span class="sxs-lookup"><span data-stu-id="5ae2d-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="5ae2d-116">Description</span><span class="sxs-lookup"><span data-stu-id="5ae2d-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-117"><strong>Identité</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p103">Identifie la portée et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-121">Liste de tous scénarios définis pour cette configuration.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-123">Termes de recherche définis pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="5ae2d-124">Office 365, pas les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-126">Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="5ae2d-127">Site, dans ce contexte, est le site tel qu’il est défini dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-128"><strong>Régions</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-129">Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).</span><span class="sxs-lookup"><span data-stu-id="5ae2d-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p106">Chemin d’accès défini à l’emplacement où sont écrits les fichiers journaux sur les ordinateurs. CLSAgent écrit les fichiers journaux et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p107">Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p108">Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p109">Emplacement dans lequel rechercher les fichiers au format de message de suivi. Les fichiers au format de message de suivi servent à convertir les fichiers binaires en format lisible.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-p110">Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-149">Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-151">Définit la durée maximale de conservation des fichiers cache, en jours.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-153">Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-154"><strong>Limite componentthrottlelimit</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-155">Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5ae2d-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-157">Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5ae2d-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5ae2d-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="5ae2d-159">Version minimale de CLSAgent autorisée à s’exécuter.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="5ae2d-160">Cet élément est destiné à Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ae2d-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ae2d-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ae2d-161">See Also</span></span>


[<span data-ttu-id="5ae2d-162">Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ae2d-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="5ae2d-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5ae2d-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="5ae2d-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5ae2d-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="5ae2d-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5ae2d-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="5ae2d-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5ae2d-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

