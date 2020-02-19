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
ms.openlocfilehash: f3f2a27e252a3e152958a45d53794216308be68e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Avec la Conférence unifiée dans Lync Server 2013, les utilisateurs peuvent collaborer, partager des informations et coordonner leurs efforts en temps réel. Tous vos utilisateurs peuvent recourir à l’ensemble des outils de réunion planifiée et de collaboration spontanée. Les fonctionnalités de conférence audio et vidéo peuvent être utilisées depuis n’importe quel emplacement offrant une connexion à Internet, et les utilisateurs n’ayant pas d’ordinateur à leur disposition peuvent participer aux conférences audio en se connectant via un téléphone PSTN (réseau téléphonique commuté).

Les outils de réunion intégrés dans Outlook permettent aux organisateurs de planifier une réunion ou de démarrer une conférence impromptue d’un simple clic, et de faciliter la participation des participants. Un client Web étend les fonctionnalités de conférence enrichie aux participants qui n’exécutent pas la version de bureau de Lync.

<div>

## <a name="audio-and-video-conferencing"></a>Conférence audio et vidéo

Lync Server offre une expérience utilisateur familière aux utilisateurs de services ponts audio traditionnels, y compris les services RTC Dial-in, avec des commandes de contrôle d’appel à fréquences vocales. Il contient en outre de puissantes fonctionnalités de planification, de participation et de gestion qui sont uniquement disponibles avec une plateforme de communications unifiées intégrée.

En un seul clic, les utilisateurs peuvent planifier une réunion à partir d’Outlook. Détails, tels que l’heure de la réunion, l’emplacement et les participants, suivez le modèle Outlook familier. De plus, les informations spécifiques à la téléconférence, telles que le numéro de connexion, les ID de réunion et les rappels de code confidentiel sont automatiquement renseignées.

Pour vous assurer que seules les personnes autorisées participent à un appel, Lync Server offre plusieurs niveaux d’authentification pour les participants. Les utilisateurs qui se connectent à l’aide de Lync sont déjà authentifiés par les services de domaine Active Directory et n’ont pas besoin d’entrer un code confidentiel, un code d’accès ou un ID de réunion.

Lync simplifie l’expérience utilisateur de la vidéoconférence en incorporant la vidéo dans le client unifié de sorte que la planification d’une réunion avec vidéo ou la transmission spontanée de la vidéo soit transparente et facile.

Lync Server facilite l’ajout d’une vidéo à un appel téléphonique standard en un seul clic. Lorsqu’une conférence ou un appel vidéo englobe plusieurs participants, chaque utilisateur peut voir simultanément les vidéos de cinq autres utilisateurs au maximum ou un présentateur peut choisir une source vidéo qui sera diffusée exclusivement à tout le monde.

La vidéo haute définition (résolution 1270 x 720 ; rapport hauteur/largeur 16:9) et la vidéo VGA (résolution 640 x 480, format d’image 4:3) sont prises en charge pour les appels P2P entre les utilisateurs exécutant Lync sur des ordinateurs haut de gamme. La résolution perçue par chaque participant lors d’une même conversation peut varier en fonction des capacités vidéo de leur matériel respectif.

Les administrateurs informatiques peuvent définir des stratégies pour restreindre ou désactiver la vidéo haute définition ou VGA sur certains clients, en fonction des capacités de l’ordinateur, de la bande passante du réseau et de la présence d’une caméra capable de fournir la résolution requise. Ces stratégies sont appliquées via un provisionnement intrabande.

</div>

<div>

## <a name="web-conferencing"></a>Conférence web

Lync Server intègre des fonctionnalités de partage de conférence telles que bureau, application, pièce jointe, tableau blanc, sondage et PowerPoint dans le Lync rationalisé. En combinant cette fonctionnalité à la conférence audio ou vidéo, vous obtenez une session hautement collaborative et efficace, et très simple à administrer.

Pour améliorer l’expérience globale des utilisateurs présentant ou affichant des présentations PowerPoint, Lync Server 2013 utilise Office Web Apps pour gérer les présentations PowerPoint. Les utilisateurs peuvent partager une image ou copier et coller du texte à l’aide d’un tableau blanc dans la réunion Lync. Les présentateurs peuvent effectuer des sondages dans la réunion Lync pour demander des commentaires auprès des participants.

Le partage de bureau permet aux présentateurs de diffuser des éléments visuels, des applications, des pages Web, des documents, des logiciels ou une partie de leurs bureaux aux participants distants, directement à partir de Lync. Les membres du public peuvent suivre les mouvements de souris et les saisies au clavier. Les présentateurs peuvent choisir de partager l’intégralité de l’écran ou seulement une partie de celui-ci. En partageant leur Bureau, les présentateurs peuvent proposer aux participants des démonstrations interactives sur des produits ou des logiciels, peu importe où ils se trouvent.

Le partage d’application permet aux présentateurs de partager le contrôle des logiciels sur leur Bureau sans perdre de vue les commentaires ou les questions textuelles des participants. Les présentateurs peuvent aussi déléguer le contrôle de l’application aux participants à la réunion.

</div>

<div>

## <a name="dial-in-conferencing"></a>Conférence rendez-vous

Pour les utilisateurs qui n’utilisent pas d’ordinateur personnel, plusieurs méthodes sont disponibles pour rejoindre une conférence téléphonique Lync Server. Un utilisateur PSTN peut composer un numéro d’accès, accéder au pont de réunion, puis entrer l’ID de réunion. Pour des réunions davantage sécurisées, le système peut aussi inviter l’utilisateur à entrer son code confidentiel afin de s’authentifier sur Active Directory. Lync Server prend également en charge les appareils Lync Phone Edition, qui sont des appareils de téléphonie IP autonomes fournis par des partenaires Microsoft.

</div>

</div>

<span> </span>

</div>

</div>

</div>

