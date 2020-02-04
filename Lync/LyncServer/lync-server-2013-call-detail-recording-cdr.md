---
title: 'Lync Server 2013 : enregistrement des détails des appels (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e7490e974b970c7c0a68e16b03ed19306d89183
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="9c4d6-102">Enregistrement des détails des appels (CDR) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-102">Call detail recording (CDR) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c4d6-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9c4d6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9c4d6-104">L’enregistrement des détails des appels permet d’enregistrer les informations de diagnostic et d’utilisation relatives aux activités P2P, notamment la messagerie d’instance, les appels VoIP (protocole voix sur IP), le partage d’application, le transfert de fichiers et les réunions.</span><span class="sxs-lookup"><span data-stu-id="9c4d6-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="9c4d6-105">Les données d’utilisation permettent de calculer le retour sur investissement alors que les données de diagnostic permettent de résoudre les problèmes spécifiques aux activités et réunions P2P.</span><span class="sxs-lookup"><span data-stu-id="9c4d6-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="9c4d6-106">Lorsque vous installez Lync Server 2013, vous devez également installer une collection prédéfinie de paramètres de configuration globale pour CDR.</span><span class="sxs-lookup"><span data-stu-id="9c4d6-106">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="9c4d6-107">Utilisez les rubriques de cette section pour configurer l’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="9c4d6-107">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c4d6-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9c4d6-108">In This Section</span></span>

  - [<span data-ttu-id="9c4d6-109">Afficher les informations de configuration de CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-109">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="9c4d6-110">Activer l’enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-110">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="9c4d6-111">Créer ou modifier un ensemble de paramètres de configuration de CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-111">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="9c4d6-112">Supprimer une collection existante de paramètres de configuration de CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-112">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="9c4d6-113">Effacement manuel des bases de données de l’enregistrement des détails des appels et de la qualité de l’interface dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-113">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c4d6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c4d6-114">See Also</span></span>


[<span data-ttu-id="9c4d6-115">Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’expérimentation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c4d6-115">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

