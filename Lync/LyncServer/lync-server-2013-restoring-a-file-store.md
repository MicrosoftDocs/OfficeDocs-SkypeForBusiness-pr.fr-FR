---
title: 'Lync Server 2013 : restauration d’un magasin de fichiers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="bab03-102">Restauration d’un magasin de fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bab03-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bab03-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="bab03-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="bab03-104">Les magasins de fichiers pour l’édition standard sont généralement situés sur le serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="bab03-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="bab03-105">Les magasins de fichiers pour Enterprise Edition sont généralement situés sur un serveur de fichiers ou un cluster.</span><span class="sxs-lookup"><span data-stu-id="bab03-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="bab03-106">La procédure suivante vous explique comment restaurer un magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bab03-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="bab03-107">Pour restaurer un magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="bab03-107">To restore a File Store</span></span>

1.  <span data-ttu-id="bab03-108">En cas d’échec d’un magasin de fichiers, copiez le\\ magasin de fichiers approprié à partir de $Backup à l’emplacement de stockage des fichiers sur le serveur de fichiers ou Standard Edition Server, puis partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="bab03-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bab03-109">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être exactement les mêmes que ceux du magasin de fichiers sauvegardés, afin que les composants qui utilisent les fichiers puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="bab03-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="bab03-110">Le cas échéant, définissez les listes de contrôle d’accès (ACL) pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="bab03-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="bab03-111">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="bab03-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bab03-112">Vous ne devez effectuer cette étape que si vous n’avez pas exécuté de générateur de topologie lors du processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="bab03-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

