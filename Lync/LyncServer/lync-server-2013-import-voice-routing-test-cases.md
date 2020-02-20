---
title: 'Lync Server 2013 : importation des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43ab26d61009683623d3c536a26c8be04a3846e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="af1b9-102">Importer des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af1b9-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af1b9-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="af1b9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="af1b9-104">Les scénarios de test vous permettent de tester les itinéraires des communications vocales au sein de votre organisation : vous définissez des éléments tels que le numéro à composer, le plan de numérotation et la stratégie de voix à utiliser, et Lync Server 2013 peut ensuite vérifier que, étant donné ces conditions, le numéro fourni peut succes sfully être acheminé vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="af1b9-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="af1b9-105">Les cas de test, qui peuvent être créés à l’aide du panneau de configuration Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été initialement créé et exécuté.</span><span class="sxs-lookup"><span data-stu-id="af1b9-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="af1b9-106">Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="af1b9-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="af1b9-107">Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="af1b9-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="af1b9-108">Pour importer un cas de test de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="af1b9-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="af1b9-109">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="af1b9-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="af1b9-110">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="af1b9-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="af1b9-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af1b9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af1b9-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af1b9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af1b9-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="af1b9-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="af1b9-114">Dans le menu **Actions**, cliquez sur **Importer des cas de test**.</span><span class="sxs-lookup"><span data-stu-id="af1b9-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="af1b9-115">Recherchez le fichier de cas de test (.vtest) que vous voulez importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="af1b9-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="af1b9-116">Cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="af1b9-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af1b9-117">Chaque fois que vous importez un fichier .vtest, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier le cas de test.</span><span class="sxs-lookup"><span data-stu-id="af1b9-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="af1b9-118">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="af1b9-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af1b9-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af1b9-119">See Also</span></span>


[<span data-ttu-id="af1b9-120">Exporter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af1b9-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

