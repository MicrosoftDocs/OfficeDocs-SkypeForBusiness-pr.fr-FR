---
title: Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 37f028c6a7347f13c6f41d88bfdb23907dfa92c3
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500614"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="c7f55-103">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="c7f55-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="c7f55-p101">Avec Skype Entreprise, vos utilisateurs peuvent rechercher et contacter par messagerie instantanéet toute personne utilisant Skype, l'application gratuite ! Cet article vous indique comment procéder pour leur permettre d'ajouter des contacts Skype.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="c7f55-106">Pour cela, vous devez disposer [d’autorisations d’administrateur](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7f55-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="c7f55-107">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="c7f55-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="c7f55-108">Connectez-vous à l'aide de votre Office 365 compte d'administrateur sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="c7f55-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="c7f55-109">Dans le Centre d'administration Office 365, allez dans **Centres d'administration** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="c7f55-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Sélectionnez le centre d'administration de Skype Entreprise.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="c7f55-111">Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.</span><span class="sxs-lookup"><span data-stu-id="c7f55-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="c7f55-112">Par défaut, vos utilisateurs peuvent communiquer avec quiconque utilisant Skype Entreprise (si la configuration de votre pare-feu le permet).</span><span class="sxs-lookup"><span data-stu-id="c7f55-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="c7f55-p102">Si vous souhaitez autoriser vos utilisateurs à communiquer avec des contacts Skype, mais pas ceux utilisant Skype Entreprise, sélectionnez **Activé uniquement pour les domaines autorisés**. Lorsque vous autorisez le contact avec des utilisateurs Skype, skype.com est automatiquement ajouté à la liste des domaine autorisés à l'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="c7f55-p103">Pour autoriser la communication avec toutes les organisations à travers le monde utilisant Skype Entreprise, excepté certaines d'entre elles, sélectionnez **Activer sauf pour les domaines bloqués** et sélectionnez **+** pour ajouter ces domaines. Tout le monde pourra vous contacter, sauf les personnes appartenant aux domaines spécifiques. Cette option peut être choisie par certaines entreprises si, par exemple, elles sont en litige et doivent s'assurer qu'aucun contact n'a lieu avec l'autre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="c7f55-119">Choisissez **Autoriser les utilisateurs à employer Skype Entreprise pour communiquer avec des utilisateurs Skype extérieurs à votre organisation**.</span><span class="sxs-lookup"><span data-stu-id="c7f55-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="c7f55-120">Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.</span><span class="sxs-lookup"><span data-stu-id="c7f55-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="c7f55-121">Si votre organisation utilise une autre solution pour empêcher les ordinateurs sur le réseau de se connecter à Internet, assurez-vous que les ordinateurs clients peuvent accéder à toutes les [adresses IP et URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour la connectivité Skype et la recherche dans l’annuaire Skype.</span><span class="sxs-lookup"><span data-stu-id="c7f55-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="c7f55-122">Il vous faudra peut-être les ajouter à la liste autorisée dans votre pare-feu ou la configuration de votre infrastructure proxy.</span><span class="sxs-lookup"><span data-stu-id="c7f55-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="c7f55-p105">**ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**. Chaque fois que vous modifiez les paramètres de communications externes, jusqu'à 24 heures peuvent être nécessaires pour que les modifications soient appliquées à tous les centres de données.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="c7f55-p106">Montrez à vos utilisateurs comment rechercher et ajouter des contacts Skype à leur liste des contacts Skype Entreprise. Dirigez-les vers [Rechercher des personnes dans Skype Entreprise](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="c7f55-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="c7f55-127">Test et dépannage</span><span class="sxs-lookup"><span data-stu-id="c7f55-127">Test and troubleshoot</span></span>

<span data-ttu-id="c7f55-p107">Pour tester votre configuration, vous devez disposer d'un contact qui ne soit pas situé derrière le pare-feu de votre entreprise. Il peut se connecter à Skype à l'aide d'un compte Gmail, Outlook.com, ou de tout autre type de compte de messagerie.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="c7f55-130">Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.</span><span class="sxs-lookup"><span data-stu-id="c7f55-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="c7f55-131">Déconnectez-vous de Skype Entreprise, puis reconnectez-vous pour afficher l'option de recherche dans l'annuaire Skype.</span><span class="sxs-lookup"><span data-stu-id="c7f55-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="c7f55-133">Dans Skype Entreprise, recherchez votre contact dans Skype et envoyez-lui une demande de conversation.</span><span class="sxs-lookup"><span data-stu-id="c7f55-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="c7f55-134">Si votre message ne peut pas être envoyé en raison d’une stratégie de votre société, vous devez vérifier à nouveau les [paramètres de votre pare-feu](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="c7f55-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="c7f55-135">Une autre solution permettant de vérifier si le problème se situe au niveau de votre pare-feu consiste à utiliser Skype Entreprise à partir d'un emplacement Wi-Fi non situé derrière votre pare-feu, par exemple un café, pour envoyer une demande de conversation à votre contact Skype.</span><span class="sxs-lookup"><span data-stu-id="c7f55-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="c7f55-p108">**Si votre contact Skype ne reçoit pas votre demande**, demandez-lui de vous envoyer une demande de conversation. Si le problème était lié à l'établissement de connexion entre Skype et Skype Entreprise, cela permettra de le résoudre.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="c7f55-138">Si le message a pu être envoyé depuis le café et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu.</span><span class="sxs-lookup"><span data-stu-id="c7f55-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="c7f55-139">Opérations possibles et impossibles</span><span class="sxs-lookup"><span data-stu-id="c7f55-139">What you can and can't do</span></span>

- <span data-ttu-id="c7f55-140">**Skype Entreprise sur Mac** ne permet de rechercher des contacts Skype et de communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="c7f55-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="c7f55-141">Lorsque la recherche dans l’annuaire est activée, vous pouvez rechercher et trouver des utilisateurs de Skype et de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7f55-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="c7f55-142">Si, pour une raison quelconque, vous ne les trouvez pas en les recherchant dans l’annuaire, vous pouvez leur envoyer une demande de contact, et leur demander de se connecter à Skype et de l’accepter pour pouvoir échanger des messages instantanés avec eux.</span><span class="sxs-lookup"><span data-stu-id="c7f55-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="c7f55-p110">Il est impossible d'autoriser la connexion par MI avec d'autres fournisseurs de MI, tels que Google ou Facebook. Vous ne pouvez pas utiliser Skype Entreprise pour envoyer des SMS.</span><span class="sxs-lookup"><span data-stu-id="c7f55-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="c7f55-145">Il n’est pas possible d’enregistrer des appels vidéo ou audio entre un contact Skype et un contact Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7f55-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="c7f55-146">Quelles sont les fonctionnalités disponibles lors de l’ajout de contacts Skype ?</span><span class="sxs-lookup"><span data-stu-id="c7f55-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="c7f55-147">Les contacts Skype connectés avec leur compte Microsoft (anciennement Windows Live ID) ne disposent pas de l’ensemble des fonctionnalités lorsqu’ils communiquent avec vos utilisateurs de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c7f55-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="c7f55-148">**Disponible avec des contacts Skype**</span><span class="sxs-lookup"><span data-stu-id="c7f55-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="c7f55-149">**Fonctions non disponibles pour les contacts Skype**</span><span class="sxs-lookup"><span data-stu-id="c7f55-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="c7f55-150">Conversations vidéo</span><span class="sxs-lookup"><span data-stu-id="c7f55-150">Video conversations</span></span> <br/>  <span data-ttu-id="c7f55-151">Messagerie instantanée de personne à personne</span><span class="sxs-lookup"><span data-stu-id="c7f55-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="c7f55-152">Présence</span><span class="sxs-lookup"><span data-stu-id="c7f55-152">Presence</span></span> <br/> | <span data-ttu-id="c7f55-153">Conversations à plusieurs par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c7f55-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="c7f55-154">Conversions audio et vidéo avec trois personnes au minimum</span><span class="sxs-lookup"><span data-stu-id="c7f55-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="c7f55-155">Partage du bureau et de programmes</span><span class="sxs-lookup"><span data-stu-id="c7f55-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="c7f55-156">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c7f55-156">Related topics</span></span>

[<span data-ttu-id="c7f55-157">Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c7f55-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="c7f55-158">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c7f55-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 