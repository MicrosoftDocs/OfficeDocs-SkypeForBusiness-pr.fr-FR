---
title: 'Lync Server 2013 : configuration de l’invitation à la réunion'
description: 'Lync Server 2013 : configuration de l’invitation à la réunion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64438d7a451cb794c125207fa594e1c00b534c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564330"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="386e2-103">Configuration de l’invitation à la réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="386e2-103">Configuring the meeting invitation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="386e2-104">_**Dernière modification de la rubrique :** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="386e2-104">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="386e2-105">Vous pouvez personnaliser les invitations aux réunions envoyées par le complément de réunion en ligne pour Lync 2013 en incluant les éléments facultatifs suivants dans le corps de l’invitation à la réunion :</span><span class="sxs-lookup"><span data-stu-id="386e2-105">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="386e2-106">**Logo de votre organisation** Ajoutez le logo de votre organisation aux invitations aux réunions à l’aide de l’option URL du logo.</span><span class="sxs-lookup"><span data-stu-id="386e2-106">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="386e2-107">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’image doit se trouver à l’URL publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="386e2-107">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="386e2-108">Les formats d’image pris en charge sont GIF et JPG.</span><span class="sxs-lookup"><span data-stu-id="386e2-108">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="386e2-109">Bien que Lync Server 2013 stocke l’URL sans aucune restriction de taille sur l’image, pour obtenir de meilleurs résultats, la taille maximale de l’image doit être de 30 pixels de haut par 188 pixels de large.</span><span class="sxs-lookup"><span data-stu-id="386e2-109">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="386e2-110">**Un lien d’aide ou de support personnalisé** Ajoutez une URL pour le site Web de l’aide ou de l’équipe de support de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="386e2-110">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="386e2-111">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="386e2-111">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="386e2-112">La longueur maximale de l’URL est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="386e2-112">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="386e2-113">**Texte de la clause d’exclusion de responsabilité légale** Ajoutez une URL pour le texte légal ou une clause d’exclusion de responsabilité qui s’affichera dans toutes les invitations à une réunion.</span><span class="sxs-lookup"><span data-stu-id="386e2-113">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="386e2-114">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="386e2-114">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="386e2-115">La longueur maximale de l’URL est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="386e2-115">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="386e2-116">**Texte de pied de page personnalisé** Ajouter du texte qui sera affiché sous la forme d’un pied de page personnalisé dans l’invitation.</span><span class="sxs-lookup"><span data-stu-id="386e2-116">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="386e2-117">La longueur maximale du texte pouvant être ajouté est de 2 Ko.</span><span class="sxs-lookup"><span data-stu-id="386e2-117">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="386e2-118">Vous pouvez configurer ces options à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="386e2-118">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="386e2-119">**Pour personnaliser l’invitation à une réunion à l’aide du panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="386e2-119">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="386e2-120">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="386e2-120">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="386e2-121">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="386e2-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="386e2-122">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="386e2-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="386e2-123">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="386e2-123">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="386e2-124">Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="386e2-124">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="386e2-p106">Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="386e2-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="386e2-p107">Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="386e2-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="386e2-131">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="386e2-131">Do any of the following:</span></span>
    
      - <span data-ttu-id="386e2-132">Dans le champ **URL du logo** , tapez l’URL de l’image du logo de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="386e2-132">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="386e2-133">Dans le champ URL de l' **aide** , entrez l’URL du site d’aide ou de support de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="386e2-133">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="386e2-134">Dans le champ **texte juridique** , tapez l’URL du texte ou de la clause d’exclusion de responsabilité que vous souhaitez inclure dans les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="386e2-134">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="386e2-135">Dans le champ de **texte de pied de page personnalisé** , tapez texte de pied de page, jusqu’à 2 Ko.</span><span class="sxs-lookup"><span data-stu-id="386e2-135">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="386e2-136">**Pour personnaliser l’invitation à une réunion à l’aide de Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="386e2-136">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="386e2-137">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="386e2-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="386e2-138">Exécutez la cmdlet **New-CsMeetingConfiguration** ou **Set-CsMeetingConfiguration** pour créer ou configurer les options d’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="386e2-138">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="386e2-139">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="386e2-139">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

