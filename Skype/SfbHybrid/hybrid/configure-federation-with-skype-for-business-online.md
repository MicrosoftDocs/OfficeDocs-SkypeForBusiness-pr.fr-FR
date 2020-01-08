---
title: Configurer Skype Entreprise hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Skype entreprise online.'
ms.openlocfilehash: c451224e7f421b4505560533b2880a14cc04e1a9
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963032"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurer Skype Entreprise hybride

Pour configurer Skype Entreprise hybride, vous devez :

- [Configurez votre service d’environnement local de sorte qu’il se fédérer avec Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).
- [Configurez votre environnement local pour qu’il approuve office 365 et activez l’espace d’adressage SIP partagé avec office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Activez l’espace d’adressage SIP partagé dans votre client Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).

Notez que si vous disposez d’Exchange en local, vous pouvez configurer OAuth entre votre environnement Exchange local et Skype entreprise online. Pour plus d’informations, consultez la rubrique [Manage Server-to-Server Authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) et [envisagez d’intégrer Skype entreprise et Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Configurer votre service Edge local pour une Fédération avec Office 365

La fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs d’Office 365 de votre organisation. Pour configurer la Fédération, exécutez l’applet de commande suivante dans Skype entreprise Server Management Shell :
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

Si la valeur « -EnablePartnerDiscovery » est définie sur 1, Skype entreprise Server utilise des enregistrements DNS pour essayer de découvrir des domaines partenaires non répertoriés dans la liste AllowedDomains. Si la valeur est définie sur 0, Skype entreprise Server se fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains. Ce paramètre est requis si vous utilisez le routage de service DNS.



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Configuration de votre environnement local pour activer l’espace d’adressage SIP partagé avec Office 365

Vous devez aussi configurer votre environnement local pour approuver Office 365 et activer l’espace d’adressage SIP partagé avec Office 365. Cela signifie qu’Office 365 peut potentiellement héberger des comptes d’utilisateurs pour le même ensemble de domaines SIP que votre environnement local et que les messages peuvent être routés entre les utilisateurs hébergés sur site et en ligne.  Pour ce faire, configurez un fournisseur d’hébergement avec ProxyFqdn = sipfed. online. Lync. com, comme décrit ci-dessous.

Tout d’abord, vérifiez si vous disposez déjà d’un fournisseur d’hébergement avec ProxyFqdn = sipfed. online. Lync. com. S’il en existe un, supprimez-le à l’aide de la commande suivante :

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Créez ensuite un fournisseur d’hébergement, utilisez la cmdlet New-CsHostingProvider comme suit : 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Activer l’espace d’adressage SIP partagé dans votre client Office 365
  
Outre les modifications que vous avez apportées dans votre déploiement local, vous devrez apporter la modification correspondante dans votre client Office 365 pour activer l’espace d’adressage SIP partagé avec votre déploiement local.  

Pour activer l’espace d’adressage SIP partagé dans votre client Office 365, établissez une session PowerShell distante avec Skype entreprise Online, puis exécutez l’applet de commande suivante :
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit rester « true » jusqu’à ce que le déplacement vers Online soit définitif et qu’aucun utilisateur ne reste en local. 
  
Pour établir une session PowerShell distante avec teams ou Skype entreprise Online, vous devez d’abord installer le module du connecteur Skype entreprise Online pour Windows PowerShell, que vous pouvez obtenir [ici](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Pour plus d’informations sur l’établissement d’une session PowerShell à distance avec Skype entreprise Online et sur l’utilisation du module connecteur Skype entreprise Online, consultez la rubrique [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Voir aussi

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

