---
title: 'Lync Server 2013 : déploiement du portail Web d’administration de Lync Room System'
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
ms.openlocfilehash: 945532f4f0514263ed0d72e00ac5224aa6d7120b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="c64e4-102">Déploiement du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c64e4-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c64e4-103">_**Dernière modification de la rubrique :** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="c64e4-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="c64e4-104">Le portail Web d’administration de Microsoft Lync Server 2013 Lync Room System (LRS) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence Lync Room System.</span><span class="sxs-lookup"><span data-stu-id="c64e4-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="c64e4-105">Les administrateurs peuvent utiliser le portail Web d’administration de LRS pour surveiller l’intégrité des LRS, par exemple en surveillant les périphériques audio/vidéo connectés.</span><span class="sxs-lookup"><span data-stu-id="c64e4-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="c64e4-106">Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="c64e4-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="c64e4-107">Le portail Web d’administration LRS est déployé sur chaque serveur frontal Lync.</span><span class="sxs-lookup"><span data-stu-id="c64e4-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="c64e4-108">Ce guide fournit aux administrateurs des instructions sur l’installation et la configuration du portail Web d’administration LRS.</span><span class="sxs-lookup"><span data-stu-id="c64e4-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="c64e4-109">Elle est destinée aux administrateurs qui ont des connaissances sur l’administration de Lync Server et qui disposent des droits d’administrateur pour modifier la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c64e4-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="c64e4-110">Une fois le portail Web d’administration LRS déployé sur le serveur, les administrateurs peuvent vérifier l’état de toutes les salles de LRS en ouvrant une session sur le site à partir de leurs propres ordinateurs ou portables.</span><span class="sxs-lookup"><span data-stu-id="c64e4-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c64e4-111">Lorsque vous installez le portail Web d’administration LRS dans un déploiement de Microsoft Lync Server 2013, vous devez utiliser le <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portail Web d’administration de Microsoft Lync Room System pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c64e4-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="c64e4-112">Une nouvelle version du portail Web d’administration LRS est disponible pour Skype entreprise Server 2015, mais vous ne devez pas installer cette version, sauf si vous avez déployé Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c64e4-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="c64e4-113">Téléchargez le <A href="http://go.microsoft.com/fwlink/?linkid=544807">portail Web d’administration de Microsoft Lync Room System pour Skype entreprise Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="c64e4-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c64e4-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c64e4-114">In This Section</span></span>

[<span data-ttu-id="c64e4-115">Configuration de votre environnement Lync Server 2013 pour le portail Web d’administration de Lync Room System</span><span class="sxs-lookup"><span data-stu-id="c64e4-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="c64e4-116">Installation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c64e4-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="c64e4-117">Utilisation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c64e4-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c64e4-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c64e4-118">See Also</span></span>


[<span data-ttu-id="c64e4-119">Déploiement de la Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c64e4-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

