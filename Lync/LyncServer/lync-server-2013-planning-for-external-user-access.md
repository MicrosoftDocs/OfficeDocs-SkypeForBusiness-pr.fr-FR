---
title: 'Lync Server 2013 : Planification de l’accès des utilisateurs externes'
TOCTitle: Planification de l’accès des utilisateurs externes
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399048(v=OCS.15)
ms:contentKeyID: 49299204
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-01-19_

Dans la plupart des entreprises, les communications impliquent des services et des utilisateurs situés à l’extérieur de votre réseau interne. Il peut s’agir d’employés travaillant de manière temporaire ou permanente hors site, d’employés travaillant pour un client ou un partenaire, d’utilisateurs de services de messagerie instantanée publics, de clients, de partenaires et d’utilisateurs anonymes potentiels conviés à des réunions et à des présentations. Dans cette documentation, ces personnes sont collectivement appelées *utilisateurs externes* .

Grâce à Microsoft Lync Server 2013, les utilisateurs de votre entreprise peuvent utiliser la messagerie instantanée et la présence pour communiquer avec des utilisateurs externes et participer à des conférences audio/vidéo (A/V) et web avec vos employés hors site et d’autres types d’utilisateurs externes. Vous pouvez également prendre en charge l’accès externe à partir de périphériques mobiles et via Voix Entreprise. Les utilisateurs externes qui ne sont pas membres de votre entreprise peuvent participer à des réunions Lync Server 2013 qui admettent les participants anonymes.

Pour prendre en charge les communications via le pare-feu de votre entreprise, vous déployez le serveur Edge Lync Server 2013 dans votre réseau de périmètre (également appelé DMZ, zone démilitarisée, et sous-réseau filtré). Le serveur Edge spécifie comment les utilisateurs à l’extérieur du pare-feu peuvent se connecter à votre déploiement Lync Server 2013 interne. Il contrôle également les communications avec les utilisateurs externes qui transitent à travers le pare-feu.

Selon vos exigences, vous pouvez déployer un ou plusieurs serveurs Edge dans un ou plusieurs emplacements. Cette section décrit des scénarios de l’accès des utilisateurs externes dans Lync Server 2013 et explique comment planifier votre topologie de périmètre et de proxy inverse.

> [!NOTE]  
> Même si vous avez besoin d’un serveur Edge pour prendre en charge Voix Entreprise et l’accès des utilisateurs externes, cette section se concentre sur la prise en charge des fonctionnalités de messagerie instantanée, de présence, de conférence A/V, de fédération, de conférence web et de Lync Mobile. Pour plus d’informations sur la prise en charge de Voix Entreprise, reportez-vous à <a href="lync-server-2013-planning-for-enterprise-voice.md">Planification de Voix Entreprise dans Lync Server 2013</a> dans la documentation relative à la planification.

## Dans cette section

  - [Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Présentation de la découverte automatique](lync-server-2013-understanding-autodiscover.md)

  - [Sélection d’une topologie dans Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Collecte des données dans Lync Server 2013](lync-server-2013-data-collection.md)

  - [Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

