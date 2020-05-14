---
title: Configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé : configurez l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.'
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221678"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurez l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.

**Résumé :** Configurez l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.

Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype entreprise Server alors que d’autres utilisateurs sont hébergés sur la version Microsoft 365 ou Office 365 de Skype entreprise Server. Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez d’abord configurer votre installation locale de Skype entreprise Server de sorte qu’elle approuve le serveur d’autorisation. L’étape initiale de ce processus peut être effectuée en exécutant le script Skype entreprise Server Management Shell suivant :

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

Pour exécuter ce script, vous devez avoir installé le module Skype entreprise Online PowerShell et vous connecter à votre client à l’aide de ce module. Si vous n’avez pas installé ces applets de commande, votre script échoue car la cmdlet Get-CsTenant n’est pas disponible. Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype entreprise Server et le serveur d’autorisation, ainsi qu’une seconde relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation. Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.

> [!NOTE]
> Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous devrez l’installer à partir du référentiel PowerShell avec l’applet de commande `install-module MSOnline` . Vous trouverez des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sur le site Web Microsoft 365. Ces instructions vous indiquent également comment configurer l’authentification unique, la Fédération et la synchronisation entre Microsoft 365 ou Office 365 et Active Directory. 



Une fois que vous avez configuré Microsoft 365 ou Office 365, et après avoir créé les principaux de service Microsoft 365 ou Office 365 pour Skype entreprise Server et Exchange 2013, vous devrez enregistrer vos informations d’identification avec ces principaux de service. Pour ce faire, vous devez d’abord obtenir un certificat X. 509 en base64 enregistré en tant que. Fichier CER. Ce certificat est ensuite appliqué aux principaux du service Microsoft 365 ou Office 365.

Une fois que vous avez obtenu le certificat X. 509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les applets de commande pouvant être utilisées pour gérer les principaux de service :

```PowerShell
Import-Module MSOnline
```

Une fois le module importé, tapez la commande suivante, puis appuyez sur entrée :

```PowerShell
Connect-MsolService
```

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez votre nom d’utilisateur et votre mot de passe Microsoft 365 ou Office 365 dans la boîte de dialogue, puis cliquez sur OK.

Dès que vous êtes connecté à Microsoft 365 ou Office 365, vous pouvez exécuter la commande suivante afin de retourner des informations sur vos principaux de service :

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

L’étape suivante consiste à importer, encoder et assigner le certificat X.509. Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier. Fichier CER lorsque vous appelez la méthode Import :

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Une fois que le certificat a été importé et codé, vous pouvez ensuite attribuer le certificat à vos principaux de service Microsoft 365 ou Office 365. Pour ce faire, utilisez d’abord la MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour les principaux de service Skype entreprise Server et Microsoft Exchange ; la valeur de la propriété AppPrincipalId sera utilisée pour identifier le principal de service auquel le certificat est affecté. Une fois la valeur de la propriété AppPrincipalId de Skype entreprise Server en main, utilisez la commande suivante pour attribuer le certificat à la version Skype entreprise Online :

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId pour Exchange 2013.

Si, par la suite, vous devez supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId pour le certificat :

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

Outre l’affectation d’un certificat, vous devez également configurer le principal du service Exchange Online et configurer votre version locale des URL de services Web externes de Skype entreprise Server en tant que principal de service Microsoft 365 ou Office 365. Cette opération peut être effectuée en exécutant les deux commandes suivantes. 

Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes pour le pool Skype entreprise Server. Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes dans le déploiement.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
