---
title: Planification de Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise Voice planification concepts de base dans Skype Business Server, y compris les sites, les régions, les liaisons réseau entre les sites et l’estimation du trafic de voix d’utilisation.
ms.openlocfilehash: f1bd8f2f8514f34390cd085bd1407894e9788620
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>Planification de Voix Entreprise dans Skype Entreprise Server 2015
 
Enterprise Voice planification concepts de base dans Skype Business Server, y compris les sites, les régions, les liaisons réseau entre les sites et l’estimation du trafic de voix d’utilisation.
  
Le processus de déploiement de voix entreprise dépend de votre topologie, l’infrastructure et les fonctionnalités Enterprise Voice que vous souhaitez prendre en charge. Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.
  
En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant. Il existe certaines considérations, par exemple une haute disponibilité, que vous devez prendre en compte lorsque vous planifiez Skype pour Business Server dans sa globalité. Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.
  
## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites dans votre topologie où vous allez déployer Enterprise Voice et les régions de réseau auquel appartiennent ces sites. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Décidez où les passerelles seront déployés localement, où seront déployés Survivable Branch Appliances (SBA) et où vous pouvez configurer jonctions SIP (localement ou sur le site central) à un fournisseur de services de téléphonie Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Liaisons réseau entre sites

Vous devez également prendre en compte l’utilisation de la bande passante que vous attendez sur les liaisons réseau entre votre site central et ses sites de succursale. Si vous avez, ou que vous souhaitez déployer, résistantes liaisons réseau étendu entre les sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale pour fournir une terminaison SDA direct local (DID) pour les utilisateurs de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous ne disposez pas des liaisons réseau étendu résistantes, héberger moins de 1 000 utilisateurs sur votre site de succursale et n’ont pas de Skype formé local pour les administrateurs Business Server disponibles, que nous vous recommandons de déployer un serveur Survivable Branch Appliance sur le site de succursale. Si vous hébergez entre 1000 et 5000 utilisateurs sur votre site de succursale, ne disposent pas d’une connexion WAN résistante et ont formé Skype pour les administrateurs Business Server disponibles, que nous vous recommandons de déployer un serveur Survivable Branch Server avec une passerelle de petite taille sur le site de succursale. Envisagez aussi d’activer la déviation du trafic multimédia sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimation du trafic et de l’utilisation de la voix

L’outil de planification, de Microsoft Lync Server 2013 utilise la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge de ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
    
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
    
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
À son tour, le nombre de ports détermine le nombre de serveurs de médiation et passerelles qui seront requises. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Composants, les fonctionnalités et les options d’Enterprise Voice

Consultez les sections suivantes pour plus d’informations sur la planification de votre déploiement d’Enterprise Voice.
  
- [Composants requis pour Enterprise Voice sur Skype pour Business Server 2015](components-required-for-enterprise-voice.md)
    
- [Planifier la connectivité PSTN dans Skype Business Server 2015](pstn-connectivity-0.md)
    
- [Paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server 2015](network-settings-for-advanced-features.md)
    
- [Planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server 2015](call-admission-control.md)
    
- [Planifier les services d’urgence dans Skype pour Business Server 2015](emergency-services.md)
    
- [Planifier le contournement de média dans Skype pour Business 2015](media-bypass.md)
    
- [Planifier des lignes téléphoniques privées avec Skype pour Business 2015](private-telephone-lines.md)
    
- [Plan pour le routage basé sur l’emplacement dans Skype pour Business 2015](location-based-routing.md)
    
- [Planifier des fonctionnalités de gestion des appels dans Skype pour Business 2015](call-management-features.md)
    
- [Planifier la résistance de voix entreprise dans Skype pour Business Server 2015](enterprise-voice-resiliency.md)
    

