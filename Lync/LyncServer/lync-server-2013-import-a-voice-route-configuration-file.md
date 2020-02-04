---
title: 'Lync Server 2013 : Importation d’un fichier de configuration d’itinéraire de communications vocales'
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
ms.openlocfilehash: 2f00b1eb3406c1a3d425727820da8686f96f1dae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="d5de0-102">Importation d’un fichier de configuration d’itinéraire de communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5de0-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5de0-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5de0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5de0-104">Si vous voulez enregistrer votre configuration de routage de la voix sans la publier, procédez comme suit pour utiliser les commandes d’exportation et d’importation du panneau de configuration de Lync Server pour enregistrer et récupérer une capture instantanée de votre configuration de routage de votre voix.</span><span class="sxs-lookup"><span data-stu-id="d5de0-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="d5de0-105">Lorsque vous importez un fichier de configuration de l’acheminement vocal (. VCFG), mais que des modifications ont été apportées à la configuration de l’acheminement du message sur le serveur, les pages du groupe de **routage vocal** dans Lync Server Control Panel indiquent qu’il n’y a pas de modifications non validées sur le routage vocal.</span><span class="sxs-lookup"><span data-stu-id="d5de0-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="d5de0-106">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="d5de0-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="d5de0-107">Si vous avez apporté des modifications non validées aux paramètres sur n’importe quelle page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG).</span><span class="sxs-lookup"><span data-stu-id="d5de0-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="d5de0-108">Cela vous permet de procéder à des modifications de la configuration de l’acheminement des messages pendant plusieurs sessions avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="d5de0-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="d5de0-109">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="d5de0-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="d5de0-110">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d5de0-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d5de0-111">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d5de0-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d5de0-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5de0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5de0-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d5de0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5de0-114">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="d5de0-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="d5de0-115">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="d5de0-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="d5de0-116">Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="d5de0-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="d5de0-117">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="d5de0-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5de0-118">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="d5de0-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="d5de0-119">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="d5de0-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5de0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5de0-120">See Also</span></span>


[<span data-ttu-id="d5de0-121">Exporter un fichier de configuration de l’itinéraire vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5de0-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="d5de0-122">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5de0-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

