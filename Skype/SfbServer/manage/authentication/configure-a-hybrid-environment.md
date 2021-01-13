---
title: Configurer l’authentification de serveur à serveur pour un environnement hybride Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Résumé : Configurez l’authentification de serveur à serveur pour un environnement hybride Skype Entreprise Server.'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828484"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="12a61-103">Configurez l’authentification de serveur à serveur pour un environnement hybride Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12a61-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="12a61-104">**Résumé :** Configurez l’authentification de serveur à serveur pour l’environnement hybride Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12a61-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="12a61-105">Dans une configuration hybride, certains de vos utilisateurs sont homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="12a61-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="12a61-106">Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez d’abord configurer votre installation sur site de Skype Entreprise Server afin d’approbation du serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="12a61-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="12a61-107">L’étape initiale de ce processus peut être effectuée en exécutant le script Skype Entreprise Server Management Shell suivant :</span><span class="sxs-lookup"><span data-stu-id="12a61-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="12a61-p102">N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation ; en fait, le nom de domaine est presque toujours identique à l’ID de client. C’est pourquoi la première ligne du script est utilisée pour retourner la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :</span><span class="sxs-lookup"><span data-stu-id="12a61-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="12a61-110">Pour exécuter ce script, vous devez avoir installé le module PowerShell de Skype Entreprise Online et vous connecter à votre client avec ce module.</span><span class="sxs-lookup"><span data-stu-id="12a61-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="12a61-111">Si vous n’avez pas installé ces cmdlets, votre script échouera, car la cmdlet Get-CsTenant ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="12a61-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="12a61-112">Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype Entreprise Server et le serveur d’autorisation, et une seconde relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="12a61-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="12a61-113">Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="12a61-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="12a61-114">Si vous n’avez pas installé les cmdlets Microsoft Online Services, vous devrez l’installer à partir du référentiel PowerShell avec l’cmdlet. `install-module MSOnline`</span><span class="sxs-lookup"><span data-stu-id="12a61-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="12a61-115">Des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sont disponibles sur le site web Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12a61-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="12a61-116">Ces instructions vous indiquent également comment configurer l’personnalisation, la fédération et la synchronisation entre Microsoft 365 ou Office 365 et Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12a61-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="12a61-117">Après avoir configuré Microsoft 365 ou Office 365 et créé des principaux de service Microsoft 365 ou Office 365 pour Skype Entreprise Server et Exchange 2013, vous devez inscrire vos informations d’identification auprès de ces principaux de service.</span><span class="sxs-lookup"><span data-stu-id="12a61-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="12a61-118">Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré en tant que . Fichier CER.</span><span class="sxs-lookup"><span data-stu-id="12a61-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="12a61-119">Ce certificat sera ensuite appliqué aux principaux de service Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="12a61-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="12a61-120">Lorsque vous avez obtenu le certificat X.509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les cmdlets qui peuvent être utilisées pour gérer les principaux de service :</span><span class="sxs-lookup"><span data-stu-id="12a61-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="12a61-121">Une fois le module importé, tapez la commande suivante, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="12a61-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="12a61-122">Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche.</span><span class="sxs-lookup"><span data-stu-id="12a61-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="12a61-123">Entrez votre nom d’utilisateur et votre mot de passe Microsoft 365 ou Office 365 dans la boîte de dialogue, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="12a61-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="12a61-124">Dès que vous êtes connecté à Microsoft 365 ou Office 365, vous pouvez exécuter la commande suivante pour retourner des informations sur vos principaux de service :</span><span class="sxs-lookup"><span data-stu-id="12a61-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="12a61-125">Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="12a61-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="12a61-126">L’étape suivante consiste à importer, encoder et assigner le certificat X.509.</span><span class="sxs-lookup"><span data-stu-id="12a61-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="12a61-127">Pour importer et encoder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet du fichier à votre . Fichier CER lorsque vous appelez la méthode Import :</span><span class="sxs-lookup"><span data-stu-id="12a61-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="12a61-128">Une fois le certificat importé et codé, vous pouvez l’affecter à vos principaux de service Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="12a61-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="12a61-129">Pour ce faire, utilisez d’abord le Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId pour skype entreprise server et les principaux de service Microsoft Exchange ; la valeur de la propriété AppPrincipalId sera utilisée pour identifier le principal de service affecté au certificat.</span><span class="sxs-lookup"><span data-stu-id="12a61-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="12a61-130">Avec la valeur de la propriété AppPrincipalId pour Skype Entreprise Server, utilisez la commande suivante pour affecter le certificat à la version de Skype Entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="12a61-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="12a61-131">Vous devez ensuite répéter la commande, cette fois à l’aide de la valeur de la propriété AppPrincipalId pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="12a61-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="12a61-132">Si vous devez par la suite supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId du certificat :</span><span class="sxs-lookup"><span data-stu-id="12a61-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="12a61-133">Cette commande retourne des données comme les suivantes :</span><span class="sxs-lookup"><span data-stu-id="12a61-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="12a61-134">Vous pouvez ensuite supprimer le certificat à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="12a61-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="12a61-135">Outre l’affectation d’un certificat, vous devez également configurer le principal de service Exchange Online et configurer votre version sur site des URL de services Web externes Skype Entreprise Server en tant que principal de service Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="12a61-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="12a61-136">Pour ce faire, vous pouvez exécuter les deux commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="12a61-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="12a61-137">Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes pour le pool Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12a61-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="12a61-138">Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="12a61-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
