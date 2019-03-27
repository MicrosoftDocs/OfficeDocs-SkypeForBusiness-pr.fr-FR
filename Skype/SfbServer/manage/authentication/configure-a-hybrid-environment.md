---
title: Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé : Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server.'
ms.openlocfilehash: d8ba920d516368d1931097e5e31b738a0d271bcf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893611"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server.

**Résumé :** Configurer l’authentification de serveur à serveur pour Skype pour un environnement hybride de Business Server.

Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype pour Business Server alors que les autres utilisateurs sont hébergés sur la version Office 365 de Skype pour Business Server. Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez configurer votre installation locale de Skype pour Business Server pour qu’il approuve le serveur d’autorisation Office 365. La première étape de ce processus peut être exécutée en exécutant la Skype pour le script Business Server Management Shell suivante :

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

Pour exécuter ce script, vous devez avoir installé Skype pour le module Powershell Online Business et se connecter à votre client avec ce module. Si vous n’avez pas installé ces applets de commande, votre script échouera, car l’applet de commande Get-CsTenant ne sera pas disponible. Une fois le script terminé, vous devez ensuite configurer une relation d’approbation entre Skype pour Business Server et le serveur d’autorisation et une deuxième relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation. Vous ne pouvez le faire qu’avec des applets de commande Microsoft Online Services.

> [!NOTE]
> Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous devrez l’installer à partir du référentiel de powershell avec l’applet de commande install-module MSOnline. Vous trouverez des informations détaillées sur l’installation et à l’aide du Module Microsoft Online Services sur le site web Office 365. Ces instructions vous indiquera également comment configurer l’authentification unique, la fédération et la synchronisation entre Active Directory et Office 365. 



Après avoir configuré Office 365 et lorsque vous avez créé pour Skype principaux du service Office 365 pour Business Server et Exchange 2013, vous devrez ensuite enregistrer vos informations d’identification avec ces entités de service. Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER. Ce certificat est appliqué aux entités de service Office 365.

Lorsque vous avez obtenu le certificat X.509, ouvrez la console Powershell et importer le module Microsoft Online Windows PowerShell contenant les applets de commande qui peuvent être utilisées pour gérer les principaux du service :

```
Import-Module MSOnline
```

Lorsque le module a été importé, tapez la commande suivante et appuyez sur ENTRÉE afin de se connecter à Office 365 :

```
Connect-MsolService
```

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez votre nom d’utilisateur Office 365 et le mot de passe dans la boîte de dialogue, puis cliquez sur OK.

Dès que vous êtes connecté à Office 365, vous pouvez ensuite exécuter la commande suivante afin de retourner des informations sur vos principaux du service :

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

L’étape suivante consiste à importer, encoder et affecter le certificat X.509. Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier votre. Fichier CER lorsque vous appelez la méthode d’importation :

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Une fois que le certificat a été importé et encodé, vous pouvez ensuite affecter le certificat à vos principaux du service Office 365. Pour ce faire, utilisez d’abord la Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour le Skype pour Business Server et les principaux de service Microsoft Exchange ; la valeur de la propriété AppPrincipalId permet d’identifier le principal de service affecté le certificat. Avec la AppPrincipalId propriété valeur Skype pour Business Server en cours, utilisez la commande suivante pour attribuer le certificat à Skype pour Business version en ligne :

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId pour Exchange 2013.

Si vous devez supprimer ce certificat, par exemple, si elle a expiré, vous pouvez le faire en récupérant l’ID de la clé pour le certificat :

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

Outre l’attribution d’un certificat, vous devez également configurer le Principal de Service Exchange Online et configurer votre version locale de Skype pour les URL de services Web externes Business Server comme un principal de service Office 365. À cet effet, exécutez les deux commandes suivantes : 

Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externe pour le Skype pour le pool de serveurs d’entreprise. Vous devez répéter ces étapes pour ajouter toutes les URL de services Web externes dans le déploiement.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
