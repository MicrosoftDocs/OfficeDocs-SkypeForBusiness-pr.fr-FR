---
title: Communiquer avec des utilisateurs de Teams dans une autre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Découvrez comment configurer teams pour permettre aux utilisateurs de communiquer avec des utilisateurs d’une autre organisation.
ms.openlocfilehash: d974197f6daedab030124dfc1117610e3504ae32
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433190"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="66eea-103">Permettre aux utilisateurs d’équipes de discuter et de communiquer avec les utilisateurs d’une autre organisation teams</span><span class="sxs-lookup"><span data-stu-id="66eea-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="66eea-104">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="66eea-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="66eea-105">Vous avez des utilisateurs dans différents domaines au sein de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="66eea-105">You have users in different domains in your business.</span></span> <span data-ttu-id="66eea-106">Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="66eea-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="66eea-107">Vous voulez que les membres de votre organisation puissent utiliser teams pour contacter des personnes dans des entreprises spécifiques en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="66eea-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="66eea-108">Vous voulez que les autres personnes qui utilisent des équipes puissent vous trouver et vous contacter à l’aide de votre adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="66eea-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="66eea-109">Par ailleurs, si vous et un autre utilisateur autorisez l’accès externe et autorisez les domaines de chacun d’eux, cela va fonctionner.</span><span class="sxs-lookup"><span data-stu-id="66eea-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="66eea-110">Si ce n’est pas le cas, l’autre utilisateur doit veiller à ce qu’il ne bloque pas votre domaine.</span><span class="sxs-lookup"><span data-stu-id="66eea-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="66eea-111">Cela permet aux utilisateurs de rechercher, appeler et envoyer des messages instantanés, ainsi que de configurer des réunions avec vous.</span><span class="sxs-lookup"><span data-stu-id="66eea-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="66eea-112">Si vous souhaitez que les utilisateurs externes aient accès à des équipes et des canaux, l’accès invité peut être une meilleure solution.</span><span class="sxs-lookup"><span data-stu-id="66eea-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="66eea-113">Suivez les étapes décrites dans cet article et assurez-vous d' [activer l’accès invité](set-up-guests.md) pour que les utilisateurs puissent communiquer.</span><span class="sxs-lookup"><span data-stu-id="66eea-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66eea-114">Pour que vous puissiez actuellement fédérer le client Microsoft teams à un utilisateur externe extérieur à votre organisation qui n’est pas un invité de votre client AAD ou de votre client, vous devez être correctement configuré pour l’environnement hybride et transféré vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="66eea-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="66eea-115">À partir de 2/25/2019, Teams ne prend pas encore en charge la Fédération native sans que l’utilisateur du profil SIP ne soit hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="66eea-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="66eea-116">Pour plus d’informations sur la configuration de votre compte hybride, puis celle-ci, reportez-vous à la rubrique [mise à niveau du déploiement hybride de Skype entreprise vers teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="66eea-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="66eea-117">Permettre aux utilisateurs d’équipes de discuter et de communiquer avec les utilisateurs d’une autre organisation teams</span><span class="sxs-lookup"><span data-stu-id="66eea-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="66eea-118">Procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="66eea-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="66eea-119">Étape 1: Veillez à configurer les ports et les URL nécessaires.</span><span class="sxs-lookup"><span data-stu-id="66eea-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="66eea-120">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="66eea-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="66eea-121">Étape 2: permettre à votre organisation de communiquer avec d’autres organisations teams</span><span class="sxs-lookup"><span data-stu-id="66eea-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="66eea-122">![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="66eea-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="66eea-123">Dans le volet de navigation de gauche, accédez à**accès externe aux** **paramètres** > à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="66eea-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="66eea-124">En haut de la page **accès externe** , cliquez sur **accès externe** à **activé**.</span><span class="sxs-lookup"><span data-stu-id="66eea-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="66eea-125">Si vous voulez autoriser toutes les organisations teams à communiquer avec les utilisateurs de votre organisation, passez à l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="66eea-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="66eea-126">Si vous souhaitez limiter les organisations qui peuvent communiquer avec des utilisateurs de votre organisation, vous pouvez autoriser tous les domaines sauf quelques domaines ou autoriser des organisations spécifiques uniquement.</span><span class="sxs-lookup"><span data-stu-id="66eea-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="66eea-127">Pour autoriser tout sauf quelques domaines, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**.</span><span class="sxs-lookup"><span data-stu-id="66eea-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="66eea-128">Dans le volet **Ajouter un domaine** , indiquez le nom de domaine, puis cliquez sur **bloqué** puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="66eea-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="66eea-129">Pour limiter les communications à des organizatioins spécifiques, ajoutez ces domaines à la liste avec un statut de **créance**.</span><span class="sxs-lookup"><span data-stu-id="66eea-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="66eea-130">Une fois que vous avez ajouté un domaine à la liste verte, les communications vers d’autres organisations sont limitées uniquement aux organisations dont le domaine figure dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="66eea-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="66eea-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="66eea-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="66eea-132">Assurez-vous ensuite que l’administrateur de l’organisation autres équipes effectue les mêmes étapes.</span><span class="sxs-lookup"><span data-stu-id="66eea-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="66eea-133">Par exemple, dans la liste de **domaines autorisés** , l’administrateur doit entrer le domaine de votre entreprise s’il limite les organisations qui peuvent communiquer avec leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="66eea-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="66eea-134">Étape 3: test</span><span class="sxs-lookup"><span data-stu-id="66eea-134">Step 3 - Test it</span></span>
<span data-ttu-id="66eea-135">Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipe qui ne se trouve pas derrière votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="66eea-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="66eea-136">Lorsque votre administrateur et vous-même avez modifié les paramètres d' **accès externe** , il est conseillé de procéder comme suit.</span><span class="sxs-lookup"><span data-stu-id="66eea-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="66eea-137">Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de discussion.</span><span class="sxs-lookup"><span data-stu-id="66eea-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="66eea-138">Demandez à votre contact teams de vous envoyer une demande de discussion.</span><span class="sxs-lookup"><span data-stu-id="66eea-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="66eea-139">Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="66eea-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="66eea-140">Un autre moyen de tester s’il s’agit d’un problème lié à votre pare-feu consiste à accéder à un point d’accès WiFi qui ne se trouve pas sur votre pare-feu (par exemple, un café) et à utiliser teams pour envoyer une demande de discussion à votre contact.</span><span class="sxs-lookup"><span data-stu-id="66eea-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="66eea-141">Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="66eea-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="66eea-142">Communiquer avec des utilisateurs dans une organisation Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="66eea-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="66eea-143">Si vous le configurez de manière à permettre aux utilisateurs de teams de rechercher et de contacter des utilisateurs de l’organisation Skype entreprise qui limitent les personnes qui peuvent contacter leurs utilisateurs, vous devez demander à l’administrateur de l’organisation de suivre ces étapes.</span><span class="sxs-lookup"><span data-stu-id="66eea-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="66eea-144">![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise dans le **Centre d’administration Skype entreprise**</span><span class="sxs-lookup"><span data-stu-id="66eea-144">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="66eea-145">Demandez à l’administrateur de l’organisation de procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="66eea-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="66eea-146">Dans le centre d’administration Office 365, accédez à centre d' **administration** > **teams &** > le**portail hérité**de Skype.</span><span class="sxs-lookup"><span data-stu-id="66eea-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="66eea-147">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="66eea-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="66eea-148">Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="66eea-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="66eea-149">Pour permettre à tous les utilisateurs du monde entier de communiquer entre eux, choisissez **activé sauf pour les domaines bloqués**.</span><span class="sxs-lookup"><span data-stu-id="66eea-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="66eea-150">Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="66eea-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="66eea-151">Sous **domaines bloqués ou autorisés**, **+** sélectionnez et ajoutez le nom du domaine que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="66eea-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="66eea-152">Assurez-vous que l’administrateur de l’autre organisation effectue les mêmes étapes.</span><span class="sxs-lookup"><span data-stu-id="66eea-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="66eea-153">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="66eea-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="66eea-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66eea-154">Related topics</span></span>

<span data-ttu-id="66eea-155">[Se connecter à](sign-in-teams.md)
la formation de l'[utilisateur final de](enduser-training.md) Microsoft teams pour teams</span><span class="sxs-lookup"><span data-stu-id="66eea-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

