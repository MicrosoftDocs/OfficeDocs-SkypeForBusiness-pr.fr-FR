---
title: Configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé: configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.'
ms.openlocfilehash: d0c82d39c5232ccc3d425bad9533bf23b67dc8a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285532"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.

**Résumé:** Configurer l’authentification de serveur à serveur pour l’environnement hybride Skype entreprise Server.

Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype entreprise Server lorsque d’autres utilisateurs sont à la maison dans la version 365 d’Office de Skype entreprise Server. Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez commencer par configurer votre installation locale de Skype entreprise Server afin de faire confiance au serveur d’autorisation d’Office 365. La première étape de ce processus peut être effectuée en exécutant le script Skype entreprise Server Management Shell suivant:

```
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

N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation. En fait, le nom de domaine est presque toujours identique à l’ID de client, donc la première ligne du script est utilisée pour renvoyer la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

Pour exécuter ce script, vous devez avoir installé le module PowerShell de Skype entreprise Online et vous connecter à votre client avec ce module. Si vous n’avez pas installé ces applets de commande, votre script échouera, car l’applet de commande Get-CsTenant ne sera pas disponible. Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype entreprise Server et le serveur d’autorisation, et une deuxième relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation. Vous ne pouvez le faire qu’avec des applets de commande Microsoft Online Services.

> [!NOTE]
> Si vous n’avez pas installé les applets de connexion Microsoft Online Services, vous devez l’installer à partir du référentiel PowerShell avec cmdlet install-module MSONLINE,. Pour plus d’informations sur l’installation et l’utilisation du module Microsoft Online Services, consultez le site Web 365. Ces instructions vous indiquent également comment configurer l’authentification unique, la Fédération et la synchronisation entre Office 365 et Active Directory. 



Une fois que vous avez configuré Office 365 et que vous avez créé des principes de service Office 365 pour Skype entreprise Server et Exchange 2013, vous devez enregistrer vos informations d’identification avec ces principaux de service. Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER. Ce certificat est alors appliqué aux principaux services d’Office 365.

Lorsque vous avez obtenu le certificat X. 509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les applets de certification qui peuvent être utilisées pour gérer les principaux de service:

```
Import-Module MSOnline
```

Lorsque le module a été importé, tapez la commande suivante et appuyez sur entrée pour vous connecter à Office 365:

```
Connect-MsolService
```

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez votre nom d’utilisateur et votre mot de passe Office 365 dans la boîte de dialogue, puis cliquez sur OK.

Dès que vous êtes connecté à Office 365, vous pouvez exécuter la commande suivante afin de renvoyer des informations sur vos principaux de service:

```
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

L’étape suivante consiste à importer, encoder et affecter le certificat X.509. Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier. Fichier CER lorsque vous appelez la méthode d’importation:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Une fois le certificat importé et encodé, vous pouvez attribuer le certificat à vos principaux services Office 365. Pour ce faire, vous devez commencer par utiliser Get-MsolServicePrincipal pour récupérer la valeur de la propriété paramètre appprincipalid que pour le serveur Skype entreprise et les principaux de service Microsoft Exchange. la valeur de la propriété paramètre appprincipalid que est utilisée pour identifier le principal de service affecté au certificat. La valeur de la propriété paramètre appprincipalid que de Skype entreprise Server étant disponible, utilisez la commande suivante pour affecter le certificat à la version de Skype entreprise Online:

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Vous devez alors répéter la commande à l’aide de la valeur de propriété paramètre appprincipalid que pour Exchange 2013.

Par exemple, si vous devez supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId du certificat:

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Cette commande renvoie des données comme les suivantes :

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Vous pouvez ensuite supprimer le certificat à l’aide d’une commande comme celle-ci :

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Outre l’attribution d’un certificat, vous devez également configurer le principal du service Exchange Online et configurer votre version locale des URL de services Web externes de Skype entreprise Server en tant que principal de service Office 365. À cet effet, exécutez les deux commandes suivantes : 

Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes du pool de serveurs Skype entreprise. Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes du déploiement.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
