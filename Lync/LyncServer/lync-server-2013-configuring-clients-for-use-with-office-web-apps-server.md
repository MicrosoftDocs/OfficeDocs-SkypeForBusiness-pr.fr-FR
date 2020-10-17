---
title: 'Lync Server 2013 : configuration des clients pour une utilisation avec Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537061"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="100cb-102">Configuration des clients de Lync Server 2013 pour une utilisation avec Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="100cb-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="100cb-103">_**Dernière modification de la rubrique :** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="100cb-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="100cb-104">Si vous souhaitez que les utilisateurs bénéficient des fonctionnalités complètes d’Office Web App Server, vous devez mettre à niveau ces utilisateurs vers Microsoft Lync 2013 ; Seuls les utilisateurs de Lync 2013 seront en mesure de faire défiler les diapositives PowerPoint indépendamment de la présentation réelle de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="100cb-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="100cb-105">(En d’autres termes, ces utilisateurs peuvent consulter toutes les diapositives de la présentation à tout moment, sans gêner leur présentation.) Les utilisateurs qui n’utilisent pas Lync 2013 pourront toujours participer à des conférences en ligne et afficher la présentation PowerPoint ; Toutefois, ils ne pourront pas faire défiler les diapositives indépendamment et ne pourront pas voir les transitions de diapositives ou afficher des vidéos incorporées.</span><span class="sxs-lookup"><span data-stu-id="100cb-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="100cb-106">Notez que ces fonctionnalités sont toujours disponibles pour les utilisateurs de Lync 2013 ; Cela est vrai même si le présentateur PowerPoint exécute Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="100cb-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="100cb-107">Si une présentation PowerPoint est hébergée par un utilisateur de Lync 2010, Lync Server 2013 est coordonné avec Office Web Apps Server pour s’assurer que les utilisateurs de Lync 2013 afficheront la version d’Office Web Apps Server de cette présentation.</span><span class="sxs-lookup"><span data-stu-id="100cb-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="100cb-108">Office Web Apps Server ne fournit pas de services PowerPoint pour les utilisateurs qui exécutent des clients autres que Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="100cb-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="100cb-109">Au lieu de cela, ces utilisateurs se connectent au service de serveur de conférence et affichent des présentations PowerPoint de la même manière que dans Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="100cb-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="100cb-110">Cela signifie également que ces utilisateurs auront uniquement accès aux fonctionnalités plus limitées proposées par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="100cb-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="100cb-111">Bien qu’aucune configuration client ne soit requise pour Office Web Apps Server (autre que la mise à niveau des utilisateurs vers Lync 2013), il est recommandé que les participants à la Conférence soient mis à niveau vers Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="100cb-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="100cb-112">Les conférences peuvent être accédées via Internet Explorer 8, mais cela comporte certaines limites.</span><span class="sxs-lookup"><span data-stu-id="100cb-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="100cb-113">Par exemple, les utilisateurs de ce navigateur ne peuvent pas redimensionner la fenêtre PowerPoint de manière personnalisée ; ils sont limités à l؊’utilisation de l’une des trois tailles de fenêtre prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="100cb-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="100cb-114">Ils ne peuvent pas non plus lire des fichiers multimédia.</span><span class="sxs-lookup"><span data-stu-id="100cb-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

