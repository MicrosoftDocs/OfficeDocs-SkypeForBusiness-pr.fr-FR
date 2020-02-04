---
title: Voix Entreprise dans Lync Server 2013
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
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a>Voix Entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-04-08_

Avec Enterprise Voice, Lync Server fournit une offre VoIP (voix sur IP) autonome pour améliorer ou remplacer les systèmes PBX (Private Branch Exchange) traditionnels. Les utilisateurs d’Enterprise Voice peuvent appeler des collègues sur le réseau VoIP ou le PBX de votre organisation, et ils peuvent appeler des numéros de téléphone traditionnels à l’extérieur de votre organisation. La solution voix entreprise inclut des fonctionnalités d’appel courantes, telles que réponse, transfert, transfert, mise en attente, dérouter, libérer et parc, et 9-1-1 (E9-1-1-1). Voix entreprise prend également en charge un vaste éventail d’appareils IP et USB plus courants.

<div>

## <a name="placing-and-receiving-calls"></a>Placement et réception d’appels

Lync permet aux utilisateurs de passer des appels en tapant un nom ou un numéro de téléphone sur leur clavier, ou à l’aide d’un pavé de numérotation affiché à l’écran. Les utilisateurs peuvent également lancer des appels directement depuis leur liste de contacts. Vous pouvez également déployer des appareils Lync Phone Edition, qui sont des appareils de téléphone IP autonomes proposés par des partenaires Microsoft.

Les utilisateurs peuvent utiliser plusieurs appareils téléphoniques enregistrés sur Lync Server et pouvoir basculer entre eux facilement.

Les utilisateurs sont avertis de tous les appels entrants sur tous leurs appareils, avec des sonneries personnalisées sur les appareils de téléphone IP et une notification similaire à un message instantané sur leur ordinateur.

Les utilisateurs peuvent également définir un numéro de téléphone qui se connecte à leur téléphone de bureau, leur PC et leur téléphone mobile, afin de pouvoir y accéder où qu’ils se trouvent.

</div>

<div>

## <a name="basic-call-features"></a>Fonctionnalités d’appel de base

Pendant un appel, un utilisateur peut répondre à d’autres appels entrants ou lancer des appels sortants, et l’appel actif actuel est mis automatiquement en attente. Les appels peuvent être transférés d’un utilisateur à un autre, directement ou après que le premier utilisateur parle en privé. Les utilisateurs peuvent également transférer des appels vers un autre appareil. par exemple, ils pourraient transférer un appel actif vers leur téléphone mobile, car ils découvrent la porte de leur bureau.

</div>

<div>

## <a name="richer-communications"></a>Communications plus complètes

Lorsque vous parlez à un autre utilisateur avec Lync, les utilisateurs peuvent facilement ajouter du texte, de la vidéo ou du partage de bureau à l’appel. La fonctionnalité ne pas déranger est intégrée aux paramètres de présence dans Lync.

Avec la messagerie unifiée Exchange, Lync et Lync Server s’intègrent à Microsoft Exchange Server 2013 et Microsoft Outlook 2013. Les utilisateurs peuvent voir s’ils ont de nouveaux messages vocaux dans leur fenêtre Lync et dans leurs messages électroniques. Dans un courrier électronique, ils peuvent cliquer pour lire le fichier audio de la messagerie vocale dans un message électronique ou afficher une transcription du message vocal.

</div>

<div>

## <a name="advanced-calling-features"></a>Fonctionnalités d’appel avancées

Voix entreprise inclut plusieurs fonctionnalités d’appel avancées, telles que la délégation d’appels Lync, les appels d’équipe, la collecte d’appels de groupe et les groupes de réponse.

La délégation d’appel Lync permet aux utilisateurs de déléguer la gestion des appels à un ou plusieurs assistants, en accédant à **Outils** \> **options** \> de **transfert d’appel**. Le délégué peut effectuer plusieurs tâches d’appel de la part de l’utilisateur, y compris les appels de filtrage, le placement d’appels et l’initiation de conférences.

<div>


> [!IMPORTANT]  
> Il est possible que vous souhaitiez Rechercher une autre fonctionnalité nommée de la même façon, délégation de calendrier Lync. La fonctionnalité voix entreprise n’est pas obligatoire et permet aux utilisateurs de planifier des réunions Lync en ligne à partir d’Outlook. Si vous recherchez ces informations, nous vous recommandons de consulter <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> pour plus d’informations sur l’activation de la synchronisation de délégué Exchange.



</div>

Les appels d’équipe permettent à un utilisateur de faire sonner simultanément les téléphones des membres de l’équipe pour que tous les membres de l’équipe puissent répondre à l’appel.

Le prélèvement d’appels de groupe, une nouvelle fonctionnalité dans les mises à jour cumulatives de Lync Server 2013 : février 2013, permet aux utilisateurs de répondre aux appels entrants de leurs collègues à partir de leur propre téléphone. Le prélèvement d’appels de groupe diffère de l’appel d’équipe dans la mesure où un appel entrant sonne uniquement sur le téléphone du destinataire prévu, mais que les autres utilisateurs peuvent choisir d’y répondre en composant un numéro de groupe.

Les groupes de réponse peuvent être configurés pour la mise en file d’attente et le routage intelligent des appels vers les agents désignés. Les utilisations courantes incluent les support informatiques, les services d’assistance aux ressources humaines et autres centres de contacts internes.

</div>

<div>

## <a name="enterprise-voice-administration"></a>Administration de voix entreprise

Lync Server utilise des normes et des interfaces publiées pour interagir avec l’infrastructure existante. Il prend en charge les options passerelle et SIP (par exemple, le trunking SIP) pour une interconnexion aux systèmes PBX IP et aux réseaux RTC, afin que vous puissiez migrer les utilisateurs vers Enterprise Voice dans le temps, tout en minimisant les interruptions. Lync Server prend en charge les codecs traditionnels tels que G. 711, G. 722 et G. 723.1 pour l’interopérabilité avec les solutions VoIP traditionnelles.

Le contrôle d’admission des appels permet aux administrateurs de définir des limites sur le volume de trafic audio et vidéo de Lync Server transporté par des liaisons réseau contraintes et de spécifier l’action à entreprendre si un nouvel appel dépasse la limite. Les actions peuvent inclure le routage via un autre chemin ou le rejet de l’appel.

Lync Server fonctionne avec des appareils de succursales Survivables tiers pour fournir des services d’appel local et une connexion RTC aux succursales, en cas de panne du WAN sur le site central.

</div>

</div>

<span> </span>

</div>

</div>

</div>

