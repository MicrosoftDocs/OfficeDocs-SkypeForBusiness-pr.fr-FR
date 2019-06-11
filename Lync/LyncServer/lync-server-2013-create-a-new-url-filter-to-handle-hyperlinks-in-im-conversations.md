---
title: Créer un nouveau filtre d’URL pour gérer les liens hypertexte dans les conversations par messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="6fb92-102">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="6fb92-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fb92-103">_**Dernière modification de la rubrique:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="6fb92-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="6fb92-104">Outre la modification du filtre d’URL global, vous pouvez configurer des filtres d’URL personnalisés pour des sites individuels au sein de votre déploiement 2013 Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fb92-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="6fb92-105">Pour plus d’informations sur le filtrage d’URL, voir [configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="6fb92-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="6fb92-106">Pour créer un nouveau filtre d’URL</span><span class="sxs-lookup"><span data-stu-id="6fb92-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="6fb92-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6fb92-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6fb92-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fb92-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fb92-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6fb92-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fb92-110">Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence**, puis cliquez sur **filtre d’URL**.</span><span class="sxs-lookup"><span data-stu-id="6fb92-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="6fb92-111">Dans la page de **filtre d’URL** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6fb92-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="6fb92-112">Dans **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre d’URL, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fb92-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="6fb92-113">Dans la boîte de dialogue **nouveau filtre d’URL** , activez la case à cocher **activer** le filtrage d’URL pour le site.</span><span class="sxs-lookup"><span data-stu-id="6fb92-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="6fb92-114">Pour bloquer toute URL active contenant un fichier avec une extension répertoriée sous **extensions de type de fichier à bloquer** dans la boîte de réception **modifier le filtre de fichier**, activez la case à cocher bloquer les **URL avec l’extension de fichier** .</span><span class="sxs-lookup"><span data-stu-id="6fb92-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="6fb92-115">Dans la zone de liste déroulante des **liens hypertexte** , cliquez sur l’option qui correspond à la manière dont vous souhaitez gérer les URL dans les conversations par messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="6fb92-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="6fb92-116">La boîte de **dialogue autoriser le message** permet d’envoyer un message d’avertissement à l’utilisateur lors de l’envoi de liens hypertexte qui peuvent être envoyés.</span><span class="sxs-lookup"><span data-stu-id="6fb92-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="6fb92-117">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6fb92-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fb92-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fb92-118">See Also</span></span>


[<span data-ttu-id="6fb92-119">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb92-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="6fb92-120">Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="6fb92-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="6fb92-121">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb92-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="6fb92-122">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fb92-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

