---
title: 'Lync Server 2013 : composants utilisés par l’application d’annonce'
description: 'Lync Server 2013 : composants utilisés par l’application d’annonce.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577690"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="f9c2f-103">Composants utilisés par l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9c2f-103">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c2f-104">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f9c2f-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f9c2f-105">Dans Lync Server 2013, l’application d’annonce est un composant de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-105">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="f9c2f-106">Lorsque vous déployez voix entreprise, l’application d’annonce est automatiquement installée et activée avec l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-106">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="f9c2f-107">Cette section décrit les composants qui prennent en charge l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-107">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="f9c2f-108">Composants de l’application d’annonce</span><span class="sxs-lookup"><span data-stu-id="f9c2f-108">Announcement Application Components</span></span>

<span data-ttu-id="f9c2f-109">Les composants de Lync Server suivants prennent en charge l’application d’annonce :</span><span class="sxs-lookup"><span data-stu-id="f9c2f-109">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="f9c2f-110">**Service**     d’application Application service fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-110">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="f9c2f-111">Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-111">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="f9c2f-112">**Application**     Response Group L’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-112">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="f9c2f-113">Lorsqu’une plage de numéros de téléphone non attribués est configurée pour acheminer vers une annonce, l’application Response Group est requise pour acheminer les appels passés au numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-113">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="f9c2f-114">(L’application Response Group n’est pas nécessaire si toutes les plages sont configurées pour acheminer la messagerie unifiée Exchange.)</span><span class="sxs-lookup"><span data-stu-id="f9c2f-114">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="f9c2f-115">**Fichiers audio**     Les fichiers audio sont utilisés pour les annonces.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-115">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="f9c2f-116">**Magasin**     de fichiers L’application d’annonce utilise le magasin de fichiers pour stocker ses fichiers audio.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-116">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="f9c2f-117">**Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-117">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="f9c2f-118">**Lync Server Management Shell**     Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer les paramètres d’annonce et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-118">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

