---
title: 'Lync Server 2013 : Préparation des services de domaine Active Directory verrouillés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="82db8-102">Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82db8-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82db8-103">_**Dernière modification de la rubrique:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="82db8-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="82db8-104">Les organisations verrouillent souvent les services de domaine Active Directory pour réduire les risques liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="82db8-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="82db8-105">Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82db8-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="82db8-106">La préparation correcte d’un environnement Active Directory verrouillé pour Lync Server 2013 implique quelques considérations et étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="82db8-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="82db8-107">Il existe deux méthodes courantes pour lesquelles les autorisations sont limitées dans un environnement Active Directory verrouillé:</span><span class="sxs-lookup"><span data-stu-id="82db8-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="82db8-108">Les entrées de contrôle d’accès des utilisateurs authentifiées (ACE) sont supprimées des conteneurs.</span><span class="sxs-lookup"><span data-stu-id="82db8-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="82db8-109">L’héritage des autorisations est désactivé sur les conteneurs d’objets utilisateur, de contact, de InetOrgPerson ou d’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="82db8-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82db8-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="82db8-110">In This Section</span></span>

  - [<span data-ttu-id="82db8-111">Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82db8-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="82db8-112">Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82db8-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

