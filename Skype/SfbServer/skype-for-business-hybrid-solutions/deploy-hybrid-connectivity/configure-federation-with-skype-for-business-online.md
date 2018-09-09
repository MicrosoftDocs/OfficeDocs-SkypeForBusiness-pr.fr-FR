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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.'
ms.openlocfilehash: 7367a1fa7bf7eb305a8b72582e488cfd6ba6fa1c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884119"
---
# <a name="configure-federation-with-skype-for-business-online"></a>Configuration de la fédération avec Skype Entreprise Online
 
**Résumé :** Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business Online.
  
Suivez les étapes décrites dans cette section pour configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurer votre service de périphérie sur site pour la fédération avec Skype pour Business Online

La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation. Pour configurer la fédération, exécutez les cmdlets suivantes dans le Skype pour Business Server Management Shell :
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurer votre Skype pour Business Online client pour un espace d’adressage SIP partagé

Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie. Avant d’essayer de déplacer les utilisateurs locaux vers Skype pour Business Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage partagé protocole SIP (Session Initiation) avec votre déploiement sur site. S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :
  
Move-CsUser : HostedMigration tolérance : Error=(510), Description = (client de cet utilisateur n’est pas activé pour l’espace d’adressage sip partagé).
  
Pour configurer un espace d’adressage SIP partagé, établir une session PowerShell distante avec Skype pour Business Online, puis exécutez l’applet de commande suivante :
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local. 
  
Pour établir une session PowerShell distante avec Skype pour Business Online, vous devez d’abord installer le Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir ici : [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Pour plus d’informations sur l’utilisation de PowerShell avec Skype pour Business Online, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

  
## <a name="see-also"></a>Voir aussi

[Nouvelle-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)