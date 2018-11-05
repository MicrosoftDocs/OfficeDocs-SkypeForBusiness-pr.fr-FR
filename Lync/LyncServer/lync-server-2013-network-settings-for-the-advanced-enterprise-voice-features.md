---
title: "Lync Server 2013 : Param. Rés. des fonctionnalités avancées de Voix Entreprise"
TOCTitle: Paramètres réseau des fonctionnalités avancées de Voix Entreprise
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398637(v=OCS.15)
ms:contentKeyID: 49297863
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-10_

Lync Server comporte trois fonctionnalités Voix Entreprise : contrôle d’admission des appels, services d’urgence (système E9-1-1) et déviation du trafic multimédia. Ces fonctionnalités partagent certaines exigences de configuration pour les régions réseau, les sites réseau et l’association de chaque sous-réseau dans la topologie Lync Server avec un site réseau. Pour plus d’informations sur la planification du déploiement de ces fonctionnalités, reportez-vous à :

  - [Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Pour plus d’informations sur le déploiement de chacune de ces fonctionnalités, reportez-vous à [Déploiement des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) dans la documentation de déploiement.

Cette rubrique fournit une vue d’ensemble des conditions de configuration requises communes aux trois fonctionnalités Voix Entreprise avancées.

## Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia.

> [!NOTE]  
> Les régions réseau sont différentes des régions de conférence rendez-vous Lync Server, qui sont requises pour associer les numéros d’accès à la conférence rendez-vous avec un ou plusieurs plans de numérotation Lync Server. Pour plus d’informations sur les régions de conférence rendez-vous, reportez-vous à <a href="lync-server-2013-dial-in-conferencing-requirements.md">Configuration requise pour les conférences rendez-vous dans Lync Server 2013</a> dans la documentation de planification.

Le contrôle d’admission des appels nécessite que chaque région réseau dispose d’un site central Lync Server associé qui gère le trafic multimédia dans la région (c’est-à-dire qu’il prend les décisions en fonction des stratégies configurées relatives à l’établissement ou non de session audio ou vidéo en temps réel). Les sites centraux Lync Server ne représentent pas les emplacements géographiques, mais plutôt des groupes logiques de serveurs configurés sous forme de pool ou d’ensemble de pools. Pour plus d’informations sur les sites centraux, reportez-vous à [Topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification. reportez-vous également à [Topologies prises en charge dans Lync Server 2013](lync-server-2013-supported-topologies.md) dans la documentation de prise en charge.

Pour configurer une région réseau, vous pouvez utiliser l’onglet **Régions** dans la section **Configuration réseau** du Panneau de configuration Lync Server, ou exécuter les applets de commande Lync Server Management Shell**New-CsNetworkRegion** ou **Set-CsNetworkRegion**. Pour obtenir des instructions, reportez-vous à [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation de déploiement, ou reportez-vous à la documentation Lync Server Management Shell.

Les mêmes définitions de région réseau sont partagées par les trois fonctionnalités Voix Entreprise avancées. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.

Pour associer un site central Lync Server à une région réseau, vous spécifiez le nom du site central à l’aide de la section **Configuration réseau** du Panneau de configuration Lync Server, ou exécutez les applets de commande Lync Server Management Shell**New-CsNetworkRegion** ou **Set-CsNetworkRegion** . Pour obtenir des instructions, reportez-vous à [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) dans la documentation du déploiement, ou reportez-vous à la documentation Lync Server Management Shell.

## Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.

> [!NOTE]  
> Les sites réseau sont utilisés uniquement par les fonctionnalités Voix Entreprise avancées. Ils diffèrent des sites de succursale que vous pouvez configurer dans votre topologie Lync Server. Pour plus d’informations sur les sites de succursale, reportez-vous à <a href="lync-server-2013-reference-topologies.md">Topologies de référence dans Lync Server 2013</a> dans la documentation de planification. Reportez-vous également à <a href="lync-server-2013-supported-topologies.md">Topologies prises en charge dans Lync Server 2013</a> dans la documentation de prise en charge.

Pour configurer un site réseau et l’associer à une région réseau, vous pouvez utiliser la section **Configuration réseau** du Panneau de configuration Lync Server, ou exécuter les applets de commande Lync Server Management Shell**New-CsNetworkSite** ou **Set-CsNetworkSite**. Pour plus d’informations, reportez-vous à [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) dans la documentation du déploiement, ou reportez-vous à la documentation Lync Server Management Shell.

## Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).

> [!WARNING]  
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un client Lync prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas la déviation du trafic multimédia, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)<br />
Par exemple, si un client Lync se connecte sur un ordinateur ayant l’adresse IP 172.29.81.57 et le masque de sous-réseau IP 255.255.255.0, il demandera l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux exacts fournis par les clients Lync (provisionnés avec des sous-réseaux lors de la configuration réseau soit de manière statique, soit par DHCP.)

## Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Cette association de sous-réseaux permet aux fonctionnalités Voix Entreprise de rechercher géographiquement les points de terminaison. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.

Pour associer des sous-réseaux à des sites réseau, vous pouvez utiliser la section **Configuration réseau** du Panneau de configuration Lync Server, ou vous pouvez utiliser Lync Server Management Shell. Pour obtenir des instructions, reportez-vous à [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) dans la documentation du déploiement, ou reportez-vous à la documentation Lync Server Management Shell.

## Voir aussi

#### Autres ressources

[Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

