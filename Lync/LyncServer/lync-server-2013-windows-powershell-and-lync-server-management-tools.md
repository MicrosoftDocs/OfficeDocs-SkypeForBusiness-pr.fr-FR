---
title: 'Lync Server 2013 : Outils de gestion de Windows PowerShell et Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814253d909ff7065ccc028cf5822be7a7331a2fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="014ac-102">Outils de gestion de Windows PowerShell et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="014ac-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="014ac-103">_**Dernière modification de la rubrique:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="014ac-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="014ac-104">Dans Microsoft Lync Server 2013, les outils de gestion sont implémentés à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="014ac-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="014ac-105">Windows PowerShell inclut un environnement de ligne de commande, des commandes spécifiques au produit et un langage de script complet.</span><span class="sxs-lookup"><span data-stu-id="014ac-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="014ac-106">Les outils Lync Server 2013 implémentés à l’aide de Windows PowerShell incluent les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="014ac-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="014ac-107">**Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="014ac-107">**Topology Builder**.</span></span> <span data-ttu-id="014ac-108">Le générateur de topologie vous permet de créer, d’ajuster et de publier votre topologie planifiée et de valider votre topologie avant de commencer les installations serveur.</span><span class="sxs-lookup"><span data-stu-id="014ac-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="014ac-109">Lorsque vous installez Lync Server 2013 sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur conformément aux instructions de la topologie.</span><span class="sxs-lookup"><span data-stu-id="014ac-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="014ac-110">After setup, configuration information is automatically replicated to all servers.</span><span class="sxs-lookup"><span data-stu-id="014ac-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="014ac-111">Components can be added to your deployment only by using Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="014ac-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="014ac-112">**Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="014ac-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="014ac-113">Vous pouvez utiliser Lync Server Management Shell pour une gestion complète de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="014ac-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="014ac-114">**Panneau de configuration de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="014ac-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="014ac-115">Vous pouvez utiliser l’interface utilisateur du panneau de configuration Microsoft Lync Server 2013 pour gérer les tâches les plus courantes dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="014ac-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="014ac-116">Ces outils utilisent des cmdlets Windows PowerShell pour la gestion de votre déploiement, y compris des applets de applet 550 spécifiques au produit.</span><span class="sxs-lookup"><span data-stu-id="014ac-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="014ac-117">Les applets de vérification intégrés à Lync Server 2013 servent essentiellement à gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="014ac-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="014ac-118">Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN).</span><span class="sxs-lookup"><span data-stu-id="014ac-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="014ac-119">De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basée sur un rôle (RBAC) pour déléguer le contrôle d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="014ac-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="014ac-120">Pour plus d’informations sur les applets de connexion Lync Server, voir [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="014ac-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="014ac-121">Les fonctionnalités de sécurité de script pour Windows PowerShell sont spécifiquement conçues pour éviter certains problèmes de sécurité liés au script des technologies plus anciennes, y compris Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="014ac-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="014ac-122">Les fonctionnalités de sécurité de Windows PowerShell sont conçues pour créer un environnement dans lequel les utilisateurs ne peuvent pas facilement exécuter de scripts ou sans le savoir.</span><span class="sxs-lookup"><span data-stu-id="014ac-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="014ac-123">Par défaut, les fonctionnalités de sécurité de Windows PowerShell sont activées.</span><span class="sxs-lookup"><span data-stu-id="014ac-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="014ac-124">Vous pouvez modifier l’état de ces fonctionnalités pour les adapter à vos besoins de script et à divers objectifs de sécurité.</span><span class="sxs-lookup"><span data-stu-id="014ac-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="014ac-125">Cela ne veut pas dire que le shell empêche les utilisateurs d’exécuter des scripts.</span><span class="sxs-lookup"><span data-stu-id="014ac-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="014ac-126">Mais plutôt, il est plus difficile, par défaut, pour les utilisateurs d’exécuter des scripts sans en avoir conscience.</span><span class="sxs-lookup"><span data-stu-id="014ac-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="014ac-127">Pour plus d’informations, consultez sécurité du script [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="014ac-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

