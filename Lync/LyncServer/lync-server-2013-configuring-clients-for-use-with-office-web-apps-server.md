---
title: 'Lync Server 2013: configuration des clients pour une utilisation avec Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 263f53b61aa609c4385af2a9646bf84da2dea3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="2b091-102">Configuration des clients de Lync Server 2013 pour une utilisation avec Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="2b091-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b091-103">_**Dernière modification de la rubrique:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="2b091-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="2b091-104">Si vous souhaitez que les utilisateurs bénéficient de toutes les fonctionnalités d’Office Web App Server, vous devez mettre à niveau ces utilisateurs vers Microsoft Lync 2013. Seuls les utilisateurs de Lync 2013 seront en mesure d’effectuer ces opérations dans les diapositives PowerPoint indépendamment de la présentation PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2b091-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="2b091-105">(C’est-à-dire que ces utilisateurs peuvent examiner n’importe quelle diapositive de la présentation à tout moment, sans interférer avec la présentation réelle.) Les utilisateurs qui n’utilisent pas Lync 2013 pourront toujours accéder à des conférences en ligne et afficher la présentation PowerPoint. Toutefois, ils ne seront pas en mesure de faire défiler les diapositives, mais ils ne pourront pas voir les transitions entre les diapositives et afficher les vidéos incorporées.</span><span class="sxs-lookup"><span data-stu-id="2b091-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="2b091-106">Notez que ces fonctionnalités seront toujours accessibles aux utilisateurs de Lync 2013; C’est vrai même si le présentateur PowerPoint exécute Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="2b091-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="2b091-107">Si une présentation PowerPoint est hébergée par un utilisateur exécutant Lync 2010, Lync Server 2013 coordonnéa avec Office Web Apps Server pour vérifier que les utilisateurs de Lync 2013 pourront voir la version Server d’Office Web Apps de cette présentation.</span><span class="sxs-lookup"><span data-stu-id="2b091-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="2b091-108">Office Web Apps Server ne fournit pas de services PowerPoint aux utilisateurs exécutant des clients autres que Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2b091-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="2b091-109">Au lieu de cela, les utilisateurs qui se connectent au service du serveur de conférence et d’afficher des présentations PowerPoint de la même façon que dans Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2b091-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="2b091-110">Cela signifie également que ces utilisateurs auront uniquement accès aux fonctionnalités les plus limitées proposées par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2b091-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="2b091-111">Bien qu’il n’est pas nécessaire de configurer le client pour Office Web Apps Server (à l’exception de la mise à niveau des utilisateurs vers Lync 2013), il est recommandé de mettre à niveau vers Internet Explorer 9.</span><span class="sxs-lookup"><span data-stu-id="2b091-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="2b091-112">Bien que les conférences puissent être consultées à l’aide d’Internet Explorer 8, il existe certaines limites à l’utilisation de ce navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="2b091-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="2b091-113">Par exemple, les utilisateurs d’Internet Explorer 8 ne seront pas en mesure de redimensionner la présentation PowerPoint à une taille personnalisée; au lieu de cela, il est limité à l’utilisation d’une des trois tailles d’étapes prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="2b091-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="2b091-114">De même, les utilisateurs d’Internet Explorer 8 ne seront pas en mesure de lire des fichiers multimédias.</span><span class="sxs-lookup"><span data-stu-id="2b091-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

