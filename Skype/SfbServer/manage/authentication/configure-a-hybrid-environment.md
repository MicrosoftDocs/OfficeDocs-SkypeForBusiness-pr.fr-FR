---
title: Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server
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
description: 'Résumé : Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server.'
ms.openlocfilehash: 889e62cf2c462dc9f1cc9ab4b96ae73f99bc9c6e
ms.sourcegitcommit: 3d1556113ce4050b79ee34c138482b34273b8c1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20178814"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="06415-103">Configurer l’authentification de serveur à serveur pour un Skype pour un environnement hybride de Business Server.</span><span class="sxs-lookup"><span data-stu-id="06415-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>
 
<span data-ttu-id="06415-104">**Résumé :** Configurer l’authentification de serveur à serveur pour Skype pour un environnement hybride de Business Server.</span><span class="sxs-lookup"><span data-stu-id="06415-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>
  
<span data-ttu-id="06415-105">Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype pour Business Server 2015 tandis que les autres utilisateurs sont hébergés sur la version Office 365 de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="06415-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server 2015 while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="06415-106">Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez configurer votre installation locale de Skype pour Business Server 2015 approuver le serveur d’autorisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server 2015 to trust the Office 365 authorization server.</span></span> <span data-ttu-id="06415-107">La première étape de ce processus peut être exécutée en exécutant la Skype pour le script Business Server Management Shell suivante :</span><span class="sxs-lookup"><span data-stu-id="06415-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>
  
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

<span data-ttu-id="06415-p102">N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation. En fait, le nom de domaine est presque toujours identique à l’ID de client, donc la première ligne du script est utilisée pour renvoyer la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :</span><span class="sxs-lookup"><span data-stu-id="06415-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="06415-110">Une fois le script terminé, vous devez ensuite configurer une relation d’approbation entre Skype pour Business Server 2015 et le serveur d’autorisation et une deuxième relation d’approbation entre Exchange 2013 et le serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="06415-110">After the script completes, you must then configure a trust relationship between Skype for Business Server 2015 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="06415-111">Vous ne pouvez le faire qu’avec des applets de commande Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="06415-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06415-112">Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous devrez effectuer deux opérations avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="06415-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="06415-113">Tout d’abord, téléchargez et installez la version 64 bits de l’Assistant de connexion Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="06415-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="06415-114">Une fois l’installation terminée, téléchargez et installez la version 64 bits de la Microsoft Online Services Module pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06415-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="06415-115">Vous trouverez des informations détaillées sur l’installation et à l’aide du Module Microsoft Online Services sur le site web Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="06415-116">Ces instructions vous indiquera également comment configurer l’authentification unique, la fédération et la synchronisation entre Active Directory et Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 
  
<span data-ttu-id="06415-117">Si vous n’avez pas installé ces applets de commande, votre script échouera, car l’applet de commande Get-CsTenant ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="06415-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>
  
<span data-ttu-id="06415-118">Après avoir configuré Office 365 et lorsque vous avez créé pour Skype principaux du service Office 365 pour Business Server 2015 et Exchange 2013, vous devrez ensuite enregistrer vos informations d’identification avec ces entités de service.</span><span class="sxs-lookup"><span data-stu-id="06415-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server 2015 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="06415-119">Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER.</span><span class="sxs-lookup"><span data-stu-id="06415-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="06415-120">Ce certificat est appliqué aux entités de service Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-120">This certificate will then be applied to the Office 365 service principals.</span></span>
  
<span data-ttu-id="06415-121">Lorsque vous avez obtenu le certificat X.509, démarrez le Module Microsoft Online Services (cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Online Services**, puis cliquez sur **Microsoft Online Services Module pour Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="06415-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="06415-122">Une fois le Module Services s’ouvre, tapez la commande suivante pour importer le module Microsoft Online Windows PowerShell contenant les applets de commande qui peuvent être utilisées pour gérer les principaux du service :</span><span class="sxs-lookup"><span data-stu-id="06415-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>
  
```
Import-Module MSOnlineExtended
```

<span data-ttu-id="06415-123">Lorsque le module a été importé, tapez la commande suivante et appuyez sur ENTRÉE afin de se connecter à Office 365 :</span><span class="sxs-lookup"><span data-stu-id="06415-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>
  
```
Connect-MsolService
```

<span data-ttu-id="06415-124">Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche.</span><span class="sxs-lookup"><span data-stu-id="06415-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="06415-125">Entrez votre nom d’utilisateur Office 365 et le mot de passe dans la boîte de dialogue, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="06415-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>
  
<span data-ttu-id="06415-126">Dès que vous êtes connecté à Office 365, vous pouvez ensuite exécuter la commande suivante afin de retourner des informations sur vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="06415-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>
  
```
Get-MsolServicePrincipal
```

<span data-ttu-id="06415-127">Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="06415-127">You should get back information similar to this for all your service principals:</span></span>
  
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

<span data-ttu-id="06415-128">L’étape suivante consiste à importer, encoder et affecter le certificat X.509.</span><span class="sxs-lookup"><span data-stu-id="06415-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="06415-129">Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier votre. Fichier CER lorsque vous appelez la méthode d’importation :</span><span class="sxs-lookup"><span data-stu-id="06415-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="06415-130">Une fois que le certificat a été importé et encodé, vous pouvez ensuite affecter le certificat à vos principaux du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="06415-131">Pour ce faire, utilisez d’abord la Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour le Skype pour Business Server et les principaux de service Microsoft Exchange ; la valeur de la propriété AppPrincipalId permet d’identifier le principal de service affecté le certificat.</span><span class="sxs-lookup"><span data-stu-id="06415-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="06415-132">Avec la AppPrincipalId propriété valeur Skype pour Business Server 2015 en cours, utilisez la commande suivante pour assigner le certificat vers la version d’Office 365 de Skype pour Business Server :</span><span class="sxs-lookup"><span data-stu-id="06415-132">With the AppPrincipalId property value for Skype for Business Server 2015 in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="06415-133">Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="06415-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>
  
<span data-ttu-id="06415-134">Si vous avez besoin de supprimer ce certificat ultérieurement, vous pouvez le faire en extrayant la propriété KeyId du certificat au préalable :</span><span class="sxs-lookup"><span data-stu-id="06415-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="06415-135">Cette commande renvoie des données comme les suivantes :</span><span class="sxs-lookup"><span data-stu-id="06415-135">That command will return data like this one:</span></span>
  
<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="06415-136">Vous pouvez ensuite supprimer le certificat à l’aide d’une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="06415-136">You can then delete the certificate by using a command similar to this:</span></span>
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="06415-137">Outre l’attribution d’un certificat, vous devez également configurer le Principal de Service Exchange Online et configurer votre version locale de Skype pour Business Server 2015 URL des services Web externes comme une entité de sécurité du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="06415-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server 2015 external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="06415-138">À cet effet, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="06415-138">That can be done by carrying out the following two commands.</span></span> 
  
<span data-ttu-id="06415-139">Dans l’exemple suivant, lync.contoso.com est l’URL des services Web externe pour le Skype pour le pool de serveurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="06415-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="06415-140">Vous devez répéter ces étapes pour ajouter toutes les URL de services Web externes dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="06415-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```