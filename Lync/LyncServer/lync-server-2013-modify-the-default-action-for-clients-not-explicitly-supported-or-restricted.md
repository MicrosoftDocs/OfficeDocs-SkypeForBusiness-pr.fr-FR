---
title: Modifier l’action par défaut pour les clients qui ne sont pas explicitement pris en charge ou restreints
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
ms.openlocfilehash: 87f2b88b43c41a5a8bf990a72f0fdfef1c5537e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="c5b0e-102">Modifier l’action par défaut pour les clients qui ne sont pas explicitement pris en charge ou restreints dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b0e-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5b0e-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c5b0e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c5b0e-104">En plus de spécifier la version des clients que vous souhaitez prendre en charge dans votre environnement Lync Server 2013, vous pouvez également spécifier une action par défaut pour les clients qui n’ont pas encore de stratégie de version définie.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="c5b0e-105">Cela vous permet de limiter les versions de client utilisées dans votre environnement Lync Server, ce qui vous permet de contrôler les coûts associés à la prise en charge de plusieurs versions du client.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="c5b0e-106">Pour modifier l’action par défaut des clients qui ne sont pas explicitement pris en charge ou restreints</span><span class="sxs-lookup"><span data-stu-id="c5b0e-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="c5b0e-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c5b0e-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5b0e-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5b0e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5b0e-110">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration de la version du client**.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="c5b0e-111">Dans la page **Configuration de la version du client**, double-cliquez sur la configuration **Global** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="c5b0e-112">Dans la boîte de dialogue **Modifier la configuration de la version du client**, vérifiez que la case à cocher **Activer le contrôle de version** est activée puis, sous **Action par défaut**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5b0e-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="c5b0e-113">**Autoriser**   : autorise le client à se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** .</span><span class="sxs-lookup"><span data-stu-id="c5b0e-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="c5b0e-114">**Bloquer**   : empêche le client de se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** .</span><span class="sxs-lookup"><span data-stu-id="c5b0e-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="c5b0e-115">**Bloquer avec une URL**   : empêche le client de se connecter si sa version ne correspond à aucun filtre dans la liste des **stratégies de version du client** , et inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="c5b0e-116">**Allow with URL**   autorise le client à se connecter si la version du client ne correspond à aucun filtre dans la liste des **stratégies de version du client** , et inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="c5b0e-117">Si vous avez sélectionné **Bloquer avec une URL**, dans la zone **URL**, tapez l’URL de téléchargement du client à inclure dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="c5b0e-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="c5b0e-119">Pour désactiver le contrôle de version des clients</span><span class="sxs-lookup"><span data-stu-id="c5b0e-119">To disable client version control</span></span>

  - <span data-ttu-id="c5b0e-120">Pour désactiver le contrôle de version afin d’autoriser tous les clients à se connecter quelle que soit leur version, désactivez la case à cocher **Activer le contrôle de version**, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c5b0e-121">Modification de l’action par défaut à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5b0e-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c5b0e-122">L’action par défaut à effectuer lorsque les utilisateurs essaient de se connecter à l’aide de clients qui ne sont pas explicitement pris en charge ou restreints par une stratégie de version de client peuvent être gérés à l’aide de l’interface de ligne de commande Windows PowerShell et de la cmdlet **Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="c5b0e-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="c5b0e-123">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c5b0e-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="c5b0e-125">Pour configurer l’action par défaut pour bloquer l’accès</span><span class="sxs-lookup"><span data-stu-id="c5b0e-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="c5b0e-p104">La commande suivante définit l’action par défaut du site Redmond à Block. Elle permet de bloquer l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="c5b0e-128">Pour configurer l’action par défaut pour autoriser l’accès</span><span class="sxs-lookup"><span data-stu-id="c5b0e-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="c5b0e-p105">Dans cet exemple, l’action par défaut du site Redmond est définie à Allow. Cela permet d’autoriser l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.</span><span class="sxs-lookup"><span data-stu-id="c5b0e-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="c5b0e-131">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c5b0e-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5b0e-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5b0e-132">See Also</span></span>


[<span data-ttu-id="c5b0e-133">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5b0e-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

