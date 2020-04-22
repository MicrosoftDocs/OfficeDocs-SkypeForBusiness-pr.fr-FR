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
ms.openlocfilehash: 191d5d2f391df73401ff27e8c71a60624e74296c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780733"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="ea7dd-103">Configurez l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="ea7dd-104">**Résumé :** Configurez l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="ea7dd-105">Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype entreprise Server alors que d’autres utilisateurs sont hébergés sur la version Office 365 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="ea7dd-106">Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez d’abord configurer votre installation locale de Skype entreprise Server de sorte qu’elle approuve le serveur d’autorisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="ea7dd-107">L’étape initiale de ce processus peut être effectuée en exécutant le script Skype entreprise Server Management Shell suivant :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="ea7dd-p102">N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation ; en fait, le nom de domaine est presque toujours identique à l’ID de client. C’est pourquoi la première ligne du script est utilisée pour retourner la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="ea7dd-110">Pour exécuter ce script, vous devez avoir installé le module Skype entreprise Online PowerShell et vous connecter à votre client à l’aide de ce module.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="ea7dd-111">Si vous n’avez pas installé ces applets de commande, votre script échoue car la cmdlet Get-CsTenant n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="ea7dd-112">Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype entreprise Server et le serveur d’autorisation, ainsi qu’une seconde relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="ea7dd-113">Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="ea7dd-114">Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous devrez l’installer à partir du référentiel PowerShell avec l’applet `install-module MSOnline`de commande.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="ea7dd-115">Des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sont disponibles sur le site web d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="ea7dd-116">Ces instructions vous indiquent également comment configurer l’authentification unique, la fédération et la synchronisation entre Office 365 et Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="ea7dd-117">Une fois que vous avez configuré Office 365 et après avoir créé les principaux de service Office 365 pour Skype entreprise Server et Exchange 2013, vous devrez enregistrer vos informations d’identification avec ces principaux de service.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="ea7dd-118">Pour ce faire, vous devez d’abord obtenir un certificat X. 509 en base64 enregistré en tant que. Fichier CER.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="ea7dd-119">Ce certificat est ensuite appliqué aux principaux du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="ea7dd-120">Une fois que vous avez obtenu le certificat X. 509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les applets de commande pouvant être utilisées pour gérer les principaux de service :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="ea7dd-121">Lorsque le module a été importé, tapez la commande suivante, puis appuyez sur Entrée afin de vous connecter à Office 365 :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="ea7dd-122">Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="ea7dd-123">Entrez votre nom d’utilisateur et votre mot de passe Microsoft 365 ou Office 365 dans la boîte de dialogue, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="ea7dd-124">Dès que vous êtes connecté à Office 365, vous pouvez exécuter la commande suivante afin de retourner des informations sur vos principaux de service :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="ea7dd-125">Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="ea7dd-126">L’étape suivante consiste à importer, encoder et assigner le certificat X.509.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="ea7dd-127">Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier. Fichier CER lorsque vous appelez la méthode Import :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="ea7dd-128">Une fois que le certificat a été importé et encodé, vous pouvez l’assigner à vos principaux du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="ea7dd-129">Pour ce faire, utilisez d’abord la MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour les principaux de service Skype entreprise Server et Microsoft Exchange ; la valeur de la propriété AppPrincipalId sera utilisée pour identifier le principal de service auquel le certificat est affecté.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="ea7dd-130">Une fois la valeur de la propriété AppPrincipalId de Skype entreprise Server en main, utilisez la commande suivante pour attribuer le certificat à la version Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="ea7dd-131">Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="ea7dd-132">Si, par la suite, vous devez supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId pour le certificat :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ea7dd-133">Cette commande retourne des données comme les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="ea7dd-134">Vous pouvez ensuite supprimer le certificat à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ea7dd-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="ea7dd-135">Outre l’affectation d’un certificat, vous devez également configurer le principal du service Exchange Online et configurer votre version locale des URL des services Web externes de Skype entreprise Server en tant que principal du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="ea7dd-136">Cette opération peut être effectuée en exécutant les deux commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="ea7dd-137">Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes pour le pool Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="ea7dd-138">Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ea7dd-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
