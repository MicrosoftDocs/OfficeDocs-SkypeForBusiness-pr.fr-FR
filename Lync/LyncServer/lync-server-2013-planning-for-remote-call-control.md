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
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planification du contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Dans Lync Server 2013, la prise en charge des scénarios de contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX en utilisant Lync 2013 sur leur ordinateur de bureau. Cette section décrit les fonctionnalités de contrôle d’appel distant et la configuration requise pour le déploiement du contrôle d’appel distant.

L’intégration entre un système PBX et Lync Server 2013 permet aux utilisateurs ayant activé le contrôle d’appel distant d’utiliser l’interface utilisateur de Lync 2013 pour contrôler les appels sur leurs téléphones PBX comme suit :

<div>


> [!NOTE]  
> Enfin, les fonctionnalités du PBX qui héberge le téléphone PBX d’un utilisateur déterminent les fonctionnalités de contrôle d’appel distant qui seront disponibles pour cet utilisateur.



</div>

  - Passer un appel sortant

  - Répondre à un appel entrant

  - Réponse à un appel entrant avec un message instantané
    
    <div>
    

    > [!NOTE]  
    > En d’autres termes, lorsque le numéro de téléphone de l’appelant peut être associé à une adresse de messagerie instantanée dans la liste d’adresses globale de votre organisation, dans la liste de contacts Lync du destinataire, ou dans une organisation de partenaire fédéré.

    
    </div>

  - Transférer un appel

  - Transférer un appel entrant

  - Bloquer les appels

  - Alterner entre plusieurs appels simultanés

  - Répondre à un deuxième appel alors qu’il est déjà en cours d’appel (en attente d’appel)

  - Composer un numéro à deux tonalités (DTMF)

  - Dans la fenêtre de conversation, tapez des notes dans le programme de prises de notes Microsoft Office OneNote

En outre, lorsqu’un utilisateur est activé pour le contrôle d’appel distant, Lync 2013 fournit les informations d’appel suivantes :

  - Identification d’un appelant par son nom lorsque le numéro de téléphone de l’appelant figure dans la liste des contacts d’un client de messagerie et de collaboration Microsoft Office Outlook prenant en charge la gestion des appels distants, liste de contacts Lync ou GAL de votre organisation.

  - Avez passé les appels entrants et sortants, qui sont enregistrés dans le dossier historique des conversations dans Outlook.

  - Les notifications d’appels manqués, qui sont envoyées au dossier de la boîte de réception Outlook de l’utilisateur, mais qui sont générées uniquement si Lync est en cours d’exécution lors de la réception de l’appel entrant.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Contrôle d’appel distant et voix entreprise

Bien que les fonctionnalités de contrôle d’appel distant soient distinctes des fonctions vocales d’entreprise et que les utilisateurs ne peuvent pas être activés pour les deux, Enterprise Voice fournit un sous-ensemble de fonctionnalités qui sont également disponibles pour les utilisateurs disposant d’un contrôle d’appel distant. Si Enterprise Voice est déployé, les utilisateurs dotés du contrôle d’appel distant peuvent utiliser Lync pour accéder aux fonctions vocales d’entreprise suivantes :

  - Passer et recevoir des appels audio vers un autre client Lync

  - Rejoindre la partie audio d’une conférence créée par un utilisateur activé pour voix entreprise

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

