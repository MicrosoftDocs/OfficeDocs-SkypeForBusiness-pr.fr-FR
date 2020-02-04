---
title: 'Lync Server 2013 : exécuter des cas de test de routage de voix'
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
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="95096-102">Exécuter des cas de test de routage de voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95096-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95096-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="95096-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="95096-104">Vous pouvez exécuter tous les cas de test dans votre suite de tests de routage de voix ou exécuter un ou plusieurs cas de test sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="95096-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="95096-105">Pour exécuter tous les cas de test de routage vocale</span><span class="sxs-lookup"><span data-stu-id="95096-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="95096-106">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="95096-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="95096-107">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="95096-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="95096-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95096-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95096-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95096-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95096-110">Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales** , puis cliquez sur **tester le routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="95096-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="95096-111">Dans la page **test de routage vocal** , cliquez sur **action** , puis sur **Tout exécuter**.</span><span class="sxs-lookup"><span data-stu-id="95096-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="95096-112">Le statut de réussite ou d’échec de chaque cas de test est affiché dans la colonne **passe/échec** .</span><span class="sxs-lookup"><span data-stu-id="95096-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="95096-113">Si un cas de test n’a pas encore été exécuté, N/A s’affiche dans la colonne **passe/échec** .</span><span class="sxs-lookup"><span data-stu-id="95096-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="95096-114">Facultatif Pour afficher les résultats détaillés pour chaque cas de test, double-cliquez sur le nom du cas de test.</span><span class="sxs-lookup"><span data-stu-id="95096-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="95096-115">Les résultats s’affichent dans la zone ombrée située sur le côté droit de la page **modifier le cas de test** :</span><span class="sxs-lookup"><span data-stu-id="95096-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="95096-116">**Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="95096-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="95096-117">**Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test correspondant au numéro composé (valeur du champ **numéro à tester** ).</span><span class="sxs-lookup"><span data-stu-id="95096-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="95096-118">**Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.</span><span class="sxs-lookup"><span data-stu-id="95096-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="95096-119">**Première utilisation RTC :** Premier enregistrement d’utilisation de réseau téléphonique commuté (PSTN) dans la stratégie vocale sélectionnée pour ce cas de test correspondant au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="95096-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="95096-120">**Premier itinéraire :** Le premier itinéraire vocal dans le premier enregistrement d’utilisation RTC qui correspond au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="95096-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="95096-121">Les champs <STRONG>enregistrement d’utilisation RTC</STRONG> et <STRONG>route attendue</STRONG> sont facultatifs dans la configuration de cas de test de l’acheminement vocal.</span><span class="sxs-lookup"><span data-stu-id="95096-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="95096-122">Si le cas de test ne spécifie pas ces valeurs, le champ correspondant dans les résultats du test sera vide.</span><span class="sxs-lookup"><span data-stu-id="95096-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="95096-123">Pour exécuter une ou plusieurs situations de test de routage vocal sélectionnées</span><span class="sxs-lookup"><span data-stu-id="95096-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="95096-124">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="95096-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="95096-125">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="95096-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="95096-126">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95096-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95096-127">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="95096-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95096-128">Dans la barre de navigation de gauche, cliquez sur **routage des communications vocales**, puis cliquez sur **tester le routage vocal**.</span><span class="sxs-lookup"><span data-stu-id="95096-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="95096-129">Dans la page de routage de la **voix** , cliquez sur les noms des cas de test que vous souhaitez exécuter.</span><span class="sxs-lookup"><span data-stu-id="95096-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="95096-130">Dans le menu **action** , cliquez sur **exécuter la sélection**.</span><span class="sxs-lookup"><span data-stu-id="95096-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="95096-131">Le statut de réussite ou d’échec de chaque cas de test est affiché dans la colonne **passe/échec** .</span><span class="sxs-lookup"><span data-stu-id="95096-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="95096-132">Si un cas de test n’a pas encore été exécuté, N/A s’affiche dans la colonne **passe/échec** .</span><span class="sxs-lookup"><span data-stu-id="95096-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="95096-133">Facultatif Pour afficher les résultats détaillés pour chaque cas de test, double-cliquez sur le nom du cas de test.</span><span class="sxs-lookup"><span data-stu-id="95096-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="95096-134">Les résultats s’affichent dans la zone ombrée située sur le côté droit de la page **modifier le cas de test** :</span><span class="sxs-lookup"><span data-stu-id="95096-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="95096-135">**Résultat du test :** État de réussite ou d’échec global du cas de test exécuté.</span><span class="sxs-lookup"><span data-stu-id="95096-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="95096-136">**Règle de normalisation :** Première règle de normalisation du plan de numérotation sélectionné pour ce cas de test correspondant au numéro composé (valeur du champ **numéro à tester** ).</span><span class="sxs-lookup"><span data-stu-id="95096-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="95096-137">**Numéro normalisé :** Valeur du numéro composé une fois la règle de normalisation traduite.</span><span class="sxs-lookup"><span data-stu-id="95096-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="95096-138">**Première utilisation RTC :** Premier enregistrement d’utilisation RTC dans la stratégie vocale sélectionnée pour ce cas de test correspondant au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="95096-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="95096-139">**Premier itinéraire :** Le premier itinéraire vocal dans le premier enregistrement d’utilisation RTC qui correspond au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="95096-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="95096-140">Les champs <STRONG>enregistrement d’utilisation RTC</STRONG> et <STRONG>route attendue</STRONG> sont facultatifs dans la configuration de cas de test de l’acheminement vocal.</span><span class="sxs-lookup"><span data-stu-id="95096-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="95096-141">Si le cas de test ne spécifie pas ces valeurs, le champ correspondant dans les résultats du test sera vide.</span><span class="sxs-lookup"><span data-stu-id="95096-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95096-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95096-142">See Also</span></span>


[<span data-ttu-id="95096-143">Test du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95096-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="95096-144">Exécution des tests de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95096-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

