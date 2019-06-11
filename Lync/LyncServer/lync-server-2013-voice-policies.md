---
title: 'Lync Server 2013 : Stratégies de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca1e72a1b62a224898d98aec7fcef9bc62ddf8bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a>Stratégies de voix dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

*Politiques vocales* Lync Server définissez les éléments suivants pour chaque utilisateur, site ou organisation affecté à la stratégie:

  - Un ensemble de fonctionnalités d’appel qui peuvent être activées ou désactivées pour déterminer la fonctionnalité voix entreprise disponible aux utilisateurs.

  - un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (PSTN) qui définissent le type des appels autorisés.

<div>

## <a name="planning-for-voice-policies"></a>Planification des politiques vocales

Les étapes suivantes vous aideront à planifier les stratégies vocales dont vous aurez besoin pour votre déploiement voix entreprise:

  - Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit). Ce paramètre s’applique à tous les utilisateurs de l’entreprise voix qui n’ont pas explicitement reçu une stratégie de niveau site ou par utilisateur.

  - Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.

  - Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.

  - Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.

  - Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.

<div>

## <a name="voice-policy-scope"></a>Étendue de stratégie de voix

L’*étendue de stratégie de voix* détermine le niveau hiérarchique auquel la stratégie peut être appliquée. Dans Lync Server, vous pouvez configurer des stratégies de voix avec les niveaux d’étendue suivants (classés du plus spécifique au plus général).

  - Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.
    
    <div>
    

    > [!NOTE]  
    > Nous vous recommandons de déployer une stratégie de voix utilisateur pour les utilisateurs de la voix de votre site de succursale et ceux qui sont inscrits auprès du déploiement de site central, ou les utilisateurs enregistrés sur une unité de succursale Survivable.

    
    </div>

  - Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.

  - La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit. Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer. Cette politique vocale s’applique à tous les utilisateurs, à tous les groupes et aux objets de contact Enterprise Voice dans votre déploiement, sauf si vous configurez et attribuez une stratégie vocale avec une étendue plus spécifique. Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.

</div>

<div>

## <a name="call-features"></a>Fonctionnalités d’appel

Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.

  - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

  - **Parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.

  - **Sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple, un téléphone mobile) ou sur d’autres périphériques de terminaison. Activée par défaut.

  - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.

  - **Réacheminement PSTN** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau étendu est saturé ou indisponible. Activée par défaut.

  - **Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.

  - Le **suivi des appels malveillants** permet aux utilisateurs de signaler des appels malveillants en utilisant le client Lync, puis de marquer ces appels dans les enregistrements des détails des appels. Désactivé par défaut.

  - La boîte **vocale** d’arrêt empêche le routage des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsqu’une sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou en dehors de la plage et repose sur une valeur de minuteur. Ce paramètre active et désactive le minuteur et définit la valeur de Timer. Il peut être configuré uniquement à l’aide de Lync Server Management Shell. Désactivé par défaut.

  - Le **transfert d’appel et la sonnerie simultanée des utilisations RTC** permettent aux administrateurs de spécifier la même utilisation PSTN que la stratégie vocale pour le transfert d’appel et la sonnerie simultanée, limiter le transfert d’appel et la sonnerie simultanée aux utilisateurs de Lync internes uniquement; vous pouvez ou spécifier une utilisation PSTN personnalisée qui est différente de l’utilisation du RTC de la stratégie vocale. L’utilisation de la même utilisation PSTN que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.

</div>

<div>

## <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation PSTN associés. Les utilisations PSTN peuvent être associées à la stratégie de voix pour les besoins de la sonnerie simultanée et du transfert d’appel uniquement. Pour plus d’informations sur la planification des enregistrements d’utilisation RTC, voir [enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md).

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

