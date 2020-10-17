---
title: 'Lync Server 2013 : prise en charge des grandes réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523921"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>Prise en charge des grandes réunions à l’aide de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Les réunions de grande taille ne suivent pas le modèle de test décrit dans la section précédente, car elles ont les caractéristiques suivantes :

  - Le format de la réunion est celui d’une présentation un-à-plusieurs.

  - Un ou plusieurs utilisateurs constituent les présentateurs. Le reste de l’assistance constitue les participants.

  - Le partage de présentation PowerPoint est la principale activité de collaboration pour les données.

  - L’audio est nécessaire et la vidéo peut également être utilisée.

  - Une personne dédiée, généralement l’organisateur de la réunion ou un assistant de l’organisateur, prépare la réunion à l’avance.

  - Le personnel dédié (et non les présentateurs) est chargé de mener la réunion, notamment en ce qui concerne la connexion à une réunion en ligne, la vérification du bon fonctionnement de l’audio, de la vidéo et du partage des diapositives, la gestion de la salle d’attente et des rôles utilisateurs, l’activation ou la désactivation du son des participants, la gestion des questions, ainsi que la gestion des enregistrements, le cas échéant.

La prise en charge de réunions de grande taille incluant jusqu’à 1 000 utilisateurs nécessite de régler les aspects liés au modèle matériel partagé et au modèle d’absence de réservation.

Pour disposer de ressources d’UC et de mémoire suffisantes pour les réunions allant jusqu’à 1000 utilisateurs, les serveurs frontaux d’hébergement ne doivent pas héberger de messagerie instantanée et de présence ou de charges de travail voix entreprise. Ils ne doivent pas non plus héberger d’autres réunions, quelles que soient leurs tailles. Cela signifie que l’hébergement de réunions allant jusqu’à 1000 utilisateurs nécessite la mise en place d’un pool Lync Server distinct dédié à l’hébergement de grandes réunions allant jusqu’à 1000 utilisateurs.

Un pool Lync Server dédié à l’hébergement de grandes réunions ne doit héberger qu’une seule réunion d’un maximum de 1000 utilisateurs en même temps, de sorte que les heures de réunion doivent être réservées à l’avance via un processus de planification hors bande pour garantir un support dédié à partir des serveurs frontaux. Pour prendre en charge plusieurs grandes réunions en même temps, nous vous recommandons de configurer plusieurs pools de réunions de grande taille dédiés.

Nous vous recommandons de dédier une personne à la conduite et au contrôle de la partie en ligne d’une réunion de grande taille. Cette personne peut être l’organisateur, un assistant de l’organisateur ou du présentateur, ou bien un membre de l’équipe de support technique dédiée aux réunions de grande taille, en fonction des préférences de l’organisation.

Dans les sections suivantes, nous décrivons comment implémenter un pool dédié pour les grandes réunions, notamment les meilleures pratiques pour l’utilisation de Lync Server 2013 afin de prendre en charge les grands scénarios de réunion.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de la prise en charge des grandes réunions dans Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gestion des grandes réunions dans Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

