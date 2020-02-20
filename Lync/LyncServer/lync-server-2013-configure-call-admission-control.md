---
title: 'Lync Server 2013 : configurer le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad0d297981bec3fe133e88a090a3c60a97f1ec9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurer le contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Il contrôle uniquement les contenus audio et vidéo du trafic en temps réel, et ne concerne pas le trafic des données. Il peut acheminer l’appel via Internet lorsque la bande passante sur le chemin du réseau étendu par défaut est insuffisante. Pour plus d’informations, reportez-vous à la rubrique [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.

Cette section propose plusieurs exemples de procédures illustrant le déploiement et la gestion du contrôle d’admission des appels dans votre réseau.

<div>


> [!IMPORTANT]  
> Avant de déployer le contrôle d’admission des appels, vous devez réunir toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification. Assurez-vous également que les composants CAC ont été installés et activés, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Tous les exemples de déploiement et de gestion CAC dans cette section sont exécutés à l’aide de Lync Server Management Shell. En guise d’alternative, vous pouvez également utiliser la section <STRONG>Configuration réseau</STRONG> du panneau de configuration Lync Server pour gérer le contrôle d’admission des serveurs.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associer des sous-réseaux à des sites réseau pour le contrôle d’admission des serveurs dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Créer des liens de région réseau dans Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Créer des itinéraires inter-région réseau dans Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Créer des stratégies inter-sites réseau dans Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Activer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Liste de vérification du déploiement du contrôle d’admission des appels pour Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

