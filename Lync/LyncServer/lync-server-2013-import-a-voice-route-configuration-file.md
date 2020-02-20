---
title: 'Lync Server 2013 : importer un fichier de configuration d’itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35c955ade3383d79a9a69b101b23e2f5327ccb58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="4eba1-102">Importer un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eba1-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eba1-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4eba1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4eba1-104">Si vous souhaitez enregistrer votre configuration de routage des communications vocales sans la publier, procédez comme suit pour utiliser les commandes exportation et importation de la configuration du panneau de configuration de Lync Server pour enregistrer et récupérer une capture instantanée de la configuration de votre routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="4eba1-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="4eba1-105">Lorsque vous importez un fichier de configuration de routage des communications vocales (. VCFG), mais que des modifications ont été apportées à la configuration du routage des communications vocales sur le serveur en attendant, les pages du groupe de **routage** des communications vocales dans le panneau de configuration Lync Server indiquent des modifications non validées dans le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="4eba1-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="4eba1-106">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="4eba1-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="4eba1-107">Si vous avez apporté des modifications non validées aux paramètres sur une page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG).</span><span class="sxs-lookup"><span data-stu-id="4eba1-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="4eba1-108">Cela vous permet de modifier la configuration du routage des communications vocales lors de sessions multiples avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="4eba1-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="4eba1-109">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="4eba1-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="4eba1-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4eba1-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4eba1-111">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4eba1-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4eba1-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4eba1-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4eba1-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4eba1-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4eba1-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="4eba1-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="4eba1-115">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="4eba1-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="4eba1-116">Recherchez le fichier de configuration que vous voulez importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="4eba1-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="4eba1-117">Cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="4eba1-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4eba1-118">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="4eba1-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="4eba1-119">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="4eba1-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4eba1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4eba1-120">See Also</span></span>


[<span data-ttu-id="4eba1-121">Exporter un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eba1-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="4eba1-122">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4eba1-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

