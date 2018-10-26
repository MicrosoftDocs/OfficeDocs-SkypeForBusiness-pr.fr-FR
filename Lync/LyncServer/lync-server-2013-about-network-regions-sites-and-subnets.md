---
title: "Lync Server 2013 : À propos des régions rés., des sites rés. et des sous-rés."
TOCTitle: À propos des régions réseau, des sites réseau et des sous-réseaux
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398467(v=OCS.15)
ms:contentKeyID: 49297449
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-24_

Les fonctionnalités Voix Entreprise avancées décrites dans cette section partagent certaines exigences de configuration pour les régions réseau, sites réseau et sous-réseaux. Par exemple, les trois fonctionnalités avancées nécessitent que chaque sous-réseau de votre topologie soit associé à un *site réseau* spécifique, et que chaque site réseau soit associé à une *région réseau* .

> [!IMPORTANT]  
> Avant de commencer la configuration réseau du contrôle d’admission des appels, E9-1-1, ou de la déviation du trafic multimédia, veillez à consulter les autres informations sur les paramètres réseau dans la rubrique <a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013</a> de la documentation de planification. Pour obtenir des informations sur la configuration réseau, notamment le contrôle d’admission des appels, reportez-vous également à <a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a> dans la documentation de planification.

Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :

  - Le contrôle d’admission des appels nécessite de spécifier un *profil de stratégie de bande passante* pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN). Si vous prévoyez de déployer le contrôle d’admission des appels, vous devez [Créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) avant de configurer vos sites réseau.

  - E9-1-1 nécessite de spécifier une *stratégie d’emplacement* pour chaque site. Si vous prévoyez de déployer E9-1-1, vous devez [Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) avant de configurer vos sites réseau.

## Créer ou modifier des régions réseau, sites réseau et sous-réseaux

Les rubriques suivantes décrivent la procédure permettant de créer ou de modifier des régions réseau et des sites réseau, mais aussi d’associer des sous-réseaux à des sites réseau. Ces rubriques ne sont pas spécifiques à une fonctionnalité Voix Entreprise avancée particulière.

  - [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

