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
ms.openlocfilehash: f5fa366ae27126ead478d66c3beb091581158d1a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="f8fc2-102">Conditions préalables à l’activation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8fc2-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8fc2-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f8fc2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f8fc2-104">Avant d’activer l’authentification Kerberos, veillez à effectuer toutes les préparations de configuration et d’infrastructure prérequises :</span><span class="sxs-lookup"><span data-stu-id="f8fc2-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="f8fc2-105">Le schéma Active Directory est étendu pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="f8fc2-106">La préparation de la forêt Active Directory est terminée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="f8fc2-107">La préparation du domaine Active Directory est terminée pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="f8fc2-108">Le magasin central de gestion est correctement installé et disponible.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="f8fc2-109">La topologie a été créée et publiée à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="f8fc2-110">Les serveurs et les rôles nécessitant des services Web ont été définis et déployés, y compris les serveurs frontaux, les serveurs Standard Edition et les directeurs.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="f8fc2-111">Les services Internet (IIS) sont configurés et déployés avec les services de rôle recommandés pour prendre en charge les services Web dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="f8fc2-112">Une fois que les conditions préalables sont remplies, vous devez être prêt à créer un ou plusieurs comptes pour les services Web à utiliser pour l’authentification Kerberos de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="f8fc2-113">Vous devez créer au moins un compte d’authentification Kerberos pour chaque déploiement.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="f8fc2-114">Néanmoins, vous pouvez créer un compte pour chaque site, afin de permettre l’authentification Kerberos locale au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="f8fc2-115">Vous ne pouvez spécifier qu’un seul compte d’authentification Kerberos par site.</span><span class="sxs-lookup"><span data-stu-id="f8fc2-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

