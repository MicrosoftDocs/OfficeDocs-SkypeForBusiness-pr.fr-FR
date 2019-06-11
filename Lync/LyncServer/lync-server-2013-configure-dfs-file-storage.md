---
title: 'Lync Server 2013 : Configuration du stockage des fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="46bae-102">Configuration du stockage des fichiers pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46bae-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46bae-103">_**Dernière modification de la rubrique:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="46bae-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="46bae-104">Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur un système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="46bae-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="46bae-105">Pour plus d’informations sur le système de fichiers DFS pour Windows Server 2008, voir le guide détaillé pour Windows Server 2008 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)à l’adresse. Pour utiliser un système de fichiers DFS, Lync Server 2013 nécessite les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="46bae-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="46bae-106">Les espaces de noms sont basés sur le domaine</span><span class="sxs-lookup"><span data-stu-id="46bae-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="46bae-107">Tous les serveurs d’espaces de noms exécutent au moins une 2008 Windows</span><span class="sxs-lookup"><span data-stu-id="46bae-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="46bae-108">Le programme d’installation de Lync Server 2013 exige que les autorisations sur le dossier partagé autorisent l’accès total à l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="46bae-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="46bae-109">Lync Server 2013 utilisera alors les autorisations de fichier NTFS pour afficher une liste de contrôle d’accès aux dossiers.</span><span class="sxs-lookup"><span data-stu-id="46bae-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="46bae-110">Les autorisations héritées du partage DFS ne seront pas utilisées pour limiter l’accès.</span><span class="sxs-lookup"><span data-stu-id="46bae-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="46bae-111">Pour plus d’informations sur la configuration requise du partage de fichiers, voir [prise en charge du stockage de fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="46bae-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46bae-112">Vous recherchez des informations sur la configuration d’un partage non-DFS.</span><span class="sxs-lookup"><span data-stu-id="46bae-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="46bae-113">Si tel est le cas, consultez <A href="lync-server-2013-hardware-setup.md">Configuration matérielle pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="46bae-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="46bae-114">La procédure suivante décrit comment configurer correctement les autorisations de dossier partagé à l’aide de l’Assistant espace de noms DFS (comme décrit dans le Guide de configuration de DFS).</span><span class="sxs-lookup"><span data-stu-id="46bae-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="46bae-115">Pour configurer les autorisations sur les dossiers partagés</span><span class="sxs-lookup"><span data-stu-id="46bae-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="46bae-116">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **gestion DFS**.</span><span class="sxs-lookup"><span data-stu-id="46bae-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="46bae-117">Dans l’arborescence de la console, cliquez avec le bouton droit sur le serveur d’espaces de noms (par exemple, filesrv1.contoso.com), puis cliquez sur **modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="46bae-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="46bae-118">Sélectionnez **autorisations sur le dossier partagé**.</span><span class="sxs-lookup"><span data-stu-id="46bae-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="46bae-119">Sélectionnez **utiliser des autorisations personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="46bae-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="46bae-120">Pour le groupe administrateur, sélectionnez les options suivantes sous **autoriser**:</span><span class="sxs-lookup"><span data-stu-id="46bae-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="46bae-121">**Contrôle total**</span><span class="sxs-lookup"><span data-stu-id="46bae-121">**Full Control**</span></span>
    
      - <span data-ttu-id="46bae-122">**Modification**</span><span class="sxs-lookup"><span data-stu-id="46bae-122">**Change**</span></span>
    
      - <span data-ttu-id="46bae-123">**Suit**</span><span class="sxs-lookup"><span data-stu-id="46bae-123">**Read**</span></span>

6.  <span data-ttu-id="46bae-124">Cliquez sur **appliquer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46bae-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

