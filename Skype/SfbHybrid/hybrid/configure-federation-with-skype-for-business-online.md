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
description: 'Résumé : Découvrez comment configurer l’interopérabilité entre votre déploiement local et Skype Entreprise Online.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569216"
---
# <a name="configure-skype-for-business-hybrid"></a>Configurer Skype Entreprise hybride

Pour configurer Skype Entreprise hybride, vous devez :

- Configurez votre service Edge local pour la fédération avec [Microsoft 365 ou Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- Configurez votre environnement local pour qu’il utilise [Microsoft 365 ou Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)et activez l’espace d’adressare SIP partagé.
- [Activez l’espace d’adressare SIP partagé dans votre organisation Microsoft 365 ou Office 365.](#enable-shared-sip-address-space-in-your-organization)

Notez que si vous avez Exchange en local, vous pouvez configurer OAuth entre vos environnements Exchange local et Skype Entreprise Online. Pour plus d’informations, voir Gérer l’authentification de serveur à serveur [dans Skype](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) Entreprise Server et planifier l’intégration de Skype Entreprise [et d’Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Configurer votre service Edge local pour la fédération avec Microsoft 365 ou Office 365

La fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs microsoft 365 ou Office 365 de votre organisation. Pour configurer la fédération, exécutez l’cmdlet suivante dans Skype Entreprise Server Management Shell :
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Si la valeur « -EnablePartnerDiscovery » est définie sur $True, Skype Entreprise Server utilise les enregistrements DNS pour essayer de découvrir les domaines partenaires non répertoriés dans la liste AllowedDomains. Si la valeur est définie sur $False, Skype Entreprise Server se fédérera uniquement avec les domaines trouvés dans la liste AllowedDomains. Ce paramètre est requis si vous utilisez le routage de service DNS.

> [!NOTE]
> Pour plus d’informations sur l’activation de la fédération entre les utilisateurs de votre déploiement Skype Entreprise local et les utilisateurs d’une organisation Skype Entreprise Online, voir Configuration de la prise en charge de la fédération pour un client Skype Entreprise Online dans [Skype Entreprise Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Configurer votre environnement local pour activer l’espace d’adressare SIP partagé avec Microsoft 365 ou Office 365

Vous devez également configurer votre environnement local pour qu’il utilise Microsoft 365 ou Office 365 et activer l’espace d’adressare SIP partagé. Cela signifie que Microsoft 365 ou Office 365 peut potentiellement héberger des comptes d’utilisateur pour le même ensemble de domaines SIP que votre environnement local, et que les messages peuvent être acheminés entre les utilisateurs hébergés en local et en ligne.  Pour ce faire, configurez un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com comme décrit ci-dessous.

Tout d’abord, vérifiez si vous avez déjà un fournisseur d’hébergement avec ProxyFqdn=sipfed.online.lync.com. S’il en existe un, supprimez-le à l’aide de la commande suivante :

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Ensuite, créez un fournisseur d’hébergement, New-CsHostingProvider cmdlet comme suit : 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Activer l’espace d’adressa ment SIP partagé dans votre organisation
  
Outre les changements que vous avez apportés dans votre déploiement local, vous devez apporter la modification correspondante dans votre organisation Microsoft 365 ou Office 365 pour activer l’espace d’adressare SIP partagé avec votre déploiement local.  

Pour activer l’espace d’adressale SIP partagé dans votre organisation, établissez une session PowerShell distante avec Skype Entreprise Online, puis exécutez l’cmdlet suivante :
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> L’attribut SharedSipAddressSpace doit rester « True » jusqu’à ce que le passage en ligne soit final et qu’aucun utilisateur ne reste en local. 
  
Pour établir une session PowerShell distante avec Teams ou Skype Entreprise Online, vous devez d’abord installer le [module PowerShell Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
  
Après avoir installé le module, vous pouvez établir une session à distance avec les cmdlets suivantes :
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Pour plus d’informations sur l’établissement d’une session PowerShell à distance avec Skype Entreprise Online et sur l’utilisation du module Connecteur Skype Entreprise Online, voir Configurer votre ordinateur pour [Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>Voir aussi

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
