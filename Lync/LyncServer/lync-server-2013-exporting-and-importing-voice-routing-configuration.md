---
title: 'Lync Server 2013 : Exportation et importation de la configuration du routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb02759cb4fa7cf9c979ef06b594f78a6b253c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="6f366-102">Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f366-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f366-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6f366-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6f366-104">Si vous voulez enregistrer votre configuration de routage de la voix sans la publier, procédez comme suit pour utiliser les commandes d’exportation et d’importation du panneau de configuration de Lync Server pour enregistrer et récupérer une capture instantanée de votre configuration de routage de votre voix.</span><span class="sxs-lookup"><span data-stu-id="6f366-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="6f366-105">Lorsque vous importez un fichier de configuration de l’acheminement vocal (. VCFG), mais que des modifications ont été apportées à la configuration de l’acheminement des messages sur le serveur en attendant, les pages du groupe de routage de la **voix** du panneau de configuration de Lync Server indiquent qu’il existe modifications non validées apportées au routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="6f366-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="6f366-106">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="6f366-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6f366-107">Si vous avez apporté des modifications non validées aux paramètres sur n’importe quelle page du groupe de <STRONG>routage vocal</STRONG> , les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG).</span><span class="sxs-lookup"><span data-stu-id="6f366-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="6f366-108">Cela vous permet d’apporter des modifications à la configuration de l’acheminement du routage lors de plusieurs sessions du panneau de configuration Lync Server avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="6f366-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f366-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6f366-109">In This Section</span></span>

  - [<span data-ttu-id="6f366-110">Exporter un fichier de configuration de l’itinéraire vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f366-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="6f366-111">Importation d’un fichier de configuration d’itinéraire de communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f366-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="6f366-112">Sections associées</span><span class="sxs-lookup"><span data-stu-id="6f366-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

