---
title: 'Lync Server 2013 : Configuration des jonctions'
TOCTitle: Configuration des jonctions
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398170(v=OCS.15)
ms:contentKeyID: 49296228
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des jonctions dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans le cadre d’un déploiement Voix Entreprise, configurez une jonction entre un serveur de médiation et les homologues suivants pour fournir la connectivité RTC aux clients Voix Entreprise et aux périphériques de votre organisation :

  - Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet

  - Passerelle RTC

  - Autocommutateur privé (PBX)

Pour plus d’informations, reportez-vous à [Planification de la connectivité RTC dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) dans la documentation de planification.

> [!IMPORTANT]  
> Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013</a> dans la documentation de déploiement.

> [!NOTE]  
> Dans le cadre de la configuration des jonctions, vous pouvez activer la fonctionnalité de déviation du trafic multimédia de Lync Server 2013, qui permet la déviation du trafic multimédia au niveau du serveur de médiation. Vous pouvez configurer les jonctions sans activer la déviation du trafic multimédia mais nous vous conseillons vivement de l’activer. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-planning-for-media-bypass.md">Planification de la déviation du trafic multimédia dans Lync Server 2013</a> dans la documentation de planification.

## Dans cette section

  - [Prise en charge de plusieurs jonctions dans Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Routage interjonctions dans Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Affichage des informations de configuration de jonction dans Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Création d’une collection de paramètre de configuration d’une jonction dans Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modification des paramètres de configuration d’une jonction SIP dans Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Test des paramètres de configuration des jonctions SIP dans Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Affichage des informations sur les jonctions SIP individuelles dans Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

## Voir aussi

#### Tâches

[Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### Autres ressources

[Planification de la connectivité RTC dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

