---
title: 'Lync Server 2013: configurer le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86961c9f282e1a486bf7cf94eda494d37c415cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurer le contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. CAC contrôle le trafic en temps réel uniquement pour les appels audio et vidéo, et n’affecte pas le trafic des données. Le CAC peut acheminer l’appel par le biais d’un chemin Internet lorsque le chemin de réseau étendu par défaut ne possède pas la bande passante requise. Pour plus d’informations, reportez-vous à [planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.

Cette section fournit un ensemble d’exemples de procédures illustrant le déploiement et la gestion de CAC dans votre réseau.

<div>


> [!IMPORTANT]  
> Avant de déployer le CAC, vous devez rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemple ci-dessous pour rassembler vos exigences en matière de contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification. Veillez également à ce que les composants CAC aient été installés et activés, comme décrit dans la rubrique <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Tous les exemples de déploiement et de gestion CAC dans cette section sont réalisés à l’aide de Lync Server Management Shell. En guise d’alternative, vous pouvez également utiliser la section <STRONG>Configuration réseau</STRONG> du panneau de configuration de Lync Server pour gérer CAC.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer des régions réseau pour CAC dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurer les sites réseau pour le CAC dans Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associez des sous-réseaux aux sites réseau pour le CAC dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Créer des liens de région réseau dans Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Créer des itinéraires réseau interrégion dans Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Créer des stratégies d’intersite réseau dans Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Activer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Liste de contrôle du déploiement de contrôle d’admission des appels pour Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

