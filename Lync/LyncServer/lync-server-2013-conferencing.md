---
title: Conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Grâce à la Conférence unifiée dans Lync Server 2013, les utilisateurs peuvent collaborer, partager des informations et coordonner leurs efforts en temps réel. Tous vos utilisateurs peuvent utiliser la totalité de la collaboration, des réunions planifiées et des outils de réunion involontaires. Les fonctionnalités de visioconférence et de visioconférence peuvent être utilisées à partir de n’importe quel emplacement disposant d’une connexion Internet, et les utilisateurs en dehors d’un ordinateur peuvent participer à des conférences audio en se connectant à l’aide d’un téléphone RTC (réseau téléphonique commuté).

Les outils de réunion intégrés dans Outlook permettent aux organisateurs de planifier une réunion ou de lancer une conférence impromptue en un seul clic, et de la rendre aussi simple aux participants. Un client Web étend les fonctionnalités de conférence riches aux participants qui n’exécutent pas la version de bureau de Lync.

<div>

## <a name="audio-and-video-conferencing"></a>Conférence audio et vidéo

Lync Server fournit une expérience utilisateur familière aux utilisateurs de services audio Bridge traditionnels, y compris les services RTC Dial-in avec des commandes de contrôle d’appel à tonalité. En même temps, elle intègre des fonctionnalités de planification, de jointure et de gestion puissantes disponibles uniquement avec une plate-forme de communications unifiées intégrée.

D’un simple clic, les utilisateurs peuvent planifier une réunion à partir d’Outlook. Les détails, tels que l’heure de la réunion, l’emplacement et les participants, suivent le modèle Outlook familier. De plus, les informations spécifiques aux conférences téléphoniques, telles que le numéro de connexion, les ID de réunion et les rappels de code confidentiel, sont automatiquement renseignées.

Pour garantir que seules les personnes autorisées participent à un appel, Lync Server fournit plusieurs niveaux d’authentification pour les participants. Les utilisateurs qui se connectent à l’aide de Lync sont déjà authentifiés par les services de domaine Active Directory et n’ont pas besoin d’entrer un code confidentiel, un code de passage ou un ID de réunion.

Lync simplifie l’utilisation de l’utilisateur pour les conférences vidéo en incorporant la vidéo dans le client unifié, de sorte que la planification d’une réunion avec des vidéos ou la réutilisation de la vidéo est transparente et facile.

Lync Server vous permet d’ajouter facilement une vidéo à un appel téléphonique standard en un seul clic. Lorsqu’un appel vidéo ou une conférence est en plusieurs participants, chaque utilisateur peut voir la vidéo d’un maximum de cinq utilisateurs simultanément, ou un présentateur peut choisir une seule source vidéo à afficher en exclusivité par tout le monde.

Vidéo haute définition (résolution 1270 x 720 ; rapport hauteur/largeur 16:9) et vidéo VGA (résolution 640 x 480 ; rapport hauteur/largeur 4:3) prises en charge pour les appels d’égal à égal entre les utilisateurs exécutant Lync sur des ordinateurs haut de gamme. La résolution affichée par chaque participant pour une seule conversation peut varier en fonction des capacités vidéo du matériel respectif de chaque utilisateur.

Les administrateurs informatiques peuvent définir des stratégies permettant de limiter ou de désactiver la vidéo haute définition ou VGA sur des clients, en fonction de la fonctionnalité de votre ordinateur, de la bande passante du réseau et de la présence d’une caméra capable de répondre à la résolution requise. Ces stratégies sont appliquées par le biais de la mise en service intrabande.

</div>

<div>

## <a name="web-conferencing"></a>Conférence web

Lync Server intègre des fonctionnalités de partage de conférences telles que l’ordinateur de bureau, l’application, la pièce jointe, le tableau blanc, le sondage et PowerPoint dans le Lync rationalisé. Combinés à des conférences audio ou vidéo, le résultat est une session de collaboration et de collaboration plus facile à utiliser.

Pour améliorer l’utilisation globale des utilisateurs qui présentent ou visualisent des présentations PowerPoint, Lync Server 2013 utilise Office Web Apps pour gérer des présentations PowerPoint. Les utilisateurs peuvent partager une image ou copier et coller du texte à l’aide d’un tableau blanc dans une réunion Lync. Les présentateurs peuvent organiser des sondages au sein de la réunion Lync afin de solliciter des commentaires des participants.

Le partage de bureau permet aux présentateurs de diffuser tout visuel, application, page Web, document, logiciel ou partie de leur bureau à des participants distants en temps réel, directement à partir de Lync. Les membres de l’assistance peuvent suivre les mouvements de la souris et le clavier. Les présentateurs peuvent choisir de partager tout l’écran ou seulement une partie. En partageant leurs bureaux, les présentateurs sont en mesure de s’impliquer sur leur public dans les démonstrations de produit ou logiciels interactifs depuis n’importe où.

Le partage d’application permet aux présentateurs de partager le contrôle des logiciels sur leur ordinateur de bureau, sans perte d’affichage des commentaires ou des questions relatives aux participants. Les présentateurs peuvent également déléguer le contrôle de l’application aux participants à la réunion.

</div>

<div>

## <a name="dial-in-conferencing"></a>Conférence rendez-vous

Pour les utilisateurs qui n’utilisent pas d’ordinateur personnel, il existe plusieurs méthodes pour participer à une téléconférence Lync Server. Un utilisateur RTC peut composer un numéro d’accès, accéder au pont de réunion, puis entrer l’ID de la réunion. Pour des réunions plus sûres, l’utilisateur peut également être tenu d’entrer son code confidentiel pour s’authentifier auprès d’Active Directory. Lync Server prend également en charge les appareils Lync Phone Edition, qui sont des appareils de téléphone IP autonomes proposés par des partenaires Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

