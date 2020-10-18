---
title: 'Lync Server 2013 : contrôle d’accès basé sur un rôle (RBAC)'
description: 'Lync Server 2013 : contrôle d’accès basé sur un rôle (RBAC).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6586517083ff6cd2c4e20d83e9b8f861edf800c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576580"
---
# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="b334b-103">Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b334b-103">Role-based access control (RBAC) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b334b-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b334b-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b334b-105">Microsoft Lync Server 2013 inclut des groupes de contrôle d’accès Role-Based (RBAC) pour vous permettre de déléguer des tâches administratives tout en conservant des normes de sécurité élevées.</span><span class="sxs-lookup"><span data-stu-id="b334b-105">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="b334b-106">Ces groupes sont créés pendant la phase de préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="b334b-106">These groups are created during forest preparation.</span></span> <span data-ttu-id="b334b-107">Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="b334b-107">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="b334b-108">Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b334b-108">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b334b-109">Avec RBAC, les privilèges d’administrateur sont accordés en affectant des utilisateurs à des rôles d’administration prédéfinis, notamment les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes.</span><span class="sxs-lookup"><span data-stu-id="b334b-109">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="b334b-110">Chaque rôle est associé à une liste spécifique de cmdlets Lync Server Management Shell que les utilisateurs de ce rôle sont autorisés à exécuter.</span><span class="sxs-lookup"><span data-stu-id="b334b-110">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="b334b-111">Vous pouvez utiliser le contrôle RBAC pour suivre le principe du « privilège minimal », dans lequel les utilisateurs disposent uniquement des capacités administratives requises par leurs travaux.</span><span class="sxs-lookup"><span data-stu-id="b334b-111">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="b334b-112">Pour plus d’informations, reportez-vous à la rubrique [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b334b-112">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

