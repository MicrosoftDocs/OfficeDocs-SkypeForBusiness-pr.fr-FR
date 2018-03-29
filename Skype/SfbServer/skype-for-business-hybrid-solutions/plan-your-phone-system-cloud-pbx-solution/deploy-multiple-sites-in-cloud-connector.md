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
ms.custom: Strat_SB_Hybrid
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenir des informations sur le déploiement de plusieurs sites RTPC dans le nuage lien édition.
ms.openlocfilehash: 04af3ffa69a0ba452277d497544d4ba6708b5cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Déployer plusieurs sites dans Cloud Connector
 
Obtenir des informations sur le déploiement de plusieurs sites RTPC dans le nuage lien édition.
  
Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Sites multiples de Réseau Téléphonique Commuté (RTC)

Voici un exemple de configuration pour le déploiement de Skype pour professionnel de connecteur de nuage pour les différents sites RTPC. Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.
  
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

Pour chaque site RTPC que vous souhaitez ajouter, suivez les étapes de [déploiement d’un site unique dans le connecteur de nuage](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> Le dossier partagé pour la préparation de la haute disponibilité (HA) est par site de RTPC. Le dossier partagé **doit** être différents entre les sites du réseau RTPC. N’utilisez pas le dossier partagé même pour plusieurs sites. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Site unique à haute disponibilité comparé aux déploiements multi-sites
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

Le tableau suivant présente les différences entre un site unique avec prise en charge de la haute disponibilité et un déploiement multisite.
  
|**Catégorie**|**Élément**|**Site unique avec haute disponibilité**|**Plusieurs sites**|
|:-----|:-----|:-----|:-----|
|Installation  <br/> |Dossier partagé  <br/> |Nécessite le **même** dossier partagé sur plusieurs appliances <br/> |Nécessite un répertoire partagé **différent** pour toutes les appliances <br/> |
|Configuration  <br/> |VirtualMachineDomain  <br/> |Nécessite le **même** domaine pour toutes les appliances <br/> |Nécessite le **même** domaine pour tous les sites RTC <br/> |
|Configuration  <br/> |Domaines SIP  <br/> |Ordre et noms de domaine doivent être le **même** sur les appareils <br/> |Ordre et noms de domaine doivent être le **même** sur les sites RTPC <br/> |
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
|Configuration  <br/> |Enregistrement DNS  <br/> |Ajouter des enregistrements avec le **même** complets d’accès externes et des adresses IP **différentes** <br/> |Ajoutez des enregistrements avec **différents** noms de domaine complets d’accès externes et **différentes** adresses IP. <br/> |
|Installation  <br/> |Clients hybride  <br/> |Site RTC hybride défini  <br/> Destination de secours des pairs définie  <br/> |Site RTC hybride défini  <br/> Destination de secours des pairs définie  <br/> |
|Installation  <br/> |Passerelle  <br/> |Mappage dans ce site de passerelle MS **M : N** <br/> |La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site  <br/> |
|Installation  <br/> |Utilisateur  <br/> |Paramètres RTC utilisateur défini  <br/> |Paramètres RTC utilisateur défini  <br/> |
   

