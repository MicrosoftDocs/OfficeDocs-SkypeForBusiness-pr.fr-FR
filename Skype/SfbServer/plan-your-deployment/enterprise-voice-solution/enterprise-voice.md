---
title: Planifier l’entreprise voix dans Skype entreprise Server
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Notions de base de la planification vocale d’entreprise dans Skype entreprise Server, y compris les sites, les régions, les liens réseau entre sites et l’estimation du trafic d’utilisation de la voix.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802894"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planifier l’entreprise voix dans Skype entreprise Server
 
Notions de base de la planification vocale d’entreprise dans Skype entreprise Server, y compris les sites, les régions, les liens réseau entre sites et l’estimation du trafic d’utilisation de la voix.
  
Le processus de déploiement d’Enterprise Voice dépend de votre topologie existante, de l’infrastructure et de la fonctionnalité voix entreprise que vous voulez prendre en charge. Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.
  
En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant. Certaines considérations peuvent être prises en compte dans le cadre de la planification de Skype entreprise Server (par exemple, haute disponibilité). Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.
  
## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites de votre topologie dans lesquels vous déploierez Enterprise Voice et les régions réseau auxquelles ces sites appartiennent. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Déterminez l’emplacement de déploiement local des passerelles (SBAs) pour le déploiement des passerelles () et l’endroit où vous pouvez configurer les Trunks SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Liaisons réseau entre sites

Vous devez également tenir compte de l’utilisation de la bande passante que vous attendez sur les liens réseau entre votre site central et ses sites de succursale. Si vous avez, ou envisagez de déployer, des liens WAN résilients entre les sites, nous vous conseillons de déployer une passerelle sur chaque site de succursale afin de fournir une résiliation directe à l’intérieur de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous n’avez pas de liens WAN résilients, l’hébergement est inférieur à 1000 utilisateurs sur votre site de succursale et ne disposent pas des administrateurs Skype entreprise Server accessibles en local, nous vous conseillons de déployer une application de succursale Survivable sur le site de la succursale. Si vous hébergez des utilisateurs de 1000 et 5000 sur votre site de succursale, que vous n’avez pas de connexion WAN fiable et que vous avez reçu des administrateurs Skype entreprise Server, nous vous conseillons de déployer un serveur de succursales Survivables avec une petite passerelle sur le site de la succursale. Envisagez aussi d’activer la déviation du trafic multimédia sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimation du trafic et de l’utilisation de la voix

L’outil de planification de Microsoft Lync Server 2013 utilise la métrique suivante pour estimer le trafic utilisateur sur chaque site, ainsi que le nombre de ports requis pour prendre en charge ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
> 
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
> 
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
Le nombre de ports à son tour détermine le nombre de serveurs de médiation et de passerelles qui seront nécessaires. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Composants, fonctionnalités et options de voix entreprise

Pour plus d’informations sur la planification de votre déploiement de voix entreprise, consultez les sections suivantes.
  
- [Composants requis pour l’entreprise voix dans Skype entreprise Server](components-required-for-enterprise-voice.md)
    
- [Planifier la connectivité PSTN dans Skype entreprise Server](pstn-connectivity-0.md)
    
- [Paramètres réseau pour les fonctions avancées de voix entreprise dans Skype entreprise Server](network-settings-for-advanced-features.md)
    
- [Planifier le contrôle d’admission des appels dans Skype entreprise Server](call-admission-control.md)
    
- [Planifier des services d’urgence dans Skype entreprise Server](emergency-services.md)
    
- [Plan de contournement de médias dans Skype entreprise](media-bypass.md)
    
- [Planifier des lignes téléphoniques privées avec Skype entreprise](private-telephone-lines.md)
    
- [Planifier le routage sur la base de l’emplacement dans Skype entreprise](location-based-routing.md)
    
- [Planifier les fonctionnalités de gestion des appels dans Skype entreprise](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

