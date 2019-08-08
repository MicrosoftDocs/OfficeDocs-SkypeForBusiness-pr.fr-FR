---
title: Déploiements hybrides de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Pour plus d’informations sur le déploiement de votre système de salle Skype dans un environnement hybride, lisez cette rubrique.
ms.openlocfilehash: 016a4cf379200dc87b8f94d13a65f10f6c3af25f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234428"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="91fc1-103">Déploiements hybrides de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="91fc1-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="91fc1-104">Pour plus d’informations sur le déploiement de votre système de salle Skype dans un environnement hybride, lisez cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="91fc1-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="91fc1-105">Déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="91fc1-105">Hybrid deployments</span></span>

<span data-ttu-id="91fc1-106">Suivez ces étapes si votre topologie utilise Skype entreprise Server et Exchange Online et si vous souhaitez héberger la boîte aux lettres de ressources du système de salle Skype sur Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="91fc1-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="91fc1-107">Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fc1-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="91fc1-108">Pour des raisons d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.</span><span class="sxs-lookup"><span data-stu-id="91fc1-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="91fc1-109">Pour créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net), connectez-vous à Exchange Online Management Shell comme décrit dans la rubrique mise en service d’Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="91fc1-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="91fc1-110">Vous pouvez vérifier la connectivité OWA à l’aide de lrstest5@LyncSample.ccsctp.net pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="91fc1-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="91fc1-111">Dans le centre d’administration Exchange d’Office 365, ajoutez une adresse de messagerie lrstest5@LyncSample.com (domaine locaux), puis définissez-la comme adresse de réponse.</span><span class="sxs-lookup"><span data-stu-id="91fc1-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="91fc1-112">Créez un lrstest5@LyncSample.com de l’utilisateur Active Directory locaux, définissez l’adresse de messagerie sur lrstest5@LyncSample.com et définissez l’adresse cible sur lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="91fc1-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="91fc1-113">Déclenchez la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs effectuent une fusion dans AAD et que vous ne pouvez pas modifier les propriétés des ressources du destinataire dans le centre d’administration Exchange d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="91fc1-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="91fc1-114">Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="91fc1-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="91fc1-115">(Auparavant, vous avez vérifié la connectivité OWA à l’aide du domaine en ligne.)</span><span class="sxs-lookup"><span data-stu-id="91fc1-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="91fc1-p103">Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="91fc1-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="91fc1-118">Si vous avez un environnement hybride avec Exchange Server et Exchange Online, accédez à Exchange Management Shell et activez-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-salle.</span><span class="sxs-lookup"><span data-stu-id="91fc1-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="91fc1-119">Puis enclenchez la synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="91fc1-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="91fc1-120">Si vous souhaitez héberger la boîte aux lettres du système de salle Skype dans Exchange Online, ces étapes de l’interpréteur de tâches Exchange Management ne sont pas nécessaires et vous pouvez passer à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="91fc1-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="91fc1-121">Activez le compte système de salle Skype pour Skype entreprise en exécutant l’applet de commande suivante sur Skype entreprise Management Shell:</span><span class="sxs-lookup"><span data-stu-id="91fc1-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="91fc1-122">Si vous disposez de Skype entreprise Online au lieu de Skype entreprise Server dans le scénario ci-dessus, après la configuration de la boîte aux lettres de ressources Exchange, approvisionnez un compte Skype entreprise comme décrit dans la rubrique mise en service de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="91fc1-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

