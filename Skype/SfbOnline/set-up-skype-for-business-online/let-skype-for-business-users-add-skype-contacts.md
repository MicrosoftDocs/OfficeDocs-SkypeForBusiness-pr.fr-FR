---
title: Autoriser les utilisateurs de Skype Entreprise à ajouter des contacts Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: 'Découvrez comment permettre à des personnes qui utilisent Skype Entreprise de contacter des utilisateurs Skype Entreprise externes à votre organisation et à les ajouter à leur liste de contacts. '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164473"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="17e38-103">Autoriser les utilisateurs de Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="17e38-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="17e38-p101">Avec Skype Entreprise, vos utilisateurs peuvent rechercher et contacter par messagerie instantanéet toute personne utilisant Skype, l'application gratuite ! Cet article vous indique comment procéder pour leur permettre d'ajouter des contacts Skype.</span><span class="sxs-lookup"><span data-stu-id="17e38-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="17e38-106">Pour ce [faire, vous](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) devez avoir des autorisations d’administrateur dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="17e38-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="17e38-107">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="17e38-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="17e38-108">Connectez-vous à l’aide de votre compte d’administrateur Microsoft 365 ou Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .</span><span class="sxs-lookup"><span data-stu-id="17e38-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="17e38-109">Dans le Centre d’administration, allez dans les **Centres d’administration**  >  **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="17e38-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="17e38-111">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="17e38-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="17e38-112">Par défaut, vos utilisateurs peuvent communiquer avec quiconque utilisant Skype Entreprise (si la configuration de votre pare-feu le permet).</span><span class="sxs-lookup"><span data-stu-id="17e38-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Sélectionnez Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="17e38-p102">Si vous souhaitez autoriser vos utilisateurs à communiquer avec des contacts Skype, mais pas ceux utilisant Skype Entreprise, sélectionnez **Activé uniquement pour les domaines autorisés**. Lorsque vous autorisez le contact avec des utilisateurs Skype, skype.com est automatiquement ajouté à la liste des domaine autorisés à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="17e38-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="17e38-p103">Pour autoriser la communication avec toutes les organisations à travers le monde utilisant Skype Entreprise, excepté certaines d'entre elles, sélectionnez **Activer sauf pour les domaines bloqués** et sélectionnez **+** pour ajouter ces domaines. Tout le monde pourra vous contacter, sauf les personnes appartenant aux domaines spécifiques. Cette option peut être choisie par certaines entreprises si, par exemple, elles sont en litige et doivent s'assurer qu'aucun contact n'a lieu avec l'autre entreprise.</span><span class="sxs-lookup"><span data-stu-id="17e38-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="17e38-119">Sélectionnez **Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec des utilisateurs Skype extérieurs à votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="17e38-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="17e38-120">Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.</span><span class="sxs-lookup"><span data-stu-id="17e38-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="17e38-121">Si votre organisation utilise une autre solution pour empêcher les ordinateurs sur le réseau de se connecter à Internet, assurez-vous que les ordinateurs clients peuvent accéder à toutes les [adresses IP et URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité Skype et la recherche dans l’annuaire Skype.</span><span class="sxs-lookup"><span data-stu-id="17e38-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="17e38-122">Vous devez peut-être les ajouter à la liste autorisée dans votre pare-feu ou à la configuration de votre infrastructure proxy.</span><span class="sxs-lookup"><span data-stu-id="17e38-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="17e38-p105">**ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.</span><span class="sxs-lookup"><span data-stu-id="17e38-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="17e38-p106">Montrez à vos utilisateurs comment rechercher et ajouter des contacts Skype à leur liste des contacts Skype Entreprise. Dirigez-les vers [Rechercher des personnes dans Skype Entreprise](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="17e38-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="17e38-127">Test et dépannage</span><span class="sxs-lookup"><span data-stu-id="17e38-127">Test and troubleshoot</span></span>

