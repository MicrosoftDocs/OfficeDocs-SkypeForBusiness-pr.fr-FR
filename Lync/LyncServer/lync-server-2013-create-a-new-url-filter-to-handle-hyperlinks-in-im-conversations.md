---
title: Créer un nouveau filtre d’URL pour gérer les liens hypertexte dans les conversations de messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b129f2f9f1aa4b9a2a07a63d0432957f2b79941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501911"
---
# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a><span data-ttu-id="a004d-102">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="a004d-102">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a004d-103">_**Dernière modification de la rubrique :** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a004d-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a004d-104">En plus de modifier le filtre d’URL globales, vous pouvez configurer des filtres d’URL personnalisés pour des sites individuels au sein de votre déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a004d-104">In addition to modifying the global URL filter, you can configure custom URL filters for individual sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="a004d-105">Pour plus d’informations sur le filtrage des URL, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="a004d-105">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-new-url-filter"></a><span data-ttu-id="a004d-106">Pour créer un filtre d’URL</span><span class="sxs-lookup"><span data-stu-id="a004d-106">To create a new URL filter</span></span>

1.  <span data-ttu-id="a004d-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a004d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a004d-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a004d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a004d-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a004d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a004d-110">Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre d’URL**.</span><span class="sxs-lookup"><span data-stu-id="a004d-110">In the left navigation bar, click **IM and Presence**, and then click **URL Filter**.</span></span>

4.  <span data-ttu-id="a004d-111">Dans la page **Filtre d’URL**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a004d-111">On the **URL Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="a004d-112">Dans la boîte de dialogue **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre d’URL, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a004d-112">In **Select a Site**, click the site for which you want to create the URL filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="a004d-113">Dans la boîte de dialogue **Nouveau filtre d’URL**, activez la case à cocher **Activer le filtre d’URL** pour activer le filtrage d’URL sur le site.</span><span class="sxs-lookup"><span data-stu-id="a004d-113">In the **New URL Filter** dialog box, select the **Enable URL Filter** check box to enable URL filtering for the site.</span></span>

7.  <span data-ttu-id="a004d-114">Pour bloquer une URL active qui contient un fichier dont l’extension figure sous **Extensions de types de fichiers à bloquer** dans **Modifier le filtre de fichiers**, activez la case à cocher **Bloquer les URL avec extension de fichier**.</span><span class="sxs-lookup"><span data-stu-id="a004d-114">To block any active URL that contains a file with an extension listed under **File type extensions to block** in **Edit File Filter**, select the **Block URLs with file extension** check box.</span></span>

8.  <span data-ttu-id="a004d-115">Dans la zone de liste déroulante **Préfixe de lient hypertexte**, cliquez sur l’option correspondant à la manière dont vous voulez gérer les URL dans les conversations de messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="a004d-115">In the **Hyperlink prefix** drop-down list box, click the option that corresponds to how you want to handle URLs in instant message conversations.</span></span>
    
    <span data-ttu-id="a004d-116">Lorsque la case à cocher **Autoriser le message** est activée, un message d’avertissement peut être envoyé à l’utilisateur lors de l’envoi des liens hypertexte autorisés à être envoyés.</span><span class="sxs-lookup"><span data-stu-id="a004d-116">The **Allow message** box enables a warning message to be sent to the user when sending hyperlinks that are allowed to be sent.</span></span>

9.  <span data-ttu-id="a004d-117">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a004d-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a004d-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a004d-118">See Also</span></span>


[<span data-ttu-id="a004d-119">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a004d-119">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="a004d-120">Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="a004d-120">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="a004d-121">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a004d-121">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="a004d-122">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a004d-122">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

