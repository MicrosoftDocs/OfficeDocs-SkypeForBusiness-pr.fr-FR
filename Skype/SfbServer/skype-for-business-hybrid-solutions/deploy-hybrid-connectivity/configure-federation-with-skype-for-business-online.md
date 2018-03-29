---
title: Configuration de la fédération avec Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Résumé : Apprenez à configurer l’interopérabilité entre Skype et de votre déploiement sur site pour l’activité en ligne.'
ms.openlocfilehash: 1a08fdb9ad9522e50bc412adcc9214fff3bbb924
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a>Configuration de la fédération avec Skype Entreprise Online
 
**Résumé :** Apprenez à configurer l’interopérabilité entre Skype et de votre déploiement sur site pour l’activité en ligne.
  
Suivez les étapes de cette section pour configurer l’interopérabilité entre Skype et de votre déploiement sur site pour l’activité en ligne.
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurer votre service de bord sur site pour la fédération avec Skype pour professionnels en ligne

La fédération permet aux utilisateurs dans votre déploiement sur site de communiquer avec les utilisateurs d’Office 365 dans votre organisation. Pour configurer la fédération, exécuter les applets de commande suivantes dans le Skype pour Business Server Management Shell :
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurer votre Skype pour les clients professionnels en ligne pour un espace d’adressage partagé SIP

Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie. Avant d’essayer de déplacer des utilisateurs sur site à Skype pour professionnels en ligne, vous aurez besoin configurer vos clients Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site. S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :
  
Déplacement-CsUser : Erreur HostedMigration : Error=(510), Description = (les clients de cet utilisateur ne sont pas activé pour l’espace d’adressage partagé sip).
  
Pour configurer un espace d’adressage partagé SIP, établir une session PowerShell à distance avec Skype pour Business Online et exécutez l’applet de commande suivante :
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local. 
  
Pour établir une session PowerShell à distance avec Skype pour professionnels en ligne, vous devez d’abord installer le Skype pour module de connecteur Business Online pour Windows PowerShell, ce que vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

Pour plus d’informations sur la façon d’établir une session PowerShell à distance avec Skype pour professionnels en ligne, consultez [connexion à Lync Online en utilisant Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
  
Pour plus d’informations sur l’utilisation de la Skype pour module de PowerShell en ligne Business connector, reportez-vous [à l’aide de Windows PowerShell pour gérer Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  
## <a name="see-also"></a>Voir aussi

#### 

[Nouvelle-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

