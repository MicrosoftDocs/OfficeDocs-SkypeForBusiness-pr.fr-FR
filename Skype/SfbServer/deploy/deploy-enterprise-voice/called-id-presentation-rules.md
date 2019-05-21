---
title: Création ou modification d’une règle de traduction pour appeler une présentation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé: Découvrez comment définir une règle de traduction à l’aide de l’outil créer une règle de traduction dans Skype entreprise Server.'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275870"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="06716-103">Création ou modification d’une règle de traduction pour appeler une présentation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06716-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="06716-104">**Résumé:** Découvrez comment définir une règle de traduction à l’aide de l’outil créer une règle de traduction dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="06716-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="06716-105">Suivez ces étapes si vous voulez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant le panneau de configuration Skype entreprise Server pour générer les modèles correspondants et les règles de traduction correspondants.</span><span class="sxs-lookup"><span data-stu-id="06716-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="06716-106">Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="06716-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="06716-107">Pour plus d’informations, voir [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="06716-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="06716-108">Pour définir une règle à l’aide de l’outil Créer une règle de traduction</span><span class="sxs-lookup"><span data-stu-id="06716-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="06716-109">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="06716-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="06716-110">Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Skype entreprise Server via l'](configure-trunk-with-media-bypass.md) étape 10 ou [configurer un Trunk sans dérivation multimédia dans Skype entreprise Server à l'](configure-trunk-without-media-bypass.md) étape 9.</span><span class="sxs-lookup"><span data-stu-id="06716-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="06716-111">Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="06716-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="06716-112">Facultatif Sous **Description**, tapez la description de la règle de traduction (par exemple, la numérotation internationale pour les appels longue distance).</span><span class="sxs-lookup"><span data-stu-id="06716-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="06716-113">Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="06716-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="06716-114">**Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="06716-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="06716-115">Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).</span><span class="sxs-lookup"><span data-stu-id="06716-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="06716-116">**Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque.</span><span class="sxs-lookup"><span data-stu-id="06716-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="06716-117">Par exemple, entrez 11 et selectAt moins dans la liste déroulante pour faire correspondre les nombres dont la longueur est d’au moins 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="06716-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="06716-118">**Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer.</span><span class="sxs-lookup"><span data-stu-id="06716-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="06716-119">Par exemple, entrez 1 pour enlever le signe + du début du numéro.</span><span class="sxs-lookup"><span data-stu-id="06716-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="06716-120">**Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="06716-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="06716-121">Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.</span><span class="sxs-lookup"><span data-stu-id="06716-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="06716-p106">Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="06716-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="06716-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="06716-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="06716-125">Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="06716-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="06716-126">Ce modèle comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="06716-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="06716-127">Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="06716-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="06716-128">(Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.</span><span class="sxs-lookup"><span data-stu-id="06716-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="06716-129">Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="06716-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="06716-130">Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="06716-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="06716-131">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="06716-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="06716-132">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="06716-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="06716-133">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="06716-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06716-134">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="06716-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="06716-135">Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="06716-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="06716-136">Pour définir une règle de traduction manuellement</span><span class="sxs-lookup"><span data-stu-id="06716-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="06716-137">Ouvrir le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06716-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="06716-138">Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Skype entreprise Server via l'](configure-trunk-with-media-bypass.md) étape 10 ou [configurer un Trunk sans dérivation multimédia dans Skype entreprise Server à l'](configure-trunk-without-media-bypass.md) étape 9.</span><span class="sxs-lookup"><span data-stu-id="06716-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="06716-139">Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="06716-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="06716-140">Facultatif Dans **Description**, tapez la description de la règle de traduction (par exemple, la numérotation internationale internationale pour les appels longue distance).</span><span class="sxs-lookup"><span data-stu-id="06716-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="06716-141">Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="06716-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="06716-142">Entrez ce qui suit dans **Taper une expression régulière** :</span><span class="sxs-lookup"><span data-stu-id="06716-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="06716-143">Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="06716-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="06716-144">Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="06716-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="06716-145">Par exemple, si vous entrez ^\+(\d{9}\d +) $ dans **respecter ce modèle** and011 $1 dans la **règle de traduction**, la règle traduira + 441235551010 en 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="06716-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="06716-146">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="06716-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="06716-147">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="06716-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="06716-148">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="06716-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06716-149">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="06716-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="06716-150">Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="06716-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="06716-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06716-151">See also</span></span>

[<span data-ttu-id="06716-152">Configuration d’une Trunk with Media bypass dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06716-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="06716-153">Configurer un Trunk sans dérivation multimédia dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06716-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="06716-154">Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="06716-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="06716-155">Déploiement du contournement multimédia dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06716-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

