---
title: Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45ca4e04146a175ec2782aa798ac27559fce495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="2f5f8-102">Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f5f8-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2f5f8-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2f5f8-104">Suivez ces étapes si vous voulez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant le panneau de configuration de Lync Server pour générer le modèle de correspondance et la règle de traduction correspondants pour vous.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="2f5f8-105">Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="2f5f8-106">Pour plus d’informations, reportez-vous à [créer ou modifier une règle de traduction manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="2f5f8-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="2f5f8-107">Pour définir une règle à l’aide de l’outil Créer une règle de traduction</span><span class="sxs-lookup"><span data-stu-id="2f5f8-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="2f5f8-108">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="2f5f8-109">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2f5f8-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="2f5f8-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f5f8-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f5f8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f5f8-112">Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) à l’étape 10 ou [configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="2f5f8-113">Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="2f5f8-114">(Facultatif) Sous **Description**, entrez la description de la règle de traduction ; par exemple, **US International long-distance dialing**.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="2f5f8-115">Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="2f5f8-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="2f5f8-116">**Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="2f5f8-117">Par exemple, entrez **+** dans ce champ pour correspondre aux nombres au format E. 164 (qui commence par +).</span><span class="sxs-lookup"><span data-stu-id="2f5f8-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="2f5f8-p105">**Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **At least** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="2f5f8-120">**Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="2f5f8-121">Par exemple, entrez **1** pour enlever le **+** début du numéro.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="2f5f8-p107">**Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="2f5f8-p108">Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="2f5f8-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="2f5f8-126">**^\\+ (\\j{9}\\d +) $**</span><span class="sxs-lookup"><span data-stu-id="2f5f8-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="2f5f8-p109">Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="2f5f8-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="2f5f8-129">Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="2f5f8-130">(Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="2f5f8-131">Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="2f5f8-132">Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="2f5f8-133">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="2f5f8-134">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="2f5f8-135">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="2f5f8-136">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="2f5f8-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2f5f8-137">Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation</span><span class="sxs-lookup"><span data-stu-id="2f5f8-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f5f8-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f5f8-138">See Also</span></span>


[<span data-ttu-id="2f5f8-139">Créer ou modifier une règle de traduction manuellement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="2f5f8-140">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="2f5f8-141">Configurer un Trunk sans dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="2f5f8-142">Publier les modifications en attente apportées à la configuration du routage de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="2f5f8-143">Options de contournement global de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f5f8-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

