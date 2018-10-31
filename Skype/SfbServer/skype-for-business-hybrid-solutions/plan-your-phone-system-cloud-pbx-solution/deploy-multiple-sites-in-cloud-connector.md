---
title: Déployer plusieurs sites dans Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: En savoir plus sur le déploiement de plusieurs sites PSTN dans le nuage connecteur Edition.
ms.openlocfilehash: 388915d0ab22dc50378d84a82c01291cfd7c99eb
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851489"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Déployer plusieurs sites dans Cloud Connector
 
En savoir plus sur le déploiement de plusieurs sites PSTN dans le nuage connecteur Edition.
  
Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Sites multiples de Réseau Téléphonique Commuté (RTC)

Voici un exemple de configuration pour déployer Skype pour édition dans le nuage connecteur pour différents sites PSTN. Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.
  
Site RTC 1
  
```
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

Site RTC 2
  
```
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

Pour chaque site PSTN que vous souhaitez ajouter, suivez les étapes de [déploiement d’un seul site dans le nuage connecteur](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> Le dossier partagé pour la préparation de la haute disponibilité est par site PSTN. Le dossier partagé **doit** être différente pour les sites PSTN. N’utilisez pas le même dossier partagé pour plusieurs sites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site unique à haute disponibilité comparé aux déploiements multi-sites
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Le tableau suivant établit la liste des différences entre un site unique à haute disponibilité et un déploiement de plusieurs sites.
  
|**Catégorie**|**Option**|**Site unique à haute disponibilité**|**Plusieurs sites**|
|:-----|:-----|:-----|:-----|
|Configuration  <br/> |Nom de l’application hôte <br/> |**Différent** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Installation  <br/> |Répertoire partagé  <br/> |Requiert le **même** dossier partagé sur appliances <br/> |Nécessite un répertoire partagé **différent** pour toutes les appliances <br/> |
|Configuration  <br/> |VirtualMachineDomain  <br/> |Nécessite le **même** domaine pour toutes les appliances <br/> |Nécessite le **même** domaine pour tous les sites RTC <br/> |
|Configuration  <br/> |Domaines SIP  <br/> |Ordre et les noms de domaine doivent être le **même** sur des appareils <br/> |Ordre et les noms de domaine doivent être le **même** entre les sites PSTN <br/> |
|Configuration  <br/> |Nom du site  <br/> |
            Le **même** nom de site pour toutes les appliances <br/> |
            Nom de site **différent** pour chaque site RTC <br/> |
|Configuration  <br/> |Noms du serveur  <br/> |**Différent** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Configuration  <br/> |FQDNs du pool interne  <br/> |**Identique** pour chaque appliance <br/> |
            Le **même** pour tous les sites RTC <br/> |
|Configuration  <br/> |Adresses IP internes  <br/> |**Différent** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Configuration  <br/> |FQDN externe  <br/> |**Identique** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Configuration  <br/> |Adresses IP externes  <br/> |**Différent** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Configuration  <br/> |Paramètres de la passerelle RTC  <br/> |**Identique** pour chaque appliance <br/> |**Différent** pour chaque site RTC <br/> |
|Configuration  <br/> |Enregistrement DNS  <br/> |Ajouter des enregistrements avec le **même** FQDN de l’accès externe et des adresses IP **différentes** <br/> |Ajout d’enregistrements avec des FQDN d'accès externe **différents** et des adresses IP **différentes** <br/> |
|Installation  <br/> |Client hybride  <br/> |Site RTC hybride défini  <br/> Destination de secours des pairs définie  <br/> |Site RTC hybride défini  <br/> Destination de secours des pairs définie  <br/> |
|Installation  <br/> |Passerelle  <br/> |Mappage dans ce site de passerelle MS **M : N** <br/> |La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site  <br/> |
|Installation  <br/> |Utilisateur  <br/> |Paramètres RTC utilisateur défini  <br/> |Paramètres RTC utilisateur défini  <br/> |
   

