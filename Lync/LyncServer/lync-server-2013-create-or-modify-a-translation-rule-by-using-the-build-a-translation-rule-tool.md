---
title: Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction
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
ms.openlocfilehash: 9641170534c4c4ad1ef4976d018699d01d6069a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="8a94d-102">Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a94d-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8a94d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8a94d-104">Procédez comme suit si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant le panneau de configuration Lync Server pour générer le modèle de correspondance et la règle de traduction correspondants pour vous.</span><span class="sxs-lookup"><span data-stu-id="8a94d-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="8a94d-105">Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="8a94d-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="8a94d-106">Pour plus d’informations, reportez-vous à [créer ou modifier une règle de traduction manuellement dans Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="8a94d-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="8a94d-107">Pour définir une règle à l’aide de l’outil Créer une règle de traduction</span><span class="sxs-lookup"><span data-stu-id="8a94d-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="8a94d-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8a94d-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8a94d-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8a94d-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8a94d-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a94d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a94d-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8a94d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a94d-112">Pour commencer à définir une règle de traduction, suivez la procédure décrite dans [Configure a trunk with Media Bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou [Configure a trunk without Media Bypass in Lync Server 2013 à l'](lync-server-2013-configure-a-trunk-without-media-bypass.md) étape 9.</span><span class="sxs-lookup"><span data-stu-id="8a94d-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="8a94d-113">Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="8a94d-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="8a94d-114">(Facultatif) Sous **Description**, entrez la description de la règle de traduction ; par exemple, **Appel longue distance international**.</span><span class="sxs-lookup"><span data-stu-id="8a94d-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="8a94d-115">Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="8a94d-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="8a94d-116">**Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="8a94d-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="8a94d-117">Par exemple, entrez **+** dans ce champ pour faire correspondre les numéros au format E. 164 (commençant par +).</span><span class="sxs-lookup"><span data-stu-id="8a94d-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="8a94d-p105">**Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **Au moins** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="8a94d-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="8a94d-120">**Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer.</span><span class="sxs-lookup"><span data-stu-id="8a94d-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="8a94d-121">Par exemple, entrez **1** pour supprimer la **+** à partir du début du numéro.</span><span class="sxs-lookup"><span data-stu-id="8a94d-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="8a94d-p107">**Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.</span><span class="sxs-lookup"><span data-stu-id="8a94d-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="8a94d-p108">Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="8a94d-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="8a94d-126">**^\\+ (\\d{9}\\+) $**</span><span class="sxs-lookup"><span data-stu-id="8a94d-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="8a94d-p109">Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="8a94d-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="8a94d-129">Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="8a94d-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="8a94d-130">(Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8a94d-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="8a94d-131">Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="8a94d-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="8a94d-132">Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="8a94d-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="8a94d-133">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="8a94d-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="8a94d-134">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="8a94d-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="8a94d-135">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="8a94d-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8a94d-136">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="8a94d-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8a94d-137">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="8a94d-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a94d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a94d-138">See Also</span></span>


[<span data-ttu-id="8a94d-139">Création ou modification manuelle d’une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="8a94d-140">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="8a94d-141">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="8a94d-142">Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="8a94d-143">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a94d-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

