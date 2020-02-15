---
title: 'Lync Server 2013 : stratégies de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a9df9b1caa42d3dc17d2f4f9e0908ed69d5660d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>Stratégies de voix dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Les *stratégies de voix* Lync Server définissent les éléments suivants pour chaque utilisateur, site ou organisation auquel la stratégie est attribuée :

  - Ensemble de fonctionnalités d’appel pouvant être activées ou désactivées pour déterminer la fonctionnalité voix entreprise disponible pour les utilisateurs.

  - un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (RTC) qui définissent le type des appels autorisés.

<div>

## <a name="planning-for-voice-policies"></a>Planification pour les stratégies de voix

Les étapes suivantes vous aideront à planifier les stratégies de voix dont vous aurez besoin pour votre déploiement de voix entreprise :

  - Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit). Cette stratégie s’applique à tous les utilisateurs voix entreprise qui ne sont pas explicitement affectés à une stratégie au niveau du site ou par utilisateur.

  - Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.

  - Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.

  - Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.

  - Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.

<div>

## <a name="voice-policy-scope"></a>Étendue de stratégie de voix

L’*étendue de stratégie de voix* détermine le niveau hiérarchique auquel la stratégie peut être appliquée. Dans Lync Server, vous pouvez configurer des stratégies de voix avec les niveaux d’étendue suivants (dont la configuration est la plus spécifique au plus général).

  - Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.
    
    <div>
    

    > [!NOTE]  
    > Nous vous recommandons de déployer une stratégie de voix utilisateur pour les utilisateurs de voix entreprise de site de succursale inscrits avec le déploiement de site central ou les utilisateurs inscrits sur un Survivable Branch appliance.

    
    </div>

  - Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.

  - La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit. Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer. Cette stratégie de voix s’applique à tous les utilisateurs, groupes et contacts de voix entreprise de votre déploiement, sauf si vous configurez et affectez une stratégie de voix avec une étendue plus spécifique. Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.

</div>

<div>

## <a name="call-features"></a>Fonctionnalités d’appel

Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.

  - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

  - Le **parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.

  - La **sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple un téléphone mobile) ou sur d’autres périphériques d’extrémité. Activée par défaut.

  - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.

  - Le **réacheminement PSTN** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau WAN est saturé ou indisponible. Activée par défaut.

  - Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.

  - Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants à l’aide du client Lync, puis d’indiquer ces appels dans les enregistrements des détails des appels. Désactivé par défaut.

  - La **messagerie vocale d’échappement** empêche les appels d’être immédiatement routés vers le système de messagerie vocale de téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou en dehors de la plage et est basé sur une valeur de minuteur. Ce paramètre active et désactive le minuteur et définit la valeur du minuteur. Il ne peut être configuré qu’à l’aide de Lync Server Management Shell. Désactivé par défaut.

  - La fonctionnalité **Utilisations PSTN du transfert d’appel et de la sonnerie simultanée** permet aux administrateurs de spécifier la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée, de limiter le transfert d’appel et la sonnerie simultanée aux utilisateurs Lync internes ou de spécifier une utilisation PSTN personnalisée différente de l’utilisation PSTN de la stratégie de voix. L’utilisation de la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.

</div>

<div>

## <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation PSTN associés. Les utilisations PSTN peuvent être associées à la stratégie de voix pour des besoins de la sonnerie simultanée et du transfert d’appel uniquement. Pour plus d’informations sur la planification des enregistrements d’utilisation RTC, voir [RTC usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).

<div>


> [!NOTE]  
> L’ordre des utilisations PSTN est important parce que, lors de la mise en correspondance des utilisateurs et des itinéraires, la fonctionnalité de routage sortant compare les utilisations PSTN du haut vers le bas. Si la première utilisation correspond à l’itinéraire d’appel, cet itinéraire est utilisé. Sinon, la fonctionnalité de routage sortant examine l’utilisation PSTN suivante dans la liste et continue jusqu’à trouver une correspondance. Ainsi, les utilisations PSTN suivantes assurent une alternative si la première de la liste est indisponible.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

