---
title: 'Lync Server 2013 : afficher une liste des applications approuvées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="5e8eb-102">Afficher une liste des applications approuvées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e8eb-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e8eb-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5e8eb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5e8eb-104">Vous pouvez utiliser le panneau de configuration de Lync Server 2013 pour afficher la liste des applications approuvées que vous avez déployées dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="5e8eb-105">Une application fiable est une application basée sur le kit de développement logiciel (Unified Communications Managed API UCMA) 3,0 principal du SDK approuvé par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="5e8eb-106">Cette relation d’approbation est résumée dans la liste suivante :</span><span class="sxs-lookup"><span data-stu-id="5e8eb-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="5e8eb-107">Les applications approuvées ne sont pas confrontées à l’authentification par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="5e8eb-108">Les applications approuvées ne sont pas limitées par Lync Server pour les transactions SIP, les connexions ou les appels voix sur IP sortants.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="5e8eb-109">Les applications approuvées peuvent emprunter l’identité d’un utilisateur et participer à des conférences sans apparaître dans les listes.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="5e8eb-110">Les applications approuvées sont hautement disponibles et résilientes.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="5e8eb-111">Dans le panneau de configuration de Lync Server, vous pouvez voir le nom de l’application, le pool sur lequel elle s’exécute et le port utilisé.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="5e8eb-112">Pour afficher une liste des applications approuvées</span><span class="sxs-lookup"><span data-stu-id="5e8eb-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="5e8eb-113">À partir d’un compte d’utilisateur affecté au CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="5e8eb-114">Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Lync Server 2013, voir [planification du contrôle d’accès basé sur les rôles dans Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="5e8eb-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="5e8eb-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5e8eb-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5e8eb-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5e8eb-117">Dans la barre de navigation de gauche, cliquez sur **Topology** et sur **application de confiance**.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="5e8eb-118">Dans la page **application fiable** , cliquez sur un en-tête de colonne pour trier les applications si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5e8eb-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e8eb-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e8eb-119">See Also</span></span>


[<span data-ttu-id="5e8eb-120">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e8eb-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

