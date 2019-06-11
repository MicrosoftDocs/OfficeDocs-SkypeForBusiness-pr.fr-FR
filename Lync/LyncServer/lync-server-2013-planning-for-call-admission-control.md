---
title: 'Lync Server 2013 : Planification du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planification du contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Pour les applications de communications unifiées (UC) qui sont basées sur le protocole IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas considérée comme un facteur limitatif dans les environnements LAN. En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites. Quand un flux réseau surabonne une liaison WAN, des mécanismes actuels comme la mise en file d’attente, la mise en mémoire tampon et la suppression de paquets sont utilisés pour résoudre le congestion. Le trafic supplémentaire est généralement retardé jusqu’à ce que la congestion du réseau soit régressif ou, si nécessaire, le trafic est rejeté. Pour le trafic de données conventionnel dans ces situations, le client de réception peut récupérer. Pour le trafic en temps réel, comme les communications unifiées, la congestion du réseau ne peut pas être résolue de cette manière, car le trafic de communications unifiées est sensible à la latence et à la perte de paquets. La congestion sur le WAN peut entraîner une médiocre qualité de l’apprentissage (QoE) pour les utilisateurs. Pour le trafic en temps réel dans des conditions congestionnées, il est préférable de rejeter les appels plutôt que d’offrir des connexions de mauvaise qualité.

Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable. Dans Lync Server 2013, CAC contrôle le trafic en temps réel uniquement pour les appels audio et vidéo, mais n’affecte pas le trafic de données. Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (RTC). Le CAC est disponible uniquement sur Lync Server.

Cette section décrit le contrôle d’admission des appels et explique comment le planifier.

<div>


> [!NOTE]  
> Lync Server comporte trois fonctionnalités avancées de voix entreprise: contrôle d’admission des appels (CAC), services d’urgence (E9-1-1) et contournement de média. Pour obtenir une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, consultez <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">la rubrique paramètres réseau pour les fonctionnalités avancées de voix entreprise de Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Exemple: rassemblement de vos exigences de contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

