---
title: 'Lync Server 2013 : Choix des modalités de déploiement de Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d641f4da1884c1fb6e84eefb2127490f2ed3c4a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Choix des modalités de déploiement de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Lors de la planification de Lync, la première décision majeure consiste à déployer Microsoft Lync: comme Lync Server 2013 en local ou Lync Online avec Microsoft Office 365 dans le Cloud.

  - **Lync Server 2013 local** : ce choix fournit l’ensemble des fonctionnalités Lync complètes et offre une souplesse de configuration, de personnalisation et d’utilisation de votre déploiement. Tous les serveurs sont installés sur site et gérés par votre organisation. Un déploiement local fournit une gamme complète de fonctionnalités de serveur Lync.

  - **Lync Online dans le Cloud** Lync Online est conçu pour les organisations qui souhaitent bénéficier de coûts et de compétences en matière de messagerie instantanée, de présence et de réunions dans le Cloud sans sacrifier les fonctionnalités de niveau professionnel de Lync Server. Avec Lync Online, Microsoft déploie et met à jour l’infrastructure de serveur requise, ainsi que les mises à jour, les correctifs et les mises à niveau en continu. Certaines fonctionnalités disponibles dans un déploiement local ne sont pas disponibles dans Lync Online.

Le type de déploiement le plus approprié dépend des charges de travail que vous voulez déployer et du statut géographique et commercial de votre organisation.

<div>

## <a name="lync-server"></a>Lync Server

Le déploiement de Lync Server local est préférable pour les scénarios suivants:

  - **Fonctionnalités vocales complètes d’entreprise**   si vous envisagez de déployer une solution voix entreprise complète pour remplacer votre PBX ou qui utilise des fonctionnalités d’appel avancées, un déploiement Lync Server local est requis. Locale prend en charge la connectivité directe avec les systèmes et les Trunks PBX, ainsi que les fonctionnalités de téléphone avancées telles que les Response Groups et le parc d’appels. Pour le moment, Lync Online ne prend pas en charge ces fonctionnalités.

  - **Contrôles qualité multimédia**   si vous voulez bénéficier de la gamme complète de fonctionnalités d’assurance qualité multimédia, comme les fonctionnalités de contrôle d’admission des appels (CAC) et de qualité de service (QoS), vous devez disposer d’un déploiement local.

  - **Discussions permanentes**   si vous devez déployer une conversation permanente pour votre organisation, vous devez choisir un déploiement local.

  - **les applications**   serveur tierces uniquement les déploiements locaux peuvent fonctionner avec des applications tierces approuvées qui utilisent l’API Microsoft Unified Communications Managed API (UCMA).

  - **Les sociétés multinationales/multiterritoriales ont besoin d’une prise en charge**   régionale si vous disposez de centres de donneurs dans plusieurs pays ou régions et que vous avez besoin de déployer et de gérer des serveurs sur une base régionale, il est préférable d’utiliser un déploiement local, car il fournit ce type de capacités de gestion régionale.

  - **Contrôle complet sur les stratégies, les rapports et les mises à niveau**   avec un déploiement de Lync Server sur site, vous avez accès à l’ensemble des stratégies du serveur et du client, à la surveillance et aux autres rapports et au minutage des mises à niveau. Lync Online fournit un sous-ensemble du paramètre de stratégie et des rapports, et fournit une fenêtre limitée, même importante, pour accepter les mises à niveau.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Si aucun des facteurs de la liste précédente n’est essentiel pour vous, vous pouvez choisir Lync Online pour faciliter le déploiement et la gestion. Lync Online fournit un ensemble de fonctionnalités de messagerie instantanée, de présence et de conférence puissantes, ainsi que des appels audio et vidéo sur IP entre les utilisateurs de votre organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