<span data-ttu-id="17e38-p107">Pour tester votre configuration, vous devez disposer d'un contact qui ne soit pas situé derrière le pare-feu de votre entreprise. Il peut se connecter à Skype à l'aide d'un compte Gmail, Outlook.com, ou de tout autre type de compte de messagerie.</span><span class="sxs-lookup"><span data-stu-id="17e38-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="17e38-130">Après avoir modifié vos paramètres de communication externe, **ATTENDEZ JUSQU’À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="17e38-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="17e38-131">Déconnectez-vous de Skype Entreprise, puis reconnectez-vous pour afficher l’option de recherche dans l’annuaire Skype.</span><span class="sxs-lookup"><span data-stu-id="17e38-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Lorsque l’annuaire Skype est activé, vous pouvez rechercher des personnes qui ont des comptes Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="17e38-133">Dans Skype Entreprise, recherchez votre contact dans Skype et envoyez-lui une demande de conversation.</span><span class="sxs-lookup"><span data-stu-id="17e38-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="17e38-134">Si votre message ne peut pas être envoyé en raison d’une stratégie de votre société, vous devez vérifier à nouveau les [paramètres de votre pare-feu](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="17e38-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="17e38-135">Une autre solution permettant de vérifier si le problème se situe au niveau de votre pare-feu consiste à accéder à un emplacement Wi-Fi non situé derrière votre pare-feu, par exemple un café, et d’utiliser Skype Entreprise pour envoyer une demande de conversation à votre contact Skype.</span><span class="sxs-lookup"><span data-stu-id="17e38-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="17e38-p108">**Si votre contact Skype ne reçoit pas votre demande**, demandez-lui de vous envoyer une demande de conversation. Si le problème était lié à l'établissement de connexion entre Skype et Skype Entreprise, cela permettra de le résoudre.</span><span class="sxs-lookup"><span data-stu-id="17e38-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="17e38-138">Si le message a pu être envoyé depuis le café et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="17e38-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="17e38-139">Ce que vous pouvez et ne pouvez pas faire</span><span class="sxs-lookup"><span data-stu-id="17e38-139">What you can and can't do</span></span>

- <span data-ttu-id="17e38-140">**Skype Entreprise sur Mac** ne permet de rechercher des contacts Skype et de communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="17e38-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="17e38-141">Lorsque la recherche dans l’annuaire est activée, vous pouvez rechercher et trouver des utilisateurs de Skype et de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="17e38-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="17e38-142">Si, pour une raison quelconque, vous ne les trouvez pas en les recherchant dans l’annuaire, vous pouvez leur envoyer une demande de contact, et leur demander de se connecter à Skype et de l’accepter pour pouvoir échanger des messages instantanés avec eux.</span><span class="sxs-lookup"><span data-stu-id="17e38-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="17e38-p110">Il est impossible d'autoriser la connexion par MI avec d'autres fournisseurs de MI, tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype Entreprise pour envoyer des SMS.</span><span class="sxs-lookup"><span data-stu-id="17e38-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="17e38-145">Il n’est pas possible d’enregistrer des appels vidéo ou audio entre un contact Skype et un contact Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="17e38-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="17e38-146">Quelles sont les fonctionnalités disponibles lors de l’ajout de contacts Skype ?</span><span class="sxs-lookup"><span data-stu-id="17e38-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="17e38-147">Les contacts Skype connectés avec leur compte Microsoft (anciennement Windows Live ID) ne disposent pas de l’ensemble des fonctionnalités lorsqu’ils communiquent avec vos utilisateurs de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="17e38-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="17e38-148">**Disponible avec des contacts Skype**</span><span class="sxs-lookup"><span data-stu-id="17e38-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="17e38-149">**Non disponible avec des contacts Skype**</span><span class="sxs-lookup"><span data-stu-id="17e38-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="17e38-150">Conversations vidéo</span><span class="sxs-lookup"><span data-stu-id="17e38-150">Video conversations</span></span> <br/>  <span data-ttu-id="17e38-151">Messagerie instantanée entre deux personnes</span><span class="sxs-lookup"><span data-stu-id="17e38-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="17e38-152">Présence</span><span class="sxs-lookup"><span data-stu-id="17e38-152">Presence</span></span> <br/> | <span data-ttu-id="17e38-153">Conversations par messagerie instantanée entre plusieurs parties</span><span class="sxs-lookup"><span data-stu-id="17e38-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="17e38-154">Conversations audio et vidéo avec trois personnes ou plus</span><span class="sxs-lookup"><span data-stu-id="17e38-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="17e38-155">Partage du bureau et de programmes</span><span class="sxs-lookup"><span data-stu-id="17e38-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="17e38-156">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="17e38-156">Related topics</span></span>

[<span data-ttu-id="17e38-157">Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="17e38-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="17e38-158">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="17e38-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
