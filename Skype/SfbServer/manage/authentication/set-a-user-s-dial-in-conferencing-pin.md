---
title: Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Résumé : Définissez le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: c34e895471fdffb13a4cdb10806bd07146474e44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119553"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="98ff3-103">Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="98ff3-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="98ff3-104">**Résumé :** Définir le code confidentiel de conférence d’un utilisateur pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="98ff3-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="98ff3-105">Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Skype Entreprise Server avec des informations d’identification des services de domaine Active Directory (AD DS) requiert un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="98ff3-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="98ff3-106">Si un utilisateur oublie le code confidentiel de la conférence téléphonique ou n’a pas encore le définir à l’aide de Skype Entreprise Server, vous pouvez définir le code confidentiel de l’utilisateur à partir du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="98ff3-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="98ff3-107">Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.</span><span class="sxs-lookup"><span data-stu-id="98ff3-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98ff3-108">Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies en tant que stratégie.</span><span class="sxs-lookup"><span data-stu-id="98ff3-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="98ff3-109">En plus de la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="98ff3-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="98ff3-110">Pour définir le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="98ff3-110">To set a user's PIN</span></span>

1. <span data-ttu-id="98ff3-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="98ff3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="98ff3-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="98ff3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="98ff3-113">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="98ff3-114">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="98ff3-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="98ff3-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="98ff3-116">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="98ff3-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="98ff3-117">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="98ff3-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="98ff3-118">a.</span><span class="sxs-lookup"><span data-stu-id="98ff3-118">a.</span></span> <span data-ttu-id="98ff3-119">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="98ff3-120">b.</span><span class="sxs-lookup"><span data-stu-id="98ff3-120">b.</span></span> <span data-ttu-id="98ff3-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="98ff3-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="98ff3-122">c.</span><span class="sxs-lookup"><span data-stu-id="98ff3-122">c.</span></span> <span data-ttu-id="98ff3-123">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="98ff3-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="98ff3-124">d.</span><span class="sxs-lookup"><span data-stu-id="98ff3-124">d.</span></span> <span data-ttu-id="98ff3-125">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="98ff3-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="98ff3-126">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="98ff3-127">e.</span><span class="sxs-lookup"><span data-stu-id="98ff3-127">e.</span></span> <span data-ttu-id="98ff3-128">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="98ff3-p108">Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="98ff3-131">Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="98ff3-132">Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="98ff3-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="98ff3-133">Pour autoriser Skype Entreprise Server à générer le code confidentiel de l’utilisateur, sélectionnez Générer automatiquement un code **confidentiel valide** (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="98ff3-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="98ff3-134">Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="98ff3-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="98ff3-135">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="98ff3-136">Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="98ff3-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="98ff3-137">Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="98ff3-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="98ff3-p109">Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est automatiquement copié dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.</span><span class="sxs-lookup"><span data-stu-id="98ff3-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="98ff3-141">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="98ff3-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98ff3-142">Affectation d’un code confidentiel utilisateur à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="98ff3-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="98ff3-143">Vous pouvez également affecter des numéros de code confidentiel à l’aide Set-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98ff3-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="98ff3-144">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98ff3-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98ff3-145">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="98ff3-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="98ff3-146">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="98ff3-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="98ff3-147">Pour attribuer automatiquement un code confidentiel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="98ff3-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="98ff3-148">La commande suivante affecte un code confidentiel à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="98ff3-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="98ff3-149">Étant donné que le paramètre Pin n’est pas inclus, Skype Entreprise Server génère et affecte automatiquement le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="98ff3-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="98ff3-150">Pour affecter un code confidentiel spécifique à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="98ff3-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="98ff3-151">Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="98ff3-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="98ff3-152">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Set-CsClientPin.](/powershell/module/skype/set-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="98ff3-152">For more information, see the help topic for the [Set-CsClientPin](/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
