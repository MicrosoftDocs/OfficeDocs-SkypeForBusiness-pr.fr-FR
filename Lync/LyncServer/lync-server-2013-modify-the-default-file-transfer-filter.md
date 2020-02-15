---
title: 'Lync Server 2013 : modifier le filtre de transfert de fichiers par défaut'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3e0da5402ea93ce33e844a2f8b32d545d4811a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="0a44e-102">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a44e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a44e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a44e-104">Lync Server 2013 fournit un filtre de transfert de fichiers global qui bloque des types de fichiers spécifiques lors des activités de fichier suivantes dans votre déploiement Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="0a44e-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="0a44e-105">Demandes de transfert de fichiers pendant les conversations de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="0a44e-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="0a44e-106">Chargements et téléchargements pendant l’utilisation de la fonctionnalité des documents dans le client Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="0a44e-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="0a44e-107">Lecture multimédia pendant les conférences</span><span class="sxs-lookup"><span data-stu-id="0a44e-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="0a44e-108">En fonction des types de fichiers que vous voulez bloquer ou autoriser, vous pouvez utiliser le panneau de configuration Lync Server pour modifier le filtre global.</span><span class="sxs-lookup"><span data-stu-id="0a44e-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="0a44e-109">Pour plus d’informations sur le filtrage du transfert de fichiers, voir [Configuring File Transfer and URL Filtering for Instant Messaging (im) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="0a44e-110">Pour modifier le filtre de transfert de fichiers par défaut</span><span class="sxs-lookup"><span data-stu-id="0a44e-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="0a44e-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0a44e-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a44e-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a44e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a44e-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a44e-114">Dans la barre de navigation de gauche, cliquez sur **Messagerie instantanée et présence**, puis cliquez sur **Filtre de fichier**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="0a44e-115">Dans la page **Filtre de fichier**, double-cliquez sur le filtre **Global**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="0a44e-116">Dans **Modifier le filtre de fichier**, activez la case à cocher **Activer le filtre de fichier**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="0a44e-117">Dans la zone de liste déroulante **Transfert de fichiers**, cliquez sur **Bloquer tout** ou **Bloquer des types de fichiers spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="0a44e-118">Si vous avez cliqué sur **Bloquer tout**, passez à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="0a44e-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="0a44e-119">Si vous avez cliqué sur **Bloquer des types de fichiers spécifiques**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0a44e-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="0a44e-120">Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier à bloquer.</span><span class="sxs-lookup"><span data-stu-id="0a44e-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="0a44e-121">Dans **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous voulez bloquer ou autoriser en ajoutant ou en supprimant leur extension dans les catégories sous **Extensions de type de fichier**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="0a44e-122">Si l’extension du type de fichier que vous souhaitez bloquer n’apparaît pas, tapez-la dans la zone de texte sous **Ajoutez des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="0a44e-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-123">Click **OK**.</span></span>

9.  <span data-ttu-id="0a44e-124">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a44e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a44e-125">See Also</span></span>


[<span data-ttu-id="0a44e-126">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="0a44e-127">Créer un nouveau filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="0a44e-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="0a44e-128">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="0a44e-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="0a44e-129">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

