---
title: Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer d’Skype Entreprise Online Connector au module PowerShell Teams à gérer les Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b08505ca97672d5285c8ff46b0e5d3cf58e9f84
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513867"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="e6bda-103">Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bda-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="e6bda-104">Teams Le module PowerShell fournit un ensemble complet d’lets de commande pour la gestion Teams à partir de la ligne de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6bda-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="e6bda-105">Les administrateurs n’ont pas besoin Skype d’un connecteur For Business Online pour leur administration Teams entreprise.</span><span class="sxs-lookup"><span data-stu-id="e6bda-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="e6bda-106">Teams administrateur ont été informés via la publication du Centre de messages (MC244740, spécifiée le 16 mars 2021 ; MC250940, dated April 16 2021) about this change.</span><span class="sxs-lookup"><span data-stu-id="e6bda-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="e6bda-107">Teams Le module PowerShell utilise l’authentification moderne, mais le client Windows gestion à distance (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base.</span><span class="sxs-lookup"><span data-stu-id="e6bda-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="e6bda-108">Pour obtenir des instructions sur [l’Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) de l’authentification de base, voir Télécharger et installer.</span><span class="sxs-lookup"><span data-stu-id="e6bda-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="e6bda-109">Skype Entreprise Les connexions Connecteur en ligne seront refusées à partir du 17 mai 2021.</span><span class="sxs-lookup"><span data-stu-id="e6bda-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="e6bda-110">Contactez le Support Microsoft pour obtenir de l’aide et une assistance pour la migration vers Teams module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6bda-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="e6bda-111">Comment migrer</span><span class="sxs-lookup"><span data-stu-id="e6bda-111">How to Migrate</span></span>

<span data-ttu-id="e6bda-112">La migration d’Skype Entreprise Online Connector vers Teams module PowerShell est simple et simple.</span><span class="sxs-lookup"><span data-stu-id="e6bda-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="e6bda-113">La procédure ci-dessous explique comment faire.</span><span class="sxs-lookup"><span data-stu-id="e6bda-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="e6bda-114">Installez la dernière version Teams module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6bda-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="e6bda-115">Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="e6bda-115">For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

2. <span data-ttu-id="e6bda-116">Désinstaller Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="e6bda-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="e6bda-117">Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.**</span><span class="sxs-lookup"><span data-stu-id="e6bda-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>

3. <span data-ttu-id="e6bda-118">Dans vos scripts PowerShell, modifiez le nom du module référencé ```Import-Module``` dans</span><span class="sxs-lookup"><span data-stu-id="e6bda-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="e6bda-119">`SkypeOnlineConnector` ou `LyncOnlineConnector` `MicrosoftTeams` à .</span><span class="sxs-lookup"><span data-stu-id="e6bda-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="e6bda-120">Par exemple, `Import-Module -Name SkypeOnlineConnector` changez pour `Import-Module -Name MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="e6bda-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="e6bda-121">Lorsque vous utilisez Teams PowerShell Module 2.0 ou version ultérieure, mettez à jour vos scripts qui font `New-CsOnlineSession` `Connect-MicrosoftTeams` référence.</span><span class="sxs-lookup"><span data-stu-id="e6bda-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="e6bda-122">`Import-PsSession`n’est plus nécessaire pour établir une session PowerShell distante Skype Entreprise Online, comme cela est implicite lors de `Connect-MicrosoftTeams` l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="e6bda-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="e6bda-123">Support en ligne</span><span class="sxs-lookup"><span data-stu-id="e6bda-123">Online Support</span></span>

<span data-ttu-id="e6bda-124">Gagnez du temps en commençant votre demande de service en ligne.</span><span class="sxs-lookup"><span data-stu-id="e6bda-124">Save time by starting your service request online.</span></span> <span data-ttu-id="e6bda-125">Nous vous aiderons à trouver une solution ou à vous mettre en relation avec le support technique.</span><span class="sxs-lookup"><span data-stu-id="e6bda-125">We'll help you find a solution or connect you to technical support.</span></span>

1.  <span data-ttu-id="e6bda-126">Pour ce faire, voir le Centre [https://admin.microsoft.com](https://admin.microsoft.com) d’administration.</span><span class="sxs-lookup"><span data-stu-id="e6bda-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="e6bda-127">Si un message vous indique que vous n’êtes pas autorisé à accéder à cette page ou à effectuer cette action, cela indique que vous n’êtes pas un administrateur. Qui avez des autorisations d’administrateur dans mon entreprise ?</span><span class="sxs-lookup"><span data-stu-id="e6bda-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>

2.  <span data-ttu-id="e6bda-128">Sélectionnez **l’aide nécessaire**? .</span><span class="sxs-lookup"><span data-stu-id="e6bda-128">Select the **Need help**? button.</span></span>

3.  <span data-ttu-id="e6bda-129">Vous avez besoin **d’aide**? , indiquez-nous ce sur quoi vous avez besoin d’aide, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="e6bda-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>

4.  <span data-ttu-id="e6bda-130">Si les résultats ne vous aident pas, sélectionnez **Contacter le support.**</span><span class="sxs-lookup"><span data-stu-id="e6bda-130">If the results don't help, select **Contact support**.</span></span>

5.  <span data-ttu-id="e6bda-131">Entrez une description de votre problème, confirmez votre numéro de contact et votre adresse de courrier, sélectionnez votre méthode de contact préférée, puis **Contactez-moi.**</span><span class="sxs-lookup"><span data-stu-id="e6bda-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="e6bda-132">Le temps d’attente attendu est indiqué dans le cas où vous avez besoin d’aide ? .</span><span class="sxs-lookup"><span data-stu-id="e6bda-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6bda-133">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e6bda-133">Related topics</span></span>

[<span data-ttu-id="e6bda-134">Installer Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bda-134">Install Microsoft Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="e6bda-135">Gérer Teams avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bda-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="e6bda-136">Teams Notes de publication de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6bda-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="e6bda-137">Microsoft Teams des cmdlet</span><span class="sxs-lookup"><span data-stu-id="e6bda-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="e6bda-138">Skype Entreprise des cmdlet</span><span class="sxs-lookup"><span data-stu-id="e6bda-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
