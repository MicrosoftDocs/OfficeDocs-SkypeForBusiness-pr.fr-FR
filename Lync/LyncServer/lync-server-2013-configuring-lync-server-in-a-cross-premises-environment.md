---
title: 'Lync Server 2013 : configuration de Lync Server dans un environnement intersite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74fd0370fd0b6b6ba829f0f4e78f322b1a5ccc21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="8c2dd-102">Configuration de Microsoft Lync Server 2013 dans un environnement intersite</span><span class="sxs-lookup"><span data-stu-id="8c2dd-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c2dd-103">_**Dernière modification de la rubrique :** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="8c2dd-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="8c2dd-104">Dans une configuration intersite, certains de vos utilisateurs sont hébergés sur une installation locale de Microsoft Lync Server 2013 tandis que d’autres sont hébergés sur la version Office 365 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="8c2dd-105">Pour configurer l’authentification de serveur à serveur dans un environnement intersite, vous devez d’abord configurer votre installation locale de Lync Server 2013 pour approuver le serveur d’autorisation Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="8c2dd-106">L’étape initiale de ce processus peut être effectuée en exécutant le script Lync Server Management Shell suivant :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="8c2dd-p102">N’oubliez pas que le nom de domaine d’un client est généralement différent du nom de l’organisation ; en fait, le nom de domaine est presque toujours identique à l’ID de client. C’est pourquoi la première ligne du script est utilisée pour retourner la valeur de la propriété TenantId du client spécifié (ici, fabrikam.com), puis pour attribuer ce nom à la variable $TenantId :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="8c2dd-109">Une fois le script terminé, vous devez configurer une relation d’approbation entre Lync Server 2013 et le serveur d’autorisation, ainsi qu’une seconde relation d’approbation entre Exchange 2013 et le serveur d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="8c2dd-110">Vous pouvez uniquement le faire à l’aide d’applets de commande Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c2dd-111">Si vous n’avez pas installé les applets de commande Microsoft Online Services, vous avez deux choses à faire avant de poursuivre.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="8c2dd-112">Tout d’abord, téléchargez et installez la version 64 bits de l’Assistant de connexion Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="8c2dd-113">Une fois l’installation terminée, téléchargez et installez la version 64 bits du module Microsoft Online Services pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="8c2dd-114">Des informations détaillées sur l’installation et l’utilisation du module Microsoft Online Services sont disponibles sur le site web d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="8c2dd-115">Ces instructions vous indiquent également comment configurer l’authentification unique, la fédération et la synchronisation entre Office 365 et Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="8c2dd-116">Si vous n’avez pas installé ces applets de commande, votre script échoue car la cmdlet Get-CsTenant n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="8c2dd-117">Une fois que vous avez configuré Office 365 et une fois que vous avez créé les principaux de service Office 365 pour Lync Server 2013 et Exchange 2013, vous devrez enregistrer vos informations d’identification avec ces principaux de service.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="8c2dd-118">Pour ce faire, vous devez d’abord obtenir un certificat X.509 Base64 enregistré sous forme de fichier .CER.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="8c2dd-119">Ce certificat est ensuite appliqué aux principaux du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="8c2dd-120">Une fois que vous avez obtenu le certificat X. 509, démarrez le module Microsoft Online Services (cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Online Services**, puis sur **module Microsoft Online Services pour Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="8c2dd-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="8c2dd-121">Une fois que le module Services s’ouvre, tapez ce qui suit pour importer le module Microsoft Online Windows PowerShell contenant les applets de commande pouvant être utilisées pour gérer les principaux de service :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="8c2dd-122">Lorsque le module a été importé, tapez la commande suivante, puis appuyez sur Entrée afin de vous connecter à Office 365 :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="8c2dd-p107">Après avoir appuyé sur Entrée, une boîte de dialogue d’informations d’identification s’affiche. Entrez-y votre nom d’utilisateur et votre mot de passe Office 365, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-p107">After you press ENTER, a credentials dialog box will appear. Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="8c2dd-125">Dès que vous êtes connecté à Office 365, vous pouvez exécuter la commande suivante afin de retourner des informations sur vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="8c2dd-126">Vous devriez obtenir des informations similaires à celles-ci pour tous vos principaux du service :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="8c2dd-127">L’étape suivante consiste à importer, encoder et assigner le certificat X.509.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="8c2dd-128">Pour importer et coder le certificat, utilisez les commandes Windows PowerShell suivantes, en veillant à spécifier le chemin d’accès complet au fichier. Fichier CER lorsque vous appelez la méthode Import :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="8c2dd-129">Une fois que le certificat a été importé et encodé, vous pouvez l’assigner à vos principaux du service Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="8c2dd-130">Pour cela, commencez par utiliser Get-MsolServicePrincipal pour récupérer la valeur de la propriété AppPrincipalId des principaux du service Lync Server et Microsoft Exchange ; la valeur de la propriété AppPrincipalId sert à identifier le principal du service auquel est assigné le certificat.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="8c2dd-131">Une fois la valeur de la propriété AppPrincipalId pour Lync Server 2013, utilisez la commande suivante pour attribuer le certificat à la version Office 365 de Lync Server (les propriétés StartDate et EndDate doivent correspondre à la période de validité du certificat) :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="8c2dd-132">Vous devez ensuite répéter la commande, cette fois en utilisant la valeur de la propriété AppPrincipalId pour Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="8c2dd-133">Si vous avez besoin de supprimer ce certificat ultérieurement, vous pouvez le faire en récupérant la propriété KeyId du certificat au préalable :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="8c2dd-134">Cette commande retourne des données comme les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="8c2dd-135">Vous pouvez ensuite supprimer le certificat à l’aide d’une commande similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="8c2dd-136">En plus d’affecter un certificat, vous devez également configurer le principal de service Office 365 pour Exchange Online en ajoutant le nom de principal du serveur pour votre version sur site de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c2dd-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="8c2dd-137">Pour ce faire, vous pouvez exécuter les quatre lignes suivantes dans une session Microsoft Online Services PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8c2dd-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

