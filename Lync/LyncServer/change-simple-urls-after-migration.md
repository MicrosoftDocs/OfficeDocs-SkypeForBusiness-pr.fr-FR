---
title: Modifier les URL simples après la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def26afe2bae21a7a3b6d0ffae4b358c76296e6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="96ce6-102">Modifier les URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="96ce6-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96ce6-103">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="96ce6-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="96ce6-104">Lync Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="96ce6-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="96ce6-p101">**Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Avec l’URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre, à communiquer et à distribuer.</span><span class="sxs-lookup"><span data-stu-id="96ce6-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="96ce6-p102">**Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="96ce6-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="96ce6-109">L' **administrateur** permet un accès rapide au panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96ce6-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="96ce6-110">L’URL simple d’administration est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="96ce6-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="96ce6-111">Après avoir effectué la migration vers Lync Server 2013, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="96ce6-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="96ce6-112">Si le directeur Lync Server 2010 hérité reste utilisé dans la topologie, aucune modification de vos URL simples n’est requise.</span><span class="sxs-lookup"><span data-stu-id="96ce6-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="96ce6-113">Si le directeur Lync Server 2010 est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour pour pointer vers l’un des pools Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96ce6-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="96ce6-114">Cependant, lorsque vous modifiez le nom d’une URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="96ce6-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="96ce6-115">Modification des URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="96ce6-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="96ce6-116">**Pour mettre à jour l’URL simple Meet**</span><span class="sxs-lookup"><span data-stu-id="96ce6-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="96ce6-117">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="96ce6-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="96ce6-118">Sélectionnez **URL simples** dans le volet de gauche, puis sous URL de la **réunion :** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="96ce6-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="96ce6-119">Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="96ce6-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="96ce6-120">**Pour mettre à jour l’URL simple Admin**</span><span class="sxs-lookup"><span data-stu-id="96ce6-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="96ce6-121">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="96ce6-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="96ce6-122">Sélectionnez **URL simples** dans le volet gauche, en dessous de zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration Lync Server 2013, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="96ce6-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="96ce6-123">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin.</span><span class="sxs-lookup"><span data-stu-id="96ce6-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="96ce6-124">L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;domaine&gt;.</span><span class="sxs-lookup"><span data-stu-id="96ce6-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96ce6-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96ce6-125">See Also</span></span>


[<span data-ttu-id="96ce6-126">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96ce6-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

