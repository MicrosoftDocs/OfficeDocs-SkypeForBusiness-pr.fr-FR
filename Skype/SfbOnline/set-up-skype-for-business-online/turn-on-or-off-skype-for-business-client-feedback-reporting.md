---
title: Activer ou désactiver les commentaires client sur Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Vous pouvez permettre aux utilisateurs de Skype entreprise d’utiliser l’outil de commentaires d’applications Skype entreprise intégré pour permettre aux utilisateurs de signaler les problèmes et de fournir des commentaires directement à Microsoft sur leur utilisation.
ms.openlocfilehash: 3b91bc88c20450b7c0d9c5705bceec53af5f9edb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814183"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="9443e-103">Activer ou désactiver les commentaires client sur Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9443e-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="9443e-104">Vous pouvez permettre aux utilisateurs de Skype entreprise Online d’utiliser l’outil de commentaires d’applications Skype entreprise intégré pour permettre aux utilisateurs de signaler les problèmes et de fournir des commentaires directement à Microsoft sur leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="9443e-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="9443e-106">À l’aide de cet outil, un utilisateur peut copier les journaux de l’application sur leur périphérique afin d’aider Microsoft à examiner et résoudre les problèmes qu’ils peuvent rencontrer.</span><span class="sxs-lookup"><span data-stu-id="9443e-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="9443e-108">Vous pouvez également utiliser le paramètre  _EnableOnlineFeedbackScreenshot_, qui permet d'inclure une capture d'écran du périphérique lors de l'envoi des commentaires.</span><span class="sxs-lookup"><span data-stu-id="9443e-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="9443e-110">Les journaux collectés par l’outil de commentaires de l’application seront stockés pour un maximum de 90 jours aux États-Unis pendant que le problème est examiné.</span><span class="sxs-lookup"><span data-stu-id="9443e-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="9443e-111">Pour cette raison, n'activez pas cet outil de commentaires si cela enfreint la politique de protection des données de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9443e-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="9443e-112">Vérifier et démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9443e-112">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="9443e-113">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9443e-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="9443e-114">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9443e-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9443e-115">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9443e-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9443e-116">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9443e-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="9443e-117">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="9443e-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="9443e-118">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="9443e-118">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="9443e-119">Vous devrez également installer le module Windows PowerShell pour les équipes qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="9443e-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
<span data-ttu-id="9443e-120">Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="9443e-120">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="9443e-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9443e-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="9443e-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="9443e-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9443e-123">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="9443e-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="9443e-124">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="9443e-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="9443e-125">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="9443e-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>
 
   ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   <span data-ttu-id="9443e-126">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9443e-126">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or[Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="9443e-127">Activer l'outil de commentaires client de l'application pour tous les utilisateurs au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="9443e-127">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="9443e-128">Pour activer le rapport de commentaires pour les utilisateurs de votre organisation et leur permettre d’envoyer des captures d’écran de l’appareil, exécutez :</span><span class="sxs-lookup"><span data-stu-id="9443e-128">To enable feedback reporting for users in your organization and allow them to submit device screen shots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9443e-129">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="9443e-129">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="9443e-130">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="9443e-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9443e-131">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="9443e-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9443e-132">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="9443e-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9443e-133">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9443e-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="9443e-134">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="9443e-134">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="9443e-135">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="9443e-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9443e-136">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9443e-136">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9443e-137">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9443e-137">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="9443e-138">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9443e-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9443e-139">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9443e-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="9443e-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9443e-140">Related topics</span></span>
[<span data-ttu-id="9443e-141">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9443e-141">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9443e-142">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="9443e-142">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
