---
title: 'Lync Server 2013 : extensions de schéma, classes et attributs du schéma Active Directory utilisés par Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e393c5c65e77f22763380563e61c30bcdb69b23a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="85183-102">Extensions de schéma, classes et attributs du schéma Active Directory utilisés par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85183-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="85183-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="85183-104">Cette section de référence inclut les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="85183-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="85183-105">Extensions de schéma Active Directory nouvelles ou modifiées pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="85183-106">Le schéma Active Directory contient des définitions formelles de chaque classe d’objet pouvant être créée dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85183-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="85183-107">Il contient également des définitions formelles de chaque attribut pouvant exister dans un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85183-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="85183-108">Le catalogue global Active Directory contient les réplicas de tous les objets de la forêt, ainsi qu’un sous-ensemble d’attributs pour chaque objet.</span><span class="sxs-lookup"><span data-stu-id="85183-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="85183-109">Cette section décrit les classes et les attributs qui sont nouveaux ou modifiés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85183-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="85183-110">Toutes les classes utilisées par Lync Server, avec une description de chacune</span><span class="sxs-lookup"><span data-stu-id="85183-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="85183-111">Tous les attributs utilisés par Lync Server, avec une description de chaque</span><span class="sxs-lookup"><span data-stu-id="85183-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="85183-112">Une liste des classes utilisées par Lync Server, avec les attributs que chacun peut contenir ;</span><span class="sxs-lookup"><span data-stu-id="85183-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="85183-113">Objets et paramètres globaux, ainsi que groupes de services universels et d’administration, qui sont créés pendant la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="85183-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="85183-114">Entrées de contrôle d’accès (ACE) créées à la racine du domaine et conteneurs intégrés pendant la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="85183-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="85183-115">Modifications apportées à une unité d’organisation (UO) Active Directory par l'\_applet de commande Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="85183-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="85183-116">Modifications apportées à une unité d’organisation Active Directory par\_l’applet de commande Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="85183-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85183-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="85183-117">In This Section</span></span>

  - [<span data-ttu-id="85183-118">Modifications apportées au schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="85183-119">Classes de schéma et descriptions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="85183-120">Attributs et descriptions de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="85183-121">Attributs de schéma par classe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="85183-122">Modifications apportées par la préparation de la forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="85183-123">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="85183-124">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="85183-125">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85183-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

