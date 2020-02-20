---
title: 'Lync Server 2013 : outils de gestion Windows PowerShell et Lync Server'
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
ms.openlocfilehash: fda7b6d7fa78dc7c5152084014e19a7b086287bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="55ce5-102">Outils de gestion Windows PowerShell et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55ce5-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55ce5-103">_**Dernière modification de la rubrique :** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="55ce5-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="55ce5-104">Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55ce5-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="55ce5-105">Windows PowerShell comprend un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="55ce5-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="55ce5-106">Les outils Lync Server 2013 qui sont implémentés à l’aide de Windows PowerShell sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="55ce5-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="55ce5-107">**Générateur de topologies**.</span><span class="sxs-lookup"><span data-stu-id="55ce5-107">**Topology Builder**.</span></span> <span data-ttu-id="55ce5-108">Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée, et de valider votre topologie avant de commencer les installations de serveurs.</span><span class="sxs-lookup"><span data-stu-id="55ce5-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="55ce5-109">Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur comme indiqué dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="55ce5-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="55ce5-110">Après l’installation, les informations de configuration sont répliquées automatiquement sur tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="55ce5-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="55ce5-111">Les composants ne peuvent être ajoutés à votre déploiement qu’à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="55ce5-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="55ce5-112">**Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="55ce5-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="55ce5-113">Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de la ligne de commande de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="55ce5-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="55ce5-114">**Panneau de configuration Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="55ce5-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="55ce5-115">Vous pouvez utiliser l’interface utilisateur du panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="55ce5-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="55ce5-116">Ces outils utilisent des applets de commande Windows PowerShell pour la gestion de votre déploiement, y compris presque 550 applets de commande spécifiques au produit.</span><span class="sxs-lookup"><span data-stu-id="55ce5-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="55ce5-117">Les cmdlets de sécurité incluses dans Lync Server 2013 sont principalement utilisées pour gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="55ce5-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="55ce5-118">Une large gamme d’applets de commande sont disponibles pour gérer l’authentification, dont certaines pour l’authentification de certificats et de codes confidentiels (PIN).</span><span class="sxs-lookup"><span data-stu-id="55ce5-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="55ce5-119">De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basé sur un rôle (RBAC) pour déléguer le contrôle administratif de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55ce5-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="55ce5-120">Pour plus d’informations sur les applets de commande Lync Server, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="55ce5-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="55ce5-121">Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains des problèmes de sécurité liés aux scripts de technologies plus anciennes, notamment Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="55ce5-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="55ce5-122">Les fonctionnalités de sécurité Windows PowerShell visent à créer un environnement dans lequel les utilisateurs ne peuvent pas exécuter facilement ou sans le savoir des scripts.</span><span class="sxs-lookup"><span data-stu-id="55ce5-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="55ce5-123">Par défaut, les fonctionnalités de sécurité Windows PowerShell sont activées.</span><span class="sxs-lookup"><span data-stu-id="55ce5-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="55ce5-124">Vous pouvez modifier l’état de ces fonctionnalités afin de répondre à vos besoins de script et à divers objectifs en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="55ce5-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="55ce5-125">Cela ne signifie pas que le shell empêche les utilisateurs d’exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="55ce5-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="55ce5-126">Au lieu de cela, l’environnement de commande Exchange Management Shell complique, par défaut, les utilisateurs qui exécutent des scripts sans les utiliser.</span><span class="sxs-lookup"><span data-stu-id="55ce5-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="55ce5-127">Pour plus d’informations, consultez la page relative [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145)à la sécurité des scripts Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="55ce5-127">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

