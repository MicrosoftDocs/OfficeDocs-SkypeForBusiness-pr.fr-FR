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
description: Pour que les membres de votre organisation peuvent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un partenaire Microsoft pour effectuer cette étape pour vous.
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568890"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="a8f1d-105">Activer une diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="a8f1d-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8f1d-106">Skype Entreprise Online prend fin le 31 juillet 2021, date à laquelle l’accès au service prendra fin.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="a8f1d-107">Nous encourageons les clients à commencer la mise à niveau vers Microsoft Teams, le client principal pour les communications et le travail d’équipe dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="a8f1d-108">Pour que les membres de votre organisation peuvent utiliser la diffusion de réunion Skype, vous devez l’activer.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="a8f1d-109">Pour ce faire, vous devez savoir comment utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="a8f1d-110">Si vous ne connaissez pas Windows PowerShell, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="a8f1d-111">Le Centre d’administration Microsoft Teams a remplacé le Centre d’administration Skype Entreprise (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a8f1d-112">Tous les paramètres de gestion de Skype Entreprise sont désormais dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a8f1d-113">Pour gérer les fonctionnalités de Skype Entreprise dans le Centre d’administration Teams, vous devez avoir le rôle d’administrateur [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) d’administrateur global ou d’administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="a8f1d-114">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="a8f1d-115">Activer la diffusion de réunion Skype au moyen du Centre d'administration de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a8f1d-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="a8f1d-116">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="a8f1d-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a8f1d-117">Connectez-vous à l’adresse : votre compte d’administrateur global ou votre compte d’administrateur Skype [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="a8f1d-118">Dans le Centre d’administration, allez dans Centres **d’administration**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="a8f1d-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="a8f1d-119">Dans le Centre **d’administration Teams,** sélectionnez **Diffusion** de réunion via le portail hérité, puis sélectionnez Activer la diffusion  >    >  de **réunion Skype.**</span><span class="sxs-lookup"><span data-stu-id="a8f1d-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="a8f1d-120">Activer la diffusion de réunion Skype avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8f1d-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="a8f1d-121">Installez le [module Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="a8f1d-121">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="a8f1d-122">Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a8f1d-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="a8f1d-123">Confirmez votre configuration Diffusion de réunion Skype actuelle en exécutant :</span><span class="sxs-lookup"><span data-stu-id="a8f1d-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="a8f1d-124">Vérifiez que le paramètre  _EnableBroadcastMeeting_ est défini sur `False`.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="a8f1d-126">Activez Diffusion de réunion Skype pour votre organisation en exécutant :</span><span class="sxs-lookup"><span data-stu-id="a8f1d-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="a8f1d-127">Vous pouvez vérifier que le paramètre est activé en le exécutant  `Get-CsBroadcastMeetingConfiguration` à nouveau.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Applet de commande d'activation de la diffusion de réunion Skype pour votre organisation.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="a8f1d-129">Une fois la modification effectuée, sa prise en compte sur le portail Diffusion de réunion Skype peut prendre jusqu'à une heure.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="a8f1d-p105">Vos utilisateurs peuvent à présent organiser des réunions diffusées avec d'autres utilisateurs dans votre entreprise. Pour commencer, dirigez-les vers [Qu'est-ce qu'une diffusion de réunion Skype ?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="a8f1d-132">Configurer votre réseau pour la diffusion de réunions à des participants externes</span><span class="sxs-lookup"><span data-stu-id="a8f1d-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="a8f1d-133">Si vous avez un pare-feu, et que vous souhaitez héberger des diffusions pour des personnes extérieures à votre entreprise (qui n'est pas une entreprise fédérée), vous devez configurer votre réseau avec les instructions suivantes : [Configurer votre réseau pour la Diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="a8f1d-134">Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="a8f1d-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="a8f1d-135">Pour ignorer cette étape et ajouter une autre entreprise à votre fédération, consultez [Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="a8f1d-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="a8f1d-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8f1d-136">Related topics</span></span>

[<span data-ttu-id="a8f1d-137">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a8f1d-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="a8f1d-138">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a8f1d-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
