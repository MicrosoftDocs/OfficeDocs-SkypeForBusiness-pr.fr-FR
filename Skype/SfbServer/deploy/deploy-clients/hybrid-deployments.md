---
title: Déploiements hybrides de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219674"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="f10d6-103">Déploiements hybrides de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="f10d6-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="f10d6-104">Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="f10d6-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="f10d6-105">Déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="f10d6-105">Hybrid deployments</span></span>

<span data-ttu-id="f10d6-106">Procédez comme suit si votre topologie comporte Skype entreprise Server et Exchange Online, et que vous voulez héberger la boîte aux lettres de ressources Skype Room System sur Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f10d6-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="f10d6-107">Cette section couvre également un scénario hybride dans lequel vous avez déployé Exchange Online et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f10d6-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="f10d6-108">À des fins d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.</span><span class="sxs-lookup"><span data-stu-id="f10d6-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="f10d6-109">Créez une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) en vous connectant à Exchange Online Management Shell comme décrit dans Exchange Online Provisioning.</span><span class="sxs-lookup"><span data-stu-id="f10d6-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="f10d6-110">Vous pouvez vérifier la connectivité OWA à l’aide de lrstest5@LyncSample.ccsctp.net pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f10d6-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="f10d6-111">Dans le centre d’administration Exchange de Microsoft 365 ou Office 365, ajoutez une adresse de messagerie lrstest5@LyncSample.com (domaine local) et définissez-la comme adresse de réponse.</span><span class="sxs-lookup"><span data-stu-id="f10d6-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="f10d6-112">Créez un lrstest5@LyncSample.com d’utilisateur Active Directory sur local, définissez l’adresse de messagerie sur lrstest5@LyncSample.com et définissez l’adresse cible sur lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="f10d6-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="f10d6-113">Déclenchez la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs fusionnent dans AAD et que vous ne pouvez pas modifier les propriétés dans les ressources du destinataire dans le centre d’administration Exchange de Microsoft 365 ou d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="f10d6-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="f10d6-114">Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="f10d6-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="f10d6-115">(Précédemment, vous avez vérifié la connectivité OWA à l’aide du domaine en ligne.)</span><span class="sxs-lookup"><span data-stu-id="f10d6-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="f10d6-116">Après avoir créé la boîte aux lettres, vous pouvez utiliser SET-CalendarProcessing sur Exchange Online Management Shell pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="f10d6-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="f10d6-117">Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous déploiements de forêt unique sur-local.</span><span class="sxs-lookup"><span data-stu-id="f10d6-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="f10d6-118">Si vous disposez d’un environnement hybride avec Exchange Server et Exchange Online, accédez à l’environnement de ligne de commande Exchange Management Shell et activez-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="f10d6-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="f10d6-119">Puis déclenchez la synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="f10d6-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="f10d6-120">Si vous voulez héberger la boîte aux lettres de Skype Room System dans Exchange Online, ces étapes de l’environnement de ligne de commande Exchange Management Shell ne sont pas requises et vous pouvez passer à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="f10d6-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="f10d6-121">Activez le compte Skype Room System pour Skype entreprise en exécutant l’applet de commande suivante sur Skype entreprise Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f10d6-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="f10d6-122">Si vous avez Skype entreprise Online au lieu de Skype entreprise Server dans le scénario ci-dessus, après avoir configuré la boîte aux lettres de ressources Exchange, configurez un compte Skype entreprise comme décrit dans Skype entreprise Online Provisioning.</span><span class="sxs-lookup"><span data-stu-id="f10d6-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

