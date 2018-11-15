---
title: Configurer Skype pour un environnement hybride Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement sur site et les Skype pour Business en ligne.'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532776"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurer Skype pour un environnement hybride Business

Pour configurer Skype pour hybride d’entreprise, vous devez :

- [Configurer votre environnement local à fédérer avec Office 365.](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [Configurer votre environnement local pour la gestion de la confidentialité Office 365 et activer l’espace d’adressage SIP partagé avec Office 365.](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365.](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> Si vous avez Exchange sur site, vous souhaiterez peut-être configurer OAuth entre votre Exchange locale et Skype pour les environnements d’entreprise en ligne. Pour plus d’informations, voir [gérer l’authentification serveur à serveur dans Skype pour Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) et [planifier l’intégration Skype pour les entreprises et Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Configurer le service Edge de local à fédérer avec Office 365

La fédération permet aux utilisateurs de votre déploiement local de communiquer avec des utilisateurs Office 365 dans votre organisation. Pour configurer la fédération, exécutez l’applet de commande suivante dans le Skype pour Business Server Management Shell :
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configurer votre environnement local pour permettre l’espace d’adressage SIP partagé avec Office 365

Vous devez également configurer votre environnement local pour la gestion de la confidentialité Office 365 et activer l’espace d’adressage SIP partagé avec Office 365. Cela signifie Office 365 peuvent potentiellement héberger des comptes d’utilisateurs pour le même ensemble de domaines SIP que votre environnement local et les messages peuvent être routés entre les utilisateurs hébergés sur site et en ligne.  Pour cela, en configurant un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme indiqué ci-dessous.

Tout d’abord, vérifiez si vous disposez déjà d’un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com. Si elle existe, puis supprimez-le à l’aide de la commande suivante :

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Puis créez un nouveau fournisseur d’hébergement, utilisez l’applet de commande New-CsHostingProvider comme suit : 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365
  
Outre les modifications apportées dans votre déploiement sur site, vous devez effectuer la modification correspondante dans votre organisation cliente Office 365 à activé espace d’adressage SIP partagé avec votre déploiement sur site.  

Pour activer l’espace d’adressage SIP partagé dans votre organisation cliente Office 365, établir une session PowerShell distante avec Skype pour Business Online, puis exécutez l’applet de commande suivante :
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit demeurer défini sur True jusqu’à ce que le déplacement vers Online soit finalisé et qu’aucun utilisateur ne soit hébergé en local. 
  
Pour établir une session PowerShell distante avec des équipes ou Skype pour Business Online, vous devez d’abord installer le Skype pour module connecteur Business en ligne pour Windows PowerShell, vous pouvez obtenir [ici](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Pour plus d’informations sur la façon d’établir une session PowerShell distante avec Skype pour Business en ligne et comment utiliser la Skype pour le module Business Connector en ligne, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Voir aussi

[Nouvelle-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

