---
title: Créer ou modifier une règle de normalisation dans Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Résumé : Apprenez à définir, créer et modifier une règle de normalisation dans Skype pour Business Server.'
ms.openlocfilehash: ef796d1484ec3848d7c6488127009f97ccc565ee
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882154"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="48c65-103">Créer ou modifier une règle de normalisation dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="48c65-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="48c65-104">**Résumé :** Apprenez à définir, créer et modifier une règle de normalisation dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="48c65-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="48c65-105">Définir, créer et modifier des règles de normalisation dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="48c65-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="48c65-106">Pour définir une règle de normalisation à l’aide de la section Créer une règle de normalisation</span><span class="sxs-lookup"><span data-stu-id="48c65-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="48c65-107">Ouvrez le panneau de configuration serveur Business Skype</span><span class="sxs-lookup"><span data-stu-id="48c65-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="48c65-108">(Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md) par le biais de l’étape 11 ou de [Modifier un Plan de numérotation](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) jusqu'à l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="48c65-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="48c65-109">Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro à normaliser dans **nom** (par exemple, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="48c65-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="48c65-110">(Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).</span><span class="sxs-lookup"><span data-stu-id="48c65-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="48c65-111">Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="48c65-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="48c65-112">**Chiffres de début** (Facultatif) Spécifiez les chiffres à gauche de numéros composés que vous souhaitez le modèle doit suivre.</span><span class="sxs-lookup"><span data-stu-id="48c65-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="48c65-113">Par exemple, type425 si vous souhaitez que le modèle doit suivre composé nombres qui commencent à 425.</span><span class="sxs-lookup"><span data-stu-id="48c65-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="48c65-114">**Longueur** Spécifier le nombre de chiffres dans le modèle correspondant et indiquez si vous souhaitez le modèle doit correspondre exactement à cette longueur, correspondance des numéros qui se trouvent au moins cette longueur composés ou correspondance composé des numéros de n’importe quelle longueur.</span><span class="sxs-lookup"><span data-stu-id="48c65-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="48c65-115">**Chiffres à supprimer** (Facultatif) Spécifier le nombre de chiffres à supprimer des numéros composés de début vous souhaitez que le modèle doit suivre.</span><span class="sxs-lookup"><span data-stu-id="48c65-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="48c65-116">**Chiffres à ajouter** (Facultatif) Spécifier les chiffres à ajouter aux numéros composés souhaité le modèle doit suivre.</span><span class="sxs-lookup"><span data-stu-id="48c65-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

    <span data-ttu-id="48c65-117">Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**.</span><span class="sxs-lookup"><span data-stu-id="48c65-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="48c65-118">Par exemple, si vous laissez type7 vide, **les chiffres de début** dans le champ de **longueur** et sélectionnez **exactement**et spécifiez la valeur 0 dans les **chiffres à supprimer**, l’expression régulière qui en résulte dans le **modèle pour la correspondance** est :</span><span class="sxs-lookup"><span data-stu-id="48c65-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

    <span data-ttu-id="48c65-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="48c65-119">^(\d{7})$</span></span>

6. <span data-ttu-id="48c65-120">Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :</span><span class="sxs-lookup"><span data-stu-id="48c65-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="48c65-121">Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre.</span><span class="sxs-lookup"><span data-stu-id="48c65-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="48c65-122">Par exemple, si le modèle correspondant est ^(\d{7})$ puis$ 1 dans la traduction de numéros composés de 7 chiffres représente la règle.</span><span class="sxs-lookup"><span data-stu-id="48c65-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="48c65-123">(Facultatif) Tapez une valeur dans le champ **chiffres à ajouter** pour spécifier les chiffres à être ajoutée au numéro traduit (par exemple, + 1425).</span><span class="sxs-lookup"><span data-stu-id="48c65-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

    <span data-ttu-id="48c65-124">Par exemple, si le **modèle à faire correspondre** contient ^(\d{7})$ comme modèle pour les numéros composés et contient de la **règle de traduction** + 1425$ 1 comme modèle pour E.164 numéros de téléphone, la règle numéro 5550100 + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="48c65-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="48c65-125">(Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.</span><span class="sxs-lookup"><span data-stu-id="48c65-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="48c65-p104">(Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.</span><span class="sxs-lookup"><span data-stu-id="48c65-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48c65-128">Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="48c65-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="48c65-129">Pour plus d’informations, voir [Routage des communications vocales Test](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="48c65-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="48c65-130">Cliquez sur **OK** pour enregistrer la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="48c65-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="48c65-131">Cliquez sur **OK** pour enregistrer le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="48c65-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="48c65-132">Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="48c65-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48c65-133">Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration.</span><span class="sxs-lookup"><span data-stu-id="48c65-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="48c65-134">Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="48c65-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="48c65-135">Pour définir une règle de normalisation manuellement</span><span class="sxs-lookup"><span data-stu-id="48c65-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="48c65-136">Ouvrez le panneau de configuration serveur Business Skype</span><span class="sxs-lookup"><span data-stu-id="48c65-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="48c65-137">(Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="48c65-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="48c65-138">Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro à normaliser dans **nom** (par exemple, nom de la normalisation rule5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="48c65-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="48c65-139">(Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».</span><span class="sxs-lookup"><span data-stu-id="48c65-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="48c65-140">Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="48c65-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="48c65-141">Entrez ce qui suit dans **Taper une expression régulière** :</span><span class="sxs-lookup"><span data-stu-id="48c65-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="48c65-142">Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.</span><span class="sxs-lookup"><span data-stu-id="48c65-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="48c65-143">Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.</span><span class="sxs-lookup"><span data-stu-id="48c65-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

    <span data-ttu-id="48c65-144">Par exemple, si vous entrez ^(\d{7})$ dans **ce modèle de correspondance** et + 1425$ 1 dans **règle de traduction**, la règle numéro 5550100 + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="48c65-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="48c65-145">(Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.</span><span class="sxs-lookup"><span data-stu-id="48c65-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="48c65-p107">(Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.</span><span class="sxs-lookup"><span data-stu-id="48c65-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="48c65-148">Cliquez sur **OK** pour enregistrer la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="48c65-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="48c65-149">Cliquez sur **OK** pour enregistrer le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="48c65-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="48c65-150">Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="48c65-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48c65-151">Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration.</span><span class="sxs-lookup"><span data-stu-id="48c65-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="48c65-152">Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="48c65-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


