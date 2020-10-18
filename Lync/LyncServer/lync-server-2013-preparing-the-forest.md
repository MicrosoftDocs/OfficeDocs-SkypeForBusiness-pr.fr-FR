---
title: 'Lync Server 2013 : préparation de la forêt'
description: 'Lync Server 2013 : préparation de la forêt.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580000"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="f6b21-103">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6b21-103">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6b21-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f6b21-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f6b21-105">La préparation de la forêt crée des paramètres globaux et des objets Active Directory, ainsi que des groupes universels Active Directory pour une utilisation par Lync Server 2013, et accorde des autorisations d’accès appropriées sur les objets Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6b21-105">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="f6b21-106">Pour obtenir une description des groupes universels, ainsi que les paramètres globaux et les objets créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="f6b21-106">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="f6b21-107">La préparation de la forêt crée également des objets contenant des jeux de propriétés et des spécificateurs d’affichage utilisés par Lync Server 2013 et les stocke dans le conteneur de configuration.</span><span class="sxs-lookup"><span data-stu-id="f6b21-107">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f6b21-108">Assurez-vous que les modifications de préparation de schéma ont été répliquées sur tous les contrôleurs de domaine avant d’effectuer la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="f6b21-108">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="f6b21-109">Si la réplication ne s’est pas terminée, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="f6b21-109">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="f6b21-110">Si vous effectuez un nouveau déploiement de Lync Server, vous devez stocker les paramètres globaux dans le conteneur de configuration.</span><span class="sxs-lookup"><span data-stu-id="f6b21-110">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="f6b21-111">Si vous effectuez une mise à niveau à partir d’une version antérieure et que vous stockez toujours les paramètres globaux dans le conteneur système, vous pouvez continuer à utiliser le conteneur système.</span><span class="sxs-lookup"><span data-stu-id="f6b21-111">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="f6b21-112">Pour effectuer cette procédure, vous devez être membre du groupe Administrateurs d’entreprise ou Administrateurs de domaine pour le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="f6b21-112">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f6b21-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f6b21-113">In This Section</span></span>

  - [<span data-ttu-id="f6b21-114">Exécution de la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6b21-114">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="f6b21-115">Utilisation d’applets de commande pour inverser la préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6b21-115">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

