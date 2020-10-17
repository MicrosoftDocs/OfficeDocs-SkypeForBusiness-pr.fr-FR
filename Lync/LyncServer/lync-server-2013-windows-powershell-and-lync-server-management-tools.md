---
title: 'Lync Server 2013 : outils de gestion Windows PowerShell et Lync Server'
description: 'Lync Server 2013 : outils de gestion Windows PowerShell et Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546040"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="ce0b4-103">Outils de gestion Windows PowerShell et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0b4-103">Windows PowerShell and Lync Server 2013 management tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0b4-104">_**Dernière modification de la rubrique :** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="ce0b4-104">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="ce0b4-105">Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-105">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="ce0b4-106">Windows PowerShell comprend un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-106">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="ce0b4-107">Les outils Lync Server 2013 qui sont implémentés à l’aide de Windows PowerShell sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ce0b4-107">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="ce0b4-108">**Générateur de topologies**.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-108">**Topology Builder**.</span></span> <span data-ttu-id="ce0b4-109">Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée, et de valider votre topologie avant de commencer les installations de serveurs.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-109">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="ce0b4-110">Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur comme indiqué dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-110">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="ce0b4-111">Après l’installation, les informations de configuration sont répliquées automatiquement sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-111">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="ce0b4-112">Les composants ne peuvent être ajoutés à votre déploiement qu’à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-112">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="ce0b4-113">**Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-113">**Lync Server Management Shell**.</span></span> <span data-ttu-id="ce0b4-114">Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de la ligne de commande de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-114">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="ce0b4-115">**Panneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-115">**Lync Server Control Panel**.</span></span> <span data-ttu-id="ce0b4-116">Vous pouvez utiliser l’interface utilisateur du panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-116">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="ce0b4-117">Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, y compris presque 550 applets de commande spécifiques au produit.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-117">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="ce0b4-118">Les cmdlets de sécurité incluses dans Lync Server 2013 sont principalement utilisées pour gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-118">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="ce0b4-119">Une large gamme d’applets de commande sont disponibles pour gérer l’authentification, dont certaines pour l’authentification de certificats et de codes confidentiels (PIN).</span><span class="sxs-lookup"><span data-stu-id="ce0b4-119">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="ce0b4-120">De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès Role-Based (RBAC) pour déléguer le contrôle administratif de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-120">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="ce0b4-121">Pour plus d’informations sur les applets de commande Lync Server, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ce0b4-121">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="ce0b4-122">Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains des problèmes de sécurité liés aux scripts de technologies plus anciennes, notamment Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="ce0b4-122">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="ce0b4-123">Les fonctionnalités de sécurité Windows PowerShell visent à créer un environnement dans lequel les utilisateurs ne peuvent pas exécuter facilement ou sans le savoir des scripts.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-123">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="ce0b4-124">Par défaut, les fonctionnalités de sécurité Windows PowerShell sont activées.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-124">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="ce0b4-125">Vous pouvez modifier l’état de ces fonctionnalités afin de répondre à vos besoins de script et à divers objectifs en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-125">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="ce0b4-126">Cela ne signifie pas que le shell empêche les utilisateurs d’exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-126">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="ce0b4-127">Au lieu de cela, l’environnement de commande Exchange Management Shell complique, par défaut, les utilisateurs qui exécutent des scripts sans les utiliser.</span><span class="sxs-lookup"><span data-stu-id="ce0b4-127">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="ce0b4-128">Pour plus d’informations, consultez la page relative à la sécurité des scripts Windows PowerShell à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .</span><span class="sxs-lookup"><span data-stu-id="ce0b4-128">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

