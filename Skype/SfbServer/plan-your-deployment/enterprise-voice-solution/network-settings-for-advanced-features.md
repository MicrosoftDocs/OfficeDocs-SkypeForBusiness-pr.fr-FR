---
title: Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ceux-ci doivent être configurés pour déployer le Plan pour contournent les médias dans Skype pour entreprise 2015, planifier appel de contrôle d’admission dans Skype 2015 de serveur d’entreprise), ou un Plan pour les services d’urgence dans Skype pour 2015 de serveur d’entreprise dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: eb24dc5098fe71cecc8099c2949039a91e61ebd7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server-2015"></a>Paramètres réseau des fonctionnalités avancées de Voix Entreprise dans Skype Entreprise Server 2015
 
Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces doivent être configurés pour déployer le [Plan de support ignorer dans Skype pour entreprise 2015](media-bypass.md), [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](call-admission-control.md)), ou le [Planifier pour les services d’urgence dans Skype pour Business Server 2015](emergency-services.md) dans Skype pour Business Server Voix Entreprise.
  
Skype pour Business Server dispose de trois fonctionnalités de Voix Entreprise : [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](call-admission-control.md)), [les services d’urgence dans Skype pour Business Server 2015](emergency-services.md)et contournement [Plan média dans Skype pour 2015 de Business](media-bypass.md). Ces fonctionnalités partagent certaines exigences de configuration pour les régions de réseau, les sites de réseau et l’association de chaque sous-réseau dans le Skype pour la topologie de serveur d’entreprise avec un site de réseau. 
  
Cette rubrique fournit une vue d’ensemble des configurations requises qui sont communes à tous les trois de ces fonctionnalités de Voix Entreprise avancées.
  
## <a name="network-regions"></a>Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia.
  
> [!NOTE]
> Régions de réseau ne sont pas la même que Skype pour les zones de conférence-in Business Server, qui sont nécessaires pour associer des numéros d’accès à distance en conférence avec un ou plusieurs Skype pour les plans de numérotation de Business Server. Pour plus d’informations sur les zones de conférence à distance, consultez [planification pour les conférences à distance](http://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx). 
  
CAC nécessite que chaque zone du réseau ont un Skype associé pour le site central Business Server, qui gère le trafic multimédia au sein de la région (autrement dit, il prend des décisions en fonction des règles que vous avez configurés, ou non un audio en temps réel ou session vidéo peut être établie). Skype pour les sites centraux Business Server ne représentent pas les emplacements géographiques, mais plutôt logiques groupes de serveurs sont configurés en tant que pool ou un jeu de pools. 
  
Pour configurer une zone du réseau, vous pouvez utiliser l’onglet **zones** dans la section de **Configuration de réseau** de Skype pour Business Server du Panneau de configuration, ou exécuter le **Nouveau-CsNetworkRegion** ou Skype **CsNetworkRegion de l’ensemble** de l’entreprise Cmdlets du Shell de gestion de serveur. Pour obtenir des instructions, voir [zones de réseau de déployer, des sites et des sous-réseaux dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement, ou consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
Les mêmes définitions de zone réseau sont partagées par tous les trois fonctionnalités avancées de Voix Entreprise. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.
  
Pour associer un Skype pour site central de Business Server avec une région de réseau, vous spécifiez le nom du site central, soit à l’aide de la section de **Configuration de réseau** de Skype pour Business Server du Panneau de configuration, soit en exécutant la **Nouvelle-CsNetworkRegion** ou des applets de commande **Set-CsNetworkRegion** . Pour obtenir des instructions, voir [zones de réseau de déployer, des sites et des sous-réseaux dans Skype pour entreprise 2015](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement, ou consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
## <a name="network-sites"></a>Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.
  
> [!NOTE]
> Les sites de réseau sont utilisées uniquement par les fonctionnalités avancées de Voix Entreprise. Ils ne sont pas la même que les sites des succursales que vous configurez dans votre Skype pour la topologie du serveur de l’entreprise. 
  
Pour configurer un site de réseau et l’associer à une région de réseau, vous pouvez utiliser la section de **Configuration de réseau** de Skype pour Business Server du Panneau de configuration, ou exécuter le Skype pour Business Server Management Shell **New-CsNetworkSite** ou ** Ensemble-CsNetworkSite** applets de commande. Pour plus d’informations, voir [créer ou modifier un Site de réseau](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) dans la documentation de déploiement, ou consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.
  
Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).
  
> [!CAUTION]
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un Skype pour client Business prend son adresse IP locale et masque de l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission appel, mais pas media ignore, appel de contrôle d’admission fonctionne correctement même si vous configurez des sous-réseaux virtuels.) Par exemple, si un Skype pour client d’entreprise se connecte sur un ordinateur avec une adresse IP de 172.29.81.57 avec un masque de sous-réseau de 255.255.255.0, il demande l’ID de contournement qui est associé à sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre sous-réseaux fournie par Skype pour les clients d’entreprise (qui sont mis en service avec des sous-réseaux lors de la configuration du réseau, soit statique soit par DHCP Dynamic Host Configuration Protocol ().) 
  
## <a name="associating-subnets-with-network-sites"></a>Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Cette association de sous-réseaux Active les fonctionnalités avancées de Voix Entreprise rechercher les points de terminaison géographiquement. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.
  
Pour associer les sous-réseaux avec les sites du réseau, vous pouvez utiliser la section de **Configuration de réseau** de Skype pour Business Server du Panneau de configuration, ou vous pouvez utiliser le Skype pour Business Server Management Shell. Pour obtenir des instructions, voir [associer un sous-réseau à un Site de réseau](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) dans la documentation de déploiement, ou consultez le Skype pour obtenir une documentation Business Server Management Shell.
  
## <a name="see-also"></a>Voir aussi

#### 

[Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](call-admission-control.md)
  
[Plan des services d’urgence dans Skype pour Business Server 2015](emergency-services.md)
  
[Planifier le contournement de média dans Skype pour entreprise 2015](media-bypass.md)

