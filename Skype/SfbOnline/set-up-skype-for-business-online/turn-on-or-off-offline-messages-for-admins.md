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
ms.openlocfilehash: fc340cff109d33a3a5afeaf6b1b2b09ae7f6ba3b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239160"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="0c836-103">Activation ou désactivation des messages hors connexion pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="0c836-103">Turn on or off Offline Messages for admins</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="0c836-104">Vous pouvez envoyer Skype Entreprise messages à vos contacts, même s’ils ne sont pas encore inscrits.</span><span class="sxs-lookup"><span data-stu-id="0c836-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="0c836-105">Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé de les joindre.</span><span class="sxs-lookup"><span data-stu-id="0c836-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="0c836-106">Vous n’avez pas à attendre qu’une personne soit en ligne pour lui envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="0c836-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="0c836-107">Pour les messages hors connexion, il est important de savoir que :</span><span class="sxs-lookup"><span data-stu-id="0c836-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="0c836-108">les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="0c836-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="0c836-109">Les messages hors connexion sont envoyés vers la boîte aux lettres de l’utilisateur, et il est averti lorsqu’il se connecte Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c836-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="0c836-110">Si le statut du destinataire  du message est Ne pas déranger ou En **présentation,** il reçoit un message manqué envoyé par le client de réception Skype Entreprise destinataire.</span><span class="sxs-lookup"><span data-stu-id="0c836-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="0c836-111">Pour plus d’informations, [voir Utiliser la messagerie hors connexion dans Skype Entreprise.](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)</span><span class="sxs-lookup"><span data-stu-id="0c836-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="0c836-112">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="0c836-112">To get you started</span></span>

> [!NOTE]
> <span data-ttu-id="0c836-113">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="0c836-113">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0c836-114">Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="0c836-114">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="0c836-115">Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="0c836-115">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0c836-116">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c836-116">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
<span data-ttu-id="0c836-117">Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter à tous les [services Office 365 dans](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="0c836-117">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="0c836-118">Activation ou désactivation de la messagerie instantanée hors connexion</span><span class="sxs-lookup"><span data-stu-id="0c836-118">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="0c836-119">Les messages  hors connexion ne sont disponibles que dans la dernière version du client Skype Entreprise « Exécuter en un clic » et ne le sont pas lorsqu’une ancienne Skype Entreprise « Exécuter en un clic » est utilisée ou qu’un fichier \*.msi a été utilisé pour installer le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c836-119">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="0c836-120">Pour activer ou désactiver l’envoi de messages hors connexion aux utilisateurs de votre organisation, définissez  _EnableIMAutoArchiving_ sur `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="0c836-120">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="0c836-121">Par défaut, cette option est définie sur `True` .</span><span class="sxs-lookup"><span data-stu-id="0c836-121">By default, this is set to `True`.</span></span>

<span data-ttu-id="0c836-122">Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :</span><span class="sxs-lookup"><span data-stu-id="0c836-122">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="0c836-123">Pour activer ou désactiver l’envoi de messages hors connexion à un utilisateur, définissez  _EnableIMAutoArchiving sur_ `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="0c836-123">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="0c836-124">Par défaut, cette option est définie sur  `True`.</span><span class="sxs-lookup"><span data-stu-id="0c836-124">By default, this is set to  `True`.</span></span> <span data-ttu-id="0c836-125">Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0c836-125">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0c836-126">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="0c836-126">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="0c836-127">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0c836-127">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0c836-128">Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes.</span><span class="sxs-lookup"><span data-stu-id="0c836-128">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="0c836-129">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="0c836-129">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="0c836-130">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c836-130">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="0c836-131">Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365</span><span class="sxs-lookup"><span data-stu-id="0c836-131">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="0c836-132">Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="0c836-132">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="0c836-133">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c836-133">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="0c836-134">[Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0c836-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="0c836-135">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c836-135">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="0c836-136">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c836-136">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="0c836-137">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0c836-137">Related topics</span></span>
[<span data-ttu-id="0c836-138">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="0c836-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0c836-139">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="0c836-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
