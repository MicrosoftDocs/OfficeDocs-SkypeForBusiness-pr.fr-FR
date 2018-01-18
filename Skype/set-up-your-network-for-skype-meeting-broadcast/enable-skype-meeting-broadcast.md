---
title: "Activer la diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Que les personnes de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer. Pour ce faire, vous devez savoir comment utiliser Windows PowerShell. Si vous ne connaissez pas Windows PowerShell, songez à faire appel à un partenaire de Microsoft d’effectuer cette étape pour vous."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="ae1fe-105">Activer la diffusion de réunion Skype</span><span class="sxs-lookup"><span data-stu-id="ae1fe-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="ae1fe-106">Que les personnes de votre organisation puissent utiliser la diffusion de réunion Skype, vous devez l’activer.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="ae1fe-107">Pour ce faire, vous devez savoir comment utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="ae1fe-108">Si vous ne connaissez pas Windows PowerShell, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ae1fe-109">Diffusion de réunion Skype est désactivée par défaut car la distribution du contenu multimédia d’une réunion de diffusion utilise un réseau de livraison de contenu (CDN de Microsoft Azure) pour atteindre une échelle très élevée pour la prise en charge des milliers de personnes Assistant à une diffusion.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="ae1fe-110">Le contenu du média mémorisé en bloc passant par le CDN est crypté, et le cache CDN a une durée de vie limitée.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="ae1fe-111">En outre, le composant Azure CDN ne répondent pas encore aux tous les éléments des Clauses de modèle de l’Union européenne qui découlent de la Directive de Protection des données de l’Union européenne.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="ae1fe-112">En activant cette fonctionnalité, vous reconnaissez cet avis.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="ae1fe-113">Activer la diffusion de réunion Skype à l’aide de la Skype pour le centre d’administration Business</span><span class="sxs-lookup"><span data-stu-id="ae1fe-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="ae1fe-114">Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="ae1fe-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="ae1fe-115">Dans le centre d’administration d’Office 365, accédez au **Centre d’administration** > **Skype pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ae1fe-116">Dans le **Skype pour Business admin center**, accédez à **des réunions en ligne** > **réunions de diffusion**, puis sélectionnez **Activer la diffusion de réunion Skype**.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="ae1fe-117">Activer la diffusion de réunion Skype à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae1fe-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="ae1fe-118">Vérifiez que vous exécutez la version 3.0 ou ultérieure de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="ae1fe-119">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ae1fe-120">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ae1fe-p104">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ae1fe-p105">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="ae1fe-127">Dans le **Menu Démarrer**, choisissez **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="ae1fe-128">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="ae1fe-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="ae1fe-129">Vérifiez votre configuration en cours de diffusion de réunion Skype en exécutant :</span><span class="sxs-lookup"><span data-stu-id="ae1fe-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="ae1fe-130">Vérifiez que le paramètre _EnableBroadcastMeeting_ est défini sur `False`.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Applet de commande Skype réunion de diffusion activer l’organisation.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="ae1fe-132">Activer la diffusion de réunion Skype pour votre organisation en exécutant :</span><span class="sxs-lookup"><span data-stu-id="ae1fe-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="ae1fe-133">Vous pouvez vérifier que le paramètre est activé en exécutant `Get-CsBroadcastMeetingConfiguration` à nouveau.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Activer de la Cmdlet de l’organisation de la diffusion de réunion Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="ae1fe-135">Après avoir apporté la modification, il peut prendre une heure soient prises en compte dans le portail de diffusion de réunion Skype.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="ae1fe-136">Vos utilisateurs peuvent maintenant organiser des réunions de diffusion avec d’autres utilisateurs dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="ae1fe-137">Pour obtenir leur démarrage, les pointer vers [ce qu’est une diffusion de réunion Skype ?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="ae1fe-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="ae1fe-138">Configurez votre réseau pour la diffusion des réunions avec des participants externes</span><span class="sxs-lookup"><span data-stu-id="ae1fe-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="ae1fe-139">Si vous disposez d’un pare-feu et que vous souhaitez avoir des diffusions avec des personnes en dehors de votre entreprise (qui ne sont pas une entreprise fédérée), vous devez configurer votre réseau à l’aide de ces instructions : [configurer votre réseau de diffusion de réunion Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="ae1fe-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="ae1fe-140">Si vous n’êtes pas familiarisé avec la configuration de votre pare-feu, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.</span><span class="sxs-lookup"><span data-stu-id="ae1fe-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="ae1fe-141">Pour ignorer cette étape et l’ajouter à la place d’une autre entreprise de votre fédération, reportez-vous à la section [Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="ae1fe-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="ae1fe-142">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ae1fe-142">Related topics</span></span>

[<span data-ttu-id="ae1fe-143">Présentation de Windows PowerShell et de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ae1fe-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="ae1fe-144">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="ae1fe-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

