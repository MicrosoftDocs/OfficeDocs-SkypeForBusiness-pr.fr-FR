---
title: 'Lync Server 2013 : création d’un itinéraire des communications vocales'
description: 'Lync Server 2013 : créez un itinéraire des communications vocales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a9becac8b35967d7b7ff05014bd6b6600f62a06
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562430"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="77f7b-103">Créer un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-103">Create a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77f7b-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="77f7b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="77f7b-105">La procédure suivante explique comment créer un nouvel itinéraire des communications vocales à l’aide du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77f7b-105">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="77f7b-106">Pour modifier un itinéraire existant, reportez-vous à la rubrique [modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md) pour la procédure.</span><span class="sxs-lookup"><span data-stu-id="77f7b-106">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="77f7b-107">Pour créer un itinéraire des communications vocales à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="77f7b-107">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="77f7b-108">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="77f7b-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77f7b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77f7b-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="77f7b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="77f7b-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-111">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="77f7b-112">Cliquez sur **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-112">Click **Route**.</span></span>

5.  <span data-ttu-id="77f7b-113">Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire de communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-113">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="77f7b-114">Dans **nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="77f7b-114">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="77f7b-115">Module Dans **Description**, entrez des informations descriptives supplémentaires pour l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="77f7b-115">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="77f7b-116">Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez soit utiliser l’outil **créer un modèle pour faire correspondre** pour générer une expression régulière, soit écrire l’expression régulière manuellement.</span><span class="sxs-lookup"><span data-stu-id="77f7b-116">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="77f7b-p103">Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :</span><span class="sxs-lookup"><span data-stu-id="77f7b-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="77f7b-119">**Chiffres de départ pour les nombres que vous souhaitez autoriser :** Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le +, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="77f7b-119">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="77f7b-120">Par exemple, tapez **+ 425**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-120">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="77f7b-121">Répétez cette opération pour chaque valeur de préfixe que vous souhaitez inclure dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="77f7b-121">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="77f7b-122">**Exceptions :** Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-122">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="77f7b-123">Tapez une ou plusieurs valeurs pour les modèles correspondants que vous ne voulez *pas* que cet itinéraire s’intègre.</span><span class="sxs-lookup"><span data-stu-id="77f7b-123">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="77f7b-124">Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez une valeur de **+ 425237** dans le champ **exceptions** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="77f7b-124">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="77f7b-125">Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué.</span><span class="sxs-lookup"><span data-stu-id="77f7b-125">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="77f7b-126">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="77f7b-126">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="77f7b-p107">Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.</span><span class="sxs-lookup"><span data-stu-id="77f7b-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="77f7b-129">Pour associer une ou plusieurs jonctions à l’itinéraire des communications vocales, cliquez sur **Ajouter** , puis sélectionnez une jonction dans la liste.</span><span class="sxs-lookup"><span data-stu-id="77f7b-129">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77f7b-130">Si votre déploiement inclut des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="77f7b-130">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="77f7b-131">Pour associer une ou plusieurs utilisations RTC (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation RTC qui ont été définis pour votre déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="77f7b-131">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77f7b-132">Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, reportez-vous à la rubrique <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage Records in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77f7b-132">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="77f7b-133">Pour créer ou modifier des enregistrements d’utilisation RTC, reportez-vous à <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77f7b-133">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="77f7b-p108">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="77f7b-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77f7b-136">Contrairement à une stratégie de voix, dans laquelle l’ordre dans lequel sont répertoriés les enregistrements d’utilisation RTC est important, l’ordre dans lequel les enregistrements d’utilisation RTC sont répertoriés dans l’itinéraire des communications vocales n’est pas significatif.</span><span class="sxs-lookup"><span data-stu-id="77f7b-136">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="77f7b-137">Toutefois, nous vous recommandons d’organiser la liste par fréquence d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="77f7b-137">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="77f7b-138">Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="77f7b-138">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="77f7b-139">(Lync Server parcourt la liste du haut vers le bas.)</span><span class="sxs-lookup"><span data-stu-id="77f7b-139">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="77f7b-p110">(Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.</span><span class="sxs-lookup"><span data-stu-id="77f7b-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77f7b-142">Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite.</span><span class="sxs-lookup"><span data-stu-id="77f7b-142">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="77f7b-143">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77f7b-143">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="77f7b-144">Cliquez sur **OK** pour enregistrer l’itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="77f7b-144">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77f7b-145">Chaque fois que vous créez un itinéraire des communications vocales, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="77f7b-145">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="77f7b-146">Pour plus d’informations, consultez <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">la rubrique publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77f7b-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77f7b-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77f7b-147">See Also</span></span>


[<span data-ttu-id="77f7b-148">Modifier un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-148">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="77f7b-149">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-149">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="77f7b-150">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-150">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="77f7b-151">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-151">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="77f7b-152">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-152">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="77f7b-153">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f7b-153">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

