---
title: Configuration d’un environnement hybride dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé : Configurer Skype pour 2015 de serveur d’entreprise dans un environnement hybride.'
ms.openlocfilehash: e31338647338854b260c9f8935cac4dde69df490
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a>Configuration d’un environnement hybride dans Skype Entreprise Server 2015
 
**Résumé :** Configurer Skype pour 2015 de serveur d’entreprise dans un environnement hybride.
  
Dans une configuration hybride, certains de vos utilisateurs sont hébergées sur une installation sur site de Skype pour Business Server 2015 tandis que les autres utilisateurs sont hébergés sur la version Office 365 de Skype pour Business Server. Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez d’abord configurer votre installation sur site de Skype pour 2015 de serveur d’entreprise faire confiance au serveur de l’autorisation d’Office 365. La première étape de ce processus peut effectuée en exécutant la suivante Skype pour script de Business Server Management Shell :
  
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

Une fois le script terminé, vous devez ensuite configurer une relation d’approbation entre Skype pour Business Server 2015 et le serveur d’autorisation et une deuxième relation d’approbation entre Exchange 2013 et le serveur d’autorisation. Vous ne pouvez le faire qu’avec des applets de commande Microsoft Online Services.
  
> [!NOTE]
> Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous devrez effectuer deux opérations avant de poursuivre. Tout d’abord, téléchargez et installez la version 64 bits de l’Assistant de connexion Microsoft Online Services. Une fois l’installation terminée, téléchargez et installez la version 64 bits du Module Microsoft Online Services pour pour Windows PowerShell. Vous trouverez des informations détaillées sur l’installation et l’utilisation du Module de Microsoft Online Services sur le site web Office 365. Ces instructions vous indiquera également comment configurer l’ouverture de session unique, fédération et la synchronisation entre Office 365 et Active Directory. 
  
Si vous n’avez pas installé ces applets de commande, votre script échouera, car l’applet de commande Get-CsTenant ne sera pas disponible.
  
Une fois que vous avez configuré Office 365, et après avoir créé Office 365 les identités de service pour Skype pour Business Server 2015 et Exchange 2013, vous devez alors enregistrer vos informations d’identification avec ces entités de service. Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER. Ce certificat est appliqué aux entités de service Office 365.
  
Lorsque vous avez obtenu le certificat X.509, démarrer le Module de Microsoft Online Services (cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **de Microsoft Online Services**, puis cliquez sur **Microsoft Online Services Module pour Windows PowerShell**). Une fois le Module de Services s’ouvre, tapez la commande suivante pour importer le module Microsoft en ligne Windows PowerShell contenant les applets de commande qui peut être utilisé pour gérer les identités de service :
  
```
Import-Module MSOnlineExtended
```

Lorsque le module a été importé, tapez la commande suivante et appuyez sur ENTRÉE pour vous connecter à Office 365 :
  
```
Connect-MsolService
```

Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez votre nom d’utilisateur Office 365 et d’un mot de passe dans la boîte de dialogue, puis cliquez sur OK.
  
Dès que vous êtes connecté à Office 365, vous pouvez ensuite exécuter la commande suivante afin de retourner des informations sur les entités de votre service :
  
```
Get-MsolServicePrincipal
```

Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :
  
```
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
```

L’étape suivante consiste à importer, encoder et affecter le certificat X.509. Pour importer et encoder le certificat, utilisez les commandes suivantes de Windows PowerShell, en veillant à spécifier le chemin d’accès complet à votre. Fichier de région d’exécution limitée lorsque vous appelez la méthode d’importation :
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Une fois que le certificat a été importé et encodé, vous pouvez ensuite affecter le certificat pour vos entités de service d’Office 365. Pour ce faire, utilisez d’abord la Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour le Skype pour Business Server et les noms principaux de service Microsoft Exchange ; la valeur de la propriété AppPrincipalId servira à identifier l’entité de service attribuée le certificat. Avec le AppPrincipalId propriété pour Skype pour Business Server 2015 en cours, utilisez la commande suivante pour attribuer le certificat à la version de Office 365 de Skype pour Business Server :
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Vous devez puis répétez la commande, à ce moment à l’aide de la valeur de la propriété AppPrincipalId pour Exchange 2013.
  
Si vous avez besoin de supprimer ce certificat ultérieurement, vous pouvez le faire en extrayant la propriété KeyId du certificat au préalable :
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

Cette commande renvoie des données comme les suivantes :
  
```
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
```

Vous pouvez ensuite supprimer le certificat à l’aide d’une commande comme celle-ci :
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

En plus de l’attribution d’un certificat, vous devez également configurer l’entité de Service en ligne Exchange et configurer votre version locale de Skype pour les URL de services Web externes 2015 de serveur d’entreprise sous la forme d’une entité de sécurité du service Office 365. À cet effet, exécutez les deux commandes suivantes : 
  
Dans l’exemple suivant, lync.contoso.com est l’URL des services Web externe pour le Skype pour un pool de serveurs d’entreprise. Vous devez répéter ces étapes pour ajouter toutes les URL de services Web externes dans le déploiement.
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true

$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```