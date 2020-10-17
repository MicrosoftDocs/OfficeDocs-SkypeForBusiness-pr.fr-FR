---
title: 'Lync Server 2013 : marquez une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique'
description: 'Lync Server 2013 : marquez une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique.'
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
ms.openlocfilehash: e1f59fb6614416c1b0e4f49a766a1373483f509d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556550"
---
# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="a51b7-103">Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51b7-103">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51b7-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a51b7-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a51b7-105">Les applications serveur MSPL (Microsoft SIP Processing Language) sont des applications script uniquement qui utilisent le langage de script MSPL au lieu de l’API 2010 de Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="a51b7-105">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="a51b7-106">Certaines applications serveur MSPL sont spécifiées comme critiques.</span><span class="sxs-lookup"><span data-stu-id="a51b7-106">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="a51b7-107">Si un script est critique, le script doit démarrer pendant le démarrage du système afin que Lync Server 2013 puisse démarrer.</span><span class="sxs-lookup"><span data-stu-id="a51b7-107">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="a51b7-108">Si le script échoue lorsque Lync Server est en cours d’exécution, le serveur ne s’arrête pas, mais il cesse d’envoyer du trafic au script et il écrit des erreurs dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="a51b7-108">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="a51b7-109">Vous pouvez utiliser le panneau de configuration Lync Server pour marquer les applications serveur MSPL (Microsoft SIP Processing Language) comme critiques ou ne pas les marquer.</span><span class="sxs-lookup"><span data-stu-id="a51b7-109">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="a51b7-p102">Les scripts ne prennent pas tous en charge cette option. Par exemple, le script DefaultRouting est marqué comme critique, et cette option ne peut pas être modifiée pour DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="a51b7-p102">Not all scripts support this option. For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="a51b7-112">Pour marquer ou démarquer une application serveur MSPL comme critique</span><span class="sxs-lookup"><span data-stu-id="a51b7-112">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="a51b7-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a51b7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="a51b7-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a51b7-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a51b7-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a51b7-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a51b7-116">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.</span><span class="sxs-lookup"><span data-stu-id="a51b7-116">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="a51b7-117">Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.</span><span class="sxs-lookup"><span data-stu-id="a51b7-117">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="a51b7-118">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="a51b7-118">Click **Action**.</span></span>

6.  <span data-ttu-id="a51b7-119">Cliquez sur **Marquer comme critique** ou **Désélectionner comme critique** (si le script prend en charge cette option).</span><span class="sxs-lookup"><span data-stu-id="a51b7-119">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a51b7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a51b7-120">See Also</span></span>


[<span data-ttu-id="a51b7-121">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51b7-121">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="a51b7-122">Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51b7-122">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="a51b7-123">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51b7-123">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

