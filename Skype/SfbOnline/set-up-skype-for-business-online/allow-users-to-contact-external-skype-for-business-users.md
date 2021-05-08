---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Découvrez comment configurer des Skype Entreprise pour laisser les utilisateurs parler aux utilisateurs d’une autre organisation ou laisser des contacts extérieurs parler à eux. '
ms.openlocfilehash: 3b4aeb2b40cf34579d3d584a50664550cd34038c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240002"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="446fe-103">Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="446fe-103">Allow users to contact external Skype for Business users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
<span data-ttu-id="446fe-104">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="446fe-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="446fe-p101">Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="446fe-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="446fe-107">Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="446fe-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="446fe-108">Vous souhaitez que les autres personnes du monde qui utilisent Skype Entreprise puissent vous trouver et vous contacter à l’aide de votre adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="446fe-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="446fe-109">S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement.</span><span class="sxs-lookup"><span data-stu-id="446fe-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="446fe-110">Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.</span><span class="sxs-lookup"><span data-stu-id="446fe-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="446fe-111">Autoriser les communications entre entreprises pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="446fe-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="446fe-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="446fe-113">Vous devez avoir [des autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Microsoft 365 ou Office 365 les deux organisations pour cette communication.</span><span class="sxs-lookup"><span data-stu-id="446fe-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="446fe-114">![Icône montrant le logo ](../images/teams-logo-30x30.png) **Microsoft Teams’aide du Centre Teams’administration**</span><span class="sxs-lookup"><span data-stu-id="446fe-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="446fe-115">Connectez-vous à l’Microsoft 365 votre Office 365 administrateur.</span><span class="sxs-lookup"><span data-stu-id="446fe-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="446fe-116">Dans le Centre d’administration, allez dans Centres **d’administration**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="446fe-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Sélectionnez le Teams administrateur de projet.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="446fe-118">Dans le **Teams, sélectionnez** Skype portail  > **hérité,** choisissez le portail hérité 
  ![ SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="446fe-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="446fe-119">Dans la **Centre d’administration Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="446fe-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="446fe-120">Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs ayant un autre domaine, dans le menu déroulant, choisissez **Activé uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="446fe-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="446fe-p103">Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="446fe-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>

6. <span data-ttu-id="446fe-123">Sous **Domaines bloqués ou autorisés,** choisissez et ajoutez le nom du **+** domaine que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="446fe-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="446fe-124">Assurez-vous que l’administrateur de l’autre organisation doit effectuer les mêmes étapes dans son **Skype Entreprise d’administration.**</span><span class="sxs-lookup"><span data-stu-id="446fe-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="446fe-125">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="446fe-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="446fe-126">Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.</span><span class="sxs-lookup"><span data-stu-id="446fe-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="446fe-127">Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](/microsoftteams/office-365-urls-ip-address-ranges) suivants.</span><span class="sxs-lookup"><span data-stu-id="446fe-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="446fe-128">Cela peut nécessiter l’ajout des FQDN à la liste de votre pare-feu ou de votre configuration d’infrastructure proxy : **\* .api.skype.com,** \* *_.users.storage.live.com_* et **graph.skype.com.**</span><span class="sxs-lookup"><span data-stu-id="446fe-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="446fe-129">Pour obtenir des instructions sur la façon d’ouvrir ces ports dans votre pare-feu, consultez la documentation qui l’intait.</span><span class="sxs-lookup"><span data-stu-id="446fe-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="446fe-130">Pour obtenir la liste de tous les ports que vous devez ouvrir, voir Office 365 [URL et plages d’adresses IP.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="446fe-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="446fe-131">Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.</span><span class="sxs-lookup"><span data-stu-id="446fe-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="446fe-132">**ATTENDEZ JUSQU’À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="446fe-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="446fe-133">Lorsque vous modifiez les paramètres de communications externes, jusqu’à 24 heures peuvent être nécessaires avant que les modifications ne s’insérez dans tous les centres de données.</span><span class="sxs-lookup"><span data-stu-id="446fe-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="446fe-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype.</span><span class="sxs-lookup"><span data-stu-id="446fe-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="446fe-135">Pour en savoir plus, voir [Laisser les utilisateurs Skype Entreprise ajouter Skype contacts.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="446fe-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="446fe-136">Test et dépannage</span><span class="sxs-lookup"><span data-stu-id="446fe-136">Test and troubleshoot</span></span>

<span data-ttu-id="446fe-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="446fe-138">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="446fe-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="446fe-139">Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="446fe-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="446fe-140">Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="446fe-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="446fe-141">Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.</span><span class="sxs-lookup"><span data-stu-id="446fe-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="446fe-142">Si vous recevez un message vous that that it couldn’t be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="446fe-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="446fe-p108">Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="446fe-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="446fe-145">Une autre façon de vérifier si le problème se trouve au-de pare-feu consiste à utiliser un emplacement Wifi qui n’est pas derrière votre pare-feu, par exemple un café.</span><span class="sxs-lookup"><span data-stu-id="446fe-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="446fe-146">Utilisez Skype Entreprise pour envoyer une demande de conversation à votre contact.</span><span class="sxs-lookup"><span data-stu-id="446fe-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="446fe-147">Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="446fe-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="446fe-148">Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.</span><span class="sxs-lookup"><span data-stu-id="446fe-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="446fe-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="446fe-150">Après avoir activé la communication externe avec d’autres Skype Entreprise utilisateurs, vos utilisateurs peuvent trouver des utilisateurs Skype Entreprise fédérés en recherchant leurs noms de sign-in.</span><span class="sxs-lookup"><span data-stu-id="446fe-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="446fe-151">C’est le cas, par exemple, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="446fe-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="446fe-152">Ils devront ensuite ajouter la personne à leurs listes de contacts.</span><span class="sxs-lookup"><span data-stu-id="446fe-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Pour rechercher un utilisateur dans une entreprise fédérée, vous devez rechercher son adresse de messagerie (il s’agit généralement également de son nom de sign in).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="446fe-154">Conseils de configuration des communications avec des entreprises fédérées</span><span class="sxs-lookup"><span data-stu-id="446fe-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="446fe-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="446fe-156">Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article : Configurer la fédération [avec Skype Entreprise Online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="446fe-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="446fe-157">Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article : Configuration de la prise en charge de la fédération pour un client [Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)</span><span class="sxs-lookup"><span data-stu-id="446fe-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="446fe-158">Lorsque deux utilisateurs de Skype Entreprise dans Microsoft 365 ou Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités de Skype Entreprise (par exemple, les conversations vidéo ou le partage de bureau) qui sont désactivées dans les deux organisations.</span><span class="sxs-lookup"><span data-stu-id="446fe-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="446fe-159">Si un utilisateur Skype Entreprise de votre organisation est placé en In-Place ou en attente pour litige, les conversations par messagerie instantanée entre cet utilisateur et d’autres utilisateurs de Skype Entreprise ou de Skype sont enregistrées dans les éléments **récupérables** de leur boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="446fe-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="446fe-160">Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="446fe-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="446fe-161">Désactiver la communication externe pour des individus spécifiques</span><span class="sxs-lookup"><span data-stu-id="446fe-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="446fe-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="446fe-163">Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="446fe-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="446fe-164">Connectez-vous à l’Microsoft 365 votre Office 365 administrateur.</span><span class="sxs-lookup"><span data-stu-id="446fe-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="446fe-165">Dans le Centre d’administration, voir **Utilisateurs**  >  **actifs.**</span><span class="sxs-lookup"><span data-stu-id="446fe-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="446fe-166">Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="446fe-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="446fe-168">Dans le Skype Entreprise **d’administration,** sélectionnez **Communications externes.**</span><span class="sxs-lookup"><span data-stu-id="446fe-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="446fe-169">Dans la page **Options,** toutes les options sont sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="446fe-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="446fe-170">Désactivez les communications que vous voulez désactiver.</span><span class="sxs-lookup"><span data-stu-id="446fe-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="446fe-171">L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.</span><span class="sxs-lookup"><span data-stu-id="446fe-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="446fe-173">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="446fe-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="446fe-174">Il est possible que les modifications ne prennent effet qu'après 24 heures.</span><span class="sxs-lookup"><span data-stu-id="446fe-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="446fe-175">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="446fe-175">Related topics</span></span>

<span data-ttu-id="446fe-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="446fe-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="446fe-177">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="446fe-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="446fe-178">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="446fe-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
