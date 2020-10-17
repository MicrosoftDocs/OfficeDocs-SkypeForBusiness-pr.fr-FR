---
title: 'Lync Server 2013 : verrouillage ou déverrouillage du code confidentiel d’un utilisateur'
description: 'Lync Server 2013 : verrouillez ou déverrouillez le code confidentiel d’un utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf04be333e9d17dd0a06e6eb98d314c2960c3b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570550"
---
# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="3dd1a-103">Verrouillage ou déverrouillage du code confidentiel d’un utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd1a-103">Lock or unlock a user PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dd1a-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3dd1a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3dd1a-105">Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **utilisateurs** du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-105">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3dd1a-106">Pour verrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="3dd1a-106">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3dd1a-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3dd1a-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3dd1a-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3dd1a-110">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3dd1a-111">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-111">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3dd1a-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3dd1a-113">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-113">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3dd1a-114">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-114">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3dd1a-115">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-115">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3dd1a-116">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-116">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3dd1a-117">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-117">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3dd1a-118">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-118">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3dd1a-119">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-119">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3dd1a-120">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-120">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3dd1a-121">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-121">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3dd1a-122">Pour déverrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="3dd1a-122">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3dd1a-123">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3dd1a-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3dd1a-125">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3dd1a-126">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-126">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3dd1a-127">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-127">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3dd1a-128">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-128">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3dd1a-129">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-129">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3dd1a-130">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-130">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3dd1a-131">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-131">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3dd1a-132">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-132">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3dd1a-133">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="3dd1a-133">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3dd1a-134">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-134">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3dd1a-135">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-135">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3dd1a-136">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-136">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3dd1a-137">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-137">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3dd1a-138">Verrouillage et déverrouillage des codes confidentiels des utilisateurs à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3dd1a-138">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3dd1a-139">Vous pouvez verrouiller et déverrouiller les codes confidentiels de l’utilisateur à l’aide de Windows PowerShell et des applets de commande Lock-CsClientPin et Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-139">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="3dd1a-140">Vous pouvez exécuter ces applets de commande à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dd1a-140">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3dd1a-141">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3dd1a-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="3dd1a-142">Pour verrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3dd1a-142">To lock a user PIN</span></span>

  - <span data-ttu-id="3dd1a-p104">Pour verrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Lock-CsClientPin. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="3dd1a-145">Pour déverrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3dd1a-145">To unlock a user PIN</span></span>

  - <span data-ttu-id="3dd1a-p105">Pour déverrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Unlock-CsClientPin. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3dd1a-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="3dd1a-148">Pour plus d’informations, consultez la rubrique d’aide relative aux applets de commande [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) et [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="3dd1a-148">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

