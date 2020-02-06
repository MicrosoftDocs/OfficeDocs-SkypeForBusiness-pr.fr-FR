---
title: Verrouillage ou déverrouillage d’un code confidentiel d’utilisateur dans Skype entreprise Server
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
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Résumé : verrouillez ou déverrouillez le code confidentiel de conférence rendez-vous d’un utilisateur pour Skype entreprise Server.'
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818786"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="b9db1-103">Verrouillage ou déverrouillage d’un code confidentiel d’utilisateur dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b9db1-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="b9db1-104">**Résumé :** Verrouiller ou déverrouiller le code confidentiel de conférence rendez-vous d’un utilisateur pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9db1-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="b9db1-105">Vous pouvez verrouiller ou déverrouiller le code confidentiel d’un utilisateur à partir de la section **utilisateurs** du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9db1-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b9db1-106">Pour verrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b9db1-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9db1-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b9db1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9db1-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9db1-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b9db1-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9db1-110">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9db1-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="b9db1-111">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="b9db1-112">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="b9db1-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="b9db1-113">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="b9db1-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="b9db1-114">a.</span><span class="sxs-lookup"><span data-stu-id="b9db1-114">a.</span></span> <span data-ttu-id="b9db1-115">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="b9db1-116">b.</span><span class="sxs-lookup"><span data-stu-id="b9db1-116">b.</span></span> <span data-ttu-id="b9db1-117">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b9db1-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="b9db1-118">c.</span><span class="sxs-lookup"><span data-stu-id="b9db1-118">c.</span></span> <span data-ttu-id="b9db1-119">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="b9db1-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="b9db1-120">d.</span><span class="sxs-lookup"><span data-stu-id="b9db1-120">d.</span></span> <span data-ttu-id="b9db1-121">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b9db1-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b9db1-122">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="b9db1-123">e.</span><span class="sxs-lookup"><span data-stu-id="b9db1-123">e.</span></span> <span data-ttu-id="b9db1-124">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-124">Click **Find**.</span></span>
    
   <span data-ttu-id="b9db1-125">touche.</span><span class="sxs-lookup"><span data-stu-id="b9db1-125">f.</span></span> <span data-ttu-id="b9db1-126">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Verrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b9db1-127">Pour déverrouiller le code confidentiel d’un utilisateur dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b9db1-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b9db1-128">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b9db1-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9db1-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9db1-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b9db1-130">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9db1-131">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9db1-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="b9db1-132">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="b9db1-133">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="b9db1-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="b9db1-134">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="b9db1-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="b9db1-135">a.</span><span class="sxs-lookup"><span data-stu-id="b9db1-135">a.</span></span> <span data-ttu-id="b9db1-136">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="b9db1-137">b.</span><span class="sxs-lookup"><span data-stu-id="b9db1-137">b.</span></span> <span data-ttu-id="b9db1-138">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b9db1-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="b9db1-139">c.</span><span class="sxs-lookup"><span data-stu-id="b9db1-139">c.</span></span> <span data-ttu-id="b9db1-140">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="b9db1-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="b9db1-141">d.</span><span class="sxs-lookup"><span data-stu-id="b9db1-141">d.</span></span> <span data-ttu-id="b9db1-142">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b9db1-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b9db1-143">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="b9db1-144">e.</span><span class="sxs-lookup"><span data-stu-id="b9db1-144">e.</span></span> <span data-ttu-id="b9db1-145">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-145">Click **Find**.</span></span>
    
   <span data-ttu-id="b9db1-146">touche.</span><span class="sxs-lookup"><span data-stu-id="b9db1-146">f.</span></span> <span data-ttu-id="b9db1-147">Cliquez successivement sur le nom de l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="b9db1-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9db1-148">Verrouillage et déverrouillage des épingles d’utilisateur à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9db1-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b9db1-149">Vous pouvez verrouiller et déverrouiller des épingles d’utilisateurs à l’aide de Windows PowerShell et des applets de CsClientPin et de verrouillage-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="b9db1-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="b9db1-150">Vous pouvez exécuter ces applets de commande à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9db1-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b9db1-151">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b9db1-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b9db1-152">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b9db1-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="b9db1-153">Pour verrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9db1-153">To lock a user PIN</span></span>

- <span data-ttu-id="b9db1-154">Pour verrouiller le code confidentiel d’un utilisateur, utilisez l’applet de passe Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="b9db1-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="b9db1-155">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b9db1-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="b9db1-156">Pour déverrouiller le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b9db1-156">To unlock a user PIN</span></span>

- <span data-ttu-id="b9db1-157">Pour déverrouiller le code confidentiel d’un utilisateur, utilisez l’applet de la cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="b9db1-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="b9db1-158">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b9db1-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="b9db1-159">Pour plus d’informations, reportez-vous à la rubrique d’aide pour les applets de [CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) et [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b9db1-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
