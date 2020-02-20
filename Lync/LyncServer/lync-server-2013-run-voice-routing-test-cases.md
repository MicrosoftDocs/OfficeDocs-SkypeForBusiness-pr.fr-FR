---
title: 'Lync Server 2013 : exécuter des cas de test de routage des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb8cb857460e233fe8f277cfabee382ff2a9ebd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="c82f1-102">Exécuter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c82f1-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c82f1-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c82f1-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c82f1-104">Vous pouvez exécuter tous les cas de test dans votre suite de cas de test de routage des communications vocales, ou vous pouvez exécuter un ou plusieurs cas de test sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c82f1-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="c82f1-105">Pour exécuter tous les cas de test de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="c82f1-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="c82f1-106">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c82f1-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c82f1-107">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c82f1-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c82f1-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c82f1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c82f1-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c82f1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c82f1-110">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="c82f1-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c82f1-111">Sur la page **Tester le routage des com. vocales**, cliquez sur **Action** puis sur **Exécuter tout**.</span><span class="sxs-lookup"><span data-stu-id="c82f1-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="c82f1-p103">Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.</span><span class="sxs-lookup"><span data-stu-id="c82f1-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="c82f1-p104">(Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :</span><span class="sxs-lookup"><span data-stu-id="c82f1-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c82f1-116">**Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="c82f1-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c82f1-117">**Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (valeur du champ **nombre à tester** ).</span><span class="sxs-lookup"><span data-stu-id="c82f1-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c82f1-118">**Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.</span><span class="sxs-lookup"><span data-stu-id="c82f1-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c82f1-119">**Première utilisation PSTN :** Premier enregistrement d’utilisation du réseau téléphonique commuté (PSTN) dans la stratégie de voix sélectionnée pour ce cas de test et qui correspond au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c82f1-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c82f1-120">**Première route :** Premier itinéraire de communications vocales dans le premier enregistrement d’utilisation PSTN correspondant au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c82f1-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c82f1-p105">Les champs <STRONG>Enregistrement d’utilisation PSTN attendu</STRONG> et <STRONG>Itinéraire attendu</STRONG> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.</span><span class="sxs-lookup"><span data-stu-id="c82f1-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="c82f1-123">Pour exécuter un ou plusieurs cas de test de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="c82f1-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="c82f1-124">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c82f1-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c82f1-125">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c82f1-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c82f1-126">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c82f1-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c82f1-127">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c82f1-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c82f1-128">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="c82f1-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c82f1-129">Sur la page **Tester le routage des com. vocales**, cliquez sur le nom des cas de test que vous souhaitez exécuter.</span><span class="sxs-lookup"><span data-stu-id="c82f1-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="c82f1-130">Dans le menu **Action**, cliquez sur **Exécuter la sélection**.</span><span class="sxs-lookup"><span data-stu-id="c82f1-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="c82f1-p108">Le statut de réussite ou d’échec de chaque cas de test apparaît dans la colonne **Réussite/échec**. Si un cas de test n’a pas encore été exécuté, la colonne **Réussite/échec** contient la mention N/A.</span><span class="sxs-lookup"><span data-stu-id="c82f1-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="c82f1-p109">(Facultatif) Pour consulter les résultats détaillés de chaque cas de test, double-cliquez sur le nom du cas de test. Les résultats apparaissent dans la zone ombrée sur le côté droit de la page **Modifier le cas de test** :</span><span class="sxs-lookup"><span data-stu-id="c82f1-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c82f1-135">**Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="c82f1-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c82f1-136">**Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test et qui correspond au numéro composé (valeur du champ **nombre à tester** ).</span><span class="sxs-lookup"><span data-stu-id="c82f1-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c82f1-137">**Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.</span><span class="sxs-lookup"><span data-stu-id="c82f1-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c82f1-138">**Première utilisation PSTN :** Premier enregistrement d’utilisation PSTN dans la stratégie de voix sélectionnée pour ce cas de test qui correspond au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c82f1-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c82f1-139">**Première route :** Premier itinéraire de communications vocales dans le premier enregistrement d’utilisation PSTN correspondant au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c82f1-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c82f1-p110">Les champs <STRONG>Enregistrement d’utilisation PSTN attendu</STRONG> et <STRONG>Itinéraire attendu</STRONG> sont facultatifs dans la configuration d’un cas de test de routage des communications vocales. Si les cas de test ne spécifient pas ces valeurs, le champ correspondant dans les résultats de test sera vide.</span><span class="sxs-lookup"><span data-stu-id="c82f1-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c82f1-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c82f1-142">See Also</span></span>


[<span data-ttu-id="c82f1-143">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c82f1-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="c82f1-144">Exécution des tests de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c82f1-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

