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
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 394613e3137c65e814cc08dd898ec797d560d1c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010937"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="cbab2-103">Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="cbab2-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="cbab2-104">La Fédération Skype entreprise n’est pas disponible pour les 365 Office gérées par 21Vianet et les organisations d’Allemagne Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbab2-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="cbab2-105">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="cbab2-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="cbab2-p101">Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="cbab2-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="cbab2-108">Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cbab2-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="cbab2-109">Vous voulez que les autres utilisateurs de Skype entreprise puissent vous trouver et vous contacter à l’aide de votre adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="cbab2-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="cbab2-110">S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cbab2-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="cbab2-111">Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.</span><span class="sxs-lookup"><span data-stu-id="cbab2-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="cbab2-112">Autoriser les communications entre entreprises pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="cbab2-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="cbab2-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-113"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="cbab2-114">Pour cela, vous devez disposer des [autorisations d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) dans Office 365 dans les deux organisations.</span><span class="sxs-lookup"><span data-stu-id="cbab2-114">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="cbab2-115">![Icône affichant le logo](../images/teams-logo-30x30.png) Microsoft teams **avec le centre d’administration teams**</span><span class="sxs-lookup"><span data-stu-id="cbab2-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="cbab2-116">Connectez-vous à l’aide de votre compte d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbab2-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="cbab2-117">Dans le centre d’administration, accédez **à centre d'** > administration**teams**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Cliquez sur l’administrateur Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="cbab2-119">Dans le **Centre d’équipes**, sélectionnez **portail** 
 ![hérité **Skype** > , puis choisissez le portail hérité marketing.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="cbab2-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="cbab2-120">Dans le **Centre d’administration de Skype entreprise** , choisissez**communications externes**de l' **organisation** > .</span><span class="sxs-lookup"><span data-stu-id="cbab2-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="cbab2-121">Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="cbab2-p103">Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbab2-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
6. <span data-ttu-id="cbab2-124">Sous **domaines bloqués ou autorisés**, **+** sélectionnez et ajoutez le nom du domaine que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="cbab2-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="cbab2-125">Assurez-vous que l’administrateur de l’autre organisation effectue les mêmes étapes dans le **Centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="cbab2-126">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbab2-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="cbab2-127">Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.</span><span class="sxs-lookup"><span data-stu-id="cbab2-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="cbab2-128">Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) suivants.</span><span class="sxs-lookup"><span data-stu-id="cbab2-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="cbab2-129">Cela peut impliquer l’ajout des noms de domaine complets dans la liste des éléments autorisés entrants dans la configuration de votre \*pare-feu ou de votre infrastructure de proxy : \*\* \*. API.Skype.com\*\*, **. Users.Storage.live.com**et **Graph.Skype.com**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="cbab2-130">Pour obtenir des instructions sur l’ouverture de ces ports sur votre pare-feu, consultez la documentation qui l’accompagne.</span><span class="sxs-lookup"><span data-stu-id="cbab2-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="cbab2-131">Pour obtenir la liste de tous les ports que vous devez ouvrir, voir [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="cbab2-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="cbab2-132">Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.</span><span class="sxs-lookup"><span data-stu-id="cbab2-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="cbab2-p106">**ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.</span><span class="sxs-lookup"><span data-stu-id="cbab2-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="cbab2-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype.</span><span class="sxs-lookup"><span data-stu-id="cbab2-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="cbab2-136">Pour en savoir plus, reportez-vous à la rubrique [autoriser les utilisateurs Skype entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="cbab2-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="cbab2-137">Test et dépannage</span><span class="sxs-lookup"><span data-stu-id="cbab2-137">Test and troubleshoot</span></span>
<span data-ttu-id="cbab2-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-138"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="cbab2-139">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="cbab2-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="cbab2-140">Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbab2-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="cbab2-141">Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="cbab2-142">Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.</span><span class="sxs-lookup"><span data-stu-id="cbab2-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="cbab2-143">Si vous recevez un message indiquant qu’il n’a pas pu être envoyé en raison d’une stratégie de l’entreprise, vous devez vérifier vos [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="cbab2-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="cbab2-p108">Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="cbab2-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="cbab2-p109">Pour vérifier si le problème provient du pare-feu, vous pouvez également vous déplacer à un endroit disposant d'un réseau Wi-Fi qui ne soit pas derrière votre pare-feu (un café par exemple) et utiliser Skype Entreprise pour envoyer une demande de discussion à votre contact Skype. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="cbab2-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="cbab2-148">Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.</span><span class="sxs-lookup"><span data-stu-id="cbab2-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="cbab2-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="cbab2-150">Après avoir activé les communications externes avec d’autres utilisateurs Skype entreprise, vos utilisateurs peuvent trouver des utilisateurs Skype entreprise fédérés en recherchant leur nom de connexion : par exemple, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cbab2-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="cbab2-151">Ils devront ensuite ajouter la personne à leurs listes de contacts.</span><span class="sxs-lookup"><span data-stu-id="cbab2-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Pour retrouver un utilisateur dans une entreprise fédérée, vous devez rechercher son adresse e-mail (il s’agit généralement de son nom de connexion).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="cbab2-153">Conseils de configuration des communications avec des entreprises fédérées</span><span class="sxs-lookup"><span data-stu-id="cbab2-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="cbab2-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-154"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="cbab2-155">Pour configurer la Fédération entre Skype entreprise 2015 et Skype entreprise Online, consultez cet article : [configuration de la Fédération avec Skype entreprise Online](https://technet.microsoft.com/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="cbab2-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="cbab2-156">Pour configurer la Fédération entre Lync et Skype entreprise Online, consultez cet article : [configuration de la prise en charge de la Fédération pour un client Lync Online](https://technet.microsoft.com/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="cbab2-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="cbab2-157">Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations.</span><span class="sxs-lookup"><span data-stu-id="cbab2-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="cbab2-158">S’il s’agit d’un utilisateur de Skype entreprise de votre organisation qui est placé sur un site ou une mise en attente de litige, les conversations par messagerie instantanée entre cet utilisateur et les autres utilisateurs Skype entreprise ou Skype seront enregistrées dans les **éléments récupérables** de la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="cbab2-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="cbab2-159">Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="cbab2-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="cbab2-160">Désactiver la communication externe pour des individus spécifiques</span><span class="sxs-lookup"><span data-stu-id="cbab2-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="cbab2-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-161"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="cbab2-162">Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cbab2-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="cbab2-163">Connectez-vous à l’aide de votre compte d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="cbab2-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="cbab2-164">Dans le **Centre d’administration, accédez à** > utilisateurs**actifs**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="cbab2-165">Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="cbab2-167">Dans le **Centre d’administration de Skype entreprise**, choisissez **communications externes**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="cbab2-168">Dans la page **options** , tous les choix seront sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="cbab2-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="cbab2-169">Effacez les communications que vous souhaitez désactiver.</span><span class="sxs-lookup"><span data-stu-id="cbab2-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="cbab2-170">L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.</span><span class="sxs-lookup"><span data-stu-id="cbab2-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="cbab2-172">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cbab2-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbab2-173">Il est possible que les modifications ne prennent effet qu'après 24 heures.</span><span class="sxs-lookup"><span data-stu-id="cbab2-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="cbab2-174">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cbab2-174">Related topics</span></span>
<span data-ttu-id="cbab2-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="cbab2-175"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="cbab2-176">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="cbab2-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="cbab2-177">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="cbab2-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
