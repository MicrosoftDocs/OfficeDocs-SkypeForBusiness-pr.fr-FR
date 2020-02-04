---
title: 'Lync Server 2013 : configuration du routage géodépendant pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuration du routage géodépendant pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-11_

L’application de conférence de routage basée sur l’emplacement repose sur la configuration du routage de l’emplacement Lync Server 2013. Les configurations principales suivantes sont disponibles :

  - L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau. Un site réseau et ses sous-réseaux de réseaux associés doivent être définis dans Lync Server pour appliquer le routage par emplacement.

  - Pour appliquer le routage de réunions par emplacement, les participants à Lync doivent être activés pour le routage par emplacement.

  - Pour appliquer le routage de points de terminaison PSTN qui se connecte à l’emplacement de la réunion, le Trunk SIP utilisé pour connecter les points de terminaison PSTN doit être configuré pour le routage basé sur l’emplacement.

Pour plus d’informations sur le déploiement et la configuration du routage en fonction de l’emplacement de Lync Server 2013, consultez la rubrique Configuration du [routage en fonction](lync-server-2013-configuring-location-based-routing.md)de l’emplacement.

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Activation de l’application de conférence de routage basée sur l’emplacement

L’application de conférence de routage basée sur l’emplacement est désactivée par défaut. Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application. Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Lync Server Management Shell :

Get-CsServerApplication-Identity service : nom\<de domaine complet du pool : FQDN\>

Dans cette applet de \<demande,\> le nom de domaine complet (FQDN) du pool est le pool dans lequel l’application de conférence de routage basée sur l’emplacement doit être activée.

Ce cmdlet renverra la liste des applications hébergées par Lync Server et la valeur Priority (priorité) pour chacune d’elles. L’application de conférence de routage basée sur l’emplacement doit être affectée d’une valeur de priorité supérieure à l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ». Nous vous recommandons d’affecter une valeur de priorité à l’application de conférence de routage basée sur l’emplacement, qui est un point supérieur à la valeur de priorité de l’application « UdcAgent ».

Par exemple, si l’application « UdcAgent » a une valeur de priorité de « 2 », l’application « DefaultRouting » a une valeur de priorité de « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 », alors vous devez attribuer une valeur de priorité de type « 3 » à l’application de conférence de routage basée sur l’emplacement. Ainsi, la priorité des applications est définie dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence avec routage géodépendant (priorité : 3), autres applications (priorités : 4 à 8), « DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).

Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de conférence de routage basée sur l’emplacement, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition sur lequel les utilisateurs ont activé le routage d’emplacement :

New-CsServerApplication-Identity service : Registrar\<: nom\>de domaine complet \<(FQDN\> )/LBRouting-Priority application Priority $true-URL critiques $truehttp://www.microsoft.com/LCS/LBRouting

Par exemple :

New-CsServerApplication-Identity service :Registrar :LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3 $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Après avoir utilisé cette applet de demande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition dans lesquels l’application de conférence de routage basée sur l’emplacement est activée.

<div>


> [!IMPORTANT]  
> Les application de routage basées sur les emplacements aux conférences ou aux transferts de consultation ne seront pas appliquées tant que tous les serveurs frontaux dans les listes applicables ou les serveurs Standard Edition Server ne sont pas redémarrés.



</div>

Lorsque l’application de conférence de routage basée sur l’emplacement est activée et que tous les serveurs Lync en vigueur ont été redémarrés, toutes les conférences organisées par les utilisateurs de Lync activées pour le routage de l’emplacement seront surveillées pour éviter le contournement du numéro RTC

</div>

</div>

<span> </span>

</div>

</div>

</div>

