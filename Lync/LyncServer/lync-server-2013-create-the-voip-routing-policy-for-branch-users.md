---
title: 'Lync Server 2013 : création de la stratégie de routage VoIP pour les utilisateurs de succursale'
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
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Création de la stratégie de routage VoIP pour les utilisateurs de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-23_

Nous vous recommandons de créer une stratégie de Voix sur IP (VoIP) distincte pour les utilisateurs sur des sites de succursale. Cette stratégie doit contenir des itinéraires vers une sortie à partir de la passerelle Survivable Branch Appliance ou de la passerelle externe du serveur Survivable Branch Server et des itinéraires de sauvegarde vers une sortie à partir d’une passerelle sur le site central. Quel que soit l’emplacement d’enregistrement de l’utilisateur, soit sur le serveur d’inscriptions sur le Survivable Branch appliance, soit sur le serveur Survivable Branch Server, ou sur le cluster de serveurs d’inscriptions de sauvegarde du site central, la stratégie VoIP de l’utilisateur est toujours en vigueur.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Pour configurer la stratégie de routage VoIP pour les utilisateurs de sites de succursale

1.  Créez un plan de numérotation utilisateur et affectez-le aux utilisateurs. (Voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)

2.  Affectez les règles de normalisation correspondantes aux habitudes de numérotation des utilisateurs sur ce site. Si l’utilisateur Survivable Branch Appliance ou le serveur Survivable Branch Server bascule vers le pool de serveurs d’inscriptions de sauvegarde sur le site central, le même plan de numérotation sera appliqué. (Voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) dans la documentation des opérations.)

3.  Configurez un itinéraire des communications vocales qui egresses à partir de la passerelle Survivable Branch Appliance ou de la passerelle externe du serveur Survivable Branch Server. (Voir [créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md) dans la documentation des opérations.)

4.  Définissez un itinéraire d’appel de sauvegarde sur le Survivable Branch Appliance ou le Survivable Branch Server Gateway de manière à pointer vers le pool de serveurs d’inscriptions de sauvegarde (colocalisé avec le serveur de médiation) sur le site central. (Consultez votre Survivable Branch Appliance ou la documentation du fournisseur Survivable Branch Server.)
    
    <div>
    

    > [!NOTE]  
    > Cette configuration de l’acheminement des appels permet de s’assurer que les appels entrants vers l’utilisateur de succursale fonctionnent lorsque le Survivable Branch Appliance ou le serveur Survivable Branch Server n’est pas disponible (par exemple, s’il est arrêté pour maintenance). Si le serveur d’inscriptions et de médiation sur le Survivable Branch Appliance ou le serveur Survivable Branch Server ne sont pas disponibles et que l’utilisateur est inscrit auprès du pool de serveurs d’inscriptions de sauvegarde sur le site central, les appels entrants peuvent toujours être acheminés vers l’utilisateur.

    
    </div>

**Étape suivante**: [configurer les paramètres de réacheminement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

