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
ms.openlocfilehash: 86d5032defc7322e96662dcfe6357bd30c598e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Activation des utilisateurs pour E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Lors de l’enregistrement du client, Lync Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs d’Enterprise Voice. Cette stratégie contient les paramètres qui déterminent la façon dont E9-1-1 est implémenté. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et si un utilisateur est tenu d’entrer manuellement un emplacement si le service d’information d’emplacement n’en a pas fourni automatiquement un. Pour obtenir une définition complète d’une stratégie d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server peut affecter une stratégie d’emplacement aux clients en fonction du sous-réseau, ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.

  - **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**  
    Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Toutefois, en assignant une stratégie d’emplacement à un site réseau du serveur Lync et en ajoutant des sous-réseaux au site, vous pouvez limiter le support de E9-1-1 à des emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage de E9-1-1 pour chaque site.

<!-- end list -->

  - **Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**  
    Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.

<!-- end list -->

  - **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**  
    Si des utilisateurs se voient attribuer une stratégie d’emplacement globale, de site ou par utilisateur, ils peuvent être obligés d’entrer manuellement un emplacement dans le client si le client ne se trouve pas dans un sous-réseau défini ou s’il n’y a pas de localisation trouvée par le service d’informations d’emplacement. Pour plus d’informations, reportez-vous à [définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

