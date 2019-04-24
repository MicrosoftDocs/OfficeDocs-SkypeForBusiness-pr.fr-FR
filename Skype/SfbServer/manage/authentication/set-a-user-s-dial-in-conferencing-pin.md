---
title: Définir des conférences rendez-vous d’un utilisateur code confidentiel dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Résumé : Définir dans les conférences rendez-vous l’utilisateur code confidentiel pour Skype pour Business Server.'
ms.openlocfilehash: 62b38b8ef15aa2283b66fc18abf5ec0e84e64870
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217900"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="804c4-103">Définir des conférences rendez-vous d’un utilisateur code confidentiel dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="804c4-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="804c4-104">**Résumé :** Définir dans les conférences rendez-vous l’utilisateur code confidentiel pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="804c4-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="804c4-105">Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un Skype pour utilisateur Business Server avec les informations d’identification des Services de domaine Active Directory (AD DS) requiert un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="804c4-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="804c4-106">Si un utilisateur oublie de conférence rendez-vous code confidentiel ou le code confidentiel n’a pas définie à l’aide de Skype pour Business Server, vous pouvez définir le code confidentiel de l’utilisateur à partir de Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="804c4-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="804c4-107">Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.</span><span class="sxs-lookup"><span data-stu-id="804c4-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="804c4-p102">Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies sous forme de stratégie. Outre la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="804c4-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="804c4-110">Pour définir le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="804c4-110">To set a user's PIN</span></span>

1. <span data-ttu-id="804c4-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="804c4-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="804c4-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="804c4-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="804c4-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="804c4-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="804c4-114">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="804c4-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="804c4-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="804c4-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="804c4-116">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="804c4-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="804c4-117">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="804c4-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="804c4-118">a.</span><span class="sxs-lookup"><span data-stu-id="804c4-118">a.</span></span> <span data-ttu-id="804c4-119">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="804c4-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="804c4-120">b.</span><span class="sxs-lookup"><span data-stu-id="804c4-120">b.</span></span> <span data-ttu-id="804c4-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="804c4-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="804c4-122">c.</span><span class="sxs-lookup"><span data-stu-id="804c4-122">c.</span></span> <span data-ttu-id="804c4-123">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="804c4-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="804c4-124">d.</span><span class="sxs-lookup"><span data-stu-id="804c4-124">d.</span></span> <span data-ttu-id="804c4-125">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="804c4-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="804c4-126">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="804c4-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="804c4-127">e.</span><span class="sxs-lookup"><span data-stu-id="804c4-127">e.</span></span> <span data-ttu-id="804c4-128">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="804c4-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="804c4-p108">Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, sélectionnez l’utilisateur, cliquez sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="804c4-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="804c4-131">Sélectionnez un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="804c4-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="804c4-132">Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="804c4-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="804c4-133">Pour autoriser Skype pour Business Server afin de générer le code confidentiel de l’utilisateur, sélectionnez **Générer automatiquement un code confidentiel valide** (par défaut).</span><span class="sxs-lookup"><span data-stu-id="804c4-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="804c4-134">Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="804c4-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="804c4-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="804c4-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="804c4-136">Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="804c4-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="804c4-137">Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="804c4-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="804c4-p109">Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est copié automatiquement dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.</span><span class="sxs-lookup"><span data-stu-id="804c4-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="804c4-141">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="804c4-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="804c4-142">Affectation d’un code confidentiel de l’utilisateur à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="804c4-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="804c4-143">Vous pouvez également affecter plusieurs codes confidentiels à l’aide de l’applet de commande Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="804c4-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="804c4-144">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="804c4-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="804c4-145">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="804c4-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="804c4-146">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="804c4-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="804c4-147">Affectation automatique d’un code confidentiel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="804c4-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="804c4-148">La commande ci-dessous affecte un code confidentiel à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="804c4-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="804c4-149">Étant donné que le paramètre Pin n’est pas inclus, Skype pour Business Server va générer automatiquement et l’assigner le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="804c4-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="804c4-150">Affectation d’un code confidentiel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="804c4-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="804c4-151">Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="804c4-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="804c4-152">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="804c4-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

