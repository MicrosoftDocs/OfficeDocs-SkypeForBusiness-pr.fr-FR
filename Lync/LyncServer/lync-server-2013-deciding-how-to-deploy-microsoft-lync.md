---
title: 'Lync Server 2013 : choix du mode de déploiement de Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f4e622d71175ec393706af39ce470c5030216a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Choix du mode de déploiement de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lors de la planification de Lync, la première décision majeure concerne le déploiement de Microsoft Lync : Lync Server 2013 sur site ou Lync Online avec Microsoft 365 ou Office 365 dans le Cloud.

  - **Lync Server 2013 en local** : ce choix fournit l’ensemble de fonctionnalités Lync complet et offre une flexibilité optimale pour la configuration, la personnalisation et l’exploitation de votre déploiement. Tous les serveurs sont installés sur site et gérés par votre organisation. Un déploiement sur site fournit toute la gamme de fonctionnalités Lync Server.

  - **Lync Online dans le Cloud** Lync Online est conçu pour les organisations qui souhaitent bénéficier des avantages offerts par la messagerie instantanée, la présence et les réunions en nuage sans sacrifier les fonctionnalités professionnelles de Lync Server. Avec Lync Online, Microsoft déploie et gère l’infrastructure serveur requise, et gère la maintenance, les correctifs et les mises à niveau en continu. Certaines fonctionnalités disponibles dans un déploiement local ne sont pas disponibles dans Lync Online.

Le type de déploiement qui vous convient le mieux dépend des charges de travail à déployer, ainsi que du statut d’entreprise et de l’emplacement géographique de votre organisation.

<div>

## <a name="lync-server"></a>Lync Server

Un déploiement Lync Server local est plus adapté aux scénarios suivants :

  - Fonctionnalités voix entreprise **complètes**     Si vous envisagez de déployer une solution voix entreprise complète pour remplacer votre système PBX ou qui utilise des fonctionnalités d’appel avancées, un déploiement Lync Server local est requis. Le déploiement local prend en charge la connectivité directe avec des systèmes et jonctions PBX, ainsi que des fonctionnalités de téléphonie avancées telles que les groupes de réponses et le parcage d’appel. Lync Online ne prend actuellement pas en charge ces fonctionnalités.

  - Contrôles de la **qualité des médias**     Si vous souhaitez bénéficier de la gamme complète de fonctionnalités d’assurance qualité des médias, telles que les fonctionnalités de contrôle d’admission des appels (CAC) et de qualité de service (QoS), vous devez disposer d’un déploiement local.

  - **Conversation permanente**     Si vous devez déployer une conversation permanente pour votre organisation, vous devez choisir un déploiement local.

  - Applications serveur tierces **3rd-Party Server Applications**     Seuls les déploiements sur site peuvent fonctionner avec des applications tierces approuvées qui utilisent Microsoft Unified Communications Managed API (UCMA).

  - **Sociétés multinationales/Multirégionaless ayant besoin d’un support régional**     Si vous avez des centres de recherche dans plusieurs pays ou régions et que vous avez besoin de déployer et de gérer des serveurs au niveau régional, il est préférable d’utiliser un déploiement local, car il fournit ce type de fonctionnalités de gestion régionales.

  - **Contrôle total des stratégies, des rapports et des mises à niveau**     Avec un déploiement Lync Server local, vous avez accès à l’ensemble complet des stratégies de serveur et de client, de surveillance et d’autres rapports, ainsi que du minutage des mises à niveau. Lync Online fournit un sous-ensemble de paramètres et de rapports de stratégie, et fournit une fenêtre limitée, bien qu’significative, pour l’acceptation des mises à niveau.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Si aucun des facteurs figurant dans la liste précédente n’est essentiel pour vous, vous pouvez choisir Lync Online, pour un déploiement plus simple et une facilité de gestion. Lync Online offre un ensemble de fonctionnalités de messagerie instantanée, de présence et de conférence, ainsi que des appels vocaux et vidéo sur IP entre les utilisateurs de votre organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>
