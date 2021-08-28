---
title: Planifier les Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Voix Entreprise base de la planification des Skype Entreprise Server, notamment les sites, les régions, les liens réseau entre les sites et l’estimation du trafic d’utilisation de la voix.
ms.openlocfilehash: bfd7d4b1491b83c6ad3ab65836777e805689c21f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618810"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planifier les Voix Entreprise dans Skype Entreprise Server
 
Voix Entreprise base de la planification des Skype Entreprise Server, notamment les sites, les régions, les liens réseau entre les sites et l’estimation du trafic d’utilisation de la voix.
  
Le processus de déploiement Voix Entreprise dépend de votre topologie, de votre infrastructure et de la Voix Entreprise que vous souhaitez prendre en charge. Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.
  
En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant. Il existe certaines considérations, telles que la haute disponibilité, que vous devez prendre en compte lorsque vous planifiez l’Skype Entreprise Server dans son ensemble. Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.
  
## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites de votre topologie où vous allez déployer Voix Entreprise et les régions réseau à laquelle ces sites appartiennent. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Décidez où les passerelles seront déployées localement, où les Survivable Branch Appliances (SBA) seront déployés et où vous pouvez configurer des trunks SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Liaisons réseau entre les sites

Vous devez également prendre en compte l’utilisation de la bande passante que vous attendez sur les liaisons réseau entre votre site central et ses sites de succursale. Si vous avez ou envisagez de déployer des liaisons wan résilientes entre des sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale pour fournir un arrêt SDN (direct inward dial) local pour les utilisateurs de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous ne disposez pas de liaisons réseau wan résistantes, si vous hébergez moins de 1 000 utilisateurs sur votre site de succursale et que vous ne disposez pas d’administrateurs Skype Entreprise Server formés en local, nous vous recommandons de déployer un Survivable Branch Appliance sur le site de succursale. Si vous hébergez entre 1 000 et 5 000 utilisateurs sur votre site de succursale, si vous ne disposez pas d’une connexion WAN résiliente et que des administrateurs Skype Entreprise Server formés sont disponibles, nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de succursale. Envisagez aussi d’activer le contournement de média sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimation de l’utilisation et du trafic des voix

L’outil de planification Microsoft Lync Server 2013 utilise la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
> 
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
> 
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
Le nombre de ports détermine à son tour le nombre de serveurs de médiation et de passerelles qui seront requis. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Composants, fonctionnalités et options de Voix Entreprise

Consultez les sections suivantes pour plus d’informations sur la planification Voix Entreprise déploiement.
  
- [Composants requis pour les Voix Entreprise dans Skype Entreprise Server](components-required-for-enterprise-voice.md)
    
- [Planifier la connectivité PSTN dans Skype Entreprise Server](pstn-connectivity-0.md)
    
- [Paramètres réseau pour les fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server](network-settings-for-advanced-features.md)
    
- [Planifier le contrôle d’admission des appels dans Skype Entreprise Server](call-admission-control.md)
    
- [Planifier les services d’urgence dans Skype Entreprise Server](emergency-services.md)
    
- [Planifier le contournement de média dans Skype Entreprise](media-bypass.md)
    
- [Planifier des lignes téléphoniques privées avec Skype Entreprise](private-telephone-lines.md)
    
- [Planifier le routage Location-Based dans Skype Entreprise](location-based-routing.md)
    
- [Planifier les fonctionnalités de gestion des appels dans Skype Entreprise](call-management-features.md)
    
- [Planifier la résilience Voix Entreprise dans Skype Entreprise Server](enterprise-voice-resiliency.md)
    

