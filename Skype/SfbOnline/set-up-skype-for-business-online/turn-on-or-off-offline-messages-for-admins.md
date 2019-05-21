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
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 9f7786e636ba49d6327486a11683e26799c01cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284933"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="91122-103">Activation ou désactivation des messages hors connexion pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="91122-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="91122-104">Vous pouvez envoyer des messages instantanés Skype entreprise à vos contacts même s’ils ne sont pas connectés.</span><span class="sxs-lookup"><span data-stu-id="91122-104">You can send Skype for Business IMs to your contacts even if they aren't signed in.</span></span> <span data-ttu-id="91122-105">Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé d’y accéder.</span><span class="sxs-lookup"><span data-stu-id="91122-105">This feature lets your contacts know that you have been trying to reach them.</span></span> <span data-ttu-id="91122-106">Vous n’avez pas besoin d’attendre qu’une personne reste en ligne avant de lui envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="91122-106">You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="91122-107">Pour les messages hors connexion, il est important de savoir que :</span><span class="sxs-lookup"><span data-stu-id="91122-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="91122-108">les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="91122-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="91122-109">Les messages hors connexion seront envoyés dans la boîte aux lettres de l’utilisateur, et l’utilisateur est averti dès qu’il se connecte à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="91122-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="91122-110">Si le statut du destinataire du message est défini sur **ne pas** déranger ou en **Présentation**, il recevra un message manqué, envoyé par le client Skype entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="91122-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="91122-111">Pour plus d’informations, reportez-vous à la rubrique [utilisation de la messagerie hors connexion dans Skype entreprise](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="91122-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="91122-112">Pour commencer</span><span class="sxs-lookup"><span data-stu-id="91122-112">To get you started</span></span>

## #

 <span data-ttu-id="91122-113">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="91122-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="91122-114">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="91122-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="91122-115">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="91122-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="91122-p102">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="91122-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="91122-p103">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="91122-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>

<span data-ttu-id="91122-122">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="91122-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="91122-123">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="91122-123">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="91122-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="91122-124">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="91122-125">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="91122-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="91122-126">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="91122-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="91122-127">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="91122-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="91122-128">Activation ou désactivation de la messagerie instantanée hors connexion</span><span class="sxs-lookup"><span data-stu-id="91122-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="91122-129">Les messages hors connexion ne sont disponibles **que** dans la dernière version du client «démarrer en un clic» de Skype entreprise et ne sont pas disponibles lorsqu’une version antérieure de Skype entreprise est utilisée ou qu’un fichier \*. msi a été utilisé pour installer le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="91122-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="91122-130">Pour activer ou désactiver les messages hors connexion pour les utilisateurs de votre organisation qui envoient `True` des `False`messages hors connexion, définissez _EnableIMAutoArchiving_ sur ou.</span><span class="sxs-lookup"><span data-stu-id="91122-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="91122-131">Par défaut, ce paramètre est défini `True`sur.</span><span class="sxs-lookup"><span data-stu-id="91122-131">By default, this is set to `True`.</span></span>

<span data-ttu-id="91122-132">Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :</span><span class="sxs-lookup"><span data-stu-id="91122-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="91122-133">Pour activer ou désactiver les messages hors connexion pour les utilisateurs qui envoient des `True` messages `False`hors connexion, définissez _EnableIMAutoArchiving_ sur ou.</span><span class="sxs-lookup"><span data-stu-id="91122-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="91122-134">Par défaut, cette option est définie sur  `True`.</span><span class="sxs-lookup"><span data-stu-id="91122-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="91122-135">Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="91122-135">You can use an existing policy or create one like the example below.</span></span>


  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="91122-136">Vous souhaitez en savoir plus sur Windows PowerShell ?</span><span class="sxs-lookup"><span data-stu-id="91122-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="91122-137">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="91122-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="91122-138">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="91122-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="91122-139">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="91122-139">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="91122-140">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="91122-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="91122-141">Six raisons d'utiliser Windows PowerShell pour gérer Office 365 </span><span class="sxs-lookup"><span data-stu-id="91122-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="91122-p107">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="91122-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="91122-144">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91122-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="91122-145">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="91122-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="91122-146">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="91122-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="91122-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91122-147">Related topics</span></span>
[<span data-ttu-id="91122-148">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="91122-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="91122-149">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="91122-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


