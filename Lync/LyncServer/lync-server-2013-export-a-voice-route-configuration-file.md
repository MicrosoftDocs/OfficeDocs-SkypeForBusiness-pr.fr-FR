---
title: 'Lync Server 2013 : exporter un fichier de configuration d’itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4128dc1e2d3a300d0305336d87f36f0d6a06a055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="e33f3-102">Exporter un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33f3-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e33f3-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e33f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e33f3-104">Si vous souhaitez enregistrer votre configuration de routage des communications vocales sans la publier, procédez comme suit pour utiliser les commandes exportation et importation de la configuration du panneau de configuration de Lync Server pour enregistrer et récupérer une capture instantanée de la configuration de votre routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="e33f3-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="e33f3-105">Lorsque vous importez un fichier de configuration de routage des communications vocales (. VCFG), mais que des modifications ont été apportées à la configuration du routage des communications vocales sur le serveur en attendant, les pages du groupe de **routage** des communications vocales dans le panneau de configuration Lync Server indiquent des modifications non validées dans le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="e33f3-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="e33f3-106">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="e33f3-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="e33f3-107">Si vous avez apporté des modifications non validées aux paramètres sur une page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG).</span><span class="sxs-lookup"><span data-stu-id="e33f3-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="e33f3-108">Cela vous permet de modifier la configuration du routage des communications vocales lors de sessions multiples avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="e33f3-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="e33f3-109">Pour exporter une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="e33f3-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="e33f3-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e33f3-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e33f3-111">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e33f3-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e33f3-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e33f3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e33f3-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e33f3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e33f3-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="e33f3-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="e33f3-115">Dans le menu **Actions**, cliquez sur **Exporter la configuration**.</span><span class="sxs-lookup"><span data-stu-id="e33f3-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="e33f3-116">Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e33f3-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e33f3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e33f3-117">See Also</span></span>


[<span data-ttu-id="e33f3-118">Importer un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33f3-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

