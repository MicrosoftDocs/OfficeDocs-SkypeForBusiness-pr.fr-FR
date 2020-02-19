---
title: 'Lync Server 2013 : test du routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eff0d59de7822f738cc7e2253cf728690dd45b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="d1d9d-102">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1d9d-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1d9d-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d1d9d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d1d9d-104">Vous pouvez utiliser l’onglet de routage de **test des communications vocales** du panneau de configuration Lync Server pour configurer les scénarios de cas de test.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="d1d9d-105">Pour définir un cas de test, vous devez spécifier le plan de numérotation, la stratégie de voix, l’utilisation PSTN et l’itinéraire des communications vocales sur lesquels tester un numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="d1d9d-106">Avant de déployer votre configuration de routage des communications vocales, nous vous recommandons de la tester sur différents numéros de téléphone afin de vous assurer que les résultats sont bien ceux que vous attendez.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d1d9d-107">Vous pouvez faire appel aux commandes <STRONG>Exporter des cas de test</STRONG> et <STRONG>Importer des cas de test</STRONG> pour enregistrer des cas de test de routage des communications vocales et les importer sur un autre ordinateur afin de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="d1d9d-108">Si vous supprimez une partie de la configuration du routage des communications vocales, comme un plan de numérotation, une stratégie de voix, un itinéraire de communications vocales ou l’utilisation téléphonique, vous devez examiner et mettre à jour vos cas de test de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="d1d9d-109">Le panneau de configuration Lync Server ne vous signale pas les cas de test qui ne sont plus valides en raison de la modification des configurations.</span><span class="sxs-lookup"><span data-stu-id="d1d9d-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1d9d-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d1d9d-110">In This Section</span></span>

  - [<span data-ttu-id="d1d9d-111">Créer un cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1d9d-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="d1d9d-112">Exporter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1d9d-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="d1d9d-113">Importer des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1d9d-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="d1d9d-114">Exécution des tests de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1d9d-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

