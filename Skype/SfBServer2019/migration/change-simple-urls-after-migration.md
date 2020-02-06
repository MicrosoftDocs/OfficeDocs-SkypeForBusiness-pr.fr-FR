---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype entreprise Server prend en charge des URL simples.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813882"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="b7368-103">Modification des URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="b7368-103">Change simple URLs after migration</span></span>

<span data-ttu-id="b7368-104">Skype entreprise Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="b7368-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="b7368-105">La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="b7368-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="b7368-106">Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser.</span><span class="sxs-lookup"><span data-stu-id="b7368-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="b7368-107">Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b7368-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="b7368-108">L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b7368-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="b7368-109">L' **administrateur** permet d’accéder rapidement au panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b7368-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b7368-110">L’URL simple Admin est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b7368-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="b7368-111">Après la migration vers Skype entreprise Server, vous devez tenir compte des différences entre les enregistrements DNS et les certificats pour des URL simples.</span><span class="sxs-lookup"><span data-stu-id="b7368-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="b7368-112">Si le directeur Skype entreprise Server hérité reste utilisé dans la topologie, aucune modification de vos URL simples n’est requise.</span><span class="sxs-lookup"><span data-stu-id="b7368-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="b7368-113">Si le directeur de Skype entreprise Server est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour de manière à ce qu’ils pointent vers l’une des listes de serveurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b7368-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="b7368-114">Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque réalisateur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="b7368-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="b7368-115">Pour mettre à jour l’URL de réunion simple</span><span class="sxs-lookup"><span data-stu-id="b7368-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="b7368-116">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b7368-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="b7368-117">Sélectionnez **URL simples** dans le volet gauche, puis sous **URL de la réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="b7368-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="b7368-118">Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée.</span><span class="sxs-lookup"><span data-stu-id="b7368-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="b7368-119">Pour mettre à jour l’URL simple d’administration</span><span class="sxs-lookup"><span data-stu-id="b7368-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="b7368-120">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Skype entreprise Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b7368-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="b7368-121">Sélectionnez **URL simples** dans le volet gauche, puis sous **URL d’accès administratif** , entrez l’URL que vous voulez pour l’accès administratif à Skype entreprise Server panneau de configuration, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7368-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="b7368-122">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="b7368-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="b7368-123">L’option la plus simple https://adminest. <em>Domain (domaine\>). \<</em></span><span class="sxs-lookup"><span data-stu-id="b7368-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b7368-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7368-124">See also</span></span>

[<span data-ttu-id="b7368-125">Configuration DNS requise pour les URL simples dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b7368-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
