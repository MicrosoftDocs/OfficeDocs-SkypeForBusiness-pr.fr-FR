---
title: 'Lync Server 2013 : création d’un filtre de transfert de fichiers pour un site spécifique'
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
ms.openlocfilehash: 911f01c4ce104c3cdd641a793065c14bed43abb4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a><span data-ttu-id="4788f-102">Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="4788f-102">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4788f-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="4788f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="4788f-104">En plus de modifier le filtre de transfert de fichiers global, vous pouvez configurer des filtres de transfert de fichiers personnalisés pour des sites spécifiques au sein de votre déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4788f-104">In addition to modifying the global file transfer filter, you can configure custom file transfer filters for specific sites within your Lync Server 2013 deployment.</span></span> <span data-ttu-id="4788f-105">Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="4788f-105">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a><span data-ttu-id="4788f-106">Pour créer un filtre de transfert de fichiers adapté à un site spécifique</span><span class="sxs-lookup"><span data-stu-id="4788f-106">To create a file transfer filter for a specific site</span></span>

1.  <span data-ttu-id="4788f-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4788f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4788f-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4788f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4788f-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4788f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4788f-110">Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre de fichier**.</span><span class="sxs-lookup"><span data-stu-id="4788f-110">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="4788f-111">Dans la page **Filtre de fichier**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="4788f-111">On the **File Filter** page, click **New**.</span></span>

5.  <span data-ttu-id="4788f-112">Dans la boîte de dialogue **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre de transfert de fichiers, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4788f-112">In the **Select a Site** dialog box, click the site for which you want to create the file transfer filter, and then click **OK**.</span></span>

6.  <span data-ttu-id="4788f-113">Dans **Nouveau filtre de fichier**, activez la case à cocher **Activer le filtre de fichier**.</span><span class="sxs-lookup"><span data-stu-id="4788f-113">In **New File Filter**, click the **Enable file filter** check box.</span></span>

7.  <span data-ttu-id="4788f-114">Dans la zone de liste déroulante **Transfert de fichiers**, cliquez sur **Bloquer tout** ou **Bloquer des types de fichiers spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="4788f-114">In **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

8.  <span data-ttu-id="4788f-115">Si vous avez cliqué sur **Bloquer tout**, passez à l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="4788f-115">If you clicked **Block All**, skip to step 10.</span></span>

9.  <span data-ttu-id="4788f-116">Si vous avez cliqué sur **Bloquer des types de fichiers spécifiques**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4788f-116">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="4788f-117">Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier à bloquer.</span><span class="sxs-lookup"><span data-stu-id="4788f-117">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="4788f-118">Dans la boîte de dialogue **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous voulez bloquer ou autoriser en ajoutant ou en supprimant leur extension dans les catégories sous **Sélectionner des extensions de type de fichier**.</span><span class="sxs-lookup"><span data-stu-id="4788f-118">In the **Select File Type** dialog box, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="4788f-119">Si l’extension du type de fichier que vous souhaitez bloquer n’apparaît pas, tapez-la dans la zone de texte sous **Ajoutez des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4788f-119">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="4788f-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4788f-120">Click **OK**.</span></span>

10. <span data-ttu-id="4788f-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4788f-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4788f-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4788f-122">See Also</span></span>


[<span data-ttu-id="4788f-123">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4788f-123">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="4788f-124">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="4788f-124">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="4788f-125">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4788f-125">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[<span data-ttu-id="4788f-126">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4788f-126">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

