---
title: 'Lync Server 2013 : planification de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e418ee1db146afa1f766aa0fc56842222f7b510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Planification de l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-19_

Dans la plupart des entreprises, les communications impliquent des services et des utilisateurs situés à l’extérieur de votre réseau interne. Il peut s’agir d’employés travaillant de manière temporaire ou permanente hors site, d’employés travaillant pour un client ou un partenaire, d’utilisateurs de services de messagerie instantanée publics, de clients, de partenaires et d’utilisateurs anonymes potentiels conviés à des réunions et à des présentations. Dans cette documentation, ces personnes sont collectivement appelées *utilisateurs externes*.

Avec Microsoft Lync Server 2013, les utilisateurs de votre organisation peuvent utiliser la messagerie instantanée et la présence pour communiquer avec les utilisateurs externes, et ils peuvent participer à la conférence audio/vidéo (A/V) et à la conférence Web avec vos employés hors site et d’autres types d’utilisateurs externes. Vous pouvez également prendre en charge l’accès externe à partir de périphériques mobiles et via Voix Entreprise. Les utilisateurs externes qui ne sont pas membres de votre organisation peuvent participer aux réunions Lync Server 2013, autorisant les participants anonymes.

Pour prendre en charge les communications entre le pare-feu de votre organisation, vous devez déployer le serveur Edge Lync Server 2013 dans votre réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré). Le serveur Edge contrôle la manière dont les utilisateurs situés à l’extérieur du pare-feu peuvent se connecter à votre déploiement interne de Lync Server 2013. Il contrôle également les communications avec les utilisateurs externes qui transitent à travers le pare-feu.

Selon vos exigences, vous pouvez déployer un ou plusieurs serveurs Edge dans un ou plusieurs emplacements. Cette section décrit les scénarios d’accès des utilisateurs externes dans Lync Server 2013 et explique comment planifier votre topologie de serveur Edge et de proxy inverse.

<div>


> [!NOTE]  
> Même si vous avez besoin d’un serveur Edge pour prendre en charge la voix entreprise et l’accès des utilisateurs externes, cette section est axée sur la prise en charge de la messagerie instantanée, de la présence, de la conférence A/V, de la Fédération, de la conférence Web et de Lync mobile. Pour plus d’informations sur la prise en charge de voix entreprise, voir <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Présentation de la découverte automatique dans Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Choix d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Collecte de données dans Lync Server 2013](lync-server-2013-data-collection.md)

  - [Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

