---
title: Fichiers et journaux de mise à jour de l’appareil Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a5b5e39f7720ac5c148a0d3d36a230d1cf4aa3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="429bc-102">Fichiers et journaux de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="429bc-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="429bc-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="429bc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="429bc-104">Les journaux de mise à jour de l’appareil contiennent des informations importantes que vous pouvez utiliser pour gérer et résoudre les problèmes du service Web de mise à jour de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="429bc-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="429bc-105">Vous pouvez modifier les journaux de périphériques et les mises à jour que vous ne souhaitez pas ou dont vous n’avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="429bc-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="429bc-106">Cette section décrit comment utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell pour modifier les paramètres de journalisation, effacer le journal des mises à jour de l’appareil ou supprimer les fichiers journaux du serveur.</span><span class="sxs-lookup"><span data-stu-id="429bc-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="429bc-107">Pour plus d’informations sur les fichiers journaux de mise à jour de l’appareil, voir <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">journaux et emplacements de fichiers</A> dans la bibliothèque TechNet de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="429bc-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="429bc-108">(Notez que le service Web de mise à jour de l’appareil, tel que tous les composants de Lync Phone Edition, fonctionne de la même façon que Lync Server 2013 comme pour Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="429bc-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="429bc-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="429bc-109">In This Section</span></span>

  - [<span data-ttu-id="429bc-110">Modifier les paramètres des fichiers journaux de mise à jour de l’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="429bc-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="429bc-111">Supprimer des fichiers journaux de mise à jour de périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="429bc-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="429bc-112">Supprimer les fichiers de mise à jour d’appareils non associés à un appareil dans les fichiers de mise à jour de périphériques non associés à un appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="429bc-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

