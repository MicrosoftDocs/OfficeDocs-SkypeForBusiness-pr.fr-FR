---
title: Déploiements hybrides de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour savoir comment déployer Skype salle système dans un environnement hybride.
ms.openlocfilehash: 4e73b182f7e957f6f8a45e2ba0ccaa113a96411f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375279"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="13ecd-103">Déploiements hybrides de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="13ecd-103">Skype Room System hybrid deployments</span></span>
 
<span data-ttu-id="13ecd-104">Lisez cette rubrique pour savoir comment déployer Skype salle système dans un environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="13ecd-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="13ecd-105">Déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="13ecd-105">Hybrid deployments</span></span>

<span data-ttu-id="13ecd-106">Si votre topologie a Skype pour Business Server et Exchange Online, et que vous souhaitez héberger la boîte aux lettres de ressources système de salle Skype dans Exchange Online, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="13ecd-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="13ecd-107">Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="13ecd-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="13ecd-108">À des fins d’illustration, nous utilisons LyncSample.com pour le domaine local et LyncSample.ccstp.net pour le domaine en ligne.</span><span class="sxs-lookup"><span data-stu-id="13ecd-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="13ecd-109">Créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) à se connecter à Exchange Online Management shell, comme décrit dans la mise en service en ligne d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="13ecd-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="13ecd-110">Vous pouvez vérifier la connectivité OWA pour se connecter à l’aide de lrstest5@LyncSample.ccsctp.net.</span><span class="sxs-lookup"><span data-stu-id="13ecd-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="13ecd-111">Dans le centre d’administration Office 365 Exchange, ajouter un e-mail adresse lrstest5@LyncSample.com (domaine sur prem) et le définir comme adresse de réponse.</span><span class="sxs-lookup"><span data-stu-id="13ecd-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="13ecd-112">Créer un sur prem Active Directory utilisateur lrstest5@LyncSample.com, définir l’adresse de messagerie à lrstest5@LyncSample.com et définir l’adresse cible à lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="13ecd-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="13ecd-113">Déclenche la synchronisation d’annuaires et, une fois la synchronisation terminée, vérifiez que les utilisateurs de fusion dans DAS et que vous n’êtes pas en mesure de modifier les propriétés dans les ressources du destinataire dans le centre d’administration Exchange Office 365.</span><span class="sxs-lookup"><span data-stu-id="13ecd-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="13ecd-114">Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="13ecd-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="13ecd-115">(Précédemment, vous vérifié la connectivité OWA à l’aide du domaine en ligne.)</span><span class="sxs-lookup"><span data-stu-id="13ecd-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="13ecd-p103">Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="13ecd-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="13ecd-118">Si vous avez un environnement hybride avec Exchange Server et Exchange Online, accédez à la lrstest5@LyncSample.mail.ccsctp.net Exchange Management Shell et Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress-salle.</span><span class="sxs-lookup"><span data-stu-id="13ecd-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="13ecd-119">Puis enclenchez la synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="13ecd-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="13ecd-120">Si vous souhaitez héberger la boîte aux lettres système de salle Skype dans Exchange Online, ces étapes Exchange Management Shell ne sont pas requis et vous pouvez passer à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="13ecd-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="13ecd-121">Activer le compte de système de salle Skype pour Skype pour les entreprises en exécutant l’applet de commande suivante sur Skype pour Business Management Shell :</span><span class="sxs-lookup"><span data-stu-id="13ecd-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="13ecd-122">Si vous avez Skype pour Business Online au lieu de Skype pour Business Server dans l’exemple ci-dessus, après la mise en service de la boîte aux lettres de ressources Exchange, configurer un Skype pour un compte professionnel comme indiqué dans Skype pour la mise en service en ligne de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="13ecd-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

