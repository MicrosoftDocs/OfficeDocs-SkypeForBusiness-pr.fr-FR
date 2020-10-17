---
title: 'Lync Server 2013 : enregistrement des détails des appels (CDR)'
description: 'Lync Server 2013 : enregistrement des détails des appels (CDR).'
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
ms.openlocfilehash: 590f99fd0b8649ffb3c4df039488dc54a8f3b7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561790"
---
# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="9c37d-103">Enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-103">Call detail recording (CDR) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c37d-104">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9c37d-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9c37d-105">L’enregistrement des détails des appels permet d’enregistrer les informations de diagnostic et d’utilisation relatives aux activités P2P, notamment la messagerie d’instance, les appels VoIP (protocole voix sur IP), le partage d’application, le transfert de fichiers et les réunions.</span><span class="sxs-lookup"><span data-stu-id="9c37d-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="9c37d-106">Les données d’utilisation permettent de calculer le retour sur investissement alors que les données de diagnostic permettent de résoudre les problèmes spécifiques aux activités et réunions P2P.</span><span class="sxs-lookup"><span data-stu-id="9c37d-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="9c37d-107">Lorsque vous installez Lync Server 2013, vous installez également une collection prédéfinie de paramètres de configuration globaux pour les enregistrements des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="9c37d-107">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="9c37d-108">Utilisez les rubriques de cette section pour configurer l’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="9c37d-108">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c37d-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9c37d-109">In This Section</span></span>

  - [<span data-ttu-id="9c37d-110">Afficher les informations de configuration de l’enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-110">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="9c37d-111">Activer l’enregistrement des détails des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-111">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="9c37d-112">Création ou modification d’une collection de paramètres de configuration CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-112">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="9c37d-113">Supprimer une collection existante de paramètres de configuration CDR dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-113">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="9c37d-114">Purge manuelle des bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-114">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c37d-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c37d-115">See Also</span></span>


[<span data-ttu-id="9c37d-116">Configuration des paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c37d-116">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

