---
title: 'Lync Server 2013 : Choix des modalités de déploiement de Microsoft Lync'
TOCTitle: Choix des modalités de déploiement de Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204979(v=OCS.15)
ms:contentKeyID: 49297522
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Choix des modalités de déploiement de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Lors de la planification de Lync, la première décision majeure à prendre a trait à la manière de déployer Microsoft Lync : en tant que serveur Lync Server 2013 local ou serveur Skype Entreprise Online avec Microsoft Office 365 sur le cloud.

  - **Lync Server 2013 local** : ce choix fournit l’intégralité des fonctionnalités Lync et offre une grande flexibilité dans la configuration, la personnalisation et l’utilisation de votre déploiement. Tous les serveurs sont installés localement et gérés par votre organisation. Un déploiement local offre l’éventail complet des fonctionnalités Lync Server.

  - **Skype Entreprise Online sur le cloud** : Skype Entreprise Online est conçu pour les organisations qui souhaitent exploiter les avantages en termes de coût et de flexibilité de la messagerie instantanée, de la présence et des réunions basées sur le cloud sans sacrifier les fonctionnalités d’exception de Lync Server. Avec Skype Entreprise Online, Microsoft déploie et gère l’infrastructure de serveur requise, et prend en charge la maintenance régulière, les correctifs et les mises à niveau. Certaines fonctionnalités disponibles dans un déploiement local ne le sont pas dans Skype Entreprise Online.

Le type de déploiement qui vous convient le mieux dépend des charges de travail à déployer, ainsi que du statut d’entreprise et de l’emplacement géographique de votre organisation.

## Lync Server

Un déploiement Lync Server local est plus adapté aux scénarios suivants :

  - **Fonctionnalités Voix Entreprise complètes**   Si vous envisagez de déployer une solution Voix Entreprise complète pour remplacer votre autocommutateur privé (PBX) ou qui utilise des fonctionnalités d’appel avancées, un déploiement Lync Server local est requis. Le déploiement local prend en charge la connectivité directe avec des systèmes et jonctions PBX, ainsi que des fonctionnalités de téléphonie avancées telles que les groupes de réponses et le parcage d’appel. Lync Online ne prend actuellement pas en charge ces fonctionnalités.

  - **Contrôles de la qualité des médias**   Si vous voulez l’éventail complet des fonctionnalités d’assurance qualité des médias, notamment les fonctionnalités du service Contrôle d’admission des appels et de qualité de service (QoS), vous avez besoin d’un déploiement local.

  - **Conversation permanente**   Si vous avez besoin de déployer la conversation permanente pour votre organisation, vous devez choisir un déploiement local.

  - **Applications de serveur tierces**   Seuls les déploiements locaux peuvent fonctionner avec des applications tierces approuvées qui utilisent Microsoft Unified Communications Managed API (UCMA).

  - **Entreprises multinationales/multirégionales ayant besoin d’une prise en charge régionale**   Si vous possédez des centres de données dans plusieurs pays ou régions et que vous avez besoin de déployer et gérer des serveurs au niveau régional, un déploiement local est plus approprié car il offre ce type de fonctionnalités de gestion régionale.

  - **Contrôle intégral sur les stratégies, les rapports et les mises à niveau**   Avec un déploiement Lync Server local, vous avez accès à la totalité des stratégies serveur et client, aux rapports de surveillance parmi d’autres, ainsi qu’au timing des mises à niveau. Lync Online propose un sous-ensemble de paramètres et de rapports de stratégie, ainsi qu’un créneau limité, mais significatif, pour accepter les mises à niveau.

## Lync Online

Si aucun des facteurs figurant dans la liste précédente n’est essentiel pour vous, vous pouvez choisir Lync Online, pour un déploiement plus simple et une facilité de gestion. Lync Online offre un éventail robuste de fonctionnalités de messagerie instantanée, de présence et de conférence, et permet également les appels vocaux et vidéo sur IP entre les utilisateurs de votre organisation.

