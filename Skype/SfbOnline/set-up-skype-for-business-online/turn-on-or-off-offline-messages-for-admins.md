---
title: Activation ou désactivation des messages hors connexion pour les administrateurs
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814603"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="8a136-103">Activation ou désactivation des messages hors connexion pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="8a136-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="8a136-p101">Vous pouvez envoyer des messages instantanés Skype entreprise à vos contacts même s’ils ne sont pas connectés. Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé d’y accéder. Vous n’avez pas besoin d’attendre qu’une personne reste en ligne avant de lui envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="8a136-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="8a136-107">Pour les messages hors connexion, il est important de savoir que :</span><span class="sxs-lookup"><span data-stu-id="8a136-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="8a136-108">les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="8a136-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="8a136-109">Les messages hors connexion seront envoyés dans la boîte aux lettres de l’utilisateur, et l’utilisateur est averti dès qu’il se connecte à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="8a136-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="8a136-110">Si le statut du destinataire du message est défini sur **ne pas déranger** ou en **Présentation**, il recevra un message manqué, envoyé par le client Skype entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="8a136-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="8a136-111">Pour plus d’informations, reportez-vous à la rubrique [utilisation de la messagerie hors connexion dans Skype entreprise](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="8a136-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="8a136-112">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="8a136-112">To get you started</span></span>

## #

 <span data-ttu-id="8a136-113">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8a136-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="8a136-114">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8a136-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="8a136-115">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8a136-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="8a136-116">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a136-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="8a136-117">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="8a136-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="8a136-118">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="8a136-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="8a136-119">Vous devrez également installer le module Windows PowerShell pour les équipes qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="8a136-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="8a136-120">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a136-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="8a136-121">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8a136-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="8a136-122">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8a136-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="8a136-123">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="8a136-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="8a136-124">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="8a136-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="8a136-125">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="8a136-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="8a136-126">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8a136-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="8a136-127">Activation ou désactivation de la messagerie instantanée hors connexion</span><span class="sxs-lookup"><span data-stu-id="8a136-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="8a136-128">Les messages hors connexion ne sont disponibles **que** dans la dernière version du client « démarrer en un clic » de Skype entreprise et ne sont pas disponibles lorsqu’une version antérieure de Skype entreprise est utilisée ou qu’un fichier \*. msi a été utilisé pour installer le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="8a136-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="8a136-129">Pour activer ou désactiver les messages hors connexion pour les utilisateurs de votre organisation qui envoient des messages hors connexion, définissez  _EnableIMAutoArchiving_ sur `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="8a136-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="8a136-130">Par défaut, ce paramètre est défini sur `True` .</span><span class="sxs-lookup"><span data-stu-id="8a136-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="8a136-131">Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :</span><span class="sxs-lookup"><span data-stu-id="8a136-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="8a136-132">Pour activer ou désactiver les messages hors connexion pour les utilisateurs qui envoient des messages hors connexion, définissez  _EnableIMAutoArchiving_ sur `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="8a136-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="8a136-133">Par défaut, cette option est définie sur  `True`.</span><span class="sxs-lookup"><span data-stu-id="8a136-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="8a136-134">Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8a136-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8a136-135">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="8a136-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="8a136-136">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="8a136-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8a136-137">Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="8a136-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8a136-138">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="8a136-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="8a136-139">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8a136-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="8a136-140">Six raisons d’utiliser Windows PowerShell pour gérer Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="8a136-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="8a136-141">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="8a136-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8a136-142">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8a136-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="8a136-143">Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a136-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="8a136-144">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8a136-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="8a136-145">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8a136-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="8a136-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a136-146">Related topics</span></span>
[<span data-ttu-id="8a136-147">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8a136-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8a136-148">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="8a136-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


