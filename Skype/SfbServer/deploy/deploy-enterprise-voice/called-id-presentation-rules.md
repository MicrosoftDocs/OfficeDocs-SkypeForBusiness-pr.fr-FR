---
title: Créer ou modifier une règle de traduction pour la présentation de l’ID appelé dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé : Découvrez comment définir une règle de traduction à l’aide de l’outil Créer une règle de traduction dans Skype Entreprise Server.'
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804194"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="37fb1-103">Créer ou modifier une règle de traduction pour la présentation de l’ID appelé dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="37fb1-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="37fb1-104">**Résumé :** Découvrez comment définir une règle de traduction à l’aide de l’outil Créer une règle de traduction dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="37fb1-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="37fb1-105">Si vous souhaitez définir une règle de traduction, suivez  ces étapes en entrant un ensemble de valeurs dans l’outil Créer une règle de traduction et en permettant au Panneau de configuration de Skype Entreprise Server de générer le modèle correspondant et la règle de traduction pour vous.</span><span class="sxs-lookup"><span data-stu-id="37fb1-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="37fb1-106">Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="37fb1-107">Pour plus d’informations, voir [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="37fb1-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="37fb1-108">Pour définir une règle à l’aide de l’outil Créer une règle de traduction</span><span class="sxs-lookup"><span data-stu-id="37fb1-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="37fb1-109">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="37fb1-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="37fb1-110">Pour commencer à définir une règle de traduction, suivez les étapes de la procédure de configuration d’une trunk avec déviation du média dans Skype Entreprise [Server](configure-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou configurez une trunk sans déviation du média dans Skype [Entreprise Server](configure-trunk-without-media-bypass.md) jusqu’à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="37fb1-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="37fb1-111">Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="37fb1-112">(Facultatif) Sous **Description**, tapez une description de la règle de traduction, par exemple la numérotation longue distance US International.</span><span class="sxs-lookup"><span data-stu-id="37fb1-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="37fb1-113">Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="37fb1-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="37fb1-114">**Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="37fb1-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="37fb1-115">Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).</span><span class="sxs-lookup"><span data-stu-id="37fb1-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="37fb1-116">**Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque.</span><span class="sxs-lookup"><span data-stu-id="37fb1-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="37fb1-117">Par exemple, entrez 11 et sélectionnez Au moins dans la liste de listes listes pour faire correspondre les numéros d’au moins 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="37fb1-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="37fb1-118">**Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer.</span><span class="sxs-lookup"><span data-stu-id="37fb1-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="37fb1-119">Par exemple, entrez 1 pour sortir le + du début du nombre.</span><span class="sxs-lookup"><span data-stu-id="37fb1-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="37fb1-120">**Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="37fb1-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="37fb1-121">Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.</span><span class="sxs-lookup"><span data-stu-id="37fb1-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="37fb1-p106">Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="37fb1-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="37fb1-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="37fb1-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="37fb1-125">Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="37fb1-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="37fb1-126">Ce modèle comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="37fb1-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="37fb1-127">Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="37fb1-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="37fb1-128">(Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.</span><span class="sxs-lookup"><span data-stu-id="37fb1-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="37fb1-129">Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="37fb1-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="37fb1-130">Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="37fb1-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="37fb1-131">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="37fb1-132">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="37fb1-133">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="37fb1-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37fb1-134">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="37fb1-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="37fb1-135">Pour plus d’informations, voir Publier les modifications en attente de la configuration du [routage](voice-route-config-changes.md) des voix dans Skype Entreprise dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="37fb1-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="37fb1-136">Pour définir une règle de traduction manuellement</span><span class="sxs-lookup"><span data-stu-id="37fb1-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="37fb1-137">Ouvrir le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="37fb1-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="37fb1-138">Pour commencer à définir une règle de traduction, suivez les étapes de la procédure de configuration d’une trunk avec déviation du média dans Skype Entreprise [Server](configure-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou configurez une trunk sans déviation du média dans Skype [Entreprise Server](configure-trunk-without-media-bypass.md) jusqu’à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="37fb1-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="37fb1-139">Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="37fb1-140">(Facultatif) Dans **Description,** tapez une description de la règle de traduction, par exemple la numérotation longue distance us-international.</span><span class="sxs-lookup"><span data-stu-id="37fb1-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="37fb1-141">Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="37fb1-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="37fb1-142">Entrez ce qui suit dans **Taper une expression régulière** :</span><span class="sxs-lookup"><span data-stu-id="37fb1-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="37fb1-143">Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="37fb1-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="37fb1-144">Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="37fb1-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="37fb1-145">Par exemple, si vous entrez ^ (\d \d+)$ dans Suivre ce modèle et 011$1 dans la règle de traduction, la règle traduit \+ {9} +441235551010 en 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="37fb1-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="37fb1-146">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="37fb1-147">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="37fb1-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="37fb1-148">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="37fb1-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37fb1-149">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="37fb1-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="37fb1-150">Pour plus d’informations, voir Publier les modifications en attente de la configuration du [routage](voice-route-config-changes.md) des voix dans Skype Entreprise dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="37fb1-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="37fb1-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37fb1-151">See also</span></span>

[<span data-ttu-id="37fb1-152">Configuration d’une trunk avec déviation du média dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="37fb1-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="37fb1-153">Configurer une trunk sans déviation du média dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="37fb1-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="37fb1-154">Publication des modifications en attente de la configuration du routage des voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="37fb1-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="37fb1-155">Déploiement du contournement de média dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="37fb1-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

