---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: d8cac3838550530666c2e7550c616a0b77cfd820
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500682"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="312a3-103">Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="312a3-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="312a3-104">Skype pour la fédération entreprise n’est pas disponible pour Office 365 exécuté par 21Vianet et organisations Office 365 Allemagne.</span><span class="sxs-lookup"><span data-stu-id="312a3-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="312a3-105">Suivez la procédure décrite dans cet article lorsque :</span><span class="sxs-lookup"><span data-stu-id="312a3-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="312a3-p101">Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="312a3-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="312a3-108">Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="312a3-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="312a3-109">-Vous souhaitez quiconque dans le monde qui utilise Skype pour les entreprises pour être en mesure de rechercher et contacter à l’aide de votre adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="312a3-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="312a3-110">S'ils utilisent les paramètres Skype Entreprise par défaut et que vous aussi, cela fonctionnera automatiquement.</span><span class="sxs-lookup"><span data-stu-id="312a3-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="312a3-111">Sinon, ils devront s'assurer que leur configuration ne bloque pas votre domaine.</span><span class="sxs-lookup"><span data-stu-id="312a3-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="312a3-112">Autoriser les communications entre entreprises pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="312a3-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="312a3-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-113"></span></span>

<span data-ttu-id="312a3-114">Vous devez disposer des [autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) dans Office 365 dans les deux organisations pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="312a3-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="312a3-115">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="312a3-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="312a3-116">Connectez-vous avec votre compte d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="312a3-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="312a3-117">Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="312a3-117">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="312a3-119">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="312a3-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="312a3-120">Pour configurer la communication avec une entreprise spécifique ou des utilisateurs dans un autre domaine, dans la zone de liste déroulante, cliquez **sur uniquement pour les domaines autorisés**.</span><span class="sxs-lookup"><span data-stu-id="312a3-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="312a3-p103">Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="312a3-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="312a3-123">Sous **bloqué ou des domaines autorisés**, choisissez **+** et ajoutez le nom du domaine que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="312a3-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="312a3-124">Assurez-vous que l’administrateur de l’autre organisation est ces étapes dans leur **Skype entreprise centre d’administration**.</span><span class="sxs-lookup"><span data-stu-id="312a3-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="312a3-125">Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="312a3-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="312a3-126">Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.</span><span class="sxs-lookup"><span data-stu-id="312a3-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="312a3-127">Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) suivants.</span><span class="sxs-lookup"><span data-stu-id="312a3-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="312a3-128">Vous devrez peut-être ajouter des noms de domaines complets pour la sortie autorisés dans votre pare-feu ou votre proxy de configuration de l’infrastructure : ** \*. api.skype.com**, \* **. users.storage.live.com**et **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="312a3-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="312a3-129">Pour obtenir des instructions sur la façon d’ouvrir ces ports sur votre pare-feu, consultez la documentation fournie avec ce dernier.</span><span class="sxs-lookup"><span data-stu-id="312a3-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="312a3-130">Pour obtenir la liste de tous les ports à ouvrir, consultez [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="312a3-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

