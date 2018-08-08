---
title: Paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces doivent être configurés pour déployer le Plan du contournement de média dans Skype pour les entreprises, planifier appel de contrôle d’admission des appels dans Skype pour Business Server), ou une planification pour les services d’urgence dans Skype pour Business Server dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: ca8cbe6de733f5a2a27552229d3f71c9fbad3b4d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981191"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server
 
Découvrez les régions réseau, les sites réseau et les sous-réseaux IP. Tous ces doivent être configurés pour déployer le [Plan pour le média de contournement dans Skype pour les entreprises](media-bypass.md), [planification pour le contrôle d’admission des appels d’appel dans Skype pour Business Server](call-admission-control.md)ou [planifier des services d’urgence dans Skype pour Business Server](emergency-services.md) dans Skype pour Business Server Enterprise Voice.
  
Skype pour Business Server comporte trois fonctionnalités voix entreprise : [Plan pour le contrôle d’admission des appels d’appel dans Skype pour Business Server](call-admission-control.md), [planifier des services d’urgence dans Skype pour Business Server](emergency-services.md)et [planification du contournement de média dans Skype pour les entreprises ](media-bypass.md). Ces fonctionnalités partagent certain configuration requise pour les régions réseau, sites réseau et l’association de chaque sous-réseau de le Skype pour la topologie du serveur d’entreprise avec un site réseau. 
  
Cette rubrique fournit une vue d’ensemble de la configuration requise qui sont communs à tous les trois de ces fonctionnalités Enterprise Voice avancées.
  
## <a name="network-regions"></a>Régions réseau

Une région réseau est un concentrateur réseau ou un segment réseau principal utilisé uniquement dans la configuration du service Contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia.
  
> [!NOTE]
> Régions de réseau ne sont pas la même que Skype pour les régions de conférence rendez-vous Business Server, qui sont nécessaires pour associer des numéros d’accès de conférence rendez-vous avec un ou plusieurs Skype pour les plans de numérotation Business Server. Pour plus d’informations sur les régions de conférence rendez-vous, consultez [planification de conférence rendez-vous](http://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx). 
  
CAC requiert qu’un Skype pour le site central Business Server, qui gère le trafic multimédia dans la région associée à chaque région réseau (autrement dit, il prend des décisions basées sur des règles que vous avez configuré ou non une audio en temps réel ou session vidéo peut être établie). Skype pour les sites centraux Business Server ne représentent pas les emplacements géographiques, mais plutôt logiques groupes de serveurs qui sont configurés en tant que pool ou un ensemble de pools. 
  
Pour configurer une région réseau, vous pouvez utiliser l’onglet **zones** dans la section **Configuration de réseau** de Skype pour le panneau de configuration serveur Business ou exécuter la **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Skype pour les entreprises Applets de commande Server Management Shell. Pour plus d’informations, voir [déployer les régions de réseau, des sites et sous-réseaux de Skype pour les entreprises](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement ou faire référence à la Skype pour la documentation sur Business Server Management Shell.
  
Les mêmes définitions de région réseau sont partagées par tous les trois fonctionnalités voix entreprise. Si vous avez créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin d’en créer de nouvelles pour les autres fonctionnalités. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le système E9-1-1 (qui ne nécessite pas de site central associé) et que vous déployez ultérieurement le contrôle d’admission des appels, vous devez modifier chacune des définitions de région réseau pour spécifier un site central.
  
Pour associer un Skype pour le site central Business Server avec une région de réseau, vous spécifiez le nom du site central, soit à l’aide de la section **Configuration de réseau** de Skype pour le panneau de configuration serveur Business, soit en exécutant la **New-CsNetworkRegion.** ou des applets de commande **Set-CsNetworkRegion** . Pour plus d’informations, voir [déployer les régions de réseau, des sites et sous-réseaux de Skype pour les entreprises](../../deploy/deploy-enterprise-voice/deploy-network.md) dans la documentation de déploiement ou faire référence à la Skype pour la documentation sur Business Server Management Shell.
  
## <a name="network-sites"></a>Sites réseau

Un site réseau représente un emplacement géographique, tel qu’une succursale, un bureau régional ou un bureau principal. Chaque site réseau doit être associé à une région réseau spécifique.
  
> [!NOTE]
> Sites réseau sont utilisés uniquement par les fonctionnalités Enterprise Voice. Ils ne sont pas la même que les sites de succursale que vous configurez dans votre Skype pour la topologie du serveur d’entreprise. 
  
Pour configurer un site réseau et l’associer à une région de réseau, vous pouvez utiliser la section **Configuration de réseau** de Skype pour le panneau de configuration serveur Business ou exécuter la Skype pour Business Server Management Shell, **New-CsNetworkSite** ou ** Set-CsNetworkSite** applets de commande. Pour plus d’informations, voir [créer ou modifier un Site réseau](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) dans la documentation de déploiement ou faire référence à la Skype pour la documentation sur Business Server Management Shell.
  
## <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.
  
Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à Détroit, se rend dans les bureaux de New York pour suivre une formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées à New York (par exemple, 172.29.80.103).
  
> [!CAUTION]
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un Skype pour client Business prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associés. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels d’appel, mais pas le contournement de média, le contrôle d’admission des appels d’appel peut fonctionner même si vous configurez les sous-réseaux virtuels.) Par exemple, si un Skype pour Business client se connecte sur un ordinateur disposant d’une adresse IP de 172.29.81.57 avec un masque de sous-réseau de 255.255.255.0, il va demander l’ID de contournement associée au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux fournie par Skype pour les clients d’entreprise (qui sont mis en service avec les sous-réseaux pendant la configuration réseau, statique ou par DHCP Dynamic Host Configuration Protocol ().) 
  
## <a name="associating-subnets-with-network-sites"></a>Association de sous-réseaux à des sites réseau

Chaque sous-réseau dans le réseau d’entreprise doit être associé à un site réseau (c’est-à-dire que chaque sous-réseau doit être associé à un emplacement géographique). Cette association de sous-réseaux Active les fonctionnalités Enterprise Voice rechercher les points de terminaison géographiquement. Par exemple, la localisation des points de terminaison permet au contrôle d’admission des appels de réguler le flux de données audio et vidéo en temps réel qui transitent vers et depuis le site réseau.
  
Pour associer des sous-réseaux à des sites réseau, vous pouvez utiliser la section **Configuration de réseau** de Skype pour le panneau de configuration serveur Business, ou vous pouvez utiliser la Skype pour Business Server Management Shell. Pour plus d’informations, voir [associer un sous-réseau à un Site réseau](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) dans la documentation de déploiement ou faire référence à la Skype pour la documentation sur Business Server Management Shell.
  
## <a name="see-also"></a>Voir aussi

[Planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server](call-admission-control.md)
  
[Planifier les services d’urgence dans Skype pour Business Server](emergency-services.md)
  
[Planification du contournement de média dans Skype pour les entreprises](media-bypass.md)

