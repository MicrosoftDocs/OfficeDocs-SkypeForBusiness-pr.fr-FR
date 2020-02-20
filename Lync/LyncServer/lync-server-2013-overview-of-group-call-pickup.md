---
title: 'Lync Server 2013 : vue d’ensemble de la prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 222d587f7c4972a8aee313d3d66da578cde08960
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Vue d’ensemble de la prise d’appel de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-12_

Group Call Pick, une nouvelle fonctionnalité des mises à jour cumulatives pour Lync Server 2013 : février 2013, permet aux utilisateurs de répondre à leurs collègues à partir de leurs propres téléphones. Cette nouvelle fonctionnalité augmente la disponibilité de la ligne d’un utilisateur en permettant à d’autres utilisateurs de répondre à un appel entrant en composant un numéro de groupe de prise d’appel. Lorsque la prise d’appel de groupe est déployée, le nombre d’appels entrants acheminés vers la messagerie vocale peut être considérablement réduit, ce qui est particulièrement utile pour les appels provenant de clients externes à votre organisation.

La fonctionnalité de prise d’appel de groupe est conçue en particulier pour les divisions dans des environnements Office ouverts. Les appels entrants ne sont pas perturbés car ils ne sonnent qu’au niveau de destination prévu. Toutefois, les autres utilisateurs qui entendent la sonnerie peuvent toujours reprendre l’appel en composant le numéro de groupe.

Dans les environnements où les utilisateurs ne se trouvent pas dans un aménagement de bureau ouvert ou dans lesquels les utilisateurs qui partagent une responsabilité commune sont répartis géographiquement, les appels d’équipe présentent la solution la plus appropriée. La principale différence entre la prise d’appel de groupe et l’appel d’équipe est que, avec la prise d’appel de groupe, un appel entrant sonne uniquement à la destination prévue, mais tout le monde peut toujours choisir de le répondre en composant un numéro de groupe. Avec l’appel d’équipe, l’appel sonne sur tous les téléphones des membres de l’équipe et n’importe quel utilisateur de l’équipe peut prendre le téléphone pour répondre à l’appel. Une autre différence entre la prise d’appel de groupe et l’appel d’équipe est que la prise d’appel de groupe est gérée par un administrateur via Lync Server. Avec l’appel d’équipe, les utilisateurs finaux gèrent la fonctionnalité à l’aide du client Lync. Avec la prise d’appel de groupe, cet aspect de la gestion des appels peut donc être centralisé.

La prise d’appel de groupe est basée sur l’application de parcage d’appel. Lorsque vous déployez la prise d’appel de groupe, vous configurez la table d’orbites de parcage d’appel avec des plages de numéros d’extension séparées qui sont désignées comme numéros de groupe de prise d’appel. Comme les numéros d’orbite de parcage d’appel, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté. Chaque pool frontal où vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel. Les plages de numéros de groupe doivent être uniques au niveau global dans le déploiement Lync Server.

<div>


> [!NOTE]  
> Les plages de numéros qui sont désignées comme numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel ne peuvent pas être gérées ou visualisées à l’aide du panneau de configuration Lync Server. La seule façon d’afficher toutes les plages de numéros dans la table des orbites de parcage d’appel consiste à utiliser Lync Server Management Shell. De même, la seule façon d’ajouter, de modifier ou de supprimer des numéros de prise d’appel de groupe est d’utiliser Lync Server Management Shell.



</div>

Après avoir configuré les numéros de groupe de prise d’appel, vous affectez des utilisateurs à un groupe de prise d’appel. Tout utilisateur affecté à un groupe de prise d’appel peut faire en sorte que les appels soient traités par d’autres utilisateurs. Lorsqu’un appel arrive à un utilisateur affecté à un groupe de prise d’appel, tout autre utilisateur qui remarque l’appel peut y répondre en appelant manuellement le numéro de groupe de prise d’appel. L’utilisateur qui sélectionne l’appel ne doit pas nécessairement être membre du groupe. Lorsqu’un autre utilisateur reçoit un appel, une notification est envoyée au numéro initialement appelé.

<div>


> [!NOTE]  
> Un utilisateur ne peut être membre que d’un seul groupe de prise d’appel.



</div>

<div>


> [!NOTE]  
> Bien que tous les utilisateurs du déploiement Lync Server puissent répondre à un appel à un membre du groupe de prise d’appel, la personne répondant à l’appel doit indiquer le numéro de groupe de prise d’appel correct à composer.



</div>

Si un utilisateur compose un numéro de groupe de prise d’appel pour répondre à un appel lorsque plusieurs téléphones dans le groupe sonnent, l’utilisateur répond à l’appel qui a été le plus long.

Les paramètres de sonnerie simultanée fonctionneront pour les utilisateurs disposant de la prise d’appel de groupe. Autrement dit, un appel passé à un utilisateur disposant de la prise d’appel de groupe sonnera pour toutes les destinations configurées, et un autre utilisateur pourra répondre à l’appel. L’exception à cette règle est lorsque l’utilisateur configure la sonnerie simultanée pour appeler tous les membres de l’équipe.

La prise d’appel de groupe ne peut pas être utilisée pour répondre aux types d’appels suivants :

  - Appels vers une ligne privée

  - Appels à partir d’un contact auquel a été attribuée la relation de confidentialité amis et famille
    
    <div>
    

    > [!TIP]  
    > Un utilisateur membre d’un groupe de prise d’appel peut empêcher l’extraction de certains appels via la prise d’appel de groupe en marquant le contact comme contact personnel dans le client Lync. Pour marquer un contact comme contact personnel, définissez la relation de confidentialité du contact sur amis et famille. Les appels entrants provenant de contacts dont la relation de confidentialité est définie sur amis et la famille ne peuvent pas être récupérés à l’aide de la prise d’appel de groupe.

    
    </div>

  - Partie vidéo des appels audio/vidéo
    
    <div>
    

    > [!NOTE]  
    > Si un utilisateur répond à un appel audio/vidéo, il reçoit uniquement l’audio. La personne qui appelle ou la personne qui répond à l’appel peut escalader l’appel pour ajouter de la vidéo.

    
    </div>

  - Appels de sonnerie simultanés routés vers les membres de l’appel d’équipe

  - Appels routés vers un délégué

  - Appels routés vers un groupe Response Group

Les types d’utilisateurs suivants ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, ils ne doivent pas être inclus dans un groupe de prise d’appel de groupe et ne peuvent pas reprendre d’appels pour les utilisateurs qui ont activé la prise d’appel de groupe.

  - Utilisateurs hébergés en ligne dans un déploiement hybride

  - Les utilisateurs qui ne sont pas hébergés sur un pool Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013 : février 2013 dans un déploiement local

Si personne ne répond à un appel à un membre d’un groupe de prise d’appel, l’appel est acheminé comme indiqué dans les paramètres du client. Autrement dit, l’appel passe à la messagerie vocale ou est transféré vers une destination différente, comme indiqué dans les paramètres du client.

</div>

<span> </span>

</div>

</div>

</div>

