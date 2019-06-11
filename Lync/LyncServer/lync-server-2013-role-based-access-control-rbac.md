---
title: 'Lync Server 2013: contrôle d’accès basé sur les rôles (RBAC)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Role-based access control (RBAC) for Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59893872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75287cd418d22418f8de2c1a1b018eab8cca4e49
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="role-based-access-control-rbac-for-lync-server-2013"></a><span data-ttu-id="8a15d-102">Contrôle d’accès basé sur les rôles (RBAC) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a15d-102">Role-based access control (RBAC) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a15d-103">_**Dernière modification de la rubrique:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8a15d-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8a15d-104">Microsoft Lync Server 2013 inclut des groupes de contrôle d’accès basé sur les rôles (RBAC) pour vous permettre de déléguer des tâches administratives tout en préservant la sécurité.</span><span class="sxs-lookup"><span data-stu-id="8a15d-104">Microsoft Lync Server 2013 includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="8a15d-105">Ces groupes sont créés durant la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="8a15d-105">These groups are created during forest preparation.</span></span> <span data-ttu-id="8a15d-106">Pour plus d’informations sur la préparation de la forêt, voir [services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="8a15d-106">For details about forest preparation, see [Active Directory Domain Services for Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md).</span></span> <span data-ttu-id="8a15d-107">Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8a15d-107">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8a15d-108">Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes.</span><span class="sxs-lookup"><span data-stu-id="8a15d-108">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="8a15d-109">Chaque rôle est associé à une liste spécifique de cmdlets Lync Server Management Shell que les utilisateurs de ce rôle peuvent exécuter.</span><span class="sxs-lookup"><span data-stu-id="8a15d-109">Each role is associated with a specific list of Lync Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="8a15d-110">Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail.</span><span class="sxs-lookup"><span data-stu-id="8a15d-110">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> <span data-ttu-id="8a15d-111">Pour plus d’informations, reportez-vous à [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="8a15d-111">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

