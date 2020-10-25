---
title: Activer une diffusion de réunion Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
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
- SMB
description: Pour que les membres de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour cela, vous devez savoir comment utiliser Windows PowerShell. Si vous ne savez pas Windows PowerShell, envisagez d’utiliser un partenaire Microsoft pour cette étape.
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753429"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="6d160-105">Activer une diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="6d160-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d160-106">Le centre d’administration Microsoft teams a remplacé le centre d’administration Skype entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="6d160-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="6d160-107">Tous les paramètres de gestion de Skype entreprise se trouvent désormais dans le centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="6d160-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="6d160-108">Pour pouvoir gérer les fonctionnalités Skype entreprise dans le centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de l’administrateur général ou de l’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d160-108">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="6d160-109">Pour en savoir plus, voir [gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="6d160-109">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="6d160-110">Pour que les membres de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer.</span><span class="sxs-lookup"><span data-stu-id="6d160-110">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="6d160-111">Pour cela, vous devez savoir comment utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d160-111">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="6d160-112">Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="6d160-112">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="6d160-113">Activer la diffusion de réunion Skype au moyen du Centre d'administration de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="6d160-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="6d160-114">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="6d160-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="6d160-115">Connectez-vous à l’aide de votre compte d’administrateur général ou du compte d’administrateur de Skype entreprise [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="6d160-115">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="6d160-116">Dans le centre d’administration, accédez **à centre d’administration**  >  **teams**.</span><span class="sxs-lookup"><span data-stu-id="6d160-116">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="6d160-117">Dans le **Centre d’administration teams**, accédez à réunions d' **ancienneté du portail**  >  **en ligne**  >  **Broadcast meetings**, puis sélectionnez **activer la diffusion de réunion Skype**.</span><span class="sxs-lookup"><span data-stu-id="6d160-117">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="6d160-118">Activer la diffusion de réunion Skype avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d160-118">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="6d160-119">Vérifiez que vous exécutez la version 3.0 ou supérieure de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d160-119">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6d160-120">Pour vérifier que vous exécutez la version 3.0 ou supérieure : cliquez sur **Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6d160-120">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="6d160-121">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6d160-121">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="6d160-122">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d160-122">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6d160-123">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="6d160-123">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="6d160-124">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="6d160-124">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="6d160-p105">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="6d160-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="6d160-128">Dans le **menu Démarrer**, sélectionnez **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6d160-128">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="6d160-129">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="6d160-129">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="6d160-130">Confirmez votre configuration Diffusion de réunion Skype actuelle en exécutant :</span><span class="sxs-lookup"><span data-stu-id="6d160-130">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="6d160-131">Vérifiez que le paramètre  _EnableBroadcastMeeting_ est défini sur `False`.</span><span class="sxs-lookup"><span data-stu-id="6d160-131">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="6d160-133">Activez Diffusion de réunion Skype pour votre organisation en exécutant :</span><span class="sxs-lookup"><span data-stu-id="6d160-133">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="6d160-134">Vous pouvez vérifier que le paramètre est activé en exécutant de  `Get-CsBroadcastMeetingConfiguration` nouveau.</span><span class="sxs-lookup"><span data-stu-id="6d160-134">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="6d160-136">Une fois la modification effectuée, sa prise en compte sur le portail Diffusion de réunion Skype peut prendre jusqu'à une heure.</span><span class="sxs-lookup"><span data-stu-id="6d160-136">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="6d160-p106">Vos utilisateurs peuvent à présent organiser des réunions diffusées avec d'autres utilisateurs dans votre entreprise. Pour commencer, dirigez-les vers [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).</span><span class="sxs-lookup"><span data-stu-id="6d160-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="6d160-139">Configurer votre réseau pour la diffusion de réunions à des participants externes</span><span class="sxs-lookup"><span data-stu-id="6d160-139">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="6d160-140">Si vous avez un pare-feu, et que vous souhaitez héberger des diffusions pour des personnes extérieures à votre entreprise (qui n'est pas une entreprise fédérée), vous devez configurer votre réseau avec les instructions suivantes : [Configurer votre réseau pour la Diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="6d160-140">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="6d160-141">Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="6d160-141">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="6d160-142">Pour ignorer cette étape et ajouter une autre entreprise à votre fédération, consultez [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="6d160-142">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="6d160-143">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6d160-143">Related topics</span></span>

[<span data-ttu-id="6d160-144">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6d160-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="6d160-145">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6d160-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