8. <span data-ttu-id="312a3-131">Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.</span><span class="sxs-lookup"><span data-stu-id="312a3-131">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
9. <span data-ttu-id="312a3-p106">**ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.</span><span class="sxs-lookup"><span data-stu-id="312a3-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="312a3-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype.</span><span class="sxs-lookup"><span data-stu-id="312a3-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="312a3-135">Pour plus d’informations, voir [permettent de Skype pour les utilisateurs professionnels Ajouter contacts Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="312a3-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="312a3-136">Test et dépannage</span><span class="sxs-lookup"><span data-stu-id="312a3-136">Test and troubleshoot</span></span>
<span data-ttu-id="312a3-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-137"></span></span>

 <span data-ttu-id="312a3-138">**Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).**</span><span class="sxs-lookup"><span data-stu-id="312a3-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="312a3-139">Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="312a3-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="312a3-140">Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="312a3-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="312a3-141">Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.</span><span class="sxs-lookup"><span data-stu-id="312a3-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="312a3-142">Si vous recevez un message qui est n’a pas pu être envoyée en raison de la stratégie d’entreprise, vous devez vérifier votre [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="312a3-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="312a3-p108">Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).</span><span class="sxs-lookup"><span data-stu-id="312a3-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="312a3-p109">Pour vérifier si le problème provient du pare-feu, vous pouvez également vous déplacer à un endroit disposant d'un réseau Wi-Fi qui ne soit pas derrière votre pare-feu (un café par exemple) et utiliser Skype Entreprise pour envoyer une demande de discussion à votre contact Skype. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="312a3-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="312a3-147">Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.</span><span class="sxs-lookup"><span data-stu-id="312a3-147">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="312a3-148"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-148"></span></span>

<span data-ttu-id="312a3-149">Après avoir activé la communication externe avec les autres Skype pour les utilisateurs professionnels, vos utilisateurs trouverez Skype fédéré pour les utilisateurs professionnels en recherchant leur nom de connexion : par exemple, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="312a3-149">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="312a3-150">Ils devrez ensuite ajouter cette personne à sa liste des contacts.</span><span class="sxs-lookup"><span data-stu-id="312a3-150">Then they will need to add the person to their list of contacts.</span></span>
  
![Pour rechercher un utilisateur dans une entreprise fédérée, vous devez rechercher leur adresse de messagerie (il s’agit généralement également leur nom de connexion).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="312a3-152">Conseils de configuration des communications avec des entreprises fédérées</span><span class="sxs-lookup"><span data-stu-id="312a3-152">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="312a3-153"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-153"></span></span>

- <span data-ttu-id="312a3-154">Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la fédération avec Skype Entreprise Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="312a3-154">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="312a3-155">Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article TechNet : [Configuration de la prise en charge de la fédération pour un client Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="312a3-155">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="312a3-156">Lorsque deux utilisateurs Skype Entreprise dans Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités Skype Entreprise (par exemple, des conversations vidéo ou un partage de bureau) qui sont activées dans les deux organisations.</span><span class="sxs-lookup"><span data-stu-id="312a3-156">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="312a3-157">Si un Skype pour l’utilisateur d’entreprise dans votre organisation est placé sur une archive ou un litige, toutes les conversations par messagerie instantanée entre cet utilisateur et autres Skype pour les utilisateurs d’entreprise ou Skype seront enregistrées dans les **Éléments récupérables** dans leur boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="312a3-157">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="312a3-158">Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="312a3-158">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="312a3-159">Désactiver la communication externe pour des individus spécifiques</span><span class="sxs-lookup"><span data-stu-id="312a3-159">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="312a3-160"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-160"></span></span>

<span data-ttu-id="312a3-161">Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="312a3-161">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="312a3-162">Connectez-vous avec votre compte d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="312a3-162">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="312a3-163">Dans le centre d’administration Office 365, accédez aux **utilisateurs** > **utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="312a3-163">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="312a3-164">Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="312a3-164">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="312a3-166">Dans la **Skype entreprise centre d’administration**, choisissez **communications externes**.</span><span class="sxs-lookup"><span data-stu-id="312a3-166">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="312a3-167">Dans la page **Options** , tous les choix seront sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="312a3-167">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="312a3-168">Désactivez les communications que vous souhaitez désactiver.</span><span class="sxs-lookup"><span data-stu-id="312a3-168">Clear the communications you want to disable.</span></span> <span data-ttu-id="312a3-169">L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.</span><span class="sxs-lookup"><span data-stu-id="312a3-169">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="312a3-171">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="312a3-171">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="312a3-172">Il est possible que les modifications ne prennent effet qu'après 24 heures.</span><span class="sxs-lookup"><span data-stu-id="312a3-172">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="312a3-173">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="312a3-173">Related topics</span></span>
<span data-ttu-id="312a3-174"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="312a3-174"></span></span>

[<span data-ttu-id="312a3-175">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="312a3-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="312a3-176">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="312a3-176">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
