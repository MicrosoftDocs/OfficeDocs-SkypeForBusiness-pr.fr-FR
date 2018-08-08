---
title: Créer ou modifier une règle de traduction pour présentation ID appelée Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé : Découvrez comment définir une règle de traduction à l’aide de la version un outil de la règle de traduction dans Skype pour Business Server.'
ms.openlocfilehash: 61c68f03ab3c9f1a34f9ae5c24f727954365fb6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006566"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="16d2e-103">Créer ou modifier une règle de traduction pour présentation ID appelée Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16d2e-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>
 
<span data-ttu-id="16d2e-104">**Résumé :** Découvrez comment définir une règle de traduction à l’aide de la version un outil de la règle de traduction dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="16d2e-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="16d2e-105">Suivez ces étapes si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant Skype pour Business Server Control Panel générer le modèle correspondant correspondant et la règle de traduction pour vous.</span><span class="sxs-lookup"><span data-stu-id="16d2e-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="16d2e-106">Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="16d2e-107">Pour plus d’informations, voir [créer ou modifier une règle de traduction manuellement](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="16d2e-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="16d2e-108">Pour définir une règle à l’aide de l’outil Créer une règle de traduction</span><span class="sxs-lookup"><span data-stu-id="16d2e-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="16d2e-109">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="16d2e-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="16d2e-110">Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement dans Skype pour Business Server](configure-trunk-with-media-bypass.md) par le biais de l’étape 10 ou [configurer une jonction sans media contournement dans Skype pour Business Server](configure-trunk-without-media-bypass.md) jusqu'à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="16d2e-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="16d2e-111">Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="16d2e-112">(Facultatif) Sous **Description**, tapez une description de la règle de traduction pour exemple appel longue distance international.</span><span class="sxs-lookup"><span data-stu-id="16d2e-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="16d2e-113">Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="16d2e-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="16d2e-p102">**Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).</span><span class="sxs-lookup"><span data-stu-id="16d2e-p102">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match. For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="16d2e-116">**Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque.</span><span class="sxs-lookup"><span data-stu-id="16d2e-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="16d2e-117">Par exemple, entrez 11 et selectAt moins dans la liste déroulante en correspondance des numéros qui se trouvent au moins à 11 chiffres.</span><span class="sxs-lookup"><span data-stu-id="16d2e-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="16d2e-118">**Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer.</span><span class="sxs-lookup"><span data-stu-id="16d2e-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="16d2e-119">Par exemple, entrez 1 à retirer le + à partir du début du numéro.</span><span class="sxs-lookup"><span data-stu-id="16d2e-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="16d2e-p105">**Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.</span><span class="sxs-lookup"><span data-stu-id="16d2e-p105">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="16d2e-p106">Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :</span><span class="sxs-lookup"><span data-stu-id="16d2e-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="16d2e-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="16d2e-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="16d2e-p107">Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :</span><span class="sxs-lookup"><span data-stu-id="16d2e-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="16d2e-127">Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.</span><span class="sxs-lookup"><span data-stu-id="16d2e-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="16d2e-128">(Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.</span><span class="sxs-lookup"><span data-stu-id="16d2e-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="16d2e-129">Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="16d2e-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="16d2e-130">Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="16d2e-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="16d2e-131">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="16d2e-132">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="16d2e-133">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="16d2e-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="16d2e-134">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="16d2e-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="16d2e-135">Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="16d2e-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="16d2e-136">Pour définir une règle de traduction manuellement</span><span class="sxs-lookup"><span data-stu-id="16d2e-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="16d2e-137">Ouvrez le panneau de configuration serveur Business Skype</span><span class="sxs-lookup"><span data-stu-id="16d2e-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="16d2e-138">Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement dans Skype pour Business Server](configure-trunk-with-media-bypass.md) par le biais de l’étape 10 ou [configurer une jonction sans media contournement dans Skype pour Business Server](configure-trunk-without-media-bypass.md) jusqu'à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="16d2e-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="16d2e-139">Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="16d2e-140">(Facultatif) Dans la zone **Description**, tapez une description de la règle de traduction, par exemple appel longue distance International de numérotation.</span><span class="sxs-lookup"><span data-stu-id="16d2e-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="16d2e-141">Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.</span><span class="sxs-lookup"><span data-stu-id="16d2e-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="16d2e-142">Entrez ce qui suit dans **Taper une expression régulière** :</span><span class="sxs-lookup"><span data-stu-id="16d2e-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="16d2e-143">Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.</span><span class="sxs-lookup"><span data-stu-id="16d2e-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="16d2e-144">Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.</span><span class="sxs-lookup"><span data-stu-id="16d2e-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="16d2e-145">Par exemple, si vous entrez ^\+(\d{9}\d+)$ dans **ce modèle de correspondance** and011$ 1 dans **règle de traduction**, la règle traduira le numéro + 441235551010 comme suit, 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="16d2e-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="16d2e-146">Cliquez sur **OK** pour enregistrer la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="16d2e-147">Cliquez sur **OK** pour enregistrer la configuration de la jonction.</span><span class="sxs-lookup"><span data-stu-id="16d2e-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="16d2e-148">Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="16d2e-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="16d2e-149">Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="16d2e-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="16d2e-150">Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="16d2e-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16d2e-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16d2e-151">See also</span></span>

[<span data-ttu-id="16d2e-152">Configurer une jonction avec contournement de média dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16d2e-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="16d2e-153">Configurer une jonction sans contournement de média dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16d2e-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="16d2e-154">Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="16d2e-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="16d2e-155">Déployer le contournement de média dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16d2e-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

