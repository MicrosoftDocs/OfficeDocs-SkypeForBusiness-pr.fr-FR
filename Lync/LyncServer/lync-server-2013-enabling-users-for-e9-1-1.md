---
title: 'Lync Server 2013 : activation des utilisateurs pour E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Activation des utilisateurs pour E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Lors de l’inscription du client, Lync Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs à extension voix entreprise. Cette stratégie contient les paramètres qui définissent comment E9-1-1 est implémenté. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et indique si un utilisateur est requis ou non pour entrer manuellement un emplacement si le service informations d’emplacement ne en fournit pas automatiquement un. Pour obtenir une définition complète d’une stratégie d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server peut attribuer une stratégie d’emplacement aux clients basés sur un sous-réseau ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.

  - **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**  
    Vous pouvez assigner un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, en affectant une stratégie d’emplacement à un site réseau Lync Server, puis en ajoutant des sous-réseaux au site, vous pouvez limiter la prise en charge du E9-1-1 aux emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage E9-1-1 pour chaque site.

<!-- end list -->

  - **Envisagez-vous d’activer des utilisateurs individuels au moyen d’une stratégie utilisateur ?**  
    Vous pouvez assigner directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.

<!-- end list -->

  - **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, ces clients doivent-ils bénéficier du service E9-1-1 ?**  
    Si des utilisateurs se voient attribuer une stratégie d’emplacement globale, de site ou par utilisateur, il peut être nécessaire d’entrer manuellement un emplacement dans le client si celui-ci ne se trouve pas dans un sous-réseau défini ou s’il a été trouvé par le service d’informations d’emplacement. Pour plus d’informations, reportez-vous à [la rubrique définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

