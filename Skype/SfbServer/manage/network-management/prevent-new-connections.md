---
title: Empêcher les nouvelles connexions
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823464"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="62ee7-102">Empêcher les nouvelles connexions à Skype Entreprise Server pour la maintenance du serveur</span><span class="sxs-lookup"><span data-stu-id="62ee7-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="62ee7-103">Skype Entreprise Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à niveau logicielles ou matérielles) sans perte de service aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="62ee7-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="62ee7-p101">Quand vous spécifiez l’option qui empêche toute nouvelle connexion ou tout nouvel appel sur un serveur appartenant à un pool, Lync Server n’accepte plus de nouvelles connexions, ni de nouveaux appels une fois cette option implémentée. Quand un serveur empêche toute nouvelle connexion, il autorise ses sessions sur des connexions existantes à se poursuivre, jusqu’à ce qu’elles se terminent normalement. Une fois toutes les sessions existantes parvenues à terme, le serveur est prêt à être mis hors connexion.</span><span class="sxs-lookup"><span data-stu-id="62ee7-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="62ee7-108">Lorsque vous empêchez de nouvelles connexions à un serveur frontal, certaines fonctionnalités et services Skype Entreprise Server reposent sur l’équilibrage de charge DNS pour s’assurer qu’il fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="62ee7-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="62ee7-109">Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, il se peut que les connexions via ces services ne soient pas ré-acheminées vers d’autres serveurs pendant la période où le serveur empêche de nouvelles connexions, et par conséquent, lorsque le serveur est mis hors connexion, certaines sessions et appels peuvent être interrompus.</span><span class="sxs-lookup"><span data-stu-id="62ee7-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="62ee7-110">Les fonctionnalités qui s’appuient sur l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="62ee7-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="62ee7-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="62ee7-111">Attendant</span></span>

  - <span data-ttu-id="62ee7-112">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="62ee7-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="62ee7-113">Application Response Group</span><span class="sxs-lookup"><span data-stu-id="62ee7-113">Response Group application</span></span>

  - <span data-ttu-id="62ee7-114">application d’annonce</span><span class="sxs-lookup"><span data-stu-id="62ee7-114">Announcement application</span></span>

  - <span data-ttu-id="62ee7-115">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="62ee7-115">Call Park application</span></span>

<span data-ttu-id="62ee7-116">Pour plus d’informations sur l’équilibrage de charge DNS, voir [la liste des exigences d’équilibrage de charge.](../../plan-your-deployment/network-requirements/load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="62ee7-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="62ee7-117">En plus d’empêcher les nouvelles connexions pour tous les services sur un serveur exécutant Skype Entreprise Server, vous pouvez également empêcher les nouvelles connexions pour les services Skype Entreprise Server individuels.</span><span class="sxs-lookup"><span data-stu-id="62ee7-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="62ee7-118">Par exemple, cette méthode est utile lorsque vous devez appliquer une mise à jour Skype Entreprise Server qui ne nécessite pas l’arrêt de l’intégralité du serveur.</span><span class="sxs-lookup"><span data-stu-id="62ee7-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="62ee7-119">Veuillez noter que lorsque vous interdisez les connexions pour un service, vous devez sélectionner un service groupé et affiché dans la liste des services Windows.</span><span class="sxs-lookup"><span data-stu-id="62ee7-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="62ee7-120">Par exemple, le service Skype Entreprise Server Front-End et l’agent de collecte de données pour la surveillance sont des services Skype Entreprise Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés en tant que service frontal Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="62ee7-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="62ee7-121">Vous pouvez empêcher les nouvelles connexions pour le service frontal Skype Entreprise Server, mais vous ne pouvez pas empêcher les nouvelles connexions pour ces deux services Skype Entreprise Server sous-jacents séparément.</span><span class="sxs-lookup"><span data-stu-id="62ee7-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62ee7-p104">Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.</span><span class="sxs-lookup"><span data-stu-id="62ee7-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="62ee7-124">Pour empêcher les nouvelles connexions à Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="62ee7-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="62ee7-125">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="62ee7-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="62ee7-126">Ouvrez la console en ligne Services : **Cliquez** sur Démarrer, pointez sur Tous les **programmes,** pointez sur **Outils** d’administration, puis cliquez sur **Services**.</span><span class="sxs-lookup"><span data-stu-id="62ee7-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="62ee7-127">Dans la liste, double-cliquez sur le service Windows Skype Entreprise Server auquel vous souhaitez empêcher les nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="62ee7-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="62ee7-128">Dans la boîte de dialogue Propriétés, sous **État du service : Démarré**, cliquez sur **Suspendre**.</span><span class="sxs-lookup"><span data-stu-id="62ee7-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="62ee7-129">La méthode facultative et recommandée consiste à cliquer sur **Manuel**, en regard de **Type de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="62ee7-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="62ee7-p105">Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.</span><span class="sxs-lookup"><span data-stu-id="62ee7-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
