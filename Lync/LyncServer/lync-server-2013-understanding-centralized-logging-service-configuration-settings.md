---
title: Présentation des paramètres de configuration du service de journalisation centralisée
description: Présentation des paramètres de configuration du service de journalisation centralisée.
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
ms.openlocfilehash: 0f99dbffe15c4b3f0dc13d231c3a2732a8554397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542400"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Présentation des paramètres de configuration du service de journalisation centralisée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Le service de journalisation centralisée est configuré pour définir ce que le service de journalisation doit collecter, le mode de collecte, l’emplacement à partir duquel il sera collecté et les paramètres de journalisation. Vous définissez ces paramètres globalement (c’est-à-dire pour l’ensemble du déploiement) ou pour un site (autrement dit, un site nommé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Pour afficher la configuration actuelle du service de journalisation centralisée

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Tapez ce qui suit dans une invite de ligne de commande :
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Vous pouvez réduire ou développer l’étendue des paramètres de configuration qui sont renvoyés par la définition <CODE>-Identity</CODE> et une étendue, telle que « site : Redmond » pour renvoyer uniquement le CsClsConfiguration pour le site Redmond. Si vous souhaitez obtenir des détails sur une partie donnée de la configuration, vous pouvez rediriger la sortie vers une autre cmdlet Windows PowerShell. Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site "Redmond", tapez : <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")
    
    Le résultat de l’applet de commande affiche la configuration actuelle du service de journalisation centralisée.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Paramètre de configuration</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Identité</strong></p></td>
    <td><p>Identifie la portée et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>Liste de tous scénarios définis pour cette configuration.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Termes de recherche définis pour la configuration. Office 365 ou Microsoft 365, pas les déploiements locaux.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Site, dans ce contexte, est le site tel qu’il est défini dans le générateur de topologies.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Régions</strong></p></td>
    <td><p>Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>Chemin d’accès défini à l’emplacement où sont écrits les fichiers journaux sur les ordinateurs. CLSAgent écrit les fichiers journaux et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Emplacement dans lequel rechercher les fichiers au format de message de suivi. Les fichiers au format de message de suivi servent à convertir les fichiers binaires en format lisible.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Définit la durée maximale de conservation des fichiers cache, en jours.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Limite componentthrottlelimit</strong></p></td>
    <td><p>Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>Version minimale de CLSAgent autorisée à s’exécuter. Cet élément est destiné à Office 365 ou Microsoft 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

