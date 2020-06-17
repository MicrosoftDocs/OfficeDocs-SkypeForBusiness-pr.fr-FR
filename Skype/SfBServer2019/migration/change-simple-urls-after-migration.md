---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype entreprise Server prend en charge les URL simples.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753904"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="82245-103">Modification des URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="82245-103">Change simple URLs after migration</span></span>

<span data-ttu-id="82245-104">Skype entreprise Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="82245-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="82245-105">**Meet** is used as the base URL for all conferences in the site or organization.</span><span class="sxs-lookup"><span data-stu-id="82245-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="82245-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span><span class="sxs-lookup"><span data-stu-id="82245-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="82245-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span><span class="sxs-lookup"><span data-stu-id="82245-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="82245-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span><span class="sxs-lookup"><span data-stu-id="82245-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="82245-109">L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82245-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="82245-110">L’URL simple d’administration est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="82245-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="82245-111">Après avoir effectué la migration vers Skype entreprise Server, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="82245-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="82245-112">Si le directeur Skype entreprise Server hérité reste en cours d’utilisation dans la topologie, aucune modification de vos URL simples n’est requise.</span><span class="sxs-lookup"><span data-stu-id="82245-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="82245-113">Si le directeur Skype entreprise Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers l’un des pools de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82245-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="82245-114">Cependant, lorsque vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="82245-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="82245-115">Pour mettre à jour l’URL simple Meet</span><span class="sxs-lookup"><span data-stu-id="82245-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="82245-116">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="82245-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="82245-117">Sélectionnez **URL simples** dans le volet de gauche, puis sous URL de la **réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="82245-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="82245-118">Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="82245-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="82245-119">Pour mettre à jour l’URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="82245-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="82245-120">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="82245-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="82245-121">Sélectionnez **URL simples** dans le volet de gauche, puis sous zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration de Skype entreprise Server, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="82245-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="82245-122">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin.</span><span class="sxs-lookup"><span data-stu-id="82245-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="82245-123">L’option la plus simple est https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="82245-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="82245-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82245-124">See also</span></span>

[<span data-ttu-id="82245-125">Configuration DNS requise pour les URL simples dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="82245-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
