---
title: Verrouiller ou déverrouiller un code confidentiel dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Résumé : Verrouiller ou déverrouiller des conférences rendez-vous d’un utilisateur code confidentiel pour Skype pour Business Server.'
ms.openlocfilehash: 36d25ad681136a88953535a902ef1d3580ff7a1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919899"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="165a5-103">Verrouiller ou déverrouiller un code confidentiel dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="165a5-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="165a5-104">**Résumé :** Verrouiller ou déverrouiller la conférence rendez-vous d’un utilisateur code confidentiel pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="165a5-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="165a5-105">Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **utilisateurs** de Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="165a5-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="165a5-106">Pour verrouiller le code confidentiel d’un utilisateur dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="165a5-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="165a5-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="165a5-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="165a5-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="165a5-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="165a5-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="165a5-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="165a5-110">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="165a5-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="165a5-111">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="165a5-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="165a5-112">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="165a5-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="165a5-113">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="165a5-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="165a5-114">a.</span><span class="sxs-lookup"><span data-stu-id="165a5-114">a.</span></span> <span data-ttu-id="165a5-115">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="165a5-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="165a5-116">b.</span><span class="sxs-lookup"><span data-stu-id="165a5-116">b.</span></span> <span data-ttu-id="165a5-117">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="165a5-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="165a5-118">c.</span><span class="sxs-lookup"><span data-stu-id="165a5-118">c.</span></span> <span data-ttu-id="165a5-119">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="165a5-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="165a5-120">d.</span><span class="sxs-lookup"><span data-stu-id="165a5-120">d.</span></span> <span data-ttu-id="165a5-121">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="165a5-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="165a5-122">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="165a5-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="165a5-123">e.</span><span class="sxs-lookup"><span data-stu-id="165a5-123">e.</span></span> <span data-ttu-id="165a5-124">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="165a5-124">Click **Find**.</span></span>
    
   <span data-ttu-id="165a5-125">f.</span><span class="sxs-lookup"><span data-stu-id="165a5-125">f.</span></span> <span data-ttu-id="165a5-126">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="165a5-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="165a5-127">Pour déverrouiller le code confidentiel d’un utilisateur dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="165a5-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="165a5-128">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="165a5-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="165a5-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="165a5-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="165a5-130">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="165a5-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="165a5-131">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="165a5-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="165a5-132">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="165a5-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="165a5-133">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="165a5-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="165a5-134">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="165a5-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="165a5-135">a.</span><span class="sxs-lookup"><span data-stu-id="165a5-135">a.</span></span> <span data-ttu-id="165a5-136">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="165a5-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="165a5-137">b.</span><span class="sxs-lookup"><span data-stu-id="165a5-137">b.</span></span> <span data-ttu-id="165a5-138">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="165a5-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="165a5-139">c.</span><span class="sxs-lookup"><span data-stu-id="165a5-139">c.</span></span> <span data-ttu-id="165a5-140">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="165a5-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="165a5-141">d.</span><span class="sxs-lookup"><span data-stu-id="165a5-141">d.</span></span> <span data-ttu-id="165a5-142">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="165a5-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="165a5-143">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="165a5-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="165a5-144">e.</span><span class="sxs-lookup"><span data-stu-id="165a5-144">e.</span></span> <span data-ttu-id="165a5-145">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="165a5-145">Click **Find**.</span></span>
    
   <span data-ttu-id="165a5-146">f.</span><span class="sxs-lookup"><span data-stu-id="165a5-146">f.</span></span> <span data-ttu-id="165a5-147">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="165a5-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="165a5-148">Verrouillage et déverrouillage codes confidentiels d’utilisateur à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="165a5-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="165a5-149">Vous pouvez verrouiller et déverrouiller des codes confidentiels d’utilisateur à l’aide de Windows PowerShell et les applets de commande Lock-CsClientPin et Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="165a5-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="165a5-150">Vous pouvez exécuter ces applets de commande de le Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="165a5-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="165a5-151">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="165a5-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="165a5-152">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="165a5-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="165a5-153">Pour verrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="165a5-153">To lock a user PIN</span></span>

- <span data-ttu-id="165a5-154">Pour verrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="165a5-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="165a5-155">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="165a5-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="165a5-156">Pour déverrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="165a5-156">To unlock a user PIN</span></span>

- <span data-ttu-id="165a5-157">Pour déverrouiller le code confidentiel d’un utilisateur, utilisez l’applet de commande Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="165a5-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="165a5-158">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="165a5-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="165a5-159">Pour plus d’informations, consultez la rubrique d’aide pour les applets de commande [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) et [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="165a5-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
