---
title: Empêcher les nouvelles connexions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817453"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="0d36c-102">Blocage de nouvelles connexions à Skype entreprise Server pour la maintenance du serveur</span><span class="sxs-lookup"><span data-stu-id="0d36c-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="0d36c-103">Skype entreprise Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à jour logicielles ou matérielles) sans aucune perte de service aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0d36c-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="0d36c-104">Lorsque vous spécifiez l’option permettant d’éviter de nouvelles connexions ou appels vers un serveur d’un pool, il cesse de prendre de nouvelles connexions et appels dès que vous implémentez cette option.</span><span class="sxs-lookup"><span data-stu-id="0d36c-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="0d36c-105">Ces nouvelles connexions et appels sont routés par le biais d’autres serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="0d36c-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="0d36c-106">Un serveur qui empêche de nouvelles connexions autorise la poursuite de ses sessions sur les connexions existantes jusqu’à ce qu’il se termine de façon naturelle.</span><span class="sxs-lookup"><span data-stu-id="0d36c-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="0d36c-107">Lorsque toutes les sessions existantes sont terminées, le serveur est prêt à être déconnecté.</span><span class="sxs-lookup"><span data-stu-id="0d36c-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="0d36c-108">Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Skype entreprise Server dépendent de l’équilibrage de charge DNS pour s’assurer qu’elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="0d36c-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="0d36c-109">Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs au cours de la période pendant laquelle le serveur empêche les nouvelles connexions, et par conséquent, lorsque le serveur est hors connexion, certaines sessions et appels peuvent être garantir.</span><span class="sxs-lookup"><span data-stu-id="0d36c-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="0d36c-110">Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d36c-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="0d36c-111">Intendant</span><span class="sxs-lookup"><span data-stu-id="0d36c-111">Attendant</span></span>

  - <span data-ttu-id="0d36c-112">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="0d36c-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="0d36c-113">application Response Group</span><span class="sxs-lookup"><span data-stu-id="0d36c-113">Response Group application</span></span>

  - <span data-ttu-id="0d36c-114">application d’annonce</span><span class="sxs-lookup"><span data-stu-id="0d36c-114">Announcement application</span></span>

  - <span data-ttu-id="0d36c-115">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="0d36c-115">Call Park application</span></span>

<span data-ttu-id="0d36c-116">Pour plus d’informations sur l’équilibrage de charge DNS, voir [exigences d’équilibrage de charge](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="0d36c-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="0d36c-117">Outre la prévention de nouvelles connexions pour tous les services sur un serveur exécutant Skype entreprise Server, vous pouvez également interdire de nouvelles connexions pour les services Skype entreprise Server individuels.</span><span class="sxs-lookup"><span data-stu-id="0d36c-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="0d36c-118">Par exemple, cette méthode est utile dans le cas où vous devez appliquer une mise à jour de Skype entreprise Server qui ne nécessite pas l’arrêt de l’intégralité du serveur.</span><span class="sxs-lookup"><span data-stu-id="0d36c-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="0d36c-119">Notez que lorsque vous interdisez les connexions d’un service, vous devez sélectionner un service tel qu’il est groupé et affiché dans la liste des services Windows.</span><span class="sxs-lookup"><span data-stu-id="0d36c-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="0d36c-120">Par exemple, le service frontal de Skype entreprise Server et l’agent de collecte des données pour la surveillance sont des services Skype entreprise Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés sous la forme de Skype entreprise Server front-end service.</span><span class="sxs-lookup"><span data-stu-id="0d36c-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="0d36c-121">Vous pouvez éviter de nouvelles connexions au service frontal Skype entreprise Server, mais vous ne pouvez pas empêcher les nouvelles connexions de ces deux services sous-jacents de Skype entreprise Server séparément.</span><span class="sxs-lookup"><span data-stu-id="0d36c-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d36c-122">Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage.</span><span class="sxs-lookup"><span data-stu-id="0d36c-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="0d36c-123">Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="0d36c-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="0d36c-124">Pour éviter de nouvelles connexions à Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0d36c-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="0d36c-125">Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0d36c-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="0d36c-126">Ouvrez la console enfichable Services : cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.</span><span class="sxs-lookup"><span data-stu-id="0d36c-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="0d36c-127">Dans la liste, double-cliquez sur le service Windows Skype entreprise Server sur lequel vous voulez empêcher les nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="0d36c-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="0d36c-128">Dans la boîte de dialogue Propriétés, sous **État du service : démarré**, cliquez sur **suspendre**.</span><span class="sxs-lookup"><span data-stu-id="0d36c-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="0d36c-129">Si vous le souhaitez, mais que vous avez le choix, en regard de **type de démarrage**, cliquez sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="0d36c-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0d36c-130">Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage.</span><span class="sxs-lookup"><span data-stu-id="0d36c-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="0d36c-131">Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="0d36c-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
