---
title: Modifier les URL simples après la migration
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server prend en charge les URL simples.
ms.openlocfilehash: 71935aab09de1598b355d2a7b27dfa02fd169216
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374989"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="14bb3-103">Modifier les URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="14bb3-103">Change simple URLs after migration</span></span>

<span data-ttu-id="14bb3-104">Skype pour Business Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="14bb3-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="14bb3-105">**Répondre à** est utilisée comme URL de base pour toutes les conférences dans le site ou une organisation.</span><span class="sxs-lookup"><span data-stu-id="14bb3-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="14bb3-106">Avec l’URL simple Meet, liens à participer à des réunions sont faciles à comprendre et à communiquer et à distribuer.</span><span class="sxs-lookup"><span data-stu-id="14bb3-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="14bb3-107">**Rendez-vous** permettant d’accéder à la page Web paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="14bb3-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="14bb3-108">L'URL simple de numérotation est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="14bb3-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="14bb3-109">**Admin** permet d’accéder rapidement à la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="14bb3-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="14bb3-110">L’URL simple Admin est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="14bb3-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="14bb3-111">Après avoir migré vers Skype pour Business Server, vous devez être conscient de la modification de l’impact de vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="14bb3-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="14bb3-112">Si le Skype hérité pour le directeur Business Server continue à être utilisé dans la topologie, aucune modification des URL simples n’est requise.</span><span class="sxs-lookup"><span data-stu-id="14bb3-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="14bb3-113">Si le Skype pour le directeur Business Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers un de la Skype pour les pools de serveurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="14bb3-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="14bb3-114">Toutefois, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et le serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="14bb3-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="14bb3-115">Pour mettre à jour l’URL simple Meet</span><span class="sxs-lookup"><span data-stu-id="14bb3-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="14bb3-116">Dans le Générateur de topologie, cliquez sur le nœud supérieur **Skype pour Business Server**, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="14bb3-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="14bb3-117">Sélectionnez les **URL simples** dans le volet gauche, puis sous **URL de réunion :** sélectionnez l’URL Meet, puis cliquez sur **Modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="14bb3-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="14bb3-118">Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée.</span><span class="sxs-lookup"><span data-stu-id="14bb3-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="14bb3-119">Pour mettre à jour l’URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="14bb3-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="14bb3-120">Dans le Générateur de topologie, cliquez sur le nœud supérieur **Skype pour Business Server**, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="14bb3-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="14bb3-121">Sélectionnez **URL simples** dans le volet gauche, puis sous la zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour un accès administratif à Skype pour Business Server le panneau de configuration, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="14bb3-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="14bb3-122">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="14bb3-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="14bb3-123">L’option la plus simple est https://admin. <em> \<domaine\></em>.</span><span class="sxs-lookup"><span data-stu-id="14bb3-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="14bb3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14bb3-124">See also</span></span>

[<span data-ttu-id="14bb3-125">Enregistrements DNS requis pour les URL simples dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="14bb3-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
