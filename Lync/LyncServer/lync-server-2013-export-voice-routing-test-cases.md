---
title: 'Lync Server 2013 : exporter des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d871379f9c9be161aec879b7ca8da16ac40e2b5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="a7e1f-102">Exporter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e1f-102">Export voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e1f-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a7e1f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a7e1f-104">Les scénarios de test vous permettent de tester les itinéraires des communications vocales dans votre organisation : vous définissez des éléments tels que le numéro à composer et le plan de numérotation et la stratégie de voix à utiliser, et Lync Server peut ensuite vérifier que, étant donné ces conditions, le numéro fourni peut correctement acheminés vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="a7e1f-105">Les cas de test, qui peuvent être créés à l’aide du panneau de configuration Lync Server, sont généralement enregistrés uniquement sur le serveur où le cas a été initialement créé et exécuté.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="a7e1f-106">Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="a7e1f-107">Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="a7e1f-108">Pour exporter un cas de test de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="a7e1f-108">To export a voice routing test case</span></span>

1.  <span data-ttu-id="a7e1f-109">Dans le panneau de configuration Lync Server, cliquez sur **routage** des communications vocales, puis sur **tester le routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-109">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="a7e1f-p102">Sous l’onglet **Tester le routage des communications vocales**, sélectionnez le cas de test (ou les cas de test) à exporter. Pour sélectionner plusieurs cas de test, cliquez sur le premier cas à exporter, puis maintenez la touche Ctrl enfoncée et sélectionnez les cas supplémentaires à exporter.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="a7e1f-112">Cliquez sur **Action**, puis sur **Exporter des cas de test**.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-112">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="a7e1f-113">Dans la boîte de dialogue **Enregistrer sous** , sélectionnez un dossier pour stocker les cas de test exportés et tapez un nom pour le fichier XML résultant dans la zone **nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="a7e1f-113">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box.</span></span> <span data-ttu-id="a7e1f-114">Notez que si vous exportez plusieurs cas de test, tous ces cas de test seront enregistrés dans un seul fichier XML.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-114">Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="a7e1f-115">Pour enregistrer les cas de test, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a7e1f-115">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7e1f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7e1f-116">See Also</span></span>


[<span data-ttu-id="a7e1f-117">Importer des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e1f-117">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

