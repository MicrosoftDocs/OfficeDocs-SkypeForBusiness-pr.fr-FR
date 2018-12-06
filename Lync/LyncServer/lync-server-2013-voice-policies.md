---
title: 'Lync Server 2013 : Stratégies de voix'
TOCTitle: Stratégies de voix
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412891(v=OCS.15)
ms:contentKeyID: 49298627
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Stratégies de voix dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Lync Server Les *stratégies de voix* définissent les éléments suivants pour chaque utilisateur, site ou organisation auxquels la stratégie est affectée :

  - un ensemble de fonctionnalités d’appel pouvant être activées ou désactivées pour déterminer la fonctionnalité Voix Entreprise disponible pour les utilisateurs ;

  - un ensemble d’enregistrements de l’utilisation du réseau téléphonique commuté (RTC) qui définissent le type des appels autorisés.

## Planification pour les stratégies de voix

Les étapes suivantes vous permettent de planifier les stratégies de voix dont vous avez besoin pour votre déploiement Voix Entreprise :

  - Déterminez la configuration prévue de votre stratégie de voix globale (stratégie de voix par défaut installée avec le produit). Cette stratégie s’applique à tous les utilisateurs Voix Entreprise auxquels vous n’avez pas explicitement affecté une stratégie utilisateur de niveau site ou par utilisateur.

  - Identifiez les stratégies de voix de niveau site dont vous avez éventuellement besoin.

  - Identifiez les stratégies de voix par utilisateur dont vous avez éventuellement besoin.

  - Décidez des fonctionnalités d’appel à activer pour chaque stratégie de voix.

  - Déterminez les enregistrements d’utilisation DNS à configurer pour chaque stratégie de voix.

## Étendue de stratégie de voix

L’*étendue de stratégie de voix* détermine le niveau hiérarchique auquel la stratégie peut être appliquée. Dans Lync Server, vous pouvez configurer des stratégies de voix avec les niveaux d’étendue suivants (répertoriés du plus spécifique au plus général).

  - Une **stratégie de voix d’utilisateur** peut être affectée à des utilisateurs individuels, à des groupes ou à des objets contact. Il s’agit de la stratégie de plus bas niveau. Les stratégies de voix d’utilisateur peuvent être déployées afin d’activer des fonctionnalités pour certains utilisateurs ou groupes au niveau d’un site, mais pas pour les autres du même site. Par exemple, il peut être utile de désactiver la numérotation longue distance pour certains employés. Dans le cadre de l’affectation d’une stratégie de voix, un objet contact est traité comme un utilisateur individuel.
    
    > [!NOTE]  
    > Il est recommandé de déployer une stratégie de voix d’utilisateur pour les utilisateurs Voix Entreprise d’un site de succursale inscrits auprès du déploiement du site central ou pour les utilisateurs inscrits sur un Survivable Branch Appliance.

  - Une **stratégie de voix de site** s’applique à un site entier, à l’exception des utilisateurs, groupes ou objets contact affectés à une stratégie de voix d’utilisateur. Pour définir une stratégie de voix de site, vous devez spécifier le site auquel la stratégie s’applique. Si aucune stratégie de voix d’utilisateur n’est affectée, la stratégie de voix de site est utilisée.

  - La **stratégie de voix globale** est la stratégie de voix par défaut installée avec le produit. Vous pouvez modifier la stratégie de voix globale pour l’adapter aux besoins spécifiques de votre organisation, mais vous ne pouvez pas la renommer ou la supprimer. Cette stratégie de voix s’applique à tous les utilisateurs, groupes et objets contact Voix Entreprise de votre déploiement, sauf si vous configurez et affectez une stratégie de voix avec une étendue plus spécifique. Si vous souhaitez désactiver entièrement cette stratégie, assurez-vous que tous les sites et utilisateurs disposent de stratégies personnalisées affectées.

## Fonctionnalités d’appel

Vous pouvez activer ou désactiver les fonctionnalités d’appel suivantes pour chaque stratégie de voix :

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Activée par défaut.

  - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Activée par défaut.

  - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

  - Le **parcage d’appel** permet aux utilisateurs de parquer des appels pour décrocher l’appel depuis un téléphone ou un client distinct. Désactivée par défaut.

  - La **sonnerie simultanée** permet aux appels entrants de sonner sur un téléphone supplémentaire (par exemple, un téléphone mobile) ou sur d’autres périphériques de terminaison. Activée par défaut.

  - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.

  - Le **réacheminement RTC** permet de réacheminer sur le réseau téléphonique commuté les appels effectués depuis des utilisateurs auxquels cette stratégie est affectée vers d’autres utilisateurs d’entreprise, si le réseau étendu est saturé ou indisponible. Activée par défaut.

  - Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.

  - Le **suivi des appels malveillants** permet aux utilisateurs de signaler les appels malveillants à l’aide du client Lync et de les indiquer dans les enregistrements des détails des appels. Désactivé par défaut.

  - La fonctionnalité **Voicemail escape** empêche que les appels soient immédiatement acheminés vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, à court de batterie ou hors de portée. Il est basé sur une valeur de minuterie. Ce paramètre active ou désactive la minuterie et en définit la valeur. Il peut être configuré uniquement à l’aide de Lync Server Management Shell. Désactivée par défaut.

  - La fonctionnalité **Utilisations RTC du transfert d’appel et de la sonnerie simultanée** permet aux administrateurs de spécifier la même utilisation RTC que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée, de limiter le transfert d’appel et la sonnerie simultanée aux utilisateurs Lync internes ou de spécifier une utilisation RTC personnalisée différente de l’utilisation RTC de la stratégie de voix. L’utilisation de la même utilisation RTC que la stratégie de voix pour le transfert d’appel et la sonnerie simultanée est la valeur par défaut.

## Enregistrements d’utilisation RTC

Chaque stratégie de voix doit disposer d’un ou de plusieurs enregistrements d’utilisation RTC associés. Les utilisations RTC peuvent être associées à la stratégie de voix pour des besoins de la sonnerie simultanée et du transfert d’appel uniquement. Pour plus d’informations sur la planification des enregistrements d’utilisation RTC, reportez-vous à [Enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-pstn-usage-records.md).

> [!NOTE]  
> L’ordre des utilisations RTC est important parce que, lors de la mise en correspondance des utilisateurs et des itinéraires, la fonctionnalité de routage sortant compare les utilisations RTC du haut vers le bas. Si la première utilisation correspond à l’itinéraire d’appel, cet itinéraire est utilisé. Sinon, la fonctionnalité de routage sortant examine l’utilisation RTC suivante dans la liste et continue jusqu’à trouver une correspondance. Ainsi, les utilisations RTC suivantes assurent une alternative si la première de la liste est indisponible.
