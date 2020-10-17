---
title: 'Lync Server 2013 : configurer le stockage de fichiers DFS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7d5dc3675f06aafed18ddd18e430e2c61dc670
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537221"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="af7be-102">Configurer le stockage de fichiers DFS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af7be-102">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af7be-103">_**Dernière modification de la rubrique :** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="af7be-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="af7be-104">Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur un système de fichiers DFS.</span><span class="sxs-lookup"><span data-stu-id="af7be-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="af7be-105">Pour plus d’informations sur DFS pour Windows Server 2008, voir le guide pas à pas de DFS pour Windows Server 2008 à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Pour utiliser un DFS, Lync Server 2013 requiert les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="af7be-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="af7be-106">Les espaces de noms sont basés sur un domaine</span><span class="sxs-lookup"><span data-stu-id="af7be-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="af7be-107">Tous les serveurs d’espaces de noms exécutent un minimum de Windows 2008</span><span class="sxs-lookup"><span data-stu-id="af7be-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="af7be-108">Le programme d’installation de Lync Server 2013 nécessite que les autorisations sur le dossier partagé autorisent l’accès total à l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="af7be-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="af7be-109">Lync Server 2013 utilise alors les autorisations de fichiers NTFS pour afficher la liste de contrôle d’accès des dossiers.</span><span class="sxs-lookup"><span data-stu-id="af7be-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="af7be-110">Les autorisations héritées du partage DFS ne seront pas utilisées pour limiter l’accès.</span><span class="sxs-lookup"><span data-stu-id="af7be-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="af7be-111">Pour plus d’informations sur les exigences en matière de partage de fichiers, voir [File Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="af7be-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af7be-112">Vous pouvez consulter des informations sur la configuration d’un partage non DFS.</span><span class="sxs-lookup"><span data-stu-id="af7be-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="af7be-113">Si c’est le cas, consultez la <A href="lync-server-2013-hardware-setup.md">Configuration matérielle de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="af7be-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="af7be-114">La procédure suivante décrit comment configurer correctement les autorisations des dossiers partagés à l’aide de l’Assistant espace de noms DFS (comme décrit dans le Guide de configuration DFS).</span><span class="sxs-lookup"><span data-stu-id="af7be-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="af7be-115">Pour configurer les autorisations des dossiers partagés</span><span class="sxs-lookup"><span data-stu-id="af7be-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="af7be-116">Cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **gestion du système de fichiers distribués DFS**.</span><span class="sxs-lookup"><span data-stu-id="af7be-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="af7be-117">Dans l’arborescence de la console du composant logiciel enfichable de gestion du système de fichiers distribués DFS, cliquez avec le bouton droit sur le serveur d’espace de noms (par exemple, filesrv1.contoso.com), puis cliquez sur **modifier les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="af7be-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="af7be-118">Sélectionnez **autorisations sur les dossiers partagés**.</span><span class="sxs-lookup"><span data-stu-id="af7be-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="af7be-119">Sélectionnez **utiliser des autorisations personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="af7be-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="af7be-120">Pour le groupe administrateurs, sélectionnez les éléments suivants sous **autoriser**:</span><span class="sxs-lookup"><span data-stu-id="af7be-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="af7be-121">**Contrôle total**</span><span class="sxs-lookup"><span data-stu-id="af7be-121">**Full Control**</span></span>
    
      - <span data-ttu-id="af7be-122">**Change**</span><span class="sxs-lookup"><span data-stu-id="af7be-122">**Change**</span></span>
    
      - <span data-ttu-id="af7be-123">**Read**</span><span class="sxs-lookup"><span data-stu-id="af7be-123">**Read**</span></span>

6.  <span data-ttu-id="af7be-124">Cliquez sur **Appliquer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af7be-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

