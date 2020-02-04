---
title: 'Lync Server 2013 : Importation des cas de test de routage des communications vocales'
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
ms.openlocfilehash: 013860ea52773f4109c56bd71d37a9f4b8938225
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="fd708-102">Importation des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd708-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd708-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fd708-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fd708-104">Les scénarios de test vous permettent de tester les itinéraires vocaux au sein de votre organisation : vous définissez des éléments tels que le numéro à composer, le plan de numérotation et la politique vocale, et Lync Server 2013 peut alors vérifier qu’il est possible d’utiliser le numéro fourni pour succes sfully être routé vers le réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="fd708-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="fd708-105">Les cas de test, qui peuvent être créés à l’aide du panneau de configuration de Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été créé et exécuté à l’origine.</span><span class="sxs-lookup"><span data-stu-id="fd708-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="fd708-106">Toutefois, ces cas de test peuvent être exportés sous forme de fichiers XML (avec l’extension. vtest), puis importés sur d’autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="fd708-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="fd708-107">Cela vous permet d’exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="fd708-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="fd708-108">Pour importer un cas de test de routage vocal</span><span class="sxs-lookup"><span data-stu-id="fd708-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="fd708-109">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fd708-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="fd708-110">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fd708-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="fd708-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd708-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fd708-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fd708-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fd708-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="fd708-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="fd708-114">Dans le menu **actions** , cliquez sur **Importer les cas de test**.</span><span class="sxs-lookup"><span data-stu-id="fd708-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="fd708-115">Recherchez le fichier de cas de test (. vtest) que vous voulez importer, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="fd708-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="fd708-116">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="fd708-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd708-117">Chaque fois que vous importez un fichier. vtest, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier le cas de test.</span><span class="sxs-lookup"><span data-stu-id="fd708-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="fd708-118">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="fd708-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd708-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fd708-119">See Also</span></span>


[<span data-ttu-id="fd708-120">Exportation des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd708-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

