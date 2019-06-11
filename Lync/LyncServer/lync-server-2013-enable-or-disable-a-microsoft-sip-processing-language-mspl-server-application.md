---
title: 'Lync Server 2013: activation ou désactivation d’une application serveur Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="4a6fd-102">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a6fd-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a6fd-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4a6fd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4a6fd-104">Le panneau de configuration de Lync Server vous permet d’activer ou de désactiver les applications serveur MSPL (Microsoft SIP Processing Language) qui s’exécutent dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="4a6fd-105">Ces applications sont des applications uniquement basées sur des scripts qui utilisent un langage de script au lieu de l’API Microsoft Lync 2013 preview.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="4a6fd-106">Tous les scripts ne peuvent pas être activés ou désactivés.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="4a6fd-107">Par exemple, le script DefaultRouting est activé, et cette option ne peut pas être modifiée pour DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="4a6fd-108">Pour activer ou désactiver une application serveur MSPL</span><span class="sxs-lookup"><span data-stu-id="4a6fd-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="4a6fd-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="4a6fd-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a6fd-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a6fd-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a6fd-112">Dans la barre de navigation de gauche, cliquez sur **topologie** , puis sur **application serveur**.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="4a6fd-113">Dans la page de l' **application serveur** , cliquez sur un en-tête de colonne pour trier les applications, le cas échéant, puis cliquez sur l’application serveur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="4a6fd-114">Cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="4a6fd-114">Click **Action**.</span></span>

6.  <span data-ttu-id="4a6fd-115">Cliquez sur **activer l’application** ou désactiver l' **application** (autrement dit, si le script prend en charge cette option).</span><span class="sxs-lookup"><span data-stu-id="4a6fd-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a6fd-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a6fd-116">See Also</span></span>


[<span data-ttu-id="4a6fd-117">Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a6fd-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="4a6fd-118">Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a6fd-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="4a6fd-119">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a6fd-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

