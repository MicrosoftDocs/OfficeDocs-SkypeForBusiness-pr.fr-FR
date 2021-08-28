---
title: Déployer plusieurs sites dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Découvrez le déploiement de plusieurs sites PSTN dans Cloud Connector Edition.
ms.openlocfilehash: 7f771875605ffef130b430fd7c7a00d9d1a63873
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613764"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Déployer plusieurs sites dans Cloud Connector

> [!Important] 
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Découvrez le déploiement de plusieurs sites PSTN dans Cloud Connector Edition.
  
Cette section décrit comment déployer plusieurs sites de réseau téléphonique commuté (PSTN). Les sites sont déployés un par un en utilisant les mêmes étapes que le déploiement d’un seul site. Cette rubrique décrit les considérations et les différences entre les sites dans un déploiement sur plusieurs sites. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Plusieurs sites de réseau téléphonique commuté (PSTN)

L’exemple suivant montre un exemple de configuration pour déployer Skype Entreprise Cloud Connector Edition pour différents sites PSTN. Assurez-vous que vos paramètres de configuration sont corrects avant de commencer un déploiement.
  
Site PSTN 1
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

Site PSTN 2
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Pour chaque site PSTN que vous souhaitez ajouter, suivez les étapes de la procédure de déploiement d’un [site unique dans Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)
  
> [!IMPORTANT]
> Le dossier partagé pour la préparation de la haute disponibilité (HA) est par site PSTN. Le dossier partagé **doit être** différent entre les sites PSTN. N’utilisez pas le même dossier partagé pour plusieurs sites.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site unique avec haute disponibilité (HA) par rapport aux déploiements multisesses
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Le tableau suivant répertorie les différences entre un site unique avec prise en charge de la ha et un déploiement sur plusieurs sites.
  
|**Catégorie**|**Élément**|**Site unique avec ha**|**Multisesse**|
|:-----|:-----|:-----|:-----|
|Configurer  <br/> |Nom d’hôte de l’appliance <br/> |**Différents d’une** appliances à l’autre <br/> |**Différents sites** PSTN <br/> |
|Installation  <br/> |Dossier partagé  <br/> |Nécessite le **même dossier** partagé entre les appliances <br/> |Nécessite un **dossier partagé différent pour** toutes les appliances <br/> |
|Configurer  <br/> |VirtualMachineDomain  <br/> |Nécessite le **même domaine pour** toutes les appliances <br/> |Nécessite le **même domaine** sur les sites PSTN <br/> |
|Configurer  <br/> |SIPDomains  <br/> |Les noms de domaine et l’ordre doivent être **les mêmes pour toutes les** appliances <br/> |Les noms de domaine et l’ordre doivent être **les mêmes** sur les sites PSTN <br/> |
|Configurer  <br/> |Nom du site  <br/> |**Identique** Nom du site sur les appliances <br/> |**Différent** Nom du site sur les sites PSTN <br/> |
|Configurer  <br/> |Noms de serveur  <br/> |**Différents d’une** appliances à l’autre <br/> |**Différents sites** PSTN <br/> |
|Configurer  <br/> |FQDN de pool interne  <br/> |**Identique pour** toutes les appliances <br/> |**Identique sur** les sites PSTN <br/> |
|Configurer  <br/> |IPs internes  <br/> |**Différents d’une** appliances à l’autre <br/> |**Différents sites** PSTN <br/> |
|Configurer  <br/> |FQDN externe  <br/> |**Identique pour** toutes les appliances <br/> |**Différents sites** PSTN <br/> |
|Configurer  <br/> |Fournisseurs d’IP externes  <br/> |**Différents d’une** appliances à l’autre <br/> |**Différents sites** PSTN <br/> |
|Configurer  <br/> |Paramètres PSTN GW  <br/> |**Identique pour** toutes les appliances <br/> |**Différents sites** PSTN <br/> |
|Configurer  <br/> |Enregistrement DNS  <br/> |Ajouter des enregistrements avec les **mêmes FQDN** d’accès externe et différentes **adresses** IP <br/> |Ajouter des enregistrements avec **différents** FQDN d’accès externe et **différentes adresses** IP <br/> |
|Installation  <br/> |Client hybride  <br/> |Définir HybridPSTNSite  <br/> Définir PeerDestination pour le retour  <br/> |Définir HybridPSTNSite  <br/> Définir PeerDestination pour le retour  <br/> |
|Installation  <br/> |Passerelle  <br/> |Mappage **M:N MS** GW dans ce site <br/> |Les passerelles PSTN de chaque site PSTN doivent uniquement se connecter au(s) serveur(s) de médiation du même site  <br/> |
|Installation  <br/> |Utilisateur  <br/> |Définir UserPSTNSettings  <br/> |Définir UserPSTNSettings  <br/> |
