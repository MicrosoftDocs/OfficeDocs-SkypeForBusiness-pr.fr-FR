---
title: Verrouillage ou déverrouillage du code confidentiel d’un utilisateur dans Skype Entreprise Server
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Résumé : Verrouillez ou déverrouillez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 46c46d2bffc8d9c0c8d3456192fb506ce754aecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119593"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="33efc-103">Verrouiller ou déverrouiller un code confidentiel utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33efc-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="33efc-104">**Résumé :** Verrouiller ou déverrouiller le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33efc-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="33efc-105">Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **Utilisateurs** du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33efc-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="33efc-106">Pour verrouiller le code confidentiel d’un utilisateur dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33efc-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="33efc-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33efc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33efc-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33efc-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="33efc-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="33efc-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="33efc-110">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33efc-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="33efc-111">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="33efc-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="33efc-112">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="33efc-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="33efc-113">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="33efc-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="33efc-114">a.</span><span class="sxs-lookup"><span data-stu-id="33efc-114">a.</span></span> <span data-ttu-id="33efc-115">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="33efc-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="33efc-116">b.</span><span class="sxs-lookup"><span data-stu-id="33efc-116">b.</span></span> <span data-ttu-id="33efc-117">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="33efc-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="33efc-118">c.</span><span class="sxs-lookup"><span data-stu-id="33efc-118">c.</span></span> <span data-ttu-id="33efc-119">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="33efc-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="33efc-120">d.</span><span class="sxs-lookup"><span data-stu-id="33efc-120">d.</span></span> <span data-ttu-id="33efc-121">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="33efc-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="33efc-122">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="33efc-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="33efc-123">e.</span><span class="sxs-lookup"><span data-stu-id="33efc-123">e.</span></span> <span data-ttu-id="33efc-124">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="33efc-124">Click **Find**.</span></span>
    
   <span data-ttu-id="33efc-125">f.</span><span class="sxs-lookup"><span data-stu-id="33efc-125">f.</span></span> <span data-ttu-id="33efc-126">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="33efc-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="33efc-127">Pour déverrouiller le code confidentiel d’un utilisateur dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33efc-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="33efc-128">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33efc-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="33efc-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33efc-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="33efc-130">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="33efc-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="33efc-131">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="33efc-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="33efc-132">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="33efc-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="33efc-133">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="33efc-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="33efc-134">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="33efc-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="33efc-135">a.</span><span class="sxs-lookup"><span data-stu-id="33efc-135">a.</span></span> <span data-ttu-id="33efc-136">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="33efc-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="33efc-137">b.</span><span class="sxs-lookup"><span data-stu-id="33efc-137">b.</span></span> <span data-ttu-id="33efc-138">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="33efc-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="33efc-139">c.</span><span class="sxs-lookup"><span data-stu-id="33efc-139">c.</span></span> <span data-ttu-id="33efc-140">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="33efc-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="33efc-141">d.</span><span class="sxs-lookup"><span data-stu-id="33efc-141">d.</span></span> <span data-ttu-id="33efc-142">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="33efc-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="33efc-143">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="33efc-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="33efc-144">e.</span><span class="sxs-lookup"><span data-stu-id="33efc-144">e.</span></span> <span data-ttu-id="33efc-145">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="33efc-145">Click **Find**.</span></span>
    
   <span data-ttu-id="33efc-146">f.</span><span class="sxs-lookup"><span data-stu-id="33efc-146">f.</span></span> <span data-ttu-id="33efc-147">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="33efc-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="33efc-148">Verrouillage et déverrouillage de pins utilisateur à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="33efc-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="33efc-149">Vous pouvez verrouiller et déverrouiller les pins utilisateur à l’aide de Windows PowerShell et des cmdlets Lock-CsClientPin et Unlock-CsClientPin de données.</span><span class="sxs-lookup"><span data-stu-id="33efc-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="33efc-150">Vous pouvez exécuter ces cmdlets à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33efc-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="33efc-151">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="33efc-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="33efc-152">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33efc-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="33efc-153">Pour verrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="33efc-153">To lock a user PIN</span></span>

- <span data-ttu-id="33efc-154">Pour verrouiller le code confidentiel d’un utilisateur, utilisez Lock-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33efc-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="33efc-155">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="33efc-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="33efc-156">Pour déverrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="33efc-156">To unlock a user PIN</span></span>

- <span data-ttu-id="33efc-157">Pour déverrouiller le code confidentiel d’un utilisateur, utilisez Unlock-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33efc-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="33efc-158">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="33efc-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="33efc-159">Pour plus d’informations, voir la rubrique d’aide pour les cmdlets [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) et [Unlock-CsClientPin.](/powershell/module/skype/unlock-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="33efc-159">For more information, see the help topic for the [Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>