---
title: 'Lync Server 2013 : Création de la stratégie de routage VoIP pour les utilisateurs de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-23_

Nous vous recommandons de créer une stratégie VoIP (Voice over IP) distincte pour les utilisateurs des sites de succursales. Cette stratégie doit contenir des itinéraires vers la sortie à partir de la passerelle de l’appareil de branchement survivant ou de la passerelle externe du serveur de succursales survivant et des itinéraires de sauvegarde vers la sortie à partir d’une passerelle sur le site central. Quel que soit l’endroit où l’utilisateur est inscrit, soit dans le Bureau d’enregistrement sur l’appareil de succursale survivant ou sur le serveur de succursales survivant, soit dans le groupe d’inscriptions de secours sur le site central, la stratégie VoIP de l’utilisateur est toujours en vigueur.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Pour configurer la stratégie de routage VoIP pour les utilisateurs de succursales

1.  Créer un plan de numérotation utilisateur et l’affecter aux utilisateurs de succursales. (Pour plus d’informations, reportez-vous à la rubrique [création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) .)

2.  Affectez des règles de normalisation correspondant aux habitudes de numérotation des utilisateurs sur ce site. Dans le cas où l’utilisateur de l’unité de branchement survivant ou du serveur de succursale Survivable bascule vers le pool d’inscriptions de secours sur le site central, le même plan de numérotation sera appliqué. (Pour plus d’informations, reportez-vous à la rubrique [création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) .)

3.  Configurez un itinéraire vocal qui egresses à partir de la passerelle de l’appareil de succursale survivant ou de la passerelle externe du serveur de succursales survivant. (Pour plus d’informations, reportez-vous à la rubrique [création d’un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) .)

4.  Définissez un itinéraire de sauvegarde sur l’appareil de branchement survivant ou la passerelle du serveur de succursales survivant pour qu’il pointe vers le pool de bureau d’enregistrement de sauvegarde (colocalisé avec le serveur de médiation) sur le site central. (Voir votre appareil de succursale survivant ou la documentation du fournisseur de votre serveur de succursales survivant.)
    
    <div>
    

    > [!NOTE]  
    > Cette opération de sauvegarde de l’itinéraire permet de garantir que les appels entrants de l’utilisateur de la succursale fonctionneront lorsque l’unité de branchement ou le serveur de succursale Survivable ne sera pas disponible (par exemple, s’il est arrêté pour maintenance). Si le serveur d’inscriptions et de médiation sur l’appareil de branchement survivant ou la succursale Survivable ne sont pas disponibles, et si l’utilisateur est inscrit auprès du pool d’inscriptions de sauvegarde au niveau du site central, les appels entrants peuvent toujours être routés vers l’utilisateur.

    
    </div>

**Étape suivante**: [configurer les paramètres de reroutage de la messagerie vocale dans Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

