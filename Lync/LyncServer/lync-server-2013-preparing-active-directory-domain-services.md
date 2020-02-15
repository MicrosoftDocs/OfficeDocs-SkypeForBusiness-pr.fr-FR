---
title: 'Lync Server 2013 : préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ba47445194f4b7d4c02966404c03ee981e1c76
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="54b40-102">Préparation des services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54b40-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="54b40-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="54b40-104">Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma, puis en créant et en configurant des objets.</span><span class="sxs-lookup"><span data-stu-id="54b40-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="54b40-105">Les extensions de schéma ajoutent les classes et attributs Active Directory requis par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54b40-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="54b40-106">Les rubriques de cette section expliquent comment préparer AD DS pour le déploiement de Lync Server et comment affecter des autorisations de configuration et d’unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="54b40-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="54b40-107">Pour plus d’informations sur les modifications de schéma requises pour Lync Server, voir [extensions de schéma Active Directory, classes et attributs utilisés par Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="54b40-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54b40-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="54b40-108">In This Section</span></span>

  - [<span data-ttu-id="54b40-109">Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="54b40-110">Vue d’ensemble de la préparation des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="54b40-111">Préparation des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="54b40-112">Préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="54b40-113">Octroi d’autorisations dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54b40-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

