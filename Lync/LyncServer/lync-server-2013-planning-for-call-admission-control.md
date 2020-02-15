---
title: 'Lync Server 2013 : planification du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0d3173b3316d4e4dff704402da94c20aa2c9f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planification du contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Pour les applications de communications unifiées basées sur IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas perçue comme un facteur limitatif dans les environnements de réseau local. En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites. Lorsque le trafic réseau afflue et sature une liaison de réseau étendu, les mécanismes courants, comme la mise en attente, la mise en mémoire tampon et l’abandon de paquets, sont utilisés pour résoudre le problème de congestion. Le trafic supplémentaire est généralement retardé jusqu’à ce que le réseau ne soit plus saturé. Si nécessaire, le trafic peut également être interrompu. Avec un trafic de données conventionnel, le client qui reçoit les données peut facilement surmonter ce type de problème. Avec un trafic en temps réel, la saturation du réseau ne peut pas être résolue de cette manière, car les communications unifiées sont sensibles à la latence et à la perte de paquets. Si le réseau étendu est saturé, la qualité de l’expérience (QoE) des utilisateurs peut s’en ressentir. Lorsque le trafic en temps réel est saturé, il vaut mieux refuser des appels plutôt que de fournir des connexions de mauvaise qualité.

Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable. Dans Lync Server 2013, le contrôle d’admission des appels contrôle le trafic en temps réel uniquement pour l’audio et la vidéo, mais il n’affecte pas le trafic de données. Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (PSTN). Le contrôle d’admission des accès est disponible uniquement dans Lync Server.

Cette section décrit le contrôle d’admission des appels et explique comment le planifier.

<div>


> [!NOTE]  
> Lync Server dispose de trois fonctionnalités voix entreprise avancées : le contrôle d’admission des appels (CAC), les services d’urgence (E9-1-1) et la déviation du trafic multimédia. Pour une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, reportez-vous à <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network Settings for the Advanced Enterprise Voice Features in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

