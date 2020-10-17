---
title: 'Lync Server 2013 : exécuter des tests de routage des communications vocales informelles'
description: 'Lync Server 2013 : exécuter des tests de routage des communications vocales informelles.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6029be34f4e4e7b366cb73f56ca611b4773331fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545030"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="88b9a-103">Exécuter des tests de routage des communications vocales informels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-103">Run informal voice routing tests in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b9a-104">_**Dernière modification de la rubrique :** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="88b9a-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="88b9a-p101">Vous pouvez utiliser la boîte de dialogue **Créer des informations de cas de test de routage des communications vocales** pour effectuer des tests informels avant de lancer un cas de test réel. Lorsque vous êtes satisfait du résultat d’un test, vous pouvez l’enregistrer comme un cas de test formel.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="88b9a-107">Pour effectuer un test de routage des communications vocales informel</span><span class="sxs-lookup"><span data-stu-id="88b9a-107">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="88b9a-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="88b9a-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="88b9a-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="88b9a-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="88b9a-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88b9a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88b9a-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88b9a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88b9a-112">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Tester le routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-112">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="88b9a-113">Dans la page **Tester le routage des com. vocales**, cliquez sur **Créer des informations de cas de test de routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-113">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="88b9a-p104">Dans le champ **Numéro composé**, entrez le numéro de téléphone à utiliser pour ce test. Ce numéro sera normalisé et affiché dans le champ **Numéro normalisé** du volet **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="88b9a-p105">Dans la liste **Plan de numérotation**, sélectionnez le plan de numérotation à utiliser pour tester le numéro composé. Le plan de numérotation global est utilisé par défaut.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="88b9a-118">Lorsque vous exécutez le test, la première règle de normalisation de ce plan de numérotation correspondant au numéro composé apparaîtra dans le champ **Règle de normalisation** du volet **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-118">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="88b9a-p106">Dans la liste **Stratégie de voix**, sélectionnez la stratégie de voix à utiliser pour tester le numéro composé. La stratégie de voix globale est utilisée par défaut.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="88b9a-p107">Lorsque vous exécutez le test, le premier enregistrement d’utilisation PSTN correspondant de cette stratégie de voix s’affichera dans le champ **Première utilisation PSTN** du volet **Résultats**. Le premier routage des communications vocales correspondant associé à cet enregistrement d’utilisation PSTN apparaîtra également dans le champ **Premier itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="88b9a-123">(Optionnel) Activez la case à cocher **Remplir à partir de l’utilisateur** pour tester le numéro composé par rapport à la stratégie de voix attribuée à un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="88b9a-123">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="88b9a-124">Cliquez sur **Parcourir** pour afficher la boîte de dialogue **Sélectionner des utilisateurs Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-124">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="88b9a-125">Cliquez sur **Rechercher** pour afficher la liste des utilisateurs activés pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="88b9a-125">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="88b9a-p108">Double-cliquez sur le nom d’utilisateur dont vous souhaitez utiliser la stratégie de voix attribuée pour ce test. Le champ **Stratégie** affiche à présent la stratégie de voix attribuée à l’utilisateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="88b9a-p109">Lorsque vous exécutez le test, le premier enregistrement d’utilisation réseau téléphonique commuté (PSTN) correspondant de cette stratégie de voix s’affichera dans le champ **Première utilisation PSTN** du volet **Résultats**. Le premier routage des communications vocales correspondant associé à cet enregistrement d’utilisation PSTN apparaîtra également dans le champ **Premier itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="88b9a-p110">Cliquez sur **Exécuter** pour lancer le cas de test. Les résultats s’affichent dans le panneau droit de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="88b9a-132">(Optionnel) Cliquez sur **Enregistrer sous** pour enregistrer la configuration de test comme un cas de test formel.</span><span class="sxs-lookup"><span data-stu-id="88b9a-132">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="88b9a-133">Dans le champ **Nom** de la boîte de dialogue **Enregistrer les informations de cas de test de routage des communications vocales**, entrez le nom unique de ce cas de test.</span><span class="sxs-lookup"><span data-stu-id="88b9a-133">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="88b9a-134">Le nom doit être unique parmi tous les cas de test de routage des communications vocales dans votre déploiement Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="88b9a-134">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="88b9a-135">Il peut comporter jusqu’à 32 caractères et peut contenir des caractères alphanumériques, outre la barre oblique inverse ( \\ ), le point (.) ou le trait de soulignement ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="88b9a-135">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="88b9a-p112">Notez que les champs restants de la boîte de dialogue **Enregistrer les informations de cas de test de routage des communications vocales** sont en lecture seule et préremplis à partir de la configuration *et* des résultats du test informel. Vérifiez qu’il s’agit effectivement de la configuration à enregistrer pour le cas de test.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="88b9a-138">Les valeurs des résultats du test servent à préremplir les champs de la boîte de dialogue <STRONG>Enregistrer les informations de cas de test de routage des communications vocales</STRONG> de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="88b9a-138">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="88b9a-139">Le champ <STRONG>Traduction attendue</STRONG> est prérempli avec la valeur du champ <STRONG>Numéro normalisé</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88b9a-139"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="88b9a-140">Le champ <STRONG>Itinéraire attendu</STRONG> est prérempli avec la valeur du champ <STRONG>Premier itinéraire</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88b9a-140"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="88b9a-141">Le champ <STRONG>Utilisation PSTN attendue</STRONG> est prérempli avec la valeur du champ <STRONG>Première utilisation PSTN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88b9a-141"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="88b9a-p113">Si le test ne renvoie aucun résultat pour ces valeurs, le champ correspondant apparaît vide dans la boîte de dialogue <STRONG>Enregistrer les informations de cas de test de routage des communications vocales</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88b9a-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="88b9a-143">Cliquez sur **Ok** pour enregistrer le cas de test, ou sur **Annuler** pour revenir à la boîte de dialogue **Afficher les informations de cas de test de routage des communications vocales** pour poursuivre le test avant de l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="88b9a-143">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="88b9a-144">Cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="88b9a-144">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88b9a-145">À chaque fois que vous créez un cas de test de routage des communications vocales, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier le cas de test.</span><span class="sxs-lookup"><span data-stu-id="88b9a-145">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="88b9a-146">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="88b9a-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88b9a-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88b9a-147">See Also</span></span>


[<span data-ttu-id="88b9a-148">Créer un cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-148">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="88b9a-149">Exécuter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-149">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="88b9a-150">Exporter des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-150">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="88b9a-151">Importer des cas de test de routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-151">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="88b9a-152">Configuration des plans de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-152">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="88b9a-153">Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b9a-153">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

