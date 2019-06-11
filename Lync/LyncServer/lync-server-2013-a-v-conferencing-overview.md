---
title: Vue d’ensemble de la fonctionnalité de conférence A/V de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Présentation de la fonctionnalité de conférence A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-13_

La fonction de conférence A/V permet des communications audio et vidéo en temps réel entre vos utilisateurs. Lorsque vous déployez des conférences, vous pouvez choisir d’activer et d’utiliser des conférences Web et des conférences A/V, ou uniquement des conférences Web.

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de trafic multimédia de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique.

Avant d’activer les utilisateurs pour les conférences A/V, assurez-vous que votre réseau peut gérer le chargement obtenu. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur. Vous pouvez utiliser le contrôle d’admission des appels pour gérer la bande passante réseau utilisée par les conférences A/V. Cela est important pour les réseaux restreints, comme les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, voir [vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Pour plus d’informations sur les contraintes de bande passante pour les médias, voir [besoins en bande passante réseau pour le trafic multimédia dans Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio, comme des casques pour y participer. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo, comme des webcams pour les utilisateurs. Nous vous recommandons d’utiliser des appareils de communications unifiées (UC) certifiés par Microsoft pour tous les types d’appareils, afin de garantir une utilisation optimale des utilisateurs. Pour plus d’informations sur les appareils validés par UC, voir «téléphones et appareils [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)pour Lync» à l’adresse. Pour les périphériques audio ou vidéo, le déploiement de périphériques et la formation des utilisateurs, vous devez prendre en compte les étapes à suivre.

Les sections suivantes décrivent les fonctionnalités des conférences audio et vidéo, ainsi que des informations sur la gestion de la bande passante et la sélection des clients appropriés.

<div>

## <a name="audio-conferencing-features"></a>Fonctionnalités de l’audioconférence

Lync Server 2013 fournit plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’interface de visioconférence pour l’utilisateur, notamment les suivantes:

  - **Désactiver**   le son du public le présentateur peut utiliser ce paramètre pour désactiver le son de tous les participants audio de la Conférence et mettre la Conférence dans un État où les non-présentateurs ne peuvent pas désactiver le son.

  - **Annonce d’entrée/sortie**   d’une conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de réduire les distractions lors de l’exécution d’une conférence.

  - **L’ajout d’un utilisateur à l’aide**   des présentateurs et des participants disposant d’une autorisation, peut ajouter des numéros RTC aux conférences et faire en sorte que la Conférence rendez-vous sur ces numéros.

</div>

<div>

## <a name="video-conferencing-features"></a>Fonctionnalités de conférence vidéo

Lync Server 2013 fournit plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’interface de conférence vidéo pour l’utilisateur, notamment les suivantes:

  - **Vue Galerie dans**   les conférences vidéo ayant plus de deux personnes, les utilisateurs voient automatiquement tous les participants à la Conférence. Si la conférence rassemble plus de cinq participants, la vidéo des participants les plus actifs s’affiche sur la ligne supérieure et seule la photo s’affiche pour les autres participants. La vidéo à plusieurs est activée par défaut. Pour plus d’informations sur la configuration ou la désactivation de la vidéo à plusieurs parties, voir [configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vidéo panoramique s'**   il s’agit d’un appareil de visioconférence dans la salle de conférence, cette fonctionnalité fournit une vue de 360 degré complète de la salle de conférence. Le clip vidéo panoramique n’est disponible qu’avec les appareils RoundTable.

  - **Présentateur seuls**   les présentateurs du mode vidéo peuvent configurer la réunion de telle sorte que seule la vidéo du présentateur soit affichée. Cela empêche toute distraction lors de grandes réunions, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les appareils RoundTable.

  - ****   Les utilisateurs de la vidéo HD peuvent bénéficier de résolutions de HD 1080p dans les appels et conférences multiparties.

  - ****   Les présentateurs de Spotlight vidéo peuvent configurer la réunion de telle sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit affichée par les autres participants à la Conférence. Ce mode s’applique également à la vidéo capturée et fournie par les appareils RoundTable pour la vidéo panoramique.

</div>

</div>

<span> </span>

</div>

</div>

</div>

