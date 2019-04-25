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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Découvrez comment configurer des équipes pour permettre aux utilisateurs de communiquer avec les utilisateurs d’une autre organisation.
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222370"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="d2932-103">Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="d2932-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="d2932-104">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="d2932-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="d2932-105">Vous avez des utilisateurs dans des domaines différents dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="d2932-105">You have users in different domains in your business.</span></span> <span data-ttu-id="d2932-106">Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="d2932-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="d2932-107">Vous souhaitez que les personnes de votre organisation d’utiliser des équipes pour contacter les personnes figurant dans les entreprises spécifiques à l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d2932-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="d2932-108">Vous souhaitez quiconque dans le monde qui utilise des équipes pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="d2932-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="d2932-109">Si vous et un autre utilisateur Activer l’accès externe et autoriser les domaines de l’autre, cela fonctionnera.</span><span class="sxs-lookup"><span data-stu-id="d2932-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="d2932-110">Si elle ne fonctionne pas, l’autre utilisateur devez vous assurer que son ou sa configuration n’est pas le blocage de votre domaine.</span><span class="sxs-lookup"><span data-stu-id="d2932-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="d2932-111">Cela permettra aux utilisateurs de rechercher, appeler et vous envoyer des messages instantanés, mais aussi définir des réunions avec vous.</span><span class="sxs-lookup"><span data-stu-id="d2932-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="d2932-112">Si vous souhaitez que les utilisateurs externes d’accéder aux équipes et les canaux, accès invité peut être une meilleure façon pour accéder.</span><span class="sxs-lookup"><span data-stu-id="d2932-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="d2932-113">Suivez les étapes décrites dans cet article et les Assurez-vous pour [Activer l’accès invité](set-up-guests.md) afin que les utilisateurs peuvent communiquer.</span><span class="sxs-lookup"><span data-stu-id="d2932-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2932-114">Afin de vous fédérer actuellement dans le client Microsoft Teams à un utilisateur externe à l’extérieur de votre organisation qui n’est pas invité de votre DAS/client, vous devez être correctement configuré pour l’environnement hybride et déplacée vers Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="d2932-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="d2932-115">25/2/2019, équipes n’encore prennent en charge native fédération sans que l’utilisateur du profil SIP en cours hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="d2932-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="d2932-116">Pour plus d’informations sur la configuration de configurer votre compte pour l’environnement hybride et ensuite vers les équipes, consultez [Mise à niveau de Skype pour un déploiement hybride Business aux équipes](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span><span class="sxs-lookup"><span data-stu-id="d2932-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="d2932-117">Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="d2932-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="d2932-118">Suivez ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d2932-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="d2932-119">Étape 1 : veillez à configurer les ports et les URL qui sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d2932-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="d2932-120">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="d2932-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="d2932-121">Étape 2 : activer votre organisation de communiquer avec une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="d2932-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="d2932-122">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="d2932-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="d2932-123">Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="d2932-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="d2932-124">En haut de la page **d’accès externe** , cliquez sur **accès externe** **activé**.</span><span class="sxs-lookup"><span data-stu-id="d2932-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="d2932-125">Si vous souhaitez autoriser toutes les organisations d’équipes de communiquer avec les utilisateurs de votre organisation, passez à l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="d2932-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="d2932-126">Si vous souhaitez limiter les organisations peuvent communiquer avec les utilisateurs de votre organisation vous pouvez autoriser tous les mais certains domaines ou autoriser uniquement les organisations spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d2932-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="d2932-127">Pour autoriser tous les mais certains domaines, ajoutez les domaines que vous souhaitez bloquer en cliquant sur **Ajouter domaine**.</span><span class="sxs-lookup"><span data-stu-id="d2932-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="d2932-128">Dans le volet **Ajouter un domaine** , placez le nom de domaine, cliquez sur **bloqué** , puis sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="d2932-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="d2932-129">Pour limiter les communications à organizatioins spécifique, ajoutez ces domaines à la liste avec l’état **Alowed**.</span><span class="sxs-lookup"><span data-stu-id="d2932-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="d2932-130">Une fois que vous avez ajouté un domaine à la liste verte, les communications à d’autres organisations seront limitées pour que les organisations dont les domaines sont dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="d2932-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="d2932-131">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d2932-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="d2932-132">Vérifiez que l’administrateur de l’autre organisation équipes est ces étapes.</span><span class="sxs-lookup"><span data-stu-id="d2932-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="d2932-133">Par exemple, dans leur liste des **domaines autorisés** , leur administrateur a besoin d’entrer le domaine de votre entreprise si elles définir les organisations peuvent communiquer avec leurs utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2932-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="d2932-134">Étape 3 : tester</span><span class="sxs-lookup"><span data-stu-id="d2932-134">Step 3 - Test it</span></span>
<span data-ttu-id="d2932-135">Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipes qui n’est pas derrière votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="d2932-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="d2932-136">Une fois que l’administration de l’organisation et vous ont modifié les paramètres **d’accès externe** , vous devez être bon.</span><span class="sxs-lookup"><span data-stu-id="d2932-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="d2932-137">Dans l’application d’équipes, rechercher la personne à l’adresse de messagerie et envoyer une requête à la conversation.</span><span class="sxs-lookup"><span data-stu-id="d2932-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="d2932-138">Demandez à votre contact équipes vous envoyer une demande à la conversation.</span><span class="sxs-lookup"><span data-stu-id="d2932-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="d2932-139">Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="d2932-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="d2932-140">Une autre manière de tester si le problème est votre pare-feu consiste à accéder à un emplacement Wi-Fi pas derrière votre pare-feu comme un café et équipes permet d’envoyer une demande à votre contact à la conversation.</span><span class="sxs-lookup"><span data-stu-id="d2932-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="d2932-141">Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="d2932-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="d2932-142">Communiquer avec les utilisateurs dans un Skype pour une organisation Business en ligne</span><span class="sxs-lookup"><span data-stu-id="d2932-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="d2932-143">Si vous le configurez pour laisser votre recherche d’utilisateurs équipes et les contacts des utilisateurs qui se trouvent dans un Skype pour l’organisation de l’entreprise qui limite qui peut contacter leurs utilisateurs, vous allez demander à l’administrateur dans cette organisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d2932-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="d2932-144">![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="d2932-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="d2932-145">Disposer de l’administrateur dans cette organisation procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d2932-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="d2932-146">Dans le centre d’administration Office 365, accédez au **Centre d’administration** > **& équipes Skype** > **portail hérité**.</span><span class="sxs-lookup"><span data-stu-id="d2932-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="d2932-147">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="d2932-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="d2932-148">Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="d2932-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="d2932-149">OU, s’il souhaite permettre la communication avec tout le monde dans le monde qui a ouvert Skype pour les stratégies d’entreprise, choisissez **sur à l’exception des domaines bloqués**.</span><span class="sxs-lookup"><span data-stu-id="d2932-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="d2932-150">Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="d2932-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="d2932-151">Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="d2932-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="d2932-152">Assurez-vous que l’administrateur de l’autre organisation est la même procédure.</span><span class="sxs-lookup"><span data-stu-id="d2932-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="d2932-153">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="d2932-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="d2932-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2932-154">Related topics</span></span>

<span data-ttu-id="d2932-155">[Se connecter à Microsoft Teams](sign-in-teams.md)
[utilisateur final de formation pour les équipes](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="d2932-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

