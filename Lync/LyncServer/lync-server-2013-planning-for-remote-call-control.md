---
title: 'Lync Server 2013 : planification du contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99cf4d98f02554e7de344ded843b60406e755a3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526451"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planification du contrôle d’appel distant dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Dans Lync Server 2013, la prise en charge des scénarios de contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (Private Branch Exchange) à l’aide de Lync 2013 sur leurs ordinateurs de bureau. Cette section décrit les fonctionnalités de contrôle d’appel distant et les conditions nécessaires au déploiement du contrôle d’appel distant.

L’intégration entre un PBX et Lync Server 2013 permet aux utilisateurs activés pour le contrôle d’appel distant d’utiliser l’interface utilisateur de Lync 2013 pour contrôler les appels sur leurs téléphones PBX des manières suivantes :

<div>


> [!NOTE]  
> En définitive, les capacités de l’autocommutateur privé (PBX) qui héberge le téléphone PBX d’un utilisateur déterminent les fonctionnalités de contrôle d’appel distant qui sont mises à la disposition de cet utilisateur.



</div>

  - Passer un appel sortant

  - Répondre à un appel entrant

  - Répondre à un appel entrant avec un message instantané
    
    <div>
    

    > [!NOTE]  
    > C’est-à-dire, lorsque le numéro de téléphone de l’appelant peut être associé à une adresse de messagerie instantanée dans la liste d’adresses globale de votre organisation, dans la liste des contacts Lync de l’appelé ou dans l’organisation d’un partenaire fédéré.

    
    </div>

  - Transférer un appel

  - Transférer un appel entrant

  - Mettre des appels en attente

  - Basculer entre plusieurs appels simultanés

  - Répondre à un deuxième appel pendant un appel en cours (c’est-à-dire, mise en attente d’un appel)

  - Composer des chiffres de numérotation en fréquences vocales (DTMF)

  - Dans la fenêtre de conversation, taper des notes dans le programme de prise de note Microsoft Office OneNote

De plus, lorsqu’un utilisateur est activé pour le contrôle d’appel distant, Lync 2013 fournit les informations d’appel suivantes :

  - Identification d’un appelant par son nom lorsque le numéro de téléphone de l’appelant existe dans la liste des contacts d’un client de messagerie et de collaboration Microsoft Office Outlook de l’utilisateur à extension à distance, liste de contacts Lync ou liste d’adresses globale de votre organisation.

  - Appels entrants et sortants précédents, qui sont enregistrés dans le dossier Historique des conversations d’Outlook.

  - Les notifications d’appels manqués, qui sont envoyées au dossier boîte de réception Outlook de l’utilisateur, mais sont générées uniquement si Lync est en cours d’exécution lors de la réception de l’appel entrant.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Contrôle d’appel distant et Voix Entreprise

Bien que les fonctionnalités de contrôle d’appel distant soient distinctes des fonctionnalités voix entreprise et que les utilisateurs ne puissent pas les activer, voix entreprise fournit un sous-ensemble de fonctionnalités également accessibles aux utilisateurs activés pour le contrôle d’appel distant. Si Enterprise Voice est déployé, les utilisateurs qui sont activés pour le contrôle d’appel distant peuvent utiliser Lync pour accéder aux fonctionnalités voix entreprise suivantes :

  - Passer et recevoir des appels audio vers un autre client Lync

  - Joindre la partie audio d’une conférence créée par un utilisateur qui est activé pour voix entreprise

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

