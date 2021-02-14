---
title: Afficher les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Résumé : Affichez les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server.'
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806504"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="cb54d-103">Afficher les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb54d-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="cb54d-104">**Résumé :** Afficher les informations de code confidentiel de l’utilisateur dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb54d-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="cb54d-105">Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Skype Entreprise Server ayant des informations d’identification AD DS (Active Directory Domain Services) requiert un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="cb54d-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="cb54d-106">Vous pouvez afficher les informations de code confidentiel d’un utilisateur à partir du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb54d-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb54d-107">Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent par exemple si le code confidentiel a été défini ou quand il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="cb54d-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="cb54d-108">Si un utilisateur a perdu son code confidentiel, vous pouvez le réinitialiser en suivant les procédures dans Définir le code confidentiel de conférence [d’un](set-a-user-s-dial-in-conferencing-pin.md) utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb54d-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="cb54d-109">Pour afficher le code confidentiel d’un utilisateur dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb54d-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cb54d-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cb54d-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cb54d-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb54d-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cb54d-112">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="cb54d-113">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="cb54d-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="cb54d-114">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="cb54d-115">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="cb54d-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="cb54d-116">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="cb54d-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="cb54d-117">a.</span><span class="sxs-lookup"><span data-stu-id="cb54d-117">a.</span></span> <span data-ttu-id="cb54d-118">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="cb54d-119">b.</span><span class="sxs-lookup"><span data-stu-id="cb54d-119">b.</span></span> <span data-ttu-id="cb54d-120">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cb54d-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="cb54d-121">c.</span><span class="sxs-lookup"><span data-stu-id="cb54d-121">c.</span></span> <span data-ttu-id="cb54d-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="cb54d-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="cb54d-123">d.</span><span class="sxs-lookup"><span data-stu-id="cb54d-123">d.</span></span> <span data-ttu-id="cb54d-124">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cb54d-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cb54d-125">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="cb54d-126">e.</span><span class="sxs-lookup"><span data-stu-id="cb54d-126">e.</span></span> <span data-ttu-id="cb54d-127">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb54d-p108">Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur **Action**, puis sur **Déverrouiller le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="cb54d-130">Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="cb54d-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb54d-131">Affichage des informations de code confidentiel de l’utilisateur à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="cb54d-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cb54d-132">Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="cb54d-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="cb54d-133">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb54d-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb54d-134">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="cb54d-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="cb54d-135">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="cb54d-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="cb54d-136">Pour afficher les informations relatives au code confidentiel de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="cb54d-136">To view user PIN information</span></span>

<span data-ttu-id="cb54d-137">Pour afficher les informations de code confidentiel d’un utilisateur, tapez une commande semblable à la suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="cb54d-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="cb54d-138">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="cb54d-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="cb54d-139">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsConferenceDisclaimer.](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cb54d-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb54d-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb54d-140">See also</span></span>

[<span data-ttu-id="cb54d-141">Définir le code confidentiel de conférence d’un utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb54d-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="cb54d-142">Verrouillage ou déverrouillage du code confidentiel d’un utilisateur dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="cb54d-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
