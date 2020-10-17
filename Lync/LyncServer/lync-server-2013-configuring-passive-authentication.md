---
title: 'Lync Server 2013 : configuration de l’authentification passive'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532491"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="9f0ae-102">Configuration de l’authentification passive Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f0ae-102">Configuring Lync Server 2013 passive authentication</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f0ae-103">_**Dernière modification de la rubrique :** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="9f0ae-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="9f0ae-104">La section suivante décrit la configuration de Lync Server 2013 avec des mises à jour cumulatives : juillet 2013 pour prendre en charge l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="9f0ae-105">Une fois activés, les utilisateurs Lync qui sont activés pour l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide de Lync 2013 avec des mises à jour cumulatives : le client juillet 2013.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="9f0ae-106">Il est vivement recommandé aux clients d’activer l’authentification passive pour les services Web et les serveurs d’inscriptions au niveau du service.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="9f0ae-107">Si l’authentification passive est activée pour le serveur d’inscriptions et les services Web au niveau global, cela entraînera probablement des échecs d’authentification à l’échelle de l’Organisation pour les utilisateurs qui ne se connectent pas avec la version cumulative de Lync 2013 : client de bureau client de juillet 2013.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="9f0ae-108">Configuration du service Web</span><span class="sxs-lookup"><span data-stu-id="9f0ae-108">Web Service Configuration</span></span>

<span data-ttu-id="9f0ae-109">Les étapes suivantes décrivent comment créer une configuration de service Web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition Server qui seront activés pour l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="9f0ae-110">**Pour créer une configuration de service Web personnalisée**</span><span class="sxs-lookup"><span data-stu-id="9f0ae-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="9f0ae-111">Connectez-vous à votre Lync Server 2013 avec des mises à jour cumulatives : le serveur frontal 2013 juillet à l’aide d’un compte d’administrateur Lync.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="9f0ae-112">Lancez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="9f0ae-113">À partir de la ligne de commande Lync Server Management Shell, créez une configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition Server qui sera activé pour l’authentification passive en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="9f0ae-114">La valeur du nom de domaine complet WsFedPassiveMetadataUri est le nom du service de Fédération de votre serveur AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="9f0ae-115">Vous pouvez trouver la valeur nom du service de Fédération dans la console de gestion AD FS 2,0 en cliquant avec le bouton droit de la souris sur <STRONG>service</STRONG> dans le volet de navigation, puis en sélectionnant <STRONG>modifier les propriétés du service de Fédération</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="9f0ae-116">Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été correctement définies en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="9f0ae-117">Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification webticket.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="9f0ae-118">Pour tous les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans Lync Web services en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="9f0ae-119">Vérifiez que tous les autres types d’authentification ont été désactivés avec succès en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="9f0ae-120">Configuration du proxy</span><span class="sxs-lookup"><span data-stu-id="9f0ae-120">Proxy Configuration</span></span>

<span data-ttu-id="9f0ae-121">Lorsque l’authentification par certificat est désactivée pour les services Web Lync, le client Lync utilise un type d’authentification moins favori, tel que Kerberos ou NTLM, pour s’authentifier auprès du service de serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="9f0ae-122">L’authentification par certificat est toujours nécessaire pour permettre au client Lync de récupérer un webticket, cependant, Kerberos et NTLM doivent être désactivés pour le service de serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="9f0ae-123">Les étapes suivantes décrivent comment créer une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition Server qui seront activés pour l’authentification passive.</span><span class="sxs-lookup"><span data-stu-id="9f0ae-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="9f0ae-124">**Pour créer une configuration de proxy personnalisée**</span><span class="sxs-lookup"><span data-stu-id="9f0ae-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="9f0ae-125">À partir de la ligne de commande Lync Server Management Shell, créez une configuration de proxy pour chaque Lync Server 2013 avec des mises à jour cumulatives : le pool de serveurs Edge de juillet 2013, le pool d’entreprise et le serveur Standard Edition Server qui seront activés pour l’authentification passive en exécutant les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="9f0ae-126">Vérifiez que tous les autres types d’authentification proxy ont été désactivés correctement en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9f0ae-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

