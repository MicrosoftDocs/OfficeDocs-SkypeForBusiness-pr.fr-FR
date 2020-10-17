---
title: 'Lync Server 2013 : démarrer les services sur les serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532961"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="842a2-102">Démarrer des services sur des serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="842a2-102">Start services on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="842a2-103">_**Dernière modification de la rubrique :** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="842a2-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="842a2-104">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins ou disposer des autorisations déléguées adéquates.</span><span class="sxs-lookup"><span data-stu-id="842a2-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="842a2-105">Pour plus d’informations sur la délégation d’autorisations, consultez la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="842a2-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="842a2-106">Après avoir installé le magasin de configuration local sur vos serveurs, installé les composants Lync Server 2013 et configuré des certificats sur un serveur frontal ou un serveur frontal, vous devez démarrer les services Lync Server 2013 sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="842a2-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="842a2-107">Utilisez la procédure suivante pour démarrer les services sur chaque serveur frontal de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="842a2-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="842a2-108">Pour démarrer les services sur un serveur frontal ou Standard Edition</span><span class="sxs-lookup"><span data-stu-id="842a2-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="842a2-109">Dans l’Assistant Déploiement de Lync Server, sur la page **Lync server 2013** , cliquez sur **exécuter** à côté de **étape 4 : démarrer les services**.</span><span class="sxs-lookup"><span data-stu-id="842a2-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="842a2-110">Sur la page **Démarrer les services** , cliquez sur **suivant** pour démarrer les services Lync Server sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="842a2-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="842a2-111">Sur la page **Exécution de commandes**, une fois que tous les services ont démarré correctement, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="842a2-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="842a2-112">Pour vérifier que les services ont bien démarré, nous vous recommandons d’utiliser la commande de démarrage des services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="842a2-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="842a2-113">Cependant, il est possible qu’elle n’indique pas l’état actuel du service.</span><span class="sxs-lookup"><span data-stu-id="842a2-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="842a2-114">Nous vous recommandons de suivre l’étape <STRONG>État des services (facultatif)</STRONG> juste après <STRONG>Démarrage de services</STRONG> pour ouvrir la console MMC (Microsoft Management Console) et confirmer que les services ont correctement démarré.</span><span class="sxs-lookup"><span data-stu-id="842a2-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="842a2-115">Si un service Lync Server n’a pas démarré, vous pouvez cliquer avec le bouton droit sur ce service dans la console MMC, puis cliquer sur <STRONG>Démarrer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="842a2-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

