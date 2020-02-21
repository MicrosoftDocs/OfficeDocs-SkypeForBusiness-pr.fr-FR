---
title: Lync Server 2013 voix entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924e15aae9590b6148864084aa68924e4c080f7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-04-08_

Avec voix entreprise, Lync Server offre une solution autonome VoIP (Voice over Internet Protocol) pour améliorer ou remplacer les systèmes PBX (Private Branch Exchange) traditionnels. Les utilisateurs de voix entreprise peuvent appeler des collègues sur le réseau VoIP ou le PBX de votre organisation, et ils peuvent appeler des numéros de téléphone traditionnels en dehors de votre organisation. La solution voix entreprise inclut des fonctionnalités d’appel courantes telles que Answer, Forward, Transfer, Hold, reroutement, Release et parcage, ainsi qu’un appel amélioré 9-1-1 (E9-1-1) (E9-1-1 n’est disponible qu’aux États-Unis). Voix entreprise prend également en charge un large éventail d’appareils IP et USB plus anciens et actuels.

<div>

## <a name="placing-and-receiving-calls"></a>Émission et réception d’appels

À l’aide de Lync, les utilisateurs peuvent passer des appels en tapant un nom ou un numéro de téléphone sur leur clavier, ou en utilisant un pavé de numérotation affiché à l’écran. Ils peuvent également passer des appels directement à partir de leur liste de contacts. Vous pouvez également déployer des appareils Lync Phone Edition, qui sont des appareils de téléphonie IP autonomes fournis par des partenaires Microsoft.

Les utilisateurs peuvent avoir plusieurs appareils téléphoniques enregistrés auprès de Lync Server et peuvent passer facilement de l’un à l’autre.

En cas d’appel entrant, les utilisateurs sont avertis simultanément sur tous leurs périphériques par des sonneries personnalisables sur les périphériques de téléphonie IP et par une notification similaire à un message instantané sur leur PC.

Ils peuvent également définir un numéro de téléphone auquel ils peuvent être contactés sur leur téléphone de bureau, leur PC et leur téléphone mobile.

</div>

<div>

## <a name="basic-call-features"></a>Fonctionnalités d’appel de base

Lorsqu’il téléphone, un utilisateur peut répondre à d’autres appels entrants ou passer des appels sortants : l’appel en cours est alors automatiquement mis en attente. Il est possible de transférer un appel d’un utilisateur à l’autre, soit directement, soit après que le premier utilisateur ait parlé en privé au deuxième utilisateur. Les utilisateurs peuvent également transférer un appel vers un autre périphérique, par exemple vers leur téléphone mobile, lorsqu’ils quittent le bureau.

</div>

<div>

## <a name="richer-communications"></a>Fonctionnalités de communication plus puissantes

Lorsqu’ils communiquent avec Lync, les utilisateurs peuvent facilement ajouter du texte, une vidéo ou un partage de bureau à l’appel. La fonctionnalité do-not-disrang est intégrée aux paramètres de présence dans Lync.

Avec la messagerie unifiée Exchange, Lync et Lync Server s’intègrent à Microsoft Exchange Server 2013 et Microsoft Outlook 2013. Les utilisateurs peuvent voir s’ils ont de nouveaux messages vocaux dans leur fenêtre Lync et dans leurs courriers électroniques. Si le message vocal est enregistré dans un message électronique, l’utilisateur peut cliquer dessus pour l’écouter ou afficher la transcription du message vocal.

</div>

<div>

## <a name="advanced-calling-features"></a>Fonctionnalités d’appel avancées

Voix entreprise comprend également plusieurs fonctionnalités d’appel avancées, telles que la délégation d’appel Lync, l’appel d’équipe, la prise d’appel de groupe et les groupes Response Group.

La délégation d’appel Lync permet aux utilisateurs de déléguer la gestion des appels à un ou plusieurs assistants, en accédant à la section **Outils** \> **options** \> de **transfert d’appel**. Le délégué peut effectuer plusieurs tâches d’appel au nom de l’utilisateur, y compris le filtrage et l’émission d’appels ou l’initialisation de conférences.

<div>


> [!IMPORTANT]  
> Il se peut que vous cherchiez une autre fonctionnalité nommée de la même manière que la délégation de calendrier Lync. Elle ne requiert pas la fonctionnalité voix entreprise et permet aux utilisateurs de planifier des réunions Lync en ligne à partir d’Outlook. Si vous êtes à la recherche de ces informations, nous vous recommandons d’extraire <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> pour plus d’informations sur l’activation de la synchronisation des délégués Exchange.



</div>

L’appel d’équipe permet à un utilisateur de faire en sorte que les appels entrants sonnent simultanément sur les téléphones des coéquipiers afin que tout le monde de l’équipe puisse répondre à l’appel.

Group Call Pick, une nouvelle fonctionnalité des mises à jour cumulatives pour Lync Server 2013 : février 2013, permet aux utilisateurs de répondre à leurs collègues à partir de leurs propres téléphones. La prise d’appel de groupe diffère de l’appel de l’équipe principalement dans le fait qu’un appel entrant sonne uniquement sur le téléphone du destinataire, mais que tous les autres utilisateurs peuvent le répondre en composant un numéro de groupe de prise d’appel.

Le service Response Group peut être configuré en vue de mettre en attente et d’acheminer intelligemment les appels vers des agents désignés. Les supports techniques informatiques, les services d’assistance téléphoniques des ressources humaines et d’autres centres de contact internes l’utilisent couramment.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administration de Voix Entreprise

Lync Server utilise des standards et des interfaces publiées pour interagir avec l’infrastructure existante. Il prend en charge les options de passerelle et SIP (comme la jonction SIP) pour permettre l’interconnexion avec les systèmes PBX IP et les réseaux PSTN afin que vous puissiez migrer progressivement les utilisateurs vers Voix Entreprise, tout en minimisant les risques d’interruption. Lync Server prend en charge les codecs traditionnels tels que G. 711, G. 722 et G. 723.1 pour l’interopérabilité avec les solutions VoIP traditionnelles.

Avec le contrôle d’admission des appels (CAC), les administrateurs peuvent définir des limites sur la quantité de trafic vocal et vidéo Lync Server transitant sur des liaisons réseau restreintes, et spécifier l’action à effectuer si un nouvel appel dépasse la limite. Par exemple, l’appel peut être routé par un autre chemin ou refusé.

Lync Server collabore avec des appliances Survivables Branch Office pour fournir des services d’appels locaux et une connexion RTC aux succursales, en cas de panne de réseau étendu (WAN) sur le site central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

