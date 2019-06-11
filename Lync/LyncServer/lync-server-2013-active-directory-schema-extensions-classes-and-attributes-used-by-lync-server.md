---
title: 'Lync Server 2013 : Attributs, classes et extensions deq schémas Active Directory utilisés par Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc883c1c85acbe41bec6a25467e50800c036996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="6d459-102">Attributs, classes et extensions des schémas Active Directory utilisés par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d459-103">_**Dernière modification de la rubrique:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="6d459-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="6d459-104">Cette section de référence contient les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="6d459-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="6d459-105">Extensions de schéma Active Directory nouvelles ou modifiées pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="6d459-106">Le schéma Active Directory contient des définitions formels de toutes les classes d’objets qui peuvent être créées dans une forêt Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6d459-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="6d459-107">Le schéma contient également des définitions formels de chaque attribut qui peut exister sur un objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6d459-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="6d459-108">Le catalogue global Active Directory contient des réplicas de tous les objets pour la forêt, ainsi qu’un sous-ensemble des attributs de chaque objet.</span><span class="sxs-lookup"><span data-stu-id="6d459-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="6d459-109">Cette section décrit les classes et attributs qui sont nouveaux ou modifiés dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d459-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="6d459-110">Toutes les classes utilisées par Lync Server, avec une description de chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="6d459-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="6d459-111">Tous les attributs utilisés par Lync Server, avec une description de chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="6d459-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="6d459-112">Une liste des classes utilisées par Lync Server, ainsi que les attributs qu’ils contiennent</span><span class="sxs-lookup"><span data-stu-id="6d459-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="6d459-113">Paramètres globaux et objets, en plus du service universel et des groupes d’administration créés lors de la préparation de la forêt</span><span class="sxs-lookup"><span data-stu-id="6d459-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="6d459-114">Entrées de contrôle d’accès (ACE) créées sur la racine de domaine et les conteneurs intégrés lors de la préparation du domaine</span><span class="sxs-lookup"><span data-stu-id="6d459-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="6d459-115">Modifications effectuées sur une unité d’organisation Active Directory par l’applet de contrôle Grant\_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="6d459-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="6d459-116">Les modifications apportées sur une unité d’organisation Active Directory\_par l’applet de contrôle Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="6d459-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d459-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6d459-117">In This Section</span></span>

  - [<span data-ttu-id="6d459-118">Modifications de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="6d459-119">Descriptions et classes de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="6d459-120">Attributs et descriptions de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="6d459-121">Attributs de schéma par classe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="6d459-122">Modifications apportées par la préparation de la forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="6d459-123">Modifications apportées par la préparation du domaine dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="6d459-124">Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="6d459-125">Modifications apportées par Grant-CsOUPermission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d459-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

