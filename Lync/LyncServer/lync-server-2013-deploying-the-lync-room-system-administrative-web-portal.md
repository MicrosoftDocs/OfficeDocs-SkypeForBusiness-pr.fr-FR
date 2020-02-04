---
title: 'Lync Server 2013 : déploiement du portail Web d’administration du système de salle Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7f62a5c7fde401452744abba5f4b6dfec175da2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="a233c-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a233c-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a233c-103">_**Dernière modification de la rubrique :** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="a233c-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="a233c-104">Le portail Web d’administration Microsoft Lync Server 2013 Lync salle (LRS) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence de systèmes de salle Lync.</span><span class="sxs-lookup"><span data-stu-id="a233c-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="a233c-105">Les administrateurs peuvent utiliser le portail Web d’administration LRS pour surveiller l’intégrité de LRS, par exemple en surveillant des périphériques audio/vidéo qui sont connectés.</span><span class="sxs-lookup"><span data-stu-id="a233c-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="a233c-106">Ils peuvent également collecter à distance des informations de diagnostic pour surveiller l’intégrité des salles de conférence.</span><span class="sxs-lookup"><span data-stu-id="a233c-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="a233c-107">Le portail Web d’administration LRS est déployé sur chaque serveur frontal Lync.</span><span class="sxs-lookup"><span data-stu-id="a233c-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="a233c-108">Ce guide fournit aux administrateurs des instructions sur l’installation et la configuration du portail Web d’administration LRS.</span><span class="sxs-lookup"><span data-stu-id="a233c-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="a233c-109">Il est destiné aux administrateurs ayant connaissance de l’administration de Lync Server et disposant de droits d’administrateur pour modifier la topologie du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="a233c-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="a233c-110">Après le déploiement d’LRS portail Web d’administration sur le serveur, les administrateurs peuvent vérifier l’état de toutes les salles LRS en se connectant au site à partir de leur ordinateur ou de leur ordinateur portable.</span><span class="sxs-lookup"><span data-stu-id="a233c-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a233c-111">Lorsque vous installez le portail Web d’administration LRS dans un déploiement Microsoft Lync Server 2013, vous devez utiliser le <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portail Web d’administration de Microsoft Lync salle pour Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a233c-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="a233c-112">Une nouvelle version du portail Web d’administration LRS est disponible pour Skype entreprise Server 2015, mais vous ne devez pas installer cette version sauf si vous avez déployé Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a233c-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="a233c-113">Téléchargez le <A href="http://go.microsoft.com/fwlink/?linkid=544807">portail Web d’administration du système de salle Microsoft Lync pour Skype entreprise Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="a233c-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a233c-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a233c-114">In This Section</span></span>

[<span data-ttu-id="a233c-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="a233c-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="a233c-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a233c-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="a233c-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a233c-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a233c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a233c-118">See Also</span></span>


[<span data-ttu-id="a233c-119">Déploiement d’une conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a233c-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

