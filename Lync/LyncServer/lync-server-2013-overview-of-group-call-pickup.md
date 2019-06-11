---
title: 'Lync Server 2013: vue d’ensemble de la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 132d987b7d8007873a27cd74aacfc11e0c882c39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Présentation de l’enlèvement de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-12_

Le prélèvement d’appels de groupe, une nouvelle fonctionnalité dans les mises à jour cumulatives de Lync Server 2013: février 2013, permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone. Cette nouvelle fonctionnalité améliore la disponibilité de la ligne d’un utilisateur en permettant à d’autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe. Lors du déploiement de la prise d’appel de groupe, le nombre d’appels entrants vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels provenant de clients extérieurs à votre organisation.

La fonctionnalité de cueillette des appels de groupe est conçue en particulier pour les unités d’entreprise dans les environnements Office ouverts. Les appels entrants n’entraînent pas de perturbation, car ils sonnent uniquement sur le poste de leur destinataire. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent prendre l’appel en composant simplement le numéro de groupe.

Dans les environnements dans lesquels les utilisateurs ne se trouvent pas dans une mise en page de bureau ouverte ou lorsque les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, l’équipe appelle la solution la plus adaptée. La principale différence entre un appel de groupe et un appel d’équipe réside dans le fait que, si vous utilisez la fonction d’appel de groupe, un appel entrant sonne uniquement vers la destination prévue, mais tout le monde peut tout de même le répondre en composant un numéro de groupe. Grâce à l’appel d’équipe, l’appel sonne sur le téléphone des membres de l’équipe, et n’importe quel utilisateur de l’équipe peut capter son téléphone pour répondre à l’appel. Une différence supplémentaire entre le prélèvement d’appels de groupe et l’appel d’équipe est la gestion par un administrateur des appels de groupe par le biais de Lync Server. Avec l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Lync. Ce choix est centralisé grâce à la fonction de redirection des appels de groupe.

La cueillette des appels de groupe repose sur l’application de stationnement d’appels. Lorsque vous déployez un appel de groupe, vous configurez la table d’orbite du parc d’appels avec des plages distinctes de numéros d’extension désignés comme numéros de groupe de cueillette d’appel. À l’image des numéros d’appel parqué, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles n’est affecté aucun utilisateur ou téléphone. Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel. Les plages de numéros de groupe doivent être globalement uniques dans le déploiement de Lync Server.

<div>


> [!NOTE]  
> Les plages de nombres qui sont désignées en tant que numéros de capture d’appel de groupe dans la table de parc d’appels ne peuvent pas être gérées ou affichées à l’aide du panneau de configuration de Lync Server. La seule façon d’afficher toutes les plages de chiffres dans la table de stationnement d’appels consiste à utiliser Lync Server Management Shell. De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de capture d’appels de groupe consiste à utiliser Lync Server Management Shell.



</div>

Après avoir configuré les numéros de groupe de prise d’appel, vous affectez les utilisateurs à un groupe de prise d’appel. Les appels destinés à un utilisateur membre d’un groupe de prise d’appel peuvent être pris par les autres utilisateurs. Lorsqu’un appel parvient à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en composant manuellement le numéro du groupe de prise d’appel. Il n’est pas nécessaire que l’utilisateur qui prend l’appel soit membre du groupe. Lorsqu’un appel est pris par un autre utilisateur, une notification est envoyée au numéro initialement appelé.

<div>


> [!NOTE]  
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel.



</div>

<div>


> [!NOTE]  
> Même si tout utilisateur du déploiement de Lync Server peut répondre à un appel d’un membre d’un groupe de capture d’appel, la personne qui répond à l’appel doit connaître le numéro du groupe de capture d’appel approprié pour composer le numéro.



</div>

Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel alors que plusieurs téléphones du groupe sonnent, il répond à l’appel qui a sonné en premier.

Les paramètres de sonnerie simultanée fonctionnent pour les utilisateurs qui bénéficient de la prise d’appel de groupe. Autrement dit, un appel passé à un utilisateur disposant d’un appel de groupe sonne pour toutes les destinations configurées et un autre utilisateur peut répondre à l’appel. Toutefois, cette règle ne s’applique pas si l’utilisateur configure une sonnerie simultanée pour appeler tous les membres de l’équipe.

La cueillette de groupe ne peut pas être utilisée pour répondre aux types d’appel suivants:

  - Appels à destination d’une ligne privée

  - Appels en provenance d’un contact auquel a été affecté le niveau de confidentialité Famille et amis
    
    <div>
    

    > [!TIP]  
    > Les utilisateurs qui sont membres d’un groupe de captures d’appels peuvent empêcher certains appels d’être récupérés par le biais du prélèvement d’appels de groupe en le marquant en tant que contact personnel dans le client Lync. Pour marquer un contact en tant que contact personnel, définissez le niveau de confidentialité du contact sur Famille et amis. Tout appel entrant provenant de contacts dont le niveau de confidentialité est défini sur amis et votre famille ne peut pas être récupéré à l’aide de la fonction de cueillette d’appel de groupe.

    
    </div>

  - Partie vidéo d’un appel audio/vidéo
    
    <div>
    

    > [!NOTE]  
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement la partie audio. La personne qui passe l’appel ou celle qui y répond peut doter l’appel de la fonctionnalité vidéo.

    
    </div>

  - Appels à sonnerie simultanée routés vers les membres d’appel de l’équipe

  - Appels routés vers un délégué

  - Appels routés vers un service Response Group

Les types d’utilisateurs suivants ne peuvent pas participer à la cueillette de groupe. Autrement dit, ils ne doivent pas être inclus dans un groupe de prélèvement d’appels de groupe et ne peuvent pas répondre aux appels pour les utilisateurs disposant d’une cueillette de groupe activée.

  - Utilisateurs hébergés en ligne dans un déploiement hybride

  - Utilisateurs qui ne sont pas hébergés sur un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 février dans un déploiement local

Si personne ne répond à un appel destiné à un membre d’un groupe de prise d’appel, l’appel est routé conformément au paramétrage défini dans les paramètres du client. En d’autres termes, l’appel est acheminé vers la messagerie vocale ou transféré à une autre destination.

</div>

<span> </span>

</div>

</div>

</div>

