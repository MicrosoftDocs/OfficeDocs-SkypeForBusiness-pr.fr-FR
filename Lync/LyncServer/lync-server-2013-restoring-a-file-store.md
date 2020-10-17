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
ms.openlocfilehash: cd1984c6e51866b1ace707f305fb2a6cc356a132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511611"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="c34a2-102">Restauration d’un magasin de fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c34a2-102">Restoring a file store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c34a2-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="c34a2-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="c34a2-104">Les magasins de fichiers pour Standard Edition se trouvent généralement sur le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c34a2-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="c34a2-105">Les magasins de fichiers pour Enterprise Edition sont généralement stockés sur un serveur de fichiers ou un cluster.</span><span class="sxs-lookup"><span data-stu-id="c34a2-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="c34a2-106">La procédure suivante décrit comment restaurer un magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c34a2-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="c34a2-107">Pour restaurer un magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="c34a2-107">To restore a File Store</span></span>

1.  <span data-ttu-id="c34a2-108">Si un magasin de fichiers échoue, copiez le magasin de fichiers approprié à partir de $Backup \\ vers l’emplacement du magasin de fichiers sur le serveur de fichiers ou le serveur Standard Edition, puis partagez le dossier.</span><span class="sxs-lookup"><span data-stu-id="c34a2-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c34a2-109">Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé, afin que les composants qui utilisent les fichiers puissent y accéder.</span><span class="sxs-lookup"><span data-stu-id="c34a2-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="c34a2-110">Si nécessaire, définissez les listes de contrôle d’accès (ACL) pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c34a2-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="c34a2-111">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="c34a2-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c34a2-112">Vous devez effectuer cette étape uniquement si vous n’avez pas exécuté le générateur de topologie lors de votre processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="c34a2-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

