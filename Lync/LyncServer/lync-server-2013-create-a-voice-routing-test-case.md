---
title: 'Lync Server 2013 : création d’un cas de test de routage des communications vocales'
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
ms.openlocfilehash: da110d7e3bfb7188384163cb572591d0bf7f8ff3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501771"
---
# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="1dcaa-102">Créer un cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcaa-102">Create a voice routing test case in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dcaa-103">_**Dernière modification de la rubrique :** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="1dcaa-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="1dcaa-104">Pour créer un cas de test</span><span class="sxs-lookup"><span data-stu-id="1dcaa-104">To create a test case</span></span>

1.  <span data-ttu-id="1dcaa-105">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1dcaa-106">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1dcaa-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1dcaa-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1dcaa-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1dcaa-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1dcaa-109">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="1dcaa-110">Dans la page **Routage des communications vocales**, cliquez sur **Nouveau** pour créer un nouveau cas de test.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="1dcaa-111">Dans **Nom**, tapez un nom unique pour le cas de test.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="1dcaa-112">Le nom doit être unique parmi tous les cas de test de routage des communications vocales dans votre déploiement Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="1dcaa-113">Il peut comporter jusqu’à 32 caractères et peut contenir des caractères alphanumériques, outre la barre oblique inverse ( \\ ), le point (.) ou le trait de soulignement ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="1dcaa-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="1dcaa-p104">Dans **Numéro composé à tester**, tapez le numéro composé que vous souhaitez utiliser pour tester la configuration du routage que vous spécifiez pour ce cas de test. À partir du plan de numérotation, de l’itinéraire et de la stratégie de voix, ce numéro sera normalisé et affiché en sortie.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="1dcaa-p105">Dans la liste **Plan de numérotation**, sélectionnez le plan de numérotation à utiliser lors de l’exécution du test. Le plan de numérotation global est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="1dcaa-p106">Dans la liste **Stratégie de la voix**, sélectionnez la stratégie de voix à utiliser lors de l’exécution du test. La stratégie de voix globale est utilisée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="1dcaa-p107">Dans **Traduction attendue**, tapez le numéro de téléphone au format dans lequel vous souhaitez le visualiser après la traduction. Il s’agit de la valeur du numéro de téléphone que vous testez une fois qu’il a été traduit par la première règle de normalisation qui correspond dans le plan de numérotation sélectionné. Quand vous exécutez le cas de test, si le numéro que vous testez ne correspond pas à la valeur contenue dans **Traduction attendue** le test échoue.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="1dcaa-p108">(Facultatif) Dans la liste **Utilisation PSTN attendue**, vous pouvez sélectionner l’enregistrement d’utilisation PSTN devant être utilisé quand vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre enregistrement d’utilisation PSTN est utilisé, le test échoue.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="1dcaa-p109">(Facultatif) Dans la liste **Itinéraire attendu**, vous pouvez sélectionner l’itinéraire des communications vocales devant être utilisé lorsque vous exécutez le cas de test, en fonction de la stratégie de voix et du plan de numérotation spécifiés. Si un autre itinéraire des communications vocales est utilisé, le test échoue.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="1dcaa-p110">(Facultatif) Cliquez sur **Exécuter** pour exécuter le cas de test. Les résultats apparaissent dans le panneau droit de la page.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="1dcaa-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-129">Click **OK**.</span></span>

14. <span data-ttu-id="1dcaa-130">Cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1dcaa-131">Chaque fois que vous créez un cas de test de routage des communications vocales, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="1dcaa-132">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="1dcaa-133">Si le plan de numérotation employé dans le test normalise les numéros de téléphone commençant par un signe plus (par exemple, + 12065551219), cette planification peut entraîner l’échec du test de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="1dcaa-134">(Le plan de numérotation et l’itinéraire des communications vocales fonctionneront ; en fait, Test-CsDialPlan aboutira.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="1dcaa-135">Toutefois, le test de routage des communications vocales peut échouer.) Il s’agit d’une information à garder à l’esprit lors du test des itinéraires des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="1dcaa-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1dcaa-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dcaa-136">See Also</span></span>


[<span data-ttu-id="1dcaa-137">Exporter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcaa-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="1dcaa-138">Importer des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcaa-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="1dcaa-139">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcaa-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="1dcaa-140">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcaa-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

