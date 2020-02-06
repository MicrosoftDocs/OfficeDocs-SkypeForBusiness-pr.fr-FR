---
title: Paramètres réseau pour les fonctions avancées de voix entreprise dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces éléments doivent être configurés pour déployer le plan de dérivation de médias dans Skype entreprise, planifier le contrôle d’admission des appels dans Skype entreprise Server) ou planifier des services d’urgence dans Skype entreprise Server dans Skype entreprise Server.
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802594"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Paramètres réseau pour les fonctions avancées de voix entreprise dans Skype entreprise Server

Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces éléments doivent être configurés pour déployer le [plan de dérivation de médias dans Skype entreprise](media-bypass.md), [planifier le contrôle d’admission des appels dans Skype entreprise Server](call-admission-control.md), ou [planifier des services d’urgence dans Skype](emergency-services.md) entreprise Server dans Skype entreprise Server Voice.

Skype entreprise Server comporte trois fonctionnalités avancées de voix entreprise : [planifiez le contrôle d’admission des appels dans Skype entreprise Server](call-admission-control.md), [planifiez des services d’urgence dans Skype entreprise Server](emergency-services.md)et [planifiez une dérivation multimédia dans Skype entreprise](media-bypass.md). Ces fonctionnalités partagent certaines exigences de configuration pour les zones du réseau, les sites réseau et l’Association de chaque sous-réseau dans la topologie de Skype entreprise Server avec un site réseau.

Cette rubrique fournit une vue d’ensemble des configurations requises qui sont communes aux trois fonctions vocales d’entreprise avancées.

## <a name="network-regions"></a>Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia.

> [!NOTE]
> Les régions réseau ne sont pas identiques aux régions de conférence rendez-vous de Skype entreprise Server, qui sont nécessaires pour associer des numéros d’accès aux conférences rendez-vous avec un ou plusieurs plans de numérotation Skype entreprise Server. Pour plus d’informations sur les régions de conférence rendez-vous, reportez-vous à [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

Le CAC nécessite que chaque région du réseau dispose d’un site central Skype entreprise Server associé qui gère le trafic multimédia au sein de la région (autrement dit, il prend des décisions basées sur les stratégies que vous avez configurées en ce qui concerne l’existence ou non d’un son en temps réel ou la session vidéo peut être établie. Les sites centraux de Skype entreprise Server ne représentent pas des emplacements géographiques, mais plutôt des groupes logiques de serveurs configurés comme pool ou ensemble de pools.

Pour configurer une région réseau, vous pouvez utiliser l’onglet **régions** de la section **Configuration réseau** du panneau de configuration Skype entreprise Server, ou exécuter les applets de commande **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Skype entreprise Server Management Shell. Pour obtenir des instructions, reportez-vous à la rubrique [déploiement de régions, de sites et de sous-réseaux dans Skype entreprise](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement, ou consultez la documentation de Skype entreprise Server Management Shell.

Les mêmes définitions de zones réseau sont partagées par les trois fonctions vocales d’entreprise avancées. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.

Pour associer un site central Skype entreprise Server à une région du réseau, vous spécifiez le nom du site central, soit à l’aide de la section **Configuration réseau** du panneau de configuration Skype entreprise Server, soit en exécutant les applets de commande **New-CsNetworkRegion** ou **Set-CsNetworkRegion** . Pour obtenir des instructions, reportez-vous à la rubrique [déploiement de régions, de sites et de sous-réseaux dans Skype entreprise](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement, ou consultez la documentation de Skype entreprise Server Management Shell.

## <a name="network-sites"></a>Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.

> [!NOTE]
> Les sites réseau sont utilisés uniquement par les fonctionnalités avancées de voix entreprise. Ils ne sont pas les mêmes que ceux que vous configurez dans votre topologie de Skype entreprise Server.

Pour configurer un site réseau et l’associer à une région du réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration Skype entreprise Server, ou bien exécuter les applets de commande **New-CsNetworkSite** ou **Set-CsNetworkSite** . Pour plus d’informations, reportez-vous à [créer ou modifier un site réseau](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) dans la documentation de déploiement ou à la documentation de Skype entreprise Server Management Shell.

## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).

> [!CAUTION]
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un client Skype entreprise utilise son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas le contournement du média, le contrôle d’admission des appels fonctionne correctement même si vous configurez des sous-réseaux virtuels.) Par exemple, si un client Skype entreprise se connecte à partir d’un ordinateur doté d’une adresse IP 172.29.81.57 avec un masque de sous-réseau IP de 255.255.255.0, il demande l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux exactement comme fourni par les clients Skype entreprise (qui sont configurés avec des sous-réseaux lors de la configuration du réseau, de manière statique ou par le protocole DHCP).)

## <a name="associating-subnets-with-network-sites"></a>Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Grâce à cette association de sous-réseaux, les fonctionnalités avancées de voix entreprise permettent de localiser les points de terminaison géographiquement. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.

Pour associer des sous-réseaux aux sites réseau, vous pouvez utiliser la section **Configuration réseau** du panneau de configuration Skype entreprise Server, ou vous pouvez utiliser Skype entreprise Server Management Shell. Pour obtenir des instructions, reportez-vous à la section [associez un sous-réseau à un site réseau](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) dans la documentation de déploiement ou reportez-vous à la documentation Skype entreprise Server Management Shell.

## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’admission des appels dans Skype entreprise Server](call-admission-control.md)

[Planifier des services d’urgence dans Skype entreprise Server](emergency-services.md)

[Plan de contournement de médias dans Skype entreprise](media-bypass.md)

