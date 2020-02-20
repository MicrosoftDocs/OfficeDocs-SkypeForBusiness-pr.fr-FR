---
title: 'Lync Server 2013 : préparation des services de domaine Active Directory verrouillés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8ea746ba8ea2ddea8d696d42865324da60ecbc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="ed46e-102">Préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed46e-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed46e-103">_**Dernière modification de la rubrique :** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="ed46e-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="ed46e-104">Les organisations verrouillent souvent les services de domaine Active Directory pour limiter les risques de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ed46e-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="ed46e-105">Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed46e-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="ed46e-106">La préparation correcte d’un environnement Active Directory verrouillé pour Lync Server 2013 implique des considérations et des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ed46e-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="ed46e-107">Deux méthodes courantes permettent de limiter les autorisations dans un environnement Active Directory verrouillé :</span><span class="sxs-lookup"><span data-stu-id="ed46e-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="ed46e-108">Les entrées de contrôle d’accès des utilisateurs authentifiés sont supprimées des conteneurs.</span><span class="sxs-lookup"><span data-stu-id="ed46e-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="ed46e-109">L’héritage des autorisations est désactivé dans les conteneurs des objets Utilisateur, Contact, InetOrgPerson ou Ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ed46e-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed46e-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ed46e-110">In This Section</span></span>

  - [<span data-ttu-id="ed46e-111">Les autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed46e-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="ed46e-112">L’héritage des autorisations est désactivé sur les conteneurs ordinateurs, utilisateurs ou InetOrgPerson dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed46e-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

