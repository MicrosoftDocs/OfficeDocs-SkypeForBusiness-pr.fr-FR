---
title: Configurer l’authentification de serveur à serveur pour un environnement Skype Entreprise Server hybride
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé : Configurez l’authentification de serveur à serveur pour un environnement Skype Entreprise Server hybride.'
ms.openlocfilehash: 617c388dc4c4120beb457e4e2c90246e06c76d6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830928"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurez l’authentification de serveur à serveur pour un environnement Skype Entreprise Server hybride.

**Résumé :** Configurez l’authentification de serveur à serveur pour Skype Entreprise Server environnement hybride.

Dans une configuration hybride, certains de vos utilisateurs sont homed sur une installation sur site de Skype Entreprise Server tandis que d’autres utilisateurs sont homed sur la version Microsoft 365 ou Office 365 de Skype Entreprise Server. Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez d’abord configurer votre installation sur site de Skype Entreprise Server pour faire confiance au serveur d’autorisation. L’étape initiale de ce processus peut être effectuée en exécutant le script Skype Entreprise Server Management Shell suivant :

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation ; en fait, le nom de domaine est presque toujours identique à l’ID de client. C’est pourquoi la première ligne du script est utilisée pour retourner la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Pour exécuter ce script, vous devez avoir installé Skype Entreprise module PowerShell en ligne et vous connecter à votre client avec ce module. Si vous n’avez pas installé ces cmdlets, votre script échouera, car la cmdlet Get-CsTenant ne sera pas disponible. Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype Entreprise Server et le serveur d’autorisation, et une seconde relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation. Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.

> [!NOTE]
> Si vous n’avez pas installé les cmdlets Microsoft Online Services, vous devrez l’installer à partir du référentiel PowerShell avec l’cmdlet. `install-module MSOnline` Des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sont disponibles sur Microsoft 365 site web. Ces instructions vous indiquent également comment configurer l’personnalisation, la fédération et la synchronisation entre Microsoft 365 ou Office 365 et Active Directory. 



Après avoir configuré Microsoft 365 ou Office 365 et créé des principaux de service Microsoft 365 ou Office 365 pour Skype Entreprise Server et Exchange 2013, vous devez inscrire vos informations d’identification auprès de ces principaux de service. Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré en tant que . Fichier CER. Ce certificat sera ensuite appliqué aux principaux Microsoft 365 ou Office 365 service.

Lorsque vous avez obtenu le certificat X.509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les cmdlets qui peuvent être utilisées pour gérer les principaux de service :

```PowerShell
Import-Module MSOnline
```

Une fois le module importé, tapez la commande suivante, puis appuyez sur Entrée :

```PowerShell
Connect-MsolService
```

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez votre Microsoft 365 ou Office 365 nom d’utilisateur et mot de passe dans la boîte de dialogue, puis cliquez sur OK.

Dès que vous êtes connecté à Microsoft 365 ou Office 365, vous pouvez exécuter la commande suivante pour retourner des informations sur vos principaux de service :

```PowerShell
Get-MsolServicePrincipal
```

Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

L’étape suivante consiste à importer, encoder et assigner le certificat X.509. Pour importer et encoder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet du fichier à votre . Fichier CER lorsque vous appelez la méthode Import :

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Une fois le certificat importé et codé, vous pouvez l’affecter à vos principaux de service Microsoft 365 ou Office 365 service. Pour ce faire, utilisez d’abord le Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour les principaux de service Skype Entreprise Server et Microsoft Exchange . la valeur de la propriété AppPrincipalId sera utilisée pour identifier le principal de service affecté au certificat. Avec la valeur de propriété AppPrincipalId Skype Entreprise Server en main, utilisez la commande suivante pour affecter le certificat à la version Skype Entreprise Online :

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Vous devez ensuite répéter la commande, cette fois à l’aide de la valeur de propriété AppPrincipalId Exchange 2013.

Si vous devez par la suite supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId du certificat :

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Cette commande retourne des données comme les suivantes :

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Vous pouvez ensuite supprimer le certificat à l’aide d’une commande similaire à celle-ci :

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Outre l’affectation d’un certificat, vous devez également configurer le principal de service Exchange Online et configurer votre version sur site des URL des services Web externes Skype Entreprise Server en tant que principal de service Microsoft 365 ou Office 365. Pour ce faire, vous pouvez exécuter les deux commandes suivantes. 

Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes du pool Skype Entreprise Server externe. Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes dans le déploiement.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
