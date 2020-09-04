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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Découvrez comment déployer plusieurs sites RTC dans la version Cloud Connector.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358920"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Déployer plusieurs sites dans Cloud Connector

> [!Important] 
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Découvrez comment déployer plusieurs sites RTC dans la version Cloud Connector.
  
Cette section décrit comment déployer plusieurs sites RTC (réseau téléphonique commuté). Les sites sont déployés l’un après l’autre en suivant les mêmes étapes que pour le déploiement d’un site unique. Cette rubrique décrit les éléments à prendre en compte et les différences entre les sites dans un déploiement sur plusieurs sites. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Plusieurs sites RTC (réseau téléphonique commuté)

Voici un exemple de configuration pour déployer Skype entreprise, version Cloud Connector pour différents sites RTC. Assurez-vous que vos paramètres de configuration sont corrects avant de démarrer un déploiement.
  
Site RTC 1
  
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

Pour chaque site RTC que vous souhaitez ajouter, suivez les étapes de la procédure de [déploiement d’un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> Le dossier partagé pour la préparation de la haute disponibilité (HA) est par site RTC. Le dossier partagé **doit** être différent entre les sites RTC. N’utilisez pas le même dossier partagé pour plusieurs sites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site unique avec haute disponibilité (HA) comparé aux déploiements multisites
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Le tableau suivant répertorie les différences entre un site unique avec prise en charge de la haute disponibilité et un déploiement sur plusieurs sites.
  
|**Catégorie**|**Élément**|**Site unique avec haute disponibilité**|**Multisite**|
|:-----|:-----|:-----|:-----|
|Configurer  <br/> |Nom d’hôte de l’appliance <br/> |**Différentes** sur plusieurs appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configuration  <br/> |Dossier partagé  <br/> |Nécessite le **même** dossier partagé entre plusieurs appliances <br/> |Nécessite un dossier partagé **différent** sur plusieurs appliances <br/> |
|Configurer  <br/> |VirtualMachineDomain  <br/> |Nécessite le **même** domaine pour toutes les appliances <br/> |Nécessite le **même** domaine pour tous les sites RTC <br/> |
|Configurer  <br/> |SIPDomains  <br/> |Les noms de domaine et l’ordre doivent être les **mêmes** pour toutes les appliances <br/> |Les noms de domaine et l’ordre doivent être les **mêmes** pour tous les sites RTC <br/> |
|Configurer  <br/> |Nom du site  <br/> |**Mêmes** Nom du site entre les appliances <br/> |**Différent** Nom du site sur les sites RTC <br/> |
|Configurer  <br/> |Noms des serveurs  <br/> |**Différentes** sur plusieurs appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configurer  <br/> |Noms de domaine complets du pool interne  <br/> |**Identique** pour toutes les appliances <br/> |**Identique** sur tous les sites PSTN <br/> |
|Configurer  <br/> |Adresses IP internes  <br/> |**Différentes** sur plusieurs appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configurer  <br/> |Nom de domaine complet externe  <br/> |**Identique** pour toutes les appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configurer  <br/> |Adresses IP externes  <br/> |**Différentes** sur plusieurs appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configurer  <br/> |Paramètres RTC GW  <br/> |**Identique** pour toutes les appliances <br/> |**Différents** sur les sites RTC <br/> |
|Configurer  <br/> |Enregistrement DNS  <br/> |Ajouter des enregistrements avec les **mêmes** noms de domaine complets d’accès externe et **différentes** adresses IP <br/> |Ajouter des enregistrements avec des noms de domaine complets d’accès externe **différents** et des adresses IP **différentes** <br/> |
|Configuration  <br/> |Client hybride  <br/> |Définir défini  <br/> Définir PeerDestination pour le secours  <br/> |Définir défini  <br/> Définir PeerDestination pour le secours  <br/> |
|Configuration  <br/> |Passerelle  <br/> |Mappage MS GW **M :N** dans ce site <br/> |La ou les passerelles PSTN de chaque site PSTN doivent se connecter uniquement au (x) serveur (s) de médiation dans le même site  <br/> |
|Configuration  <br/> |Utilisateur  <br/> |Définir défini  <br/> |Définir défini  <br/> |
   

