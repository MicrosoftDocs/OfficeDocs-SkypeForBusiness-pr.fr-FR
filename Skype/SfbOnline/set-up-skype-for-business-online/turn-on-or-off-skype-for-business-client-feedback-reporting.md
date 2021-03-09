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
description: Vous pouvez permettre aux utilisateurs de Skype Entreprise d’utiliser l’outil de commentaires intégré de l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience.
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569000"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a><span data-ttu-id="3f049-103">Activer ou désactiver les commentaires client sur Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3f049-103">Turn on or off Skype for Business client feedback reporting</span></span>

<span data-ttu-id="3f049-104">Vous pouvez permettre à vos utilisateurs Skype Entreprise Online d’utiliser l’outil de commentaires intégré de l’application Skype Entreprise pour permettre aux utilisateurs de signaler des problèmes et de faire part de leurs commentaires directement à Microsoft sur leur expérience.</span><span class="sxs-lookup"><span data-stu-id="3f049-104">You can enable your Skype for Business Online users to use the built-in Skype for Business app feedback tool to let users report issues and provide feedback directly to Microsoft about their experience.</span></span> 
  
![Icône Fournir des commentaires](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
<span data-ttu-id="3f049-106">Cet outil permet à un utilisateur de copier les journaux de l’application sur son appareil pour aider Microsoft à mieux étudier et résoudre les problèmes qu’il peut avoir.</span><span class="sxs-lookup"><span data-stu-id="3f049-106">Using this tool, a user can copy the logs from the app on their device to help Microsoft better investigate and troubleshoot problems that they might have.</span></span> 
  
![Signaler un problème à l’aide de l’icône Paramètres](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
<span data-ttu-id="3f049-108">Vous pouvez également utiliser le paramètre  _EnableOnlineFeedbackScreenshot_, qui permet d'inclure une capture d'écran du périphérique lors de l'envoi des commentaires.</span><span class="sxs-lookup"><span data-stu-id="3f049-108">You can also use the  _EnableOnlineFeedbackScreenshot_ setting so users can include a screenshot of their device as a part of their feedback.</span></span>
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> <span data-ttu-id="3f049-110">Les journaux collectés par l’outil de commentaires de l’application seront stockés pendant 90 jours au maximum aux États-Unis pendant que le problème est en cours d’examen.</span><span class="sxs-lookup"><span data-stu-id="3f049-110">The logs collected by the app's feedback tool will be stored for up to a maximum of 90 days in the United States while the issue is being investigated.</span></span> <span data-ttu-id="3f049-111">Pour cette raison, n'activez pas cet outil de commentaires si cela enfreint la politique de protection des données de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3f049-111">Because of this, please don't enable this feedback tool if this violates your organization's data protection policy.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="3f049-112">Démarrer Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f049-112">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="3f049-113">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="3f049-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="3f049-114">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="3f049-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="3f049-115">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="3f049-115">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="3f049-116">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f049-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   <span data-ttu-id="3f049-117">Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3f049-117">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a><span data-ttu-id="3f049-118">Activer l'outil de commentaires client de l'application pour tous les utilisateurs au sein de votre organisation</span><span class="sxs-lookup"><span data-stu-id="3f049-118">Turn on client app feedback reporting for all the users in your organization</span></span>

<span data-ttu-id="3f049-119">Pour activer la déclaration de commentaires pour les utilisateurs de votre organisation et leur permettre d’envoyer des captures d’écran d’appareil, exécutez :</span><span class="sxs-lookup"><span data-stu-id="3f049-119">To enable feedback reporting for users in your organization and allow them to submit device screenshots, run:</span></span>
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3f049-120">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="3f049-120">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="3f049-121">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="3f049-121">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3f049-122">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="3f049-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3f049-123">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="3f049-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3f049-124">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3f049-124">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3f049-125">Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="3f049-125">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3f049-126">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="3f049-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3f049-127">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f049-127">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3f049-128">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f049-128">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3f049-129">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3f049-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3f049-130">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3f049-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3f049-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f049-131">Related topics</span></span>
[<span data-ttu-id="3f049-132">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3f049-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3f049-133">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="3f049-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
