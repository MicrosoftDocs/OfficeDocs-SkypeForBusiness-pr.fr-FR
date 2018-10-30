---
title: 'Lync Server 2013 : Configuration du contrôle d’admission des appels'
TOCTitle: Configuration du contrôle d’admission des appels
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398870(v=OCS.15)
ms:contentKeyID: 49298898
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Il contrôle uniquement les contenus audio et vidéo du trafic en temps réel, et ne concerne pas le trafic des données. Il peut acheminer l’appel via Internet lorsque la bande passante sur le chemin du réseau étendu par défaut est insuffisante. Pour plus d’informations, reportez-vous à [Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.

Cette section propose plusieurs exemples de procédures illustrant le déploiement et la gestion du contrôle d’admission des appels dans votre réseau.

> [!IMPORTANT]  
> Avant de déployer le contrôle d’admission des appels, vous devez regrouper toutes les informations nécessaires à la topologie réseau de votre entreprise, comme décrit dans la section <a href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a> dans la documentation de planification. Vérifiez également que les composants du contrôle d’admission des appels ont été installés et activés, comme décrit dans les sections <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013</a> de la documentation de déploiement.

> [!NOTE]  
> Lync Server Management Shell est utilisé dans tous les exemples de déploiement et de gestion du contrôle d’admission des appels décrits dans cette section. Vous pouvez également utiliser la section <strong>Configuration réseau</strong> du Panneau de configuration Lync Server pour gérer le contrôle d’admission des appels.

## Dans cette section

  - [Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)](lync-server-2013-configure-network-regions-for-cac.md)

  - [Créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurer les sites réseau pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associer des sous-réseaux à des sites réseau pour CAC](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Créer des liens de région réseau](lync-server-2013-create-network-region-links.md)

  - [Créer des itinéraires inter-région réseau](lync-server-2013;-create-network-interregion-routes.md)

  - [Créer des stratégies inter-sites réseau](lync-server-2013-create-network-intersite-policies.md)

  - [Activer le contrôle d’admission des appels](lync-server-2013-enable-call-admission-control.md)

  - [Liste de contrôle du déploiement du contrôle d’admission des appels](lync-server-2013-call-admission-control-deployment-checklist.md)

