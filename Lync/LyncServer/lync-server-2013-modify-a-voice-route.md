---
title: 'Lync Server 2013 : modifier un itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e04f3a46d283139e745f1430f835222f25d4d912
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="14ef0-102">Modifier un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14ef0-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="14ef0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="14ef0-104">Cette rubrique explique comment modifier un itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="14ef0-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="14ef0-105">Pour créer un itinéraire, voir [créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="14ef0-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="14ef0-106">Pour modifier un itinéraire de communications vocales</span><span class="sxs-lookup"><span data-stu-id="14ef0-106">To modify a voice route</span></span>

1.  <span data-ttu-id="14ef0-107">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="14ef0-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="14ef0-108">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="14ef0-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="14ef0-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14ef0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="14ef0-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="14ef0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="14ef0-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="14ef0-112">Dans la page **Itinéraire**, utilisez l’une des méthodes suivantes pour modifier un itinéraire de communications vocales :</span><span class="sxs-lookup"><span data-stu-id="14ef0-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="14ef0-113">Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="14ef0-p104">Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire de communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="14ef0-116">Dans la page **Modifier l’itinéraire de communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="14ef0-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="14ef0-117">(Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="14ef0-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="14ef0-118">Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre**, ou l’écrire manuellement.</span><span class="sxs-lookup"><span data-stu-id="14ef0-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="14ef0-p105">Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :</span><span class="sxs-lookup"><span data-stu-id="14ef0-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="14ef0-121">**Chiffres de départ pour les nombres que vous souhaitez autoriser :** Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le +, le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="14ef0-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="14ef0-122">Par exemple, tapez **+ 425** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="14ef0-123">Répétez cette opération pour chaque valeur de préfixe que vous souhaitez inclure dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="14ef0-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="14ef0-124">**Exceptions :** Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="14ef0-125">Tapez une ou plusieurs valeurs pour les modèles correspondants que vous ne voulez *pas* que cet itinéraire s’intègre.</span><span class="sxs-lookup"><span data-stu-id="14ef0-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="14ef0-126">Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez une valeur de **+ 425237** dans le champ **exceptions** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="14ef0-127">Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué.</span><span class="sxs-lookup"><span data-stu-id="14ef0-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="14ef0-128">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)Framework regular expressions » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="14ef0-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="14ef0-129">Sélectionnez **Supprimer l’ID** de l’appelant si vous ne souhaitez pas que l’ID du téléphone soit l’ID du destinataire de l’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="14ef0-129">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="14ef0-130">Si vous sélectionnez cette option, vous devez spécifier un **Autre ID de l’appelant** qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.</span><span class="sxs-lookup"><span data-stu-id="14ef0-130">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="14ef0-131">Pour associer une ou plusieurs jonctions RTC (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.</span><span class="sxs-lookup"><span data-stu-id="14ef0-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14ef0-132">Si votre déploiement inclut des serveurs de médiation Microsoft Office Communications Server 2007 R2, ils seront également disponibles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="14ef0-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="14ef0-133">Pour associer une ou plusieurs utilisations RTC à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation RTC qui ont été définis pour votre déploiement de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="14ef0-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14ef0-134">Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, reportez-vous à la rubrique <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage Records in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="14ef0-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="14ef0-135">Pour créer ou modifier des enregistrements d’utilisation RTC, reportez-vous à <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="14ef0-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="14ef0-p110">Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="14ef0-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14ef0-138">Contrairement à une stratégie de voix dans laquelle l’ordre dans lequel sont répertoriés les enregistrements d’utilisation RTC est important, l’ordre des enregistrements d’utilisation RTC dans un itinéraire des communications vocales est insignifiant.</span><span class="sxs-lookup"><span data-stu-id="14ef0-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="14ef0-139">Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="14ef0-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="14ef0-140">(Lync Server parcourt la liste du haut vers le bas.)</span><span class="sxs-lookup"><span data-stu-id="14ef0-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="14ef0-p112">(Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.</span><span class="sxs-lookup"><span data-stu-id="14ef0-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14ef0-143">Vous pouvez enregistrer un itinéraire de communications vocales qui ne réussit pas encore le test, puis le reconfigurer par la suite.</span><span class="sxs-lookup"><span data-stu-id="14ef0-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="14ef0-144">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="14ef0-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="14ef0-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-145">Click **OK**.</span></span>

14. <span data-ttu-id="14ef0-146">Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="14ef0-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14ef0-147">Chaque fois que vous créez ou modifiez un itinéraire des communications vocales, vous devez exécuter la commande <STRONG>valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="14ef0-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="14ef0-148">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="14ef0-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14ef0-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14ef0-149">See Also</span></span>


[<span data-ttu-id="14ef0-150">Créer un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="14ef0-151">Afficher les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="14ef0-152">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="14ef0-153">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="14ef0-154">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="14ef0-155">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14ef0-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

