---
title: Modification des URL simples après la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0203b33d787310544f4f376872ecf9c99fc7254d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="395d3-102">Modification des URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="395d3-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="395d3-103">_**Dernière modification de la rubrique:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="395d3-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="395d3-104">Lync Server prend en charge trois URL simples:</span><span class="sxs-lookup"><span data-stu-id="395d3-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="395d3-105">La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="395d3-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="395d3-106">Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser.</span><span class="sxs-lookup"><span data-stu-id="395d3-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="395d3-107">Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="395d3-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="395d3-108">L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="395d3-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="395d3-109">L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="395d3-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="395d3-110">L’URL simple Admin est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="395d3-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="395d3-111">Après avoir effectué la migration vers Lync Server 2013, vous devez tenir compte de la façon dont le changement a un impact sur vos enregistrements et certificats DNS pour des URL simples.</span><span class="sxs-lookup"><span data-stu-id="395d3-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="395d3-112">Si le réalisateur du serveur Lync Server 2010 hérité reste en cours d’utilisation dans la topologie, aucune modification de vos URL simples n’est requise.</span><span class="sxs-lookup"><span data-stu-id="395d3-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="395d3-113">Si le directeur de Lync Server 2010 est supprimé de la topologie après la migration, les enregistrements DNS d’URL simples doivent être mis à jour de manière à ce qu’ils pointent vers l’une des listes 2013 du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="395d3-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="395d3-114">Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter Enable-CsComputer sur chaque réalisateur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="395d3-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="395d3-115">Modification d’URL simples après la migration</span><span class="sxs-lookup"><span data-stu-id="395d3-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="395d3-116">**Pour mettre à jour l’URL de réunion simple**</span><span class="sxs-lookup"><span data-stu-id="395d3-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="395d3-117">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="395d3-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="395d3-118">Sélectionnez **URL simples** dans le volet gauche, puis sous **URL de la réunion:** sélectionnez l’URL de la réunion, puis cliquez sur **modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="395d3-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="395d3-119">Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée.</span><span class="sxs-lookup"><span data-stu-id="395d3-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="395d3-120">**Pour mettre à jour l’URL simple d’administration**</span><span class="sxs-lookup"><span data-stu-id="395d3-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="395d3-121">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="395d3-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="395d3-122">Sélectionnez **URL simples** dans le volet gauche, puis sous **URL d’accès administratif** , entrez l’URL de votre choix pour l’accès administratif à Lync Server 2013 panneau de configuration, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="395d3-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="395d3-123">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="395d3-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="395d3-124">L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;Domain&gt;(domaine).</span><span class="sxs-lookup"><span data-stu-id="395d3-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="395d3-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="395d3-125">See Also</span></span>


[<span data-ttu-id="395d3-126">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="395d3-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

