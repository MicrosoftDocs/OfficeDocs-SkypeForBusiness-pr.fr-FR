---
title: Déploiements hybrides de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lisez cette rubrique pour savoir comment déployer le système d’espace Skype dans un environnement hybride.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="46cc8-103">Déploiements hybrides de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="46cc8-103">Skype Room System hybrid deployments</span></span>
 
<span data-ttu-id="46cc8-104">Lisez cette rubrique pour savoir comment déployer le système d’espace Skype dans un environnement hybride.</span><span class="sxs-lookup"><span data-stu-id="46cc8-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="46cc8-105">Déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="46cc8-105">Hybrid deployments</span></span>

<span data-ttu-id="46cc8-106">Si votre topologie inclut Skype pour Business Server et Exchange Online, et que vous souhaitez héberger la boîte aux lettres de ressource système de salle Skype sur Exchange Online, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="46cc8-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="46cc8-107">Cette section décrit également un scénario hybride où vous avez déployé à la fois Exchange Online et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="46cc8-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="46cc8-108">À des fins d’illustration, nous utilisons LyncSample.com pour le domaine de locaux et LyncSample.ccstp.net pour le domaine en ligne.</span><span class="sxs-lookup"><span data-stu-id="46cc8-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="46cc8-109">Créer une boîte aux lettres de ressources dans le centre d’administration Exchange (LyncSample.ccsctp.net) en vous connectant à l’interface de gestion en ligne d’Exchange, comme décrit dans la mise en service en ligne d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="46cc8-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    <span data-ttu-id="46cc8-110">Vous pouvez vérifier la connectivité OWA pour se connecter à l’aide de lrstest5@LyncSample.ccsctp.net.</span><span class="sxs-lookup"><span data-stu-id="46cc8-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="46cc8-111">Dans le centre d’administration Office 365 Exchange, ajouter un courrier électronique adresse lrstest5@LyncSample.com (domaine sur prem) et le définir comme adresse de réponse.</span><span class="sxs-lookup"><span data-stu-id="46cc8-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="46cc8-112">Créer une sous-prem Active Directory utilisateur lrstest5@LyncSample.com, la valeur lrstest5@LyncSample.com l’adresse de messagerie et l’adresse cible la valeur lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="46cc8-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="46cc8-113">Déclencher la synchronisation d’annuaire et, une fois la synchronisation terminée, vérifiez que les utilisateurs fusionner dans DAS et que vous n’êtes pas en mesure de modifier les propriétés des ressources de destinataire dans le centre d’administration Exchange d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="46cc8-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="46cc8-114">Vérifiez la connectivité OWA à l’aide de lrstest5@LyncSample.com. (Version antérieure, vous vérifiez la connectivité OWA en utilisant le domaine en ligne.)</span><span class="sxs-lookup"><span data-stu-id="46cc8-114">Verify OWA connectivity using lrstest5@LyncSample.com. (Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="46cc8-p102">Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing dans l’Exchange Online Management Shell pour configurer la boîte aux lettres. Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="46cc8-p102">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46cc8-117">Si vous disposez d’un environnement hybride avec Exchange Server et Exchange Online, accédez à le lrstest5@LyncSample.mail.ccsctp.net Exchange Management Shell et activer-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress-salle.</span><span class="sxs-lookup"><span data-stu-id="46cc8-117">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="46cc8-118">Puis enclenchez la synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="46cc8-118">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="46cc8-119">Si vous souhaitez héberger la boîte aux lettres système de salle Skype dans Exchange en ligne, ces étapes d’Exchange Management Shell ne sont pas nécessaires et vous pouvez passer à l’étape 6.</span><span class="sxs-lookup"><span data-stu-id="46cc8-119">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="46cc8-120">Activer le compte système local de Skype pour Skype pour entreprise en exécutant l’applet de commande suivant sur Skype pour Business Management Shell :</span><span class="sxs-lookup"><span data-stu-id="46cc8-120">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="46cc8-121">Si vous avez Skype pour entreprise en ligne au lieu de Skype pour Business Server dans le scénario ci-dessus, puis après la mise en service de la boîte aux lettres de ressources Exchange, mettre en service un Skype pour compte professionnel comme décrit dans Skype pour les professionnels de la mise en service en ligne.</span><span class="sxs-lookup"><span data-stu-id="46cc8-121">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

