---
title: 'Lync Server 2013 : Nouvelles fonctionnalités de l’application Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nouvelles fonctionnalités de l’application Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

L’application Response Group vous permet d’acheminer et de traiter en file d’attente les appels entrants vers des personnes disposant de personnes spécifiques, comme le service clientèle, le support technique interne ou l’assistance téléphonique générale pour un service.

Les fonctionnalités d’application de groupe de réponse suivantes sont une nouveauté de Lync Server 2013 :

  - **Rôle du responsable**
    
    Lync Server 2013 introduit un nouveau rôle responsable de groupe de réponse. Il existe désormais deux rôles de gestion pour les groupes de réponse : responsable de groupe de réponse et administrateur de groupe de réponse. Si les administrateurs de groupe de réponse peuvent tout de même configurer tous les éléments pour n’importe quel groupe de réponse, les responsables peuvent configurer uniquement certains éléments, uniquement pour les groupes de réponse qu’ils possèdent.
    
    Cette amélioration apportée au modèle d’administration offre une évolutivité du groupe de réponse, en particulier pour des scénarios de déploiement importants.

  - **Haute disponibilité**
    
    La prise en charge de la haute disponibilité pour l’application Response Group, sous la forme de la mise en miroir SQL Server, est activée dans le cadre de la configuration générale et du déploiement de la haute disponibilité pour Lync Server 2013. Si vous configurez pour une haute disponibilité et perdez votre connectivité au serveur principal principal, la fonctionnalité de groupe de réponse n’est pas affectée par l’utilisation du serveur principal en miroir.
    
    La prise en charge de la mise en miroir SQL Server pour l’application Response Group ne peut pas être activée ou configurée en dehors de la configuration globale de haute disponibilité Lync Server 2013.

  - **Récupération d’urgence**
    
    La prise en charge du reprise après sinistre pour l’application Response Group est activée dans le cadre de la configuration et du déploiement des pools frontaux couplés, qui font partie de la configuration globale de reprise après sinistre de Lync Server 2013. De plus, les cmdlets d’importation et d’exportation de groupe de réponse prennent en charge le processus de basculement vers le pool de sauvegarde et le processus de restauration vers le pool principal ou vers un nouveau pool. Si une interruption se produit dans le pool principal, les groupes de réponses peuvent être basculés vers le pool de sauvegardes, puis restaurés au pool principal ou à un nouveau pool lorsque l’interruption est terminée.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des groupes Response Group dans Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

