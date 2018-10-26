---
title: 'Lync Server 2013 : Définition de la configuration requise pour Voix Entreprise'
TOCTitle: Définition de la configuration requise de votre organisation pour Voix Entreprise
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425826(v=OCS.15)
ms:contentKeyID: 49296803
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-07_

Cette rubrique présente les points à prendre en compte concernant les régions, sites et liaisons entre sites de votre topologie et explique leur importance lors du déploiement de Voix Entreprise. Pour plus d’informations sur ces points, reportez-vous à [Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) dans la documentation de planification.

## Sites et régions

En premier lieu, identifiez les sites de votre topologie sur lesquels vous allez déployer Voix Entreprise ainsi que les régions réseau auxquelles ces sites appartiennent. En particulier, pensez à la façon dont vous allez assurer la connectivité RTC (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Décidez de l’emplacement où déployer les passerelles localement, où déployer les serveurs Survivable Branch Appliance (SBA) et où vous pouvez configurer les jonctions SIP (soit en local, soit sur le site central) vers un fournisseur de services de téléphonie Internet.

## Liaisons réseau entre sites

Vous devez aussi considérer l’utilisation de la bande passante attendue sur les liaisons réseau entre votre site central et ses sites de succursale. Si vous avez déployé ou envisagez de déployer des liaisons de réseau étendu (WAN) résistantes entre sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale afin de fournir une terminaison de numéros SDA (sélection directe à l’arrivée) locale aux utilisateurs hébergés sur ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous ne disposez pas de liaison de réseau étendu résistante, si votre site de succursale héberge moins de 1 000 utilisateurs et si aucun administrateur Lync Server formé n’est disponible sur ce site, nous vous recommandons de déployer un Survivable Branch Appliance sur votre site de succursale. Si votre site de succursale héberge entre 1 000 et 5 000 utilisateurs, si vous ne disposez pas d’une connexion de réseau étendu résistante et si des administrateurs Lync Server sont disponibles, nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de succursale. Envisagez aussi d’activer la déviation du trafic multimédia sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.

## Voir aussi

#### Concepts

[Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

