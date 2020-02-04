---
title: 'Lync Server 2013 : création d’un plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="23368-102">Créer un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23368-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23368-103">_**Dernière modification de la rubrique :** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="23368-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="23368-104">Pour créer un nouveau plan de numérotation, suivez les étapes de la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="23368-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="23368-105">Si vous voulez modifier un plan de numérotation, reportez-vous à [la rubrique modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="23368-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="23368-106">Pour créer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="23368-106">To create a dial plan</span></span>

1.  <span data-ttu-id="23368-107">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="23368-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="23368-108">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="23368-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="23368-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23368-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23368-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23368-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23368-111">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.</span><span class="sxs-lookup"><span data-stu-id="23368-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="23368-112">Dans la page **Plan de numérotation**, cliquez sur **Nouveau**, puis sélectionnez une étendue pour le plan de numérotation :</span><span class="sxs-lookup"><span data-stu-id="23368-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="23368-p104">**Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes attribués au plan de numérotation d’un utilisateur. Si vous sélectionnez **Site** comme étendue d’un plan de numérotation, vous devez choisir le site dans la boîte de dialogue **Sélectionner un site**. Si un plan de numérotation a déjà été créé pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.</span><span class="sxs-lookup"><span data-stu-id="23368-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="23368-p105">**Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (RTC) ou à un serveur d’inscriptions. Si vous sélectionnez **Pool** comme étendue d’un plan de numérotation, choisissez la passerelle RTC ou le serveur d’inscriptions dans la boîte de dialogue **Sélectionner un service**. Si un plan de numérotation a déjà été créé pour un service (passerelle RTC ou serveur d’inscriptions), le service ne s’affiche pas dans la liste.</span><span class="sxs-lookup"><span data-stu-id="23368-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="23368-119">**Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="23368-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-120">Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="23368-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="23368-p106">Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation**. Une fois enregistré, ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="23368-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-123">Pour les plans de numérotation de site, le champ <STRONG>Nom</STRONG> contient déjà le nom du site qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="23368-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="23368-124">Pour les plans de numérotation du pool, le champ <STRONG>Nom</STRONG> contient déjà les noms de la passerelle RTC ou du serveur d’inscriptions qui ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="23368-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="23368-p107">Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom**. Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.</span><span class="sxs-lookup"><span data-stu-id="23368-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23368-127">Le <STRONG>nom simple</STRONG> doit être unique parmi tous les plans de numérotation dans le cadre du déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23368-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="23368-128">Il ne peut pas contenir plus de 256 caractères Unicode, dont chacun peut être un caractère alphabétique ou numérique, un trait d’Union (-), un point (.) ou un trait de soulignement (_).</span><span class="sxs-lookup"><span data-stu-id="23368-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="23368-129">Les caractères <STRONG>non pris en charge</STRONG> sont les espaces et les caractères réservés telshttp://www.ietf.org/rfc/rfc3966.txt)qu’ils sont définis dans RFC 3966 (.</span><span class="sxs-lookup"><span data-stu-id="23368-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="23368-130">Les caractères réservés <STRONG>non pris en charge</STRONG> dans le <STRONG>nom simple</STRONG> incluent les caractères suivants :</span><span class="sxs-lookup"><span data-stu-id="23368-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="23368-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="23368-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="23368-132">(Facultatif) Dans le champ **Description**, vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="23368-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="23368-p110">(Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="23368-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-135">Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="23368-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="23368-136">(Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 9, par exemple) pour obtenir une ligne externe.</span><span class="sxs-lookup"><span data-stu-id="23368-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="23368-137">Vous pouvez taper une valeur de préfixe composée de quatre caractères maximum\#( \*, et 0-9).</span><span class="sxs-lookup"><span data-stu-id="23368-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-138">Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="23368-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="23368-139">Associez et configurez les règles de normalisation du plan de numérotation comme suit :</span><span class="sxs-lookup"><span data-stu-id="23368-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="23368-140">Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="23368-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="23368-141">Dans **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="23368-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="23368-142">Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="23368-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="23368-143">Pour plus d’informations sur la définition d’une règle, voir [définition des règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23368-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23368-144">Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="23368-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="23368-145">Pour plus d’informations sur la modification de la règle, voir [définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23368-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23368-146">Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="23368-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="23368-147">Pour plus d’informations sur la modification de la copie, voir [définir les règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23368-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23368-148">Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="23368-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-149">Chaque plan de numérotation doit être associé à au moins une règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="23368-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="23368-150">Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par le plan de numérotation, voir <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et règles de normalisation dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="23368-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="23368-p117">Vérifiez que les règles de normalisation du plan de numérotation sont classées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="23368-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23368-153">Lync Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="23368-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="23368-154">Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives.</span><span class="sxs-lookup"><span data-stu-id="23368-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="23368-155"><STRONG>Par défaut</STRONG> , la règle de normalisation <STRONG>^ (\d{11}) $</STRONG> correspond à n’importe quel numéro à 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="23368-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="23368-156">Par exemple, si vous ajoutez une règle de normalisation qui correspond aux numéros à 11 chiffres commençant par 1425, assurez-vous que l’ensemble de la fonction <STRONG>conserver tout</STRONG> est trié sous la règle de <STRONG>^ (1425 \{7}p) $</STRONG> la plus restrictive.</span><span class="sxs-lookup"><span data-stu-id="23368-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="23368-p120">(Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.</span><span class="sxs-lookup"><span data-stu-id="23368-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-159">Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="23368-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="23368-160">Pour plus d’informations, consultez <A href="lync-server-2013-test-voice-routing.md">tester le routage vocal dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23368-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="23368-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="23368-161">Click **OK**.</span></span>

14. <span data-ttu-id="23368-162">Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="23368-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23368-163">À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="23368-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="23368-164">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="23368-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23368-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23368-165">See Also</span></span>


[<span data-ttu-id="23368-166">Modification d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23368-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="23368-167">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23368-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="23368-168">Définition de règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23368-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

