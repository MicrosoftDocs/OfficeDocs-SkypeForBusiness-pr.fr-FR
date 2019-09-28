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
description: 'Résumé : configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.'
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305770"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="677a0-103">Configurer l’authentification de serveur à serveur pour un environnement hybride Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="677a0-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="677a0-104">**Résumé :** Configurer l’authentification de serveur à serveur pour l’environnement hybride Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="677a0-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="677a0-105">Dans une configuration hybride, certains de vos utilisateurs sont hébergés sur une installation locale de Skype entreprise Server lorsque d’autres utilisateurs sont à la maison dans la version 365 d’Office de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="677a0-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="677a0-106">Pour configurer l’authentification de serveur à serveur dans un environnement hybride, vous devez commencer par configurer votre installation locale de Skype entreprise Server afin de faire confiance au serveur d’autorisation d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="677a0-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="677a0-107">La première étape de ce processus peut être effectuée en exécutant le script Skype entreprise Server Management Shell suivant :</span><span class="sxs-lookup"><span data-stu-id="677a0-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="677a0-p102">N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation. En fait, le nom de domaine est presque toujours identique à l’ID de client, donc la première ligne du script est utilisée pour renvoyer la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :</span><span class="sxs-lookup"><span data-stu-id="677a0-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="677a0-110">Pour exécuter ce script, vous devez avoir installé le module PowerShell de Skype entreprise Online et vous connecter à votre client avec ce module.</span><span class="sxs-lookup"><span data-stu-id="677a0-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="677a0-111">Si vous n’avez pas installé ces applets de commande, votre script échouera, car l’applet de commande Get-CsTenant ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="677a0-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="677a0-112">Une fois le script terminé, vous devez configurer une relation d’approbation entre Skype entreprise Server et le serveur d’autorisation, et une deuxième relation d’approbation entre Exchange 2013/2016 et le serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="677a0-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="677a0-113">Vous ne pouvez le faire qu’avec des applets de commande Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="677a0-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="677a0-114">Si vous n’avez pas installé les applets de service Microsoft Online Services, vous devez l’installer à partir du référentiel PowerShell avec l’applet `install-module MSOnline`de connexion.</span><span class="sxs-lookup"><span data-stu-id="677a0-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="677a0-115">Pour plus d’informations sur l’installation et l’utilisation du module Microsoft Online Services, consultez le site Web 365.</span><span class="sxs-lookup"><span data-stu-id="677a0-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="677a0-116">Ces instructions vous indiquent également comment configurer l’authentification unique, la Fédération et la synchronisation entre Office 365 et Active Directory.</span><span class="sxs-lookup"><span data-stu-id="677a0-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="677a0-117">Une fois que vous avez configuré Office 365 et que vous avez créé des principes de service Office 365 pour Skype entreprise Server et Exchange 2013, vous devez enregistrer vos informations d’identification avec ces principaux de service.</span><span class="sxs-lookup"><span data-stu-id="677a0-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="677a0-118">Pour cela, vous devez d’abord obtenir un certificat base64 X. 509 enregistré en tant que. Fichier CER.</span><span class="sxs-lookup"><span data-stu-id="677a0-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="677a0-119">Ce certificat est alors appliqué aux principaux services d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="677a0-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="677a0-120">Lorsque vous avez obtenu le certificat X. 509, ouvrez la console PowerShell et importez le module Microsoft Online Windows PowerShell contenant les applets de certification qui peuvent être utilisées pour gérer les principaux de service :</span><span class="sxs-lookup"><span data-stu-id="677a0-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="677a0-121">Lorsque le module a été importé, tapez la commande suivante et appuyez sur entrée pour vous connecter à Office 365 :</span><span class="sxs-lookup"><span data-stu-id="677a0-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="677a0-122">Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche.</span><span class="sxs-lookup"><span data-stu-id="677a0-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="677a0-123">Entrez votre nom d’utilisateur et votre mot de passe Office 365 dans la boîte de dialogue, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="677a0-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="677a0-124">Dès que vous êtes connecté à Office 365, vous pouvez exécuter la commande suivante afin de renvoyer des informations sur vos principaux de service :</span><span class="sxs-lookup"><span data-stu-id="677a0-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="677a0-125">Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="677a0-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="677a0-126">L’étape suivante consiste à importer, encoder et affecter le certificat X.509.</span><span class="sxs-lookup"><span data-stu-id="677a0-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="677a0-127">Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier. Fichier CER lorsque vous appelez la méthode d’importation :</span><span class="sxs-lookup"><span data-stu-id="677a0-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="677a0-128">Une fois le certificat importé et encodé, vous pouvez attribuer le certificat à vos principaux services Office 365.</span><span class="sxs-lookup"><span data-stu-id="677a0-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="677a0-129">Pour ce faire, vous devez commencer par utiliser Get-MsolServicePrincipal pour récupérer la valeur de la propriété paramètre appprincipalid que pour le serveur Skype entreprise et les principaux de service Microsoft Exchange. la valeur de la propriété paramètre appprincipalid que est utilisée pour identifier le principal de service affecté au certificat.</span><span class="sxs-lookup"><span data-stu-id="677a0-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="677a0-130">La valeur de la propriété paramètre appprincipalid que de Skype entreprise Server étant disponible, utilisez la commande suivante pour affecter le certificat à la version de Skype entreprise Online :</span><span class="sxs-lookup"><span data-stu-id="677a0-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="677a0-131">Vous devez alors répéter la commande à l’aide de la valeur de propriété paramètre appprincipalid que pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="677a0-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="677a0-132">Par exemple, si vous devez supprimer ce certificat, par exemple s’il a expiré, vous pouvez le faire en récupérant d’abord le KeyId du certificat :</span><span class="sxs-lookup"><span data-stu-id="677a0-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="677a0-133">Cette commande renvoie des données comme les suivantes :</span><span class="sxs-lookup"><span data-stu-id="677a0-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="677a0-134">Vous pouvez ensuite supprimer le certificat à l’aide d’une commande comme celle-ci :</span><span class="sxs-lookup"><span data-stu-id="677a0-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="677a0-135">Outre l’attribution d’un certificat, vous devez également configurer le principal du service Exchange Online et configurer votre version locale des URL de services Web externes de Skype entreprise Server en tant que principal de service Office 365.</span><span class="sxs-lookup"><span data-stu-id="677a0-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="677a0-136">À cet effet, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="677a0-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="677a0-137">Dans l’exemple suivant, Pool1ExternalWebFQDN.contoso.com est l’URL des services Web externes du pool de serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="677a0-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="677a0-138">Vous devez répéter ces étapes pour ajouter toutes les URL des services Web externes du déploiement.</span><span class="sxs-lookup"><span data-stu-id="677a0-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
