---
title: 'Lync Server 2013 : déploiement du portail Web d’administration de Lync Room System'
description: 'Lync Server 2013 : déploiement du portail Web d’administration de Lync Room System.'
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
ms.openlocfilehash: e67723b3ddf3f452c53411e560420bb0b043128e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565980"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="6eeee-103">Déploiement du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eeee-103">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eeee-104">_**Dernière modification de la rubrique :** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="6eeee-104">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="6eeee-105">Le portail Web d’administration de Microsoft Lync Server 2013 Lync Room System (LRS) est un portail Web que les organisations peuvent utiliser pour gérer leurs salles de conférence Lync Room System.</span><span class="sxs-lookup"><span data-stu-id="6eeee-105">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="6eeee-106">Les administrateurs peuvent utiliser le portail Web d’administration de LRS pour surveiller l’intégrité des LRS, par exemple en surveillant les périphériques audio/vidéo connectés.</span><span class="sxs-lookup"><span data-stu-id="6eeee-106">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="6eeee-107">Grâce à ce portail, les administrateurs peuvent collecter à distance des informations de diagnostic pour surveiller l’état de la salle de conférence.</span><span class="sxs-lookup"><span data-stu-id="6eeee-107">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="6eeee-108">Le portail Web d’administration LRS est déployé sur chaque serveur frontal Lync.</span><span class="sxs-lookup"><span data-stu-id="6eeee-108">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="6eeee-109">Ce guide fournit aux administrateurs des instructions sur l’installation et la configuration du portail Web d’administration LRS.</span><span class="sxs-lookup"><span data-stu-id="6eeee-109">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="6eeee-110">Elle est destinée aux administrateurs qui ont des connaissances sur l’administration de Lync Server et qui disposent des droits d’administrateur pour modifier la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6eeee-110">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="6eeee-111">Une fois le portail Web d’administration LRS déployé sur le serveur, les administrateurs peuvent vérifier l’état de toutes les salles de LRS en ouvrant une session sur le site à partir de leurs propres ordinateurs ou portables.</span><span class="sxs-lookup"><span data-stu-id="6eeee-111">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6eeee-112">Lorsque vous installez le portail Web d’administration LRS dans un déploiement de Microsoft Lync Server 2013, vous devez utiliser le <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">portail Web d’administration de Microsoft Lync Room System pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6eeee-112">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="6eeee-113">Une nouvelle version du portail Web d’administration LRS est disponible pour Skype entreprise Server 2015, mais vous ne devez pas installer cette version, sauf si vous avez déployé Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6eeee-113">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="6eeee-114">Téléchargez le <A href="https://go.microsoft.com/fwlink/?linkid=544807">portail Web d’administration de Microsoft Lync Room System pour Skype entreprise Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="6eeee-114">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6eeee-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6eeee-115">In This Section</span></span>

[<span data-ttu-id="6eeee-116">Configuration de votre environnement Lync Server 2013 pour le portail Web d’administration de Lync Room System</span><span class="sxs-lookup"><span data-stu-id="6eeee-116">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="6eeee-117">Installation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eeee-117">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="6eeee-118">Utilisation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eeee-118">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6eeee-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6eeee-119">See Also</span></span>


[<span data-ttu-id="6eeee-120">Déploiement de la Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eeee-120">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

