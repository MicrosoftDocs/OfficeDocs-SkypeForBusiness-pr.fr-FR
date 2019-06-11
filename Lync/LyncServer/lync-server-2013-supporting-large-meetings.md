---
title: 'Lync Server 2013: prise en charge de grandes réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Prise en charge de grandes réunions à l’aide de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Les grandes réunions ne suivent pas le modèle de test décrit dans la section précédente, car ils présentent les caractéristiques suivantes:

  - Le format de la réunion est celui d’une présentation un-à-plusieurs.

  - Un ou plusieurs utilisateurs sont des présentateurs. Le reste de l’assistance sont des participants.

  - Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.

  - L’audio est nécessaire et la vidéo peut également être utilisée.

  - En règle générale, une personne dédiée, qui est l’organisateur de la réunion ou un Assistant, organise la réunion à l’avance.

  - Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, de façon appropriée.

La prise en charge de grandes réunions d’un maximum de 1000 utilisateurs nécessite de traiter les problèmes liés au modèle de matériel partagé et au modèle sans réservation.

Pour disposer de suffisamment de ressources aux niveaux du processeur et de la mémoire pour les réunions incluant jusqu’à 1 000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas gérer de fonctionnalités de messagerie instantanée et de présence, ni de charges de travail liées à Voix Entreprise. Elle ne doit pas non plus accueillir d’autres réunions, quelle que soit la taille des autres réunions. Cela signifie que les réunions d’hébergement d’un maximum de 1000 utilisateurs nécessitent de configurer un pool Lync Server distinct destiné à accueillir des réunions de grande envergure de plus de 1000 utilisateurs.

Un pool de serveurs Lync dédié à l’hébergement de réunions volumineuses doit accueillir une seule réunion d’au maximum 1000 utilisateurs, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors-bande pour garantir une prise en charge dédiée du service frontal gens. Pour prendre en charge plusieurs réunions de grande envergure en même temps, nous vous recommandons de configurer plusieurs pools de réunions volumineux dédiées.

Nous recommandons qu’une personne dédiée exécute et contrôle la partie en ligne d’une grande réunion. Il peut s’agir de l’organisateur, du délégué de l’organisateur ou du présentateur ou d’un membre de l’équipe de support technique dédiée de grande réunion, selon les préférences de l’organisation.

Dans les sections suivantes, nous décrivons comment implémenter un pool dédié pour les réunions de grande envergure, y compris des pratiques recommandées pour l’utilisation de Lync Server 2013 pour prendre en charge des scénarios de réunion importants.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de la prise en charge des réunions de grande envergure dans Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gérer des réunions de grande envergure dans Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

