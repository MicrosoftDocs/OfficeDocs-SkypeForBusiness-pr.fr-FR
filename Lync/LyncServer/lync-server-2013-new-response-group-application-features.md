---
title: 'Lync Server 2013 : nouvelles fonctionnalités de l’application Response Group'
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
ms.openlocfilehash: f4ae3ad427164d8a948130e69fd54d1e6f8c37b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536851"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nouvelles fonctionnalités de l’application Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

L’application Response Group vous permet de router et de placer en file d’attente des appels entrants vers des entités désignées pour des objectifs spéciaux (par exemple, un service clientèle, un service d’assistance interne ou un service d’assistance téléphonique général dédié à un service).

Les fonctionnalités d’application Response Group suivantes sont nouvelles dans Lync Server 2013 :

  - **Rôle de gestionnaire**
    
    Lync Server 2013 introduit un nouveau rôle gestionnaire de groupes Response Group. À présent, il existe deux rôles de gestion pour les groupes Response Group : Response Group Manager et l’administrateur Response Group. Alors que les administrateurs de groupes de réponse peuvent toujours configurer un élément pour un groupe Response Group, les gestionnaires peuvent configurer uniquement certains éléments, uniquement pour les groupes Response Group qu’ils possèdent.
    
    Cette amélioration du modèle d’administration tire parti de l’extensibilité Response Group, en particulier pour les scénarios de déploiement de grande taille.

  - **Haute disponibilité**
    
    La prise en charge de la haute disponibilité pour l’application Response Group, sous la forme de la mise en miroir SQL Server, est activée dans le cadre de la configuration globale et du déploiement de la haute disponibilité pour Lync Server 2013. Si vous configurez la haute disponibilité et si vous perdez la connectivité au serveur principal, la fonctionnalité Response Group n’est pas affectée, car elle tire profit du serveur principal en miroir.
    
    La prise en charge de la mise en miroir SQL Server pour l’application Response Group ne peut pas être activée ou configurée de manière individuelle en dehors de la configuration globale de la haute disponibilité de Lync Server 2013.

  - **Récupération d’urgence**
    
    La prise en charge de la récupération d’urgence pour l’application Response Group est activée dans le cadre de la configuration et du déploiement des pools frontaux couplés, qui font partie de la configuration globale de la récupération d’urgence de Lync Server 2013. En outre, les applets de commande d’importation et d’exportation Response Group prennent en charge le processus de basculement vers le pool de sauvegarde, ainsi que le processus de restauration automatique vers le pool principal ou un nouveau pool. Si une panne survient dans le pool principal, les groupes Response Group peuvent faire l’objet d’un basculement vers le pool de sauvegarde, puis d’une restauration automatique vers le pool principal ou un nouveau pool une fois la panne terminée.

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

