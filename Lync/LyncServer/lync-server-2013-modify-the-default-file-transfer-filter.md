---
title: 'Lync Server 2013: modifier le filtre de transfert de fichiers par défaut'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a><span data-ttu-id="59b01-102">Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b01-102">Modify the default file transfer filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59b01-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="59b01-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="59b01-104">Lync Server 2013 fournit un filtre de transfert de fichiers global qui bloque des types de fichiers spécifiques pendant les activités suivantes relatives aux fichiers dans votre déploiement de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="59b01-104">Lync Server 2013 provides a global file transfer filter that blocks specific types of files during the following file-related activities within your Lync Server 2013 deployment:</span></span>

  - <span data-ttu-id="59b01-105">Demandes de transfert de fichiers lors des conversations de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="59b01-105">File transfer requests during instant messaging (IM) conversations</span></span>

  - <span data-ttu-id="59b01-106">Chargement et téléchargement de fichiers lors de l’utilisation de la fonctionnalité de documentation dans le client Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="59b01-106">File uploads and downloads while using the handout feature in the Office Live Meeting 2007 client</span></span>

  - <span data-ttu-id="59b01-107">Lecture de contenu multimédia lors de conférences</span><span class="sxs-lookup"><span data-stu-id="59b01-107">Multimedia playback during conferences</span></span>

<span data-ttu-id="59b01-108">En fonction des types de fichiers que vous souhaitez bloquer ou autoriser, vous pouvez utiliser le panneau de configuration de Lync Server pour modifier le filtre global.</span><span class="sxs-lookup"><span data-stu-id="59b01-108">Depending on the types of files you want to block or allow, you can use Lync Server Control Panel to modify the global filter.</span></span> <span data-ttu-id="59b01-109">Pour plus d’informations sur le filtrage du transfert de fichiers, voir [configurer le transfert de fichiers et le filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-109">For details about file transfer filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a><span data-ttu-id="59b01-110">Pour modifier le filtre de transfert de fichiers par défaut</span><span class="sxs-lookup"><span data-stu-id="59b01-110">To modify the default file transfer filter</span></span>

1.  <span data-ttu-id="59b01-111">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="59b01-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59b01-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b01-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59b01-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="59b01-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59b01-114">Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence** , puis cliquez sur **filtre de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="59b01-114">In the left navigation bar, click **IM and Presence** and then click **File Filter**.</span></span>

4.  <span data-ttu-id="59b01-115">Sur la page **filtre de fichiers** , double-cliquez sur le filtre **Global** .</span><span class="sxs-lookup"><span data-stu-id="59b01-115">On the **File Filter** page, double-click the **Global** filter.</span></span>

5.  <span data-ttu-id="59b01-116">Dans **modifier le filtre de fichier**, activez la case à cocher **activer le filtre de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="59b01-116">In **Edit File Filter**, select the **Enable file filter** check box.</span></span>

6.  <span data-ttu-id="59b01-117">Dans la zone de liste déroulante **transfert de fichiers** , cliquez sur **bloquer tout** ou **bloquer des types de fichiers spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="59b01-117">In the **File transfer** drop-down list box, click **Block All** or **Block specific file types**.</span></span>

7.  <span data-ttu-id="59b01-118">Si vous avez cliqué sur **bloquer tout**, passez à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="59b01-118">If you clicked **Block All**, skip to step 9.</span></span>

8.  <span data-ttu-id="59b01-119">Si vous avez cliqué sur **bloquer des types de fichiers spécifiques**, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="59b01-119">If you clicked **Block specific file types**, do the following:</span></span>
    
    1.  <span data-ttu-id="59b01-120">Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier que vous voulez bloquer.</span><span class="sxs-lookup"><span data-stu-id="59b01-120">Click **Select** to modify the default list of file type extensions that you want to block.</span></span>
    
    2.  <span data-ttu-id="59b01-121">Dans **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous souhaitez bloquer ou autoriser en ajoutant ou en supprimant leurs extensions des catégories sous **extensions de type de fichier**.</span><span class="sxs-lookup"><span data-stu-id="59b01-121">In **Select File Type**, select the file types that you want to block or allow by adding or removing their extensions from the categories under **File type extensions**.</span></span>
    
    3.  <span data-ttu-id="59b01-122">Si vous ne voyez pas l’extension correspondant au type de fichier que vous voulez bloquer, tapez l’extension dans la zone de texte sous **Ajouter des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="59b01-122">If you do not see the extension for a file type that you want to block, type the extension in the text box under **Add file type extensions to the list**, and then click **Add**.</span></span>
    
    4.  <span data-ttu-id="59b01-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="59b01-123">Click **OK**.</span></span>

9.  <span data-ttu-id="59b01-124">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="59b01-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59b01-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59b01-125">See Also</span></span>


[<span data-ttu-id="59b01-126">Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b01-126">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="59b01-127">Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique</span><span class="sxs-lookup"><span data-stu-id="59b01-127">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="59b01-128">Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="59b01-128">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[<span data-ttu-id="59b01-129">Modifier le filtre d’URL par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b01-129">Modify the default URL filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

