---
title: Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation
description: Créez ou modifiez une règle de normalisation à l’aide de créer une règle de normalisation.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 824936359c070090ad4225a3ead6e8e46fe14785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574600"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="3383b-103">Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-103">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3383b-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3383b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3383b-105">Pour créer ou modifier une règle de normalisation dans le panneau de configuration Lync Server, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3383b-105">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="3383b-106">Par ailleurs, si vous souhaitez créer ou modifier une règle de normalisation manuellement, voir [créer ou modifier une règle de normalisation manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="3383b-106">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="3383b-107">Pour définir une règle à l’aide de la section Créer une règle de normalisation</span><span class="sxs-lookup"><span data-stu-id="3383b-107">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="3383b-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3383b-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3383b-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3383b-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3383b-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3383b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3383b-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3383b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3383b-112">Module Suivez les étapes de la procédure [créer un plan de numérotation dans Lync server 2013 à l'](lync-server-2013-create-a-dial-plan.md) étape 11 ou [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) à l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="3383b-112">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="3383b-113">Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **Postes5chiffres**).</span><span class="sxs-lookup"><span data-stu-id="3383b-113">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="3383b-114">(Optionnel) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).</span><span class="sxs-lookup"><span data-stu-id="3383b-114">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="3383b-115">Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="3383b-115">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="3383b-116">**Chiffres**     de début Module Spécifiez les chiffres de début des numéros composés que le modèle doit respecter.</span><span class="sxs-lookup"><span data-stu-id="3383b-116">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="3383b-117">Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.</span><span class="sxs-lookup"><span data-stu-id="3383b-117">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="3383b-118">**Longueur**     Spécifiez le nombre de chiffres dans le modèle de correspondance et indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, mettez en correspondance les numéros composés qui ont au moins cette longueur ou qui correspondent à des numéros de n’importe quelle longueur.</span><span class="sxs-lookup"><span data-stu-id="3383b-118">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="3383b-119">**Chiffres à supprimer**     Module Spécifiez le nombre de chiffres de début à supprimer des numéros composés que le modèle doit respecter.</span><span class="sxs-lookup"><span data-stu-id="3383b-119">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="3383b-120">**Chiffres à ajouter**     Module Spécifiez les chiffres à ajouter aux numéros composés que le modèle doit respecter.</span><span class="sxs-lookup"><span data-stu-id="3383b-120">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="3383b-p105">Les valeurs que vous entrez dans ces champs apparaissent dans **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous laissez vide le champ **Chiffres de début**, tapez **7** dans le champ **Longueur** et sélectionnez **Exactement**, puis spécifiez **0** dans le champ **Chiffres à supprimer**, l’expression régulière obtenue dans **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="3383b-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="3383b-123">**^ ( \\ d {7} ) $**</span><span class="sxs-lookup"><span data-stu-id="3383b-123">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="3383b-124">Dans **Règle de traduction**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 traduits :</span><span class="sxs-lookup"><span data-stu-id="3383b-124">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="3383b-125">Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre.</span><span class="sxs-lookup"><span data-stu-id="3383b-125">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="3383b-126">Par exemple, si le modèle de correspondance est **^ ( \\ d {7} ) $** Then **$1** dans la règle de conversion, représente les numéros composés à 7 chiffres.</span><span class="sxs-lookup"><span data-stu-id="3383b-126">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="3383b-127">(Optionnel) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro traduit (par exemple **+1425**).</span><span class="sxs-lookup"><span data-stu-id="3383b-127">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="3383b-128">Par exemple, si le modèle **à faire correspondre** contient **^ ( \\ d {7} ) $** comme modèle pour les numéros composés et que la **règle de traduction** contient **+ 1425 $1** comme modèle pour les numéros de téléphone E. 164, la règle normalise 5550100 à + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="3383b-128">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="3383b-129">(Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.</span><span class="sxs-lookup"><span data-stu-id="3383b-129">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="3383b-p107">(Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.</span><span class="sxs-lookup"><span data-stu-id="3383b-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3383b-132">Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="3383b-132">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="3383b-133">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3383b-133">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="3383b-134">Cliquez sur **OK** pour enregistrer la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="3383b-134">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="3383b-135">Cliquez sur **OK** pour enregistrer le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="3383b-135">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="3383b-136">Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="3383b-136">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3383b-137">Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de configuration.</span><span class="sxs-lookup"><span data-stu-id="3383b-137">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3383b-138">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="3383b-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3383b-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3383b-139">See Also</span></span>


[<span data-ttu-id="3383b-140">Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-140">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="3383b-141">Création d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-141">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="3383b-142">Modifier un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-142">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="3383b-143">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="3383b-144">Tester le routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3383b-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

