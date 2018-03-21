---
title: "Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 459be3e5ca1c9c2e2ba008ed169942435910b4f4
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a><span data-ttu-id="78f96-103">Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook</span><span class="sxs-lookup"><span data-stu-id="78f96-103">Turn on or off allowing content to be preloaded for meetings using Outlook</span></span>

<span data-ttu-id="78f96-104">Les utilisateurs peuvent précharger contenu, les fichiers ou les pièces jointes associées à une invitation à une réunion Outlook à un Skype pour une réunion commerciale en ligne, mais vous pouvez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="78f96-104">Users can preload content, files, or attachments that are attached to an Outlook meeting invitation to a Skype for Business Online meeting, but you can it turn on or off.</span></span> <span data-ttu-id="78f96-105">Il est activé par défaut pour toutes les organisations qui utilisent Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="78f96-105">It's turned on by default for all organizations that are using Skype for Business Online.</span></span> <span data-ttu-id="78f96-106">Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span><span class="sxs-lookup"><span data-stu-id="78f96-106">See how to [Preload attachments for a Skype for Business meeting](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).</span></span>
  
> [!NOTE]
> <span data-ttu-id="78f96-107">Actuellement, aucun applets de commande ne sont disponibles dans Skype pour Business Online pour définir ou afficher des valeurs en ligne pour _MaxContentStorageMB_ et _MaxUploadFileMB_.</span><span class="sxs-lookup"><span data-stu-id="78f96-107">Currently, there are no cmdlets available in Skype for Business Online for setting or viewing online values for  _MaxContentStorageMB_ and _MaxUploadFileMB_.</span></span> <span data-ttu-id="78f96-108">Elles ne sont disponibles que pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="78f96-108">They are only available for on-premises deployments.</span></span> <span data-ttu-id="78f96-109">Il est important de savoir que le contenu ne seront pas téléchargé à une réunion si le contenu joint dépasse le _MaxUploadFileSizeMB_ ou le _MaxContentStorageMB_ est atteint.</span><span class="sxs-lookup"><span data-stu-id="78f96-109">It's important to know that content won't be uploaded to a meeting if the attached content exceeds the  _MaxUploadFileSizeMB_ or if the _MaxContentStorageMB_ limit is reached.</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="78f96-110">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="78f96-110">To get you started</span></span>

### 

 <span data-ttu-id="78f96-111">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78f96-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="78f96-112">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78f96-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="78f96-113">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78f96-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="78f96-p103">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="78f96-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="78f96-p104">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="78f96-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="78f96-120">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="78f96-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="78f96-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="78f96-121">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="78f96-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="78f96-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="78f96-123">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="78f96-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78f96-124">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="78f96-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="78f96-125">Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="78f96-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-it-on-or-off"></a><span data-ttu-id="78f96-126">Activation ou désactivation des applications intégrées</span><span class="sxs-lookup"><span data-stu-id="78f96-126">Turning it on or off</span></span>

<span data-ttu-id="78f96-127">Possibilité de précharger le contenu associé à une invitation à une réunion Outlook à Skype pour les réunions d’entreprise en ligne est activé par défaut, mais vous devrez peut-être empêcher les utilisateurs de votre organisation de précharger le contenu de leurs réunions.</span><span class="sxs-lookup"><span data-stu-id="78f96-127">Being able to preload content attached to an Outlook meeting invitation to Skype for Business Online meetings is turned on by default, but you may need to prevent users in your organization from preloading content in their meetings.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="78f96-128">Ce paramètre ne peut être activé ou non pour l’ensemble de votre organisation ; Vous ne pouvez pas l’activer ou la désactiver pour un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="78f96-128">This setting can only be turned on or off for your entire organization; you can't turn it on or off for a single user.</span></span> 
  
 <span data-ttu-id="78f96-129">**Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="78f96-129">**To turn it off, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 <span data-ttu-id="78f96-130">**Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**</span><span class="sxs-lookup"><span data-stu-id="78f96-130">**If you want to turn it back on, open Windows PowerShell and do the following:**</span></span>
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78f96-131">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="78f96-131">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="78f96-p105">Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="78f96-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="78f96-135">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="78f96-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="78f96-136">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="78f96-136">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="78f96-p106">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="78f96-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="78f96-139">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="78f96-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="78f96-140">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="78f96-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="78f96-141">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="78f96-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="78f96-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="78f96-142">Related topics</span></span>
[<span data-ttu-id="78f96-143">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="78f96-143">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="78f96-144">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="78f96-144">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="78f96-145">Commentaires ?</span><span class="sxs-lookup"><span data-stu-id="78f96-145">Feedback?</span></span>
<span data-ttu-id="78f96-146">Pour fournir des commentaires sur le produit ou pour nous faire savoir comment nous faisons, consultez [Skype pour les commentaires de l’entreprise](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="78f96-146">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>