---
title: Modifier l’action par défaut pour les clients non explicitement pris en charge ou limités
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0262bface172c965d12fc276bc08882cac8348ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="084d6-102">Modifier l’action par défaut pour les clients non explicitement pris en charge ou limités dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="084d6-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="084d6-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="084d6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="084d6-104">En plus de spécifier la version de clients que vous voulez prendre en charge dans votre environnement Lync Server 2013, vous pouvez également spécifier une action par défaut pour les clients qui ne disposent pas encore d’une stratégie de version définie.</span><span class="sxs-lookup"><span data-stu-id="084d6-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="084d6-105">Cela vous permet de limiter les versions de client utilisées dans votre environnement Lync Server, qui peuvent vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de clients.</span><span class="sxs-lookup"><span data-stu-id="084d6-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="084d6-106">Pour modifier l’action par défaut pour les clients non explicitement pris en charge ou limités</span><span class="sxs-lookup"><span data-stu-id="084d6-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="084d6-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="084d6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="084d6-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="084d6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="084d6-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="084d6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="084d6-110">Dans la barre de navigation gauche, cliquez sur **clients**, puis sur Configuration de la **version du client**.</span><span class="sxs-lookup"><span data-stu-id="084d6-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="084d6-111">Dans la page Configuration de la **version du client** , double-cliquez sur la configuration **globale** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="084d6-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="084d6-112">Dans la boîte de dialogue **modifier la configuration de version du client** , assurez-vous que la case à cocher Activer le contrôle de **version** est activée, puis, sous **action par défaut**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="084d6-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="084d6-113">**Autoriser**   autorise le client à se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="084d6-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="084d6-114">**Bloquer**   empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="084d6-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="084d6-115">**Bloquer avec une URL**   empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la **version du client** , et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="084d6-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="084d6-116">**Allow with URL**   autorise le client à se connecter si la version du client ne correspond à aucun filtre figurant dans la liste des stratégies de la **version du client** , et qu’il s’agit d’un message d’erreur contenant une URL indiquant qu’un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="084d6-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="084d6-117">Si vous avez sélectionné **bloquer avec une URL**, tapez l’URL de téléchargement du client à inclure dans le message d’erreur dans la zone **URL** .</span><span class="sxs-lookup"><span data-stu-id="084d6-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="084d6-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="084d6-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="084d6-119">Pour désactiver le contrôle de version du client</span><span class="sxs-lookup"><span data-stu-id="084d6-119">To disable client version control</span></span>

  - <span data-ttu-id="084d6-120">Pour désactiver le contrôle de version afin de permettre à tous les clients de se connecter quelle que soit la version du client, désactivez la case à cocher **activer le contrôle de version** , puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="084d6-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="084d6-121">Modification de l’action par défaut à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="084d6-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="084d6-122">L’action par défaut à effectuer lorsque les utilisateurs essaient de se connecter à l’aide de clients qui ne sont pas explicitement pris en charge ou limités par une stratégie de version du client peuvent être gérés à l’aide de l’interface de ligne de commande Windows PowerShell et de l’applet **de commande Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="084d6-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="084d6-123">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="084d6-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="084d6-124">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="084d6-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="084d6-125">Pour configurer l’action par défaut pour bloquer l’accès</span><span class="sxs-lookup"><span data-stu-id="084d6-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="084d6-126">La commande suivante définit l’action par défaut pour le bloc de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="084d6-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="084d6-127">Tout client pour lequel aucune règle de configuration de la version client n’existe.</span><span class="sxs-lookup"><span data-stu-id="084d6-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="084d6-128">Pour configurer l’action par défaut pour autoriser l’accès</span><span class="sxs-lookup"><span data-stu-id="084d6-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="084d6-129">Dans cet exemple, l’action par défaut du site Redmond est définie sur autoriser.</span><span class="sxs-lookup"><span data-stu-id="084d6-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="084d6-130">Cela permettra une inscription pour les clients pour lesquels il n’existe aucune règle de configuration de version de client.</span><span class="sxs-lookup"><span data-stu-id="084d6-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="084d6-131">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="084d6-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="084d6-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="084d6-132">See Also</span></span>


[<span data-ttu-id="084d6-133">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="084d6-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

