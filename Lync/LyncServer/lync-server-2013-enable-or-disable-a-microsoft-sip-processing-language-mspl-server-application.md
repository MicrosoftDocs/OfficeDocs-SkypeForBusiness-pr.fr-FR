---
title: 'Lync Server 2013 : activation ou désactivation d’une application serveur MSPL (Microsoft SIP Processing Language)'
description: 'Lync Server 2013 : activation ou désactivation d’une application serveur MSPL (Microsoft SIP Processing Language).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f919599d6c6a39fea73424f4e287f00636c0982
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544780"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="0dc15-103">Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc15-103">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dc15-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0dc15-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0dc15-105">Vous pouvez utiliser le panneau de configuration Lync Server pour activer ou désactiver les applications serveur MSPL (Microsoft SIP Processing Language) qui s’exécutent dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dc15-105">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="0dc15-106">Ces applications script uniquement utilisent un langage de script au lieu de l’API de prévisualisation Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0dc15-106">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="0dc15-p102">Il n’est pas possible d’activer ou de désactiver tous les scripts. Par exemple, le script DefaultRouting est activé et ce paramètre ne peut pas être modifié pour DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="0dc15-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="0dc15-109">Pour activer ou désactiver une application serveur MSPL</span><span class="sxs-lookup"><span data-stu-id="0dc15-109">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="0dc15-110">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dc15-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0dc15-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dc15-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0dc15-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0dc15-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dc15-113">Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application de serveur**.</span><span class="sxs-lookup"><span data-stu-id="0dc15-113">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="0dc15-114">Dans la page **Application de serveur**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire, puis sur l’application de serveur à modifier.</span><span class="sxs-lookup"><span data-stu-id="0dc15-114">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="0dc15-115">Cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="0dc15-115">Click **Action**.</span></span>

6.  <span data-ttu-id="0dc15-116">Cliquez sur **Activer l’application** ou sur **Désactiver l’application** (si le script prend en charge cette option).</span><span class="sxs-lookup"><span data-stu-id="0dc15-116">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0dc15-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dc15-117">See Also</span></span>


[<span data-ttu-id="0dc15-118">Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc15-118">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="0dc15-119">Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc15-119">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="0dc15-120">Gestion de la topologie Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dc15-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

