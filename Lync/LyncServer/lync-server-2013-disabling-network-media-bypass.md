---
title: 'Lync Server 2013 : désactivation de la déviation du trafic multimédia réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee2ef091b9288406285de099cc0aa427feb008d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="697a0-102">Désactivation de la déviation du trafic multimédia réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="697a0-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="697a0-103">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="697a0-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="697a0-104">Les paramètres de contournement de média s’appliquent globalement à un déploiement de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="697a0-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="697a0-105">La déviation du trafic multimédia autorise les appels à contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="697a0-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="697a0-106">Pour plus d’informations sur l’utilisation de la déviation du trafic multimédia, reportez-vous à la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la section Planning. Vous pouvez désactiver la déviation du trafic multimédia à partir du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="697a0-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="697a0-107">Pour plus d’informations sur l’activation et la configuration de la déviation du trafic, consultez la rubrique [activation du contournement de média réseau dans Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="697a0-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="697a0-108">Pour désactiver le contournement de média</span><span class="sxs-lookup"><span data-stu-id="697a0-108">To disable media bypass</span></span>

1.  <span data-ttu-id="697a0-109">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="697a0-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="697a0-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="697a0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="697a0-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="697a0-112">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.</span><span class="sxs-lookup"><span data-stu-id="697a0-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="697a0-p103">Dans la page **Globale**, cliquez sur la configuration **Globale**. Il n’existe toujours qu’une seule configuration, qui se nomme toujours Globale.</span><span class="sxs-lookup"><span data-stu-id="697a0-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="697a0-115">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="697a0-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="697a0-116">Dans la page **Modifier la configuration globale**, décochez la case **Activer le contournement de média**.</span><span class="sxs-lookup"><span data-stu-id="697a0-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="697a0-117">Cliquez sur \*\*OK \*\* pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="697a0-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="697a0-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="697a0-118">See Also</span></span>


[<span data-ttu-id="697a0-119">Activation de la déviation du trafic multimédia réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="697a0-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

