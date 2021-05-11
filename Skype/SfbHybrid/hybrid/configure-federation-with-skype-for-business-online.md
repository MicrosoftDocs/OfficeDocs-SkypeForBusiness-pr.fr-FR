---
title: Configurer Skype Entreprise hybride
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
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
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305968"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurer Skype Entreprise hybride

Pour configurer Skype Entreprise hybride, vous devez :

- [Configurez votre service Edge local](#configure-your-on-premises-edge-service-to-federate-with-teams)pour la fédération avec Teams .
- [Configurez votre environnement local pour qu’il Teams et activez l’espace d’adressan SIP partagé.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [Activez l’espace d’adressa ment SIP](#enable-shared-sip-address-space-in-your-organization)partagé dans Teams organisation.

Si vous avez Exchange local, vous pouvez configurer OAuth entre vos environnements Exchange local et Skype Entreprise Online. Pour plus d’informations, voir Gérer l’authentification de serveur à serveur dans [Skype Entreprise Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) et planifier l’intégration Skype Entreprise [et Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Configurer votre service Edge local pour la fédération avec Teams

La fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs Teams et Skype Entreprise Online de votre organisation. Pour configurer la fédération, exécutez la cmdlet suivante dans l’Skype Entreprise Server Management Shell :
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si la valeur « -EnablePartnerDiscovery » est définie sur $True, Skype Entreprise Server utilise les enregistrements DNS pour essayer de découvrir les domaines partenaires non répertoriés dans la liste AllowedDomains. Si la valeur est définie sur $False , Skype Entreprise Server fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains. Ce paramètre est requis si vous utilisez le routage de service DNS.

> [!NOTE]
> Pour plus d’informations sur l’activation de la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’une organisation Microsoft 365, voir Configuration de la prise en charge de la fédération pour un client Microsoft 365 dans [Skype Entreprise Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Configurez votre environnement local pour activer l’espace d’adressan SIP partagé avec Teams

Vous devez également configurer votre environnement local pour qu’il soit Teams et activer l’espace d’adressan SIP partagé. Cette configuration signifie que Teams peut potentiellement héberger des comptes d’utilisateur pour le même ensemble de domaines SIP que votre environnement local, et que les messages peuvent être acheminés entre les utilisateurs hébergés sur site et en ligne. Vous configurez un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme décrit ci-dessous.

Tout d’abord, vérifiez si vous avez déjà un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com. S’il en existe un, supprimez-le à l’aide de la commande suivante dans Skype Entreprise Server Management Shell :

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Créez ensuite un fournisseur d’hébergement à l’aide New-CsHostingProvider cmdlet comme suit : 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Activer l’espace d’adressa ment SIP partagé dans votre organisation
  
En plus de la modification que vous avez faite dans votre déploiement local, vous devez apporter la modification correspondante dans votre organisation Teams pour activer l’espace d’adressan SIP partagé avec votre déploiement local.  

Pour activer l’espace d’adressale SIP partagé dans votre organisation, établissez une session PowerShell distante avec Teams, puis exécutez l’cmdlet suivante :
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit rester « True » jusqu’à ce que le passage en ligne soit final et qu’aucun utilisateur ne reste en local. 
  
Pour établir une session PowerShell distante avec Teams (ou Skype Entreprise Online), vous devez d’abord installer Teams [module PowerShell.](/microsoftteams/teams-powershell-install) Le Teams Module PowerShell remplace le module Skype Busines Online Connector, qui a été retiré.
  
Après avoir installé le module, vous pouvez établir une session à distance avec les cmdlets suivantes :
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Teams et sur l’utilisation du module Teams PowerShell, voir Configurer votre ordinateur pour [Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  


## <a name="see-also"></a>Voir aussi

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
