---
title: 'Lync Server 2013 : créer un nouveau filtre de transfert de fichiers pour un site spécifique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="f4e92-102">Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="f4e92-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e92-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f4e92-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f4e92-104">Outre la modification du filtre global de transfert de fichiers, vous pouvez configurer des filtres de transfert de fichier personnalisés pour des sites spécifiques au sein de votre déploiement 2013 Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4e92-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="f4e92-105">Pour plus d’informations sur le filtrage du transfert de fichiers, voir [configurer le transfert de fichiers et le filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="f4e92-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="f4e92-106">Pour créer un filtre de transfert de fichiers pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="f4e92-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="f4e92-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f4e92-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4e92-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4e92-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f4e92-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f4e92-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f4e92-110">Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence** , puis cliquez sur **filtre de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="f4e92-111">Dans la page **filtre de fichier** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="f4e92-112">Dans la boîte de dialogue **Sélectionner un site** , cliquez sur le site pour lequel vous souhaitez créer le filtre de transfert de fichiers, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="f4e92-113">Dans le **nouveau filtre de fichier**, activez la case à cocher **activer le filtre de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="f4e92-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="f4e92-114">Dans la zone de liste déroulante **transfert de fichier** , cliquez sur **bloquer tout** ou **bloquer des types de fichiers spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="f4e92-115">Si vous avez cliqué sur **bloquer tout**, passez à l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="f4e92-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="f4e92-116">Si vous avez cliqué sur **bloquer des types de fichiers spécifiques**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4e92-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="f4e92-117">Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier que vous voulez bloquer.</span><span class="sxs-lookup"><span data-stu-id="f4e92-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="f4e92-118">Dans la boîte de dialogue **Sélectionner le type de fichier** , sélectionnez les types de fichiers que vous souhaitez bloquer ou autoriser en ajoutant ou en supprimant leurs extensions des catégories sous extensions de type de **fichier**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="f4e92-119">Si vous ne voyez pas l’extension correspondant au type de fichier que vous voulez bloquer, tapez l’extension dans la zone de texte sous **Ajouter des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="f4e92-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-120">Click **OK**.</span></span>

10. <span data-ttu-id="f4e92-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f4e92-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4e92-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4e92-122">See Also</span></span>


[<span data-ttu-id="f4e92-123">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e92-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="f4e92-124">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f4e92-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="f4e92-125">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e92-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="f4e92-126">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4e92-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

