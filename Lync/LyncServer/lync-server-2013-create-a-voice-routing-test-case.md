---
title: 'Lync Server 2013 : Création d’un cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="63fe8-102">Création d’un cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe8-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63fe8-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="63fe8-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="63fe8-104">Pour créer un cas de test</span><span class="sxs-lookup"><span data-stu-id="63fe8-104">To create a test case</span></span>

1.  <span data-ttu-id="63fe8-105">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="63fe8-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="63fe8-106">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="63fe8-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="63fe8-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63fe8-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="63fe8-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="63fe8-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="63fe8-109">Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales** , puis cliquez sur **tester le routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="63fe8-110">Dans la page **test de routage vocal** , cliquez sur **nouveau** pour créer un nouveau cas de test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="63fe8-111">Dans **nom**, entrez un nom unique pour le cas de test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="63fe8-112">Ce nom doit être unique parmi les cas de test de routage vocal dans votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="63fe8-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="63fe8-113">Il peut y avoir une longueur maximale de 32 caractères et contenir des caractères alphanumériques, en plus de la barre\\oblique inverse (), du point (.) ou\_du trait de soulignement ().</span><span class="sxs-lookup"><span data-stu-id="63fe8-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="63fe8-114">Dans **numéro composé à tester**, entrez le numéro de téléphone que vous voulez utiliser pour tester la configuration de routage que vous spécifiez pour ce cas de test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="63fe8-115">En fonction du plan de numérotation, de l’itinéraire et de la stratégie vocale, ce numéro est normalisé et affiché en sortie.</span><span class="sxs-lookup"><span data-stu-id="63fe8-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="63fe8-116">Dans la liste **plan de numérotation** , sélectionnez le plan de numérotation à utiliser lors de l’exécution du test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="63fe8-117">Par défaut est le plan de numérotation global.</span><span class="sxs-lookup"><span data-stu-id="63fe8-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="63fe8-118">Dans la liste de la **stratégie vocale** , sélectionnez la stratégie vocale à utiliser lors de l’exécution du test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="63fe8-119">La valeur par défaut est la stratégie de voix globale.</span><span class="sxs-lookup"><span data-stu-id="63fe8-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="63fe8-120">Dans **traduction prévue**, entrez le numéro de téléphone dans le format que vous souhaitez voir apparaître après la traduction.</span><span class="sxs-lookup"><span data-stu-id="63fe8-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="63fe8-121">Il s’agit de la valeur du numéro de téléphone que vous testez après sa traduction en commençant par la première règle de normalisation qui correspond au plan de numérotation sélectionné.</span><span class="sxs-lookup"><span data-stu-id="63fe8-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="63fe8-122">Lorsque vous exécutez le cas de test, si le nombre que vous testez n’entraîne pas la valeur de la **traduction attendue**, le test échoue.</span><span class="sxs-lookup"><span data-stu-id="63fe8-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="63fe8-123">Facultatif Dans la liste **utilisation RTC attendue** , vous pouvez sélectionner l’enregistrement d’utilisation de réseau téléphonique commuté (PSTN) à utiliser lors de l’exécution du cas de test, en fonction du plan de numérotation et de la stratégie vocale spécifiés.</span><span class="sxs-lookup"><span data-stu-id="63fe8-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="63fe8-124">Si un autre enregistrement d’utilisation RTC est utilisé, le test échoue.</span><span class="sxs-lookup"><span data-stu-id="63fe8-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="63fe8-125">Facultatif Dans la liste des **itinéraires attendus** , vous pouvez sélectionner l’itinéraire que vous vous attendez à utiliser lors de l’exécution du cas de test, en fonction du plan de numérotation et de la stratégie vocale spécifiés.</span><span class="sxs-lookup"><span data-stu-id="63fe8-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="63fe8-126">S’il s’agit d’une autre gamme vocale utilisée, le test échoue.</span><span class="sxs-lookup"><span data-stu-id="63fe8-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="63fe8-127">Facultatif Cliquez sur **exécuter** pour exécuter le cas de test.</span><span class="sxs-lookup"><span data-stu-id="63fe8-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="63fe8-128">Les résultats sont affichés dans le volet droit de la page.</span><span class="sxs-lookup"><span data-stu-id="63fe8-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="63fe8-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-129">Click **OK**.</span></span>

14. <span data-ttu-id="63fe8-130">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="63fe8-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63fe8-131">Chaque fois que vous créez un cas de test de routage de voix, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de configuration.</span><span class="sxs-lookup"><span data-stu-id="63fe8-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="63fe8-132">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="63fe8-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="63fe8-133">Si le plan de numérotation qui est utilisé dans le test normalise les numéros de téléphone qui commencent par un signe plus (par exemple, + 12065551219), ce plan peut entraîner l’échec du test de routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="63fe8-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="63fe8-134">(Le plan de numérotation et l’itinéraire vocal fonctionneront ; en fait, test-CsDialPlan réussit.</span><span class="sxs-lookup"><span data-stu-id="63fe8-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="63fe8-135">Toutefois, le test de routage vocal peut échouer.) Il s’agit d’éléments à garder à l’esprit lors du test des itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="63fe8-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63fe8-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63fe8-136">See Also</span></span>


[<span data-ttu-id="63fe8-137">Exportation des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe8-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="63fe8-138">Importation des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe8-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="63fe8-139">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe8-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="63fe8-140">Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63fe8-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

