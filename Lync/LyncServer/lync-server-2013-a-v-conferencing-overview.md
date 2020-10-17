---
title: Vue d’ensemble des conférences A/V de Lync Server 2013
description: Vue d’ensemble des conférences A/V de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76ef4f76a4df0187a7c36394b2c95e99876df9be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568960"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Vue d’ensemble de la conférence A/V dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-13_

La conférence A/V permet d’établir des communications audio et vidéo en temps réel entre vos utilisateurs. Lorsque vous déployez la conférence, vous pouvez choisir d’activer et d’utiliser la conférence web et la conférence A/V, ou uniquement la conférence web.

Pour planifier votre conférence A/V, vous devez connaître la bande passante réseau nécessaire au type de média de conférence que requiert votre organisation. Cela peut inclure l’audio, la vidéo et la vidéo panoramique.

Avant d’activer les utilisateurs pour la conférence A/V, assurez-vous que votre réseau est en mesure de gérer la charge qui en résulte. Si la bande passante réseau est insuffisante, les performances du système seront largement diminuées pour l’utilisateur. Vous pouvez utiliser le contrôle d’admission des appels (CAC) pour gérer la bande passante réseau utilisée par la conférence A/V. Ceci est important pour les réseaux restreints, tels que les liaisons à bande passante limitée entre les sites centraux et les sites de succursale. Pour plus d’informations, reportez-vous à [vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Pour plus d’informations sur les besoins en bande passante des médias, voir [Network Bandwidth Requirements for Media Traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Si vous déployez la conférence audio sur votre réseau, vos utilisateurs auront besoin de périphériques audio tels que des casques pour y prendre part. Si vous déployez la conférence vidéo, vous devez déployer des périphériques vidéo tels que des webcams pour les utilisateurs. Nous vous recommandons d’utiliser des appareils de communications unifiées certifiés par Microsoft pour tous les types d’appareils, afin de garantir une expérience utilisateur optimale. Pour plus d’informations sur les périphériques certifiés UC, voir « téléphones et appareils pour Lync » à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) . Pour les périphériques audio ou vidéo, le déploiement des périphériques et la formation des utilisateurs sont des étapes importantes qu’il convient de planifier soigneusement.

Les sections suivantes décrivent les fonctionnalités de conférence audio et vidéo et fournissent des informations sur la gestion de la bande passante et la sélection de clients appropriés.

<div>

## <a name="audio-conferencing-features"></a>Fonctionnalités d’audioconférence

Lync Server 2013 offre plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience de conférence audio pour l’utilisateur, notamment les suivantes :

  - **Public muet**     Le présentateur peut utiliser ce paramètre pour désactiver tous les participants audio de la Conférence et placer la Conférence dans un État où les non-présentateurs ne peuvent pas le désactiver.

  - Annonces d’entrée **/sortie de conférence**     Si vous avez activé la Conférence rendez-vous, les présentateurs peuvent utiliser ce paramètre pour activer ou désactiver les annonces d’entrée et de sortie afin de minimiser les distractions lorsqu’une conférence est en cours.

  - **Ajout d’un utilisateur en appelant**     Les présentateurs et les participants qui bénéficient d’une autorisation peuvent ajouter des numéros RTC aux conférences et faire en sorte que la Conférence rende les numéros de téléphone.

</div>

<div>

## <a name="video-conferencing-features"></a>Fonctionnalités de visioconférence

Lync Server 2013 offre plusieurs fonctionnalités que vous pouvez utiliser pour configurer l’expérience de conférence vidéo pour l’utilisateur, notamment les suivantes :

  - **Mode Galerie**     Dans les conférences vidéo qui contiennent plus de deux personnes, les utilisateurs voient automatiquement tous les participants de la Conférence. Si celle-ci comporte plus de cinq participants, la vidéo des participants les plus actifs apparaît sur la ligne supérieure et seule la photo apparaît pour les autres participants. La vidéo à plusieurs est activée par défaut. Pour plus d’informations sur la configuration ou la désactivation de la vidéo à plusieurs, voir [configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Vidéo panoramique**     Si un périphérique de conférence vidéo RoundTable est installé dans la salle de conférence, cette fonctionnalité fournit une vue complète de 360 degrés de la salle de conférence. Le clip vidéo panoramique est disponible uniquement avec les périphériques RoundTable.

  - Mode vidéo présentateur **uniquement**     Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo du présentateur s’affiche. Ceci empêche toute distraction lors des réunions à grande échelle, lorsque plusieurs flux vidéo sont disponibles et verrouillés à différentes sources. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable.

  - **Vidéo HD**     Les utilisateurs peuvent bénéficier de résolutions jusqu’à la haute définition haute tension (HD) dans les appels à deux et les conférences à plusieurs.

  - **Projecteur vidéo**     Les présentateurs peuvent configurer la réunion de sorte que seule la vidéo d’un participant sélectionné qui est une source vidéo soit visible par les autres participants à la Conférence. Ce mode s’applique également à la vidéo capturée et fournie par les périphériques RoundTable pour la vidéo panoramique.

</div>

</div>

<span> </span>

</div>

</div>

</div>

