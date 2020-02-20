---
title: 'Lync Server 2013 : configuration de l’invitation à la réunion'
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
ms.openlocfilehash: 0bd615179a3aac9edcebb45dd2241ebf17453951
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="662d5-102">Configuration de l’invitation à la réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="662d5-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="662d5-103">_**Dernière modification de la rubrique :** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="662d5-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="662d5-104">Vous pouvez personnaliser les invitations aux réunions envoyées par le complément de réunion en ligne pour Lync 2013 en incluant les éléments facultatifs suivants dans le corps de l’invitation à la réunion :</span><span class="sxs-lookup"><span data-stu-id="662d5-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="662d5-105">**Logo de votre organisation** Ajoutez le logo de votre organisation aux invitations aux réunions à l’aide de l’option URL du logo.</span><span class="sxs-lookup"><span data-stu-id="662d5-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="662d5-106">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’image doit se trouver à l’URL publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="662d5-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="662d5-107">Les formats d’image pris en charge sont GIF et JPG.</span><span class="sxs-lookup"><span data-stu-id="662d5-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="662d5-108">Bien que Lync Server 2013 stocke l’URL sans aucune restriction de taille sur l’image, pour obtenir de meilleurs résultats, la taille maximale de l’image doit être de 30 pixels de haut par 188 pixels de large.</span><span class="sxs-lookup"><span data-stu-id="662d5-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="662d5-109">**Un lien d’aide ou de support personnalisé** Ajoutez une URL pour le site Web de l’aide ou de l’équipe de support de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="662d5-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="662d5-110">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="662d5-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="662d5-111">La longueur maximale de l’URL est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="662d5-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="662d5-112">**Texte de la clause d’exclusion de responsabilité légale** Ajoutez une URL pour le texte légal ou une clause d’exclusion de responsabilité qui s’affichera dans toutes les invitations à une réunion.</span><span class="sxs-lookup"><span data-stu-id="662d5-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="662d5-113">Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible.</span><span class="sxs-lookup"><span data-stu-id="662d5-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="662d5-114">La longueur maximale de l’URL est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="662d5-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="662d5-115">**Texte de pied de page personnalisé** Ajouter du texte qui sera affiché sous la forme d’un pied de page personnalisé dans l’invitation.</span><span class="sxs-lookup"><span data-stu-id="662d5-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="662d5-116">La longueur maximale du texte pouvant être ajouté est de 2 Ko.</span><span class="sxs-lookup"><span data-stu-id="662d5-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="662d5-117">Vous pouvez configurer ces options à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="662d5-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="662d5-118">**Pour personnaliser l’invitation à une réunion à l’aide du panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="662d5-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="662d5-119">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="662d5-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="662d5-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="662d5-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="662d5-121">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="662d5-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="662d5-122">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="662d5-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="662d5-123">Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="662d5-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="662d5-p106">Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="662d5-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="662d5-p107">Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="662d5-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="662d5-130">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="662d5-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="662d5-131">Dans le champ **URL du logo** , tapez l’URL de l’image du logo de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="662d5-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="662d5-132">Dans le champ URL de l' **aide** , entrez l’URL du site d’aide ou de support de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="662d5-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="662d5-133">Dans le champ **texte juridique** , tapez l’URL du texte ou de la clause d’exclusion de responsabilité que vous souhaitez inclure dans les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="662d5-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="662d5-134">Dans le champ de **texte de pied de page personnalisé** , tapez texte de pied de page, jusqu’à 2 Ko.</span><span class="sxs-lookup"><span data-stu-id="662d5-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="662d5-135">**Pour personnaliser l’invitation à une réunion à l’aide de Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="662d5-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="662d5-136">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="662d5-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="662d5-137">Exécutez la cmdlet **New-CsMeetingConfiguration** ou **Set-CsMeetingConfiguration** pour créer ou configurer les options d’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="662d5-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="662d5-138">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="662d5-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

