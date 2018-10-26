---
title: 'Lync Server 2013 : Planification du contrôle d’admission des appels'
TOCTitle: Planification du contrôle d’admission des appels (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398842(v=OCS.15)
ms:contentKeyID: 49298822
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification du contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Pour les applications de communications unifiées basées sur IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas perçue comme un facteur limitatif dans les environnements de réseau local. En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites. Lorsque le trafic réseau afflue et sature une liaison de réseau étendu, les mécanismes courants, comme la mise en attente, la mise en mémoire tampon et l’abandon de paquets, sont utilisés pour résoudre le problème de congestion. Le trafic supplémentaire est généralement retardé jusqu’à ce que le réseau ne soit plus saturé. Si nécessaire, le trafic peut également être interrompu. Avec un trafic de données conventionnel, le client qui reçoit les données peut facilement surmonter ce type de problème. Avec un trafic en temps réel, la saturation du réseau ne peut pas être résolue de cette manière, car les communications unifiées sont sensibles à la latence et à la perte de paquets. Si le réseau étendu est saturé, la qualité de l’expérience (QoE) des utilisateurs peut s’en ressentir. Lorsque le trafic en temps réel est saturé, il vaut mieux refuser des appels plutôt que de fournir des connexions de mauvaise qualité.

Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable. Dans Lync Server 2013, le contrôle d’admission des appels contrôle uniquement les contenus audio et vidéo du trafic en temps réel, sans affecter le trafic des données. Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (RTC). Le contrôle d’admission des appels est uniquement disponible dans Lync Server.

Cette section décrit le contrôle d’admission des appels et explique comment le planifier.

> [!NOTE]  
> Lync Server comporte trois fonctionnalités Voix Entreprise avancées : contrôle d’admission des appels, services d’urgence (système E9-1-1) et déviation du trafic multimédia. Pour une vue d’ensemble des informations de planification communes à ces trois fonctionnalités, reportez-vous à <a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013</a>.

## Dans cette section

  - [Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Composants et topologies pour CAC dans Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

