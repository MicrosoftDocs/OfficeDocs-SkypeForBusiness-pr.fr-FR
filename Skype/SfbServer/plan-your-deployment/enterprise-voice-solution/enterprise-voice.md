---
title: Planification de Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Planification des notions de base dans Skype pour Business Server, notamment les sites, les régions, les liaisons réseau entre les sites et estimation du trafic de l’utilisation de voix de Voix Entreprise.
ms.openlocfilehash: a04c379e3a616a511306db62fd908af26e325418
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a>Planification de Voix Entreprise dans Skype Entreprise Server 2015
 
Planification des notions de base dans Skype pour Business Server, notamment les sites, les régions, les liaisons réseau entre les sites et estimation du trafic de l’utilisation de voix de Voix Entreprise.
  
Le processus de déploiement de Voix Entreprise dépend de la topologie existante, l’infrastructure et la fonctionnalité Voix Entreprise que vous souhaitez prendre en charge. Les procédures requises dépendront des fonctionnalités que vous choisirez, mais vous devrez tenir compte d’autres facteurs pour la planification à un niveau supérieur.
  
En règle générale, tenez compte du type et du nombre de sites que vous voulez déployer et de leur emplacement géographique, du volume d’appels sur chaque site, des types de liens réseaux qui relient les sites, si vous souhaitez offrir la redondance et le basculement pour la fonctionnalité voix pour chaque site, et enfin si vous voulez utiliser l’équipement PBX existant. Il existe certaines considérations, telles que de la haute disponibilité, que vous devez considérer lorsque vous planifiez Skype pour Business Server dans son ensemble. Ces considérations sont traitées dans les rubriques de cette section, selon les besoins.
  
## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites dans votre topologie où vous déploierez Voix Entreprise et les zones du réseau auxquelles appartiennent ces sites. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Décidez où passerelles seront déployés localement, où seront déployées Survivable Branch Appliances (SBA) et où vous pouvez configurer les trunks SIP (localement ou sur le site central) à un fournisseur de service de téléphonie Internet (ITSP).
  
## <a name="network-links-between-sites"></a>Liaisons réseau entre sites

Vous devez également envisager l’utilisation de la bande passante que vous comptez sur les liaisons réseau entre votre site central et ses sites de succursales. Si vous disposez ou prévoyez de déployer, robuste des liaisons de réseau étendu entre les sites, nous vous recommandons de déployer une passerelle au niveau de chaque site de la succursale pour fournir la résiliation de numérotation vers l’intérieur directe (DID) local pour les utilisateurs de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous n’avez pas résilient WAN links, héberger de moins de 1 000 utilisateurs à votre site de la succursale et n’ont pas de locaux Skype formé pour les administrateurs de serveur d’entreprise disponibles, que nous vous recommandons de déployer un Survivable Branch Appliance sur le site de la succursale. Si vous hébergez entre 1000 et 5000 utilisateurs à votre site de la succursale, ne disposent pas d’une connexion WAN robuste et ont reçu une formation Skype pour les administrateurs de serveur d’entreprise disponibles, que nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de la succursale. Envisagez aussi d’activer la déviation du trafic multimédia sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.
  
## <a name="estimating-voice-usage-and-traffic"></a>Estimation du trafic et de l’utilisation de la voix

L’outil de planification, de Microsoft Lync Server 2013 utilise la métrique de ci-dessous pour estimer le trafic des utilisateurs sur chaque site et le nombre de ports requis pour prendre en charge de ce trafic.
  
> Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.
    
> Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.
    
> Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.
    
Le nombre de ports détermine ensuite le nombre de serveurs de médiation et passerelles qui seront nécessaires. La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)
  
Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Les composants, les fonctionnalités et options de Voix Entreprise

Consultez les sections suivantes pour plus d’informations sur la planification de votre déploiement de Voix Entreprise.
  
- [Composants requis pour la Voix Entreprise dans Skype pour Business Server 2015](components-required-for-enterprise-voice.md)
    
- [Plan de connectivité RTPC dans Skype pour Business Server 2015](pstn-connectivity-0.md)
    
- [Paramètres réseau pour les fonctionnalités avancées de Voix Entreprise dans Skype pour Business Server 2015](network-settings-for-advanced-features.md)
    
- [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](call-admission-control.md)
    
- [Plan des services d’urgence dans Skype pour Business Server 2015](emergency-services.md)
    
- [Planifier le contournement de média dans Skype pour entreprise 2015](media-bypass.md)
    
- [Plan pour les lignes téléphoniques privées avec Skype pour entreprise 2015](private-telephone-lines.md)
    
- [Planifier le routage par emplacement dans Skype pour entreprise 2015](location-based-routing.md)
    
- [Plan des fonctionnalités de gestion d’appel dans Skype pour entreprise 2015](call-management-features.md)
    
- [Plan de reprise de Voix Entreprise dans Skype pour Business Server 2015](enterprise-voice-resiliency.md)
    

