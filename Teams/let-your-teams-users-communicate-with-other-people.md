---
title: Communiquer avec les utilisateurs d’équipes dans une autre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Découvrez comment configurer des équipes pour permettre aux utilisateurs de communiquer avec les utilisateurs d’une autre organisation.
ms.openlocfilehash: 3eaffac3571abc70d4964ea4a8955f187d1e988f
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844636"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="a128f-103">Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="a128f-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="a128f-104">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="a128f-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="a128f-105">Vous avez des utilisateurs dans des domaines différents dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a128f-105">You have users in different domains in your business.</span></span> <span data-ttu-id="a128f-106">Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="a128f-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="a128f-107">Vous souhaitez que les personnes de votre organisation d’utiliser des équipes pour contacter les personnes figurant dans les entreprises spécifiques à l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a128f-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="a128f-108">Vous souhaitez quiconque dans le monde qui utilise des équipes pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="a128f-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="a128f-109">Si vous et un autre utilisateur Activer l’accès externe et autoriser les domaines de l’autre, cela fonctionnera.</span><span class="sxs-lookup"><span data-stu-id="a128f-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="a128f-110">Si elle ne fonctionne pas, l’autre utilisateur devez vous assurer que son ou sa configuration n’est pas le blocage de votre domaine.</span><span class="sxs-lookup"><span data-stu-id="a128f-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="a128f-111">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a128f-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="a128f-112">Laissez votre conversation d’utilisateurs équipes et communiquer avec les utilisateurs d’une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="a128f-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="a128f-113">Étape 1 : veillez à configurer les ports et les URL qui sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a128f-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="a128f-114">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="a128f-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="a128f-115">Étape 2 : activer votre organisation de communiquer avec une autre organisation d’équipes</span><span class="sxs-lookup"><span data-stu-id="a128f-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="a128f-116">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="a128f-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="a128f-117">Dans la navigation de gauche, accédez à **paramètres à l’échelle de la société** > **l’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="a128f-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="a128f-118">En haut de la page **d’accès externe** , cliquez sur **accès externe** **activé**.</span><span class="sxs-lookup"><span data-stu-id="a128f-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="a128f-119">Ajouter le domaine de l’autre organisation à la liste autorisée en cliquant sur **Ajouter domaine**.</span><span class="sxs-lookup"><span data-stu-id="a128f-119">Add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="a128f-120">Dans le volet **Ajouter un domaine** , placez dans le domaine, cliquez sur nom **autorisé** , puis sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="a128f-120">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="a128f-121">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a128f-121">Click **Save**.</span></span> 

   5. <span data-ttu-id="a128f-122">Vérifiez que l’administrateur de l’autre organisation équipes est ces étapes.</span><span class="sxs-lookup"><span data-stu-id="a128f-122">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="a128f-123">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a128f-123">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

### <a name="step-3---test-it"></a><span data-ttu-id="a128f-124">Étape 3 : tester</span><span class="sxs-lookup"><span data-stu-id="a128f-124">Step 3 - Test it</span></span>
<span data-ttu-id="a128f-125">Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipes qui n’est pas derrière votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a128f-125">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="a128f-126">Une fois que l’administration de l’organisation et vous ont modifié les paramètres **d’accès externe** , vous devez être bon.</span><span class="sxs-lookup"><span data-stu-id="a128f-126">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="a128f-127">Dans l’application d’équipes, rechercher la personne à l’adresse de messagerie et envoyer une requête à la conversation.</span><span class="sxs-lookup"><span data-stu-id="a128f-127">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="a128f-128">Demandez à votre contact équipes vous envoyer une demande à la conversation.</span><span class="sxs-lookup"><span data-stu-id="a128f-128">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="a128f-129">Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="a128f-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="a128f-130">Une autre manière de tester si le problème est votre pare-feu consiste à accéder à un emplacement Wi-Fi pas derrière votre pare-feu comme un café et équipes permet d’envoyer une demande à votre contact à la conversation.</span><span class="sxs-lookup"><span data-stu-id="a128f-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="a128f-131">Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a128f-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="a128f-132">Communiquer avec les utilisateurs dans un Skype pour une organisation Business en ligne</span><span class="sxs-lookup"><span data-stu-id="a128f-132">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="a128f-133">Si vous le configurez jusqu'à let vos utilisateurs équipes rechercher et contacter les utilisateurs qui se trouvent dans un Skype pour l’organisation de l’entreprise, vous serez l’administrateur dans cette organisation, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a128f-133">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization, you will the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="a128f-134">![SFB-logo-30x30.png](media/sfb-logo-30x30.png) **à l’aide de Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="a128f-134">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="a128f-135">Disposer de l’administrateur dans cette organisation procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a128f-135">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="a128f-136">Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a128f-136">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
  
2. <span data-ttu-id="a128f-137">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="a128f-137">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="a128f-138">Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="a128f-138">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="a128f-p107">Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="a128f-p107">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
4. <span data-ttu-id="a128f-141">Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="a128f-141">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="a128f-142">Assurez-vous que l’administrateur de l’autre organisation est la même procédure.</span><span class="sxs-lookup"><span data-stu-id="a128f-142">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="a128f-143">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a128f-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="a128f-144">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a128f-144">Related topics</span></span>

<span data-ttu-id="a128f-145">[Connecter les équipes](sign-in-teams.md)
[utilisateur final de formation pour les équipes](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="a128f-145">[Sign in teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

