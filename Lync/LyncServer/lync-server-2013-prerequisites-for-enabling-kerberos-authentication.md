---
title: 'Lync Server 2013 : conditions préalables pour l’activation de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0be98112431b9e57486bb33e0eab84eada94e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506781"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="c4150-102">Conditions préalables à l’activation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4150-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4150-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c4150-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c4150-104">Avant d’activer l’authentification Kerberos, veillez à effectuer toutes les préparations de configuration et d’infrastructure prérequises :</span><span class="sxs-lookup"><span data-stu-id="c4150-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="c4150-105">Le schéma Active Directory est étendu pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4150-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="c4150-106">La préparation de la forêt Active Directory est terminée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4150-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="c4150-107">La préparation du domaine Active Directory est terminée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4150-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="c4150-108">Le magasin central de gestion est correctement installé et disponible.</span><span class="sxs-lookup"><span data-stu-id="c4150-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="c4150-109">La topologie a été créée et publiée à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c4150-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="c4150-110">Les serveurs et les rôles nécessitant des services Web ont été définis et déployés, y compris les serveurs frontaux, les serveurs Standard Edition et les directeurs.</span><span class="sxs-lookup"><span data-stu-id="c4150-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="c4150-111">Les services Internet (IIS) sont configurés et déployés avec les services de rôle recommandés pour prendre en charge les services Web dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4150-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="c4150-112">Une fois que les conditions préalables sont remplies, vous devez être prêt à créer un ou plusieurs comptes pour les services Web à utiliser pour l’authentification Kerberos de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="c4150-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="c4150-113">Vous devez créer au moins un compte d’authentification Kerberos pour chaque déploiement.</span><span class="sxs-lookup"><span data-stu-id="c4150-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="c4150-114">Néanmoins, vous pouvez créer un compte pour chaque site, afin de permettre l’authentification Kerberos locale au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="c4150-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="c4150-115">Vous ne pouvez spécifier qu’un seul compte d’authentification Kerberos par site.</span><span class="sxs-lookup"><span data-stu-id="c4150-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

