---
title: 'Lync Server 2013 : composants utilisés par l’application d’annonce'
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
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517711"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="72c5c-102">Composants utilisés par l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72c5c-102">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72c5c-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="72c5c-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="72c5c-104">Dans Lync Server 2013, l’application d’annonce est un composant de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="72c5c-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="72c5c-105">Lorsque vous déployez voix entreprise, l’application d’annonce est automatiquement installée et activée avec l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="72c5c-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="72c5c-106">Cette section décrit les composants qui prennent en charge l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="72c5c-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="72c5c-107">Composants de l’application d’annonce</span><span class="sxs-lookup"><span data-stu-id="72c5c-107">Announcement Application Components</span></span>

<span data-ttu-id="72c5c-108">Les composants de Lync Server suivants prennent en charge l’application d’annonce :</span><span class="sxs-lookup"><span data-stu-id="72c5c-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="72c5c-109">**Service**     d’application Application service fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées.</span><span class="sxs-lookup"><span data-stu-id="72c5c-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="72c5c-110">Application service est automatiquement installé sur chaque serveur frontal d’un pool frontal et sur chaque serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72c5c-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="72c5c-111">**Application**     Response Group L’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application.</span><span class="sxs-lookup"><span data-stu-id="72c5c-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="72c5c-112">Lorsqu’une plage de numéros de téléphone non attribués est configurée pour acheminer vers une annonce, l’application Response Group est requise pour acheminer les appels passés au numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="72c5c-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="72c5c-113">(L’application Response Group n’est pas nécessaire si toutes les plages sont configurées pour acheminer la messagerie unifiée Exchange.)</span><span class="sxs-lookup"><span data-stu-id="72c5c-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="72c5c-114">**Fichiers audio**     Les fichiers audio sont utilisés pour les annonces.</span><span class="sxs-lookup"><span data-stu-id="72c5c-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="72c5c-115">**Magasin**     de fichiers L’application d’annonce utilise le magasin de fichiers pour stocker ses fichiers audio.</span><span class="sxs-lookup"><span data-stu-id="72c5c-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="72c5c-116">**Panneau de configuration**     Lync Server Vous pouvez utiliser le panneau de configuration Lync Server pour configurer la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="72c5c-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="72c5c-117">**Lync Server Management Shell**     Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer les paramètres d’annonce et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="72c5c-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

