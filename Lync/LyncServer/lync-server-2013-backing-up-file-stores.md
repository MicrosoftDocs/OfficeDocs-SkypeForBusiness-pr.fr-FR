---
title: 'Lync Server 2013 : sauvegarde des magasins de fichiers'
description: 'Lync Server 2013 : sauvegarde des magasins de fichiers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6a92d189c39242be1b2167ffc336d9eb406719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563280"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="4f04c-103">Sauvegarde de magasins de fichiers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f04c-103">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f04c-104">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4f04c-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4f04c-105">La sauvegarde des magasins de fichiers Lync Server inclut tous les fichiers et dossiers utilisés par les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f04c-105">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="4f04c-106">Pour sauvegarder des magasins de fichiers</span><span class="sxs-lookup"><span data-stu-id="4f04c-106">To back up File Stores</span></span>

1.  <span data-ttu-id="4f04c-107">Pour rechercher les emplacements spécifiques de vos magasins de fichiers Lync Server, ouvrez le générateur de topologies et regardez dans le nœud **magasins de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="4f04c-107">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="4f04c-108">Utilisez Robocopy ou un autre outil de gestion de système de fichiers pour copier chaque magasin de fichiers vers $Backup de stockage de fichiers \\ .</span><span class="sxs-lookup"><span data-stu-id="4f04c-108">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

