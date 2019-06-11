---
title: 'Lync Server 2013: FAQ sur la prise en charge des réunions de grande taille'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>FAQ sur la prise en charge des réunions de grande taille pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Les sections suivantes fournissent des réponses aux questions les plus fréquentes sur la création et l’exécution de réunions de grande envergure.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>Q: combien d’utilisateurs peuvent participer à une réunion de grande envergure?

Le modèle utilisateur de Lync Server spécifie des limites d’utilisateurs 250 dans un pool partagé ou 1000 utilisateurs dans un pool dédié à des réunions de grande taille, mais ces numéros représentent uniquement le nombre d’utilisateurs que nous avons testés et uniquement pour l’ensemble spécifique de matériel que nous avons utilisé dans le cadre de nos tests. D’après nos tests, nous vous conseillons de les limiter à des tailles maximales. Toutefois, vous contrôlez le nombre réel de participants autorisés à participer à des réunions au sein de votre organisation en configurant une ou plusieurs stratégies de conférence (que vous configurez à l’aide d’applets de commande Windows PowerShell dans Lync Server Management Shell ou à l’aide du serveur Lync. Panneau de configuration). Le numéro que vous spécifiez dans une stratégie de conférence peut être tout nombre entier de 32 bits compris entre 1 et 4 294 967 295, mais la taille recommandée est comprise entre 2 et 250 participants, y compris. et la valeur par défaut est 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>Q: combien de réunions ou autres charges de travail puis-je avoir dans un pool dédié aux grandes réunions?

Pour garantir 1000 une meilleure utilisation de l’utilisateur dans les réunions de grande taille, nous vous conseillons d’héberger uniquement une seule grande réunion à la fois sur un pool dédié aux réunions de grande envergure. Nous vous recommandons également de ne pas autoriser l’exécution de toutes les autres charges de travail sur le pool lors de la grande réunion.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>Q: les organisateurs de grande réunion doivent-ils être hébergés sur le pool dédié?

Non. Nous vous recommandons de ne pas organiser des utilisateurs autres que le personnel spécialisé qui gère la planification de réunions de grande envergure sur le pool dédié. Cela empêche tout trafic de communication en temps réel de provoquer des problèmes liés aux réunions importantes qui sont hébergées dans le pool. Il est recommandé de planifier des réunions de grande envergure sur le pool dédié en utilisant un compte d’utilisateur du personnel directeur de la réunion. Vous devez ajouter le compte d’utilisateur de l’organisateur de la réunion (l’utilisateur qui demande une importante réunion) en tant que présentateur de la grande réunion.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>Q: Quelles sont les modalités de médias que j’utilise dans une grande réunion?

Les réunions de grande envergure avec un maximum de 1000 peuvent inclure des éléments audio, vidéo, partage PowerPoint, tableaux blancs et interrogation de présence.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>Q: est-il possible d’utiliser la messagerie instantanée de groupe dans de grandes réunions?

Oui. Toutefois, un grand nombre de messages instantanés, en particulier ceux envoyés par un grand nombre de participants à la réunion, peuvent influer sur l’interface utilisateur en raison de problèmes liés au défilement rapide du texte dans la fenêtre de messagerie instantanée. La livraison d’un grand nombre de messages instantanés à un maximum de 1000 utilisateurs peut également provoquer de importants efforts de chargement du serveur, ce qui peut affecter les performances. En règle générale, la messagerie instantanée est uniquement requise pour les\&questions et réponses (Q As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Les utilisateurs peuvent-ils participer à des réunions importantes en se connectant depuis un téléphone?

Oui. Si le pool Lync Server 2013 est correctement déployé et activé pour la Conférence rendez-vous, les utilisateurs peuvent rejoindre les réunions de grande taille en composant un numéro de téléphone. Nos tests ont démontré qu’un maximum de 15% des utilisateurs de 1000 peuvent rejoindre la réunion de grande taille sur une période de 10 minutes.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>Q: est-il possible d’héberger de grandes réunions dans une topologie virtuelle?

Comme nous n’avons pas testé de grande réunion dans une topologie virtuelle, nous ne prenons pas en charge l’utilisation d’ordinateurs virtuels pour l’hébergement d’une réserve dédiée pour les réunions de grande envergure.

</div>

</div>

<span> </span>

</div>

</div>

</div>

