---
title: 'Lync Server 2013 : marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="88d5a-102">Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88d5a-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88d5a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="88d5a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="88d5a-104">Les applications serveur MSPL (Microsoft SIP Processing Language) sont des applications qui utilisent le langage de script MSPL au lieu de l’API 2010 Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="88d5a-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="88d5a-105">Certaines applications serveur MSPL sont spécifiées comme étant critiques.</span><span class="sxs-lookup"><span data-stu-id="88d5a-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="88d5a-106">Si le script est essentiel, le script doit commencer au démarrage du système pour que Lync Server 2013 commence.</span><span class="sxs-lookup"><span data-stu-id="88d5a-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="88d5a-107">Si le script échoue alors que Lync Server est en cours d’exécution, le serveur ne s’arrête pas, mais il cesse d’envoyer du trafic au script et il écrit les erreurs dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="88d5a-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="88d5a-108">Vous pouvez utiliser le panneau de configuration de Lync Server pour marquer les applications serveur MSPL (Microsoft SIP Processing Language) comme étant critiques ou annuler la marque.</span><span class="sxs-lookup"><span data-stu-id="88d5a-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="88d5a-109">Tous les scripts ne prennent pas en charge cette option.</span><span class="sxs-lookup"><span data-stu-id="88d5a-109">Not all scripts support this option.</span></span> <span data-ttu-id="88d5a-110">Par exemple, le script DefaultRouting est marqué comme Critical et cette option ne peut pas être modifiée pour DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="88d5a-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="88d5a-111">Pour marquer ou démarquer une application serveur MSPL comme essentielle</span><span class="sxs-lookup"><span data-stu-id="88d5a-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="88d5a-112">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88d5a-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="88d5a-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88d5a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88d5a-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88d5a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88d5a-115">Dans la barre de navigation de gauche, cliquez sur **topologie** , puis sur **application serveur**.</span><span class="sxs-lookup"><span data-stu-id="88d5a-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="88d5a-116">Dans la page de l' **application serveur** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant, puis cliquez sur l’application serveur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="88d5a-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="88d5a-117">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="88d5a-117">Click **Action**.</span></span>

6.  <span data-ttu-id="88d5a-118">Cliquez sur **marquer comme critique** ou **désélectionner comme critique** (autrement dit, si le script prend en charge cette option).</span><span class="sxs-lookup"><span data-stu-id="88d5a-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88d5a-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88d5a-119">See Also</span></span>


[<span data-ttu-id="88d5a-120">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88d5a-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="88d5a-121">Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88d5a-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="88d5a-122">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88d5a-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

