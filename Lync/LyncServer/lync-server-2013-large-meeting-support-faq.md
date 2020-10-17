---
title: 'Lync Server 2013 : Forum aux questions sur la prise en charge des grandes réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d25c317aa672b56f244fafefc8d96b0c31bc33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514001"
---
# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Forum aux questions sur la prise en charge des grandes réunions pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Les sections suivantes apportent des réponses aux questions fréquemment posées sur la création et l’exécution de grandes réunions.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Q : Combien d’utilisateurs peuvent participer à une grande réunion ?

Le modèle utilisateur Lync Server spécifie des limites de 250 utilisateurs dans un pool partagé ou 1000 utilisateurs dans un pool dédié aux grandes réunions, mais ces chiffres représentent uniquement le nombre d’utilisateurs que nous avons testés et uniquement pour le jeu de matériel spécifique que nous avons utilisé lors de nos tests. En fonction de nos tests, nous recommandons ces limites pour les tailles maximales. Toutefois, vous contrôlez le nombre réel de participants autorisés dans les réunions de votre organisation en configurant une ou plusieurs stratégies de conférence (que vous configurez à l’aide des applets de commande Windows PowerShell dans Lync Server Management Shell ou à l’aide du panneau de configuration Lync Server). Le nombre que vous spécifiez dans une stratégie de conférence peut être n’importe quel nombre entier de 32 bits compris entre 1 et 4 294 967 295, mais la taille recommandée est comprise entre 2 et 250 participants (inclus). et la valeur par défaut est 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Q : Combien de réunions ou autres charges de travail puis-je avoir dans un pool dédié aux grandes réunions ?

Pour garantir la meilleure expérience utilisateur dans les grandes réunions d’un maximum de 1 000 participants, nous vous conseillons d’héberger sur un pool dédié aux grandes réunions une seule grande réunion à la fois. Il est aussi préférable de ne pas autoriser l’exécution d’autres charges de travail sur ce pool pendant le déroulement d’une grande réunion.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Q : Les organisateurs de grandes réunions doivent-ils être hébergés sur le pool dédié ?

Non. Nous ne recommandons pas d’héberger sur le pool dédié des utilisateurs autres que le personnel dédié à la planification des grandes réunions. Cela permet d’éviter que les grandes réunions hébergées dans le pool ne soient affectées par le trafic d’autres communications en temps réel. Vous devez planifier les grandes réunions sur le pool dédié à l’aide d’un compte d’utilisateur appartenant à un membre du personnel chargé de la planification des grandes réunions. Vous devez ajouter le compte d’utilisateur de l’organisateur de la réunion (celui qui sollicite la grande réunion) en tant que présentateur de la grande réunion.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Q : Quelles modalités multimédias puis-je utiliser dans une grande réunion ?

Les grandes réunions de plus de 1 000 utilisateurs peuvent inclure de l’audio, de la vidéo, un partage PowerPoint, des tableaux blancs et l’interrogation de présence.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Q : Puis-je utiliser la messagerie instantanée de groupe dans les grandes réunions ?

Oui. Toutefois, un grand nombre de messages instantanés, en particulier quand ils sont envoyés par un grand nombre de participants à la réunion, peuvent affecter l’expérience utilisateur en raison des problèmes liés au défilement rapide du texte dans la fenêtre de messagerie instantanée. La distribution d’un grand nombre de messages instantanés à un groupe de 1 000 utilisateurs peut également introduire des charges de serveur considérable, et ainsi nuire aux performances. En règle générale, la messagerie instantanée est uniquement requise pour les questions et les réponses (Q \& As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Q :Les utilisateurs peuvent-ils participer à de grandes réunions en composant le numéro à partir d’un téléphone ?

Oui. Si le pool Lync Server 2013 est correctement déployé et activé pour la Conférence rendez-vous, les utilisateurs pourront participer aux grandes réunions en appelant. Nos tests ont montré que jusqu’à 15 % de 1 000 participants peuvent participer à une grande réunion pendant 10 minutes.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Q : Puis-je héberger des grandes réunions dans une topologie virtuelle ?

Nous n’avons pas testé de grandes réunions dans une topologie virtuelle, nous ne sommes donc pas en mesure d’assurer un support en cas d’utilisation d’ordinateurs virtuels pour héberger un pool dédié aux grandes réunions.

</div>

</div>

<span> </span>

</div>

</div>

</div>

