---
title: Paramètres réseau pour les fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces éléments doivent être configurés pour déployer le plan de contournement de média dans Skype Entreprise, planifier le contrôle d’admission des appels dans Skype Entreprise Server) ou planifier les services d’urgence dans Skype Entreprise Server dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 50e076cd4be0e0c98b6319a7d0b4ce1a848689cd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861091"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Paramètres réseau pour les fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server

Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces éléments doivent être configurés pour déployer le plan de contournement de média dans [Skype Entreprise,](media-bypass.md)planifier le contrôle d’admission des appels dans [Skype Entreprise Server](call-admission-control.md)ou planifier les services d’urgence dans [Skype Entreprise Server](emergency-services.md) dans Skype Entreprise Server Voix Entreprise.

Skype Entreprise Server offre trois fonctionnalités Voix Entreprise avancées : planifier le contrôle d’admission des appels dans [Skype Entreprise Server,](call-admission-control.md)Planifier les services d’urgence dans [Skype Entreprise Server](emergency-services.md)et Planifier le contournement de média [dans Skype Entreprise](media-bypass.md). Ces fonctionnalités partagent certaines configurations requises pour les régions réseau, les sites réseau et l’association de chaque sous-réseau de la topologie Skype Entreprise Server avec un site réseau.

Cette rubrique fournit une vue d’ensemble des exigences de configuration communes à ces trois fonctionnalités Voix Entreprise avancées.

## <a name="network-regions"></a>Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et du contournement de média.

> [!NOTE]
> Les régions réseau ne sont pas les mêmes que les régions de conférence Skype Entreprise Server, qui sont requises pour associer des numéros d’accès de conférence à un ou plusieurs plans de numérotation Skype Entreprise Server conférence. Pour plus d’informations sur les régions de conférence rendez-vous, voir [Planning for Dial-In Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements).

Le contrôle d’enregistrement des données exige que chaque région réseau soit associée à un site central Skype Entreprise Server, qui gère le trafic multimédia au sein de la région (autrement dit, il prend des décisions en fonction des stratégies que vous avez configurées, en ce qui concerne la création ou non d’une session audio ou vidéo en temps réel). Skype Entreprise Server sites centraux ne représentent pas des emplacements géographiques, mais plutôt des groupes logiques de serveurs configurés en tant que pool ou ensemble de pools.

Pour configurer une région réseau, vous pouvez utiliser l’onglet **Régions** de la section **Configuration** réseau du Panneau de configuration Skype Entreprise Server ou exécuter les cmdlets **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Skype Entreprise Server Management Shell. Pour obtenir des instructions, voir Déployer des régions [réseau,](../../deploy/deploy-enterprise-voice/deploy-network.md) des sites et des sous-réseaux dans Skype Entreprise dans la documentation de déploiement, ou reportez-vous à la documentation Skype Entreprise Server Management Shell.

Les mêmes définitions de région réseau sont partagées par les trois fonctionnalités Voix Entreprise avancées. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.

Pour associer un site central Skype Entreprise Server à une région réseau, vous devez spécifier le nom du site central, soit à l’aide de la section **Configuration** du réseau du Panneau de configuration Skype Entreprise Server, soit en exécutant les cmdlets **New-CsNetworkRegion** ou **Set-CsNetworkRegion.** Pour obtenir des instructions, voir Déployer des régions [réseau,](../../deploy/deploy-enterprise-voice/deploy-network.md) des sites et des sous-réseaux dans Skype Entreprise dans la documentation de déploiement, ou reportez-vous à la documentation Skype Entreprise Server Management Shell.

## <a name="network-sites"></a>Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.

> [!NOTE]
> Les sites réseau sont utilisés uniquement par les fonctionnalités Voix Entreprise avancées. Ils ne sont pas identiques aux sites de succursale que vous configurez dans Skype Entreprise Server topologie.

Pour configurer un site réseau et l’associer à une région réseau, vous pouvez utiliser la section **Configuration** réseau du Panneau de configuration Skype Entreprise Server ou exécuter les cmdlets Skype Entreprise Server Management Shell **New-CsNetworkSite** ou **Set-CsNetworkSite.** Pour plus d’informations, voir [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) in the Deployment documentation, or refer to the Skype Entreprise Server Management Shell documentation.

## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).

> [!CAUTION]
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour le contournement de média. Un client Skype Entreprise prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas le contournement de média, le contrôle d’admission des appels fonctionne correctement même si vous configurez des sous-réseaux virtuels.) Par exemple, si un client Skype Entreprise se signe sur un ordinateur avec une adresse IP 172.29.81.57 avec un masque de sous-réseau IP 255.255.255.0, il demande l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, bien que le client appartienne au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux exactement tels que fournis par les clients Skype Entreprise (qui sont mis en service avec des sous-réseaux lors de la configuration réseau, de manière statique ou par le protocole DHCP (Dynamic Host Configuration Protocol).

## <a name="associating-subnets-with-network-sites"></a>Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Cette association de sous-réseaux permet aux fonctionnalités Voix Entreprise avancées de localiser géographiquement les points de terminaison. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.

Pour associer des sous-réseaux à des sites réseau, vous pouvez utiliser la section **Configuration** réseau du Panneau de configuration Skype Entreprise Server ou utiliser Skype Entreprise Server Management Shell. Pour obtenir des instructions, voir Associer un sous-réseau à un [site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) réseau dans la documentation de déploiement ou consultez la documentation Skype Entreprise Server Management Shell.

## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’admission des appels dans Skype Entreprise Server](call-admission-control.md)

[Planifier les services d’urgence dans Skype Entreprise Server](emergency-services.md)

[Planifier le contournement de média dans Skype Entreprise](media-bypass.md)