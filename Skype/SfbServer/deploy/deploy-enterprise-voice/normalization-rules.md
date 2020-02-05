---
title: Création ou modification d’une règle de normalisation dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Résumé : Découvrez comment définir, créer et modifier une règle de normalisation dans Skype entreprise Server.'
ms.openlocfilehash: c206bd20c02053f4e3775f32b1ba61000bb59a63
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767087"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Création ou modification d’une règle de normalisation dans Skype entreprise

**Résumé :** Familiarisez-vous avec la définition, la création et la modification d’une règle de normalisation dans Skype entreprise Server.

Définir, créer et modifier des règles de normalisation dans Skype entreprise Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle de normalisation à l’aide de la section Créer une règle de normalisation

1. Ouvrir le panneau de configuration Skype entreprise Server

2. Facultatif Suivez les étapes de la rubrique [créer ou modifier un plan de numérotation dans Skype entreprise Server via l'](dial-plans.md) étape 11 ou [modifier un plan de numérotation](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) via l’étape 10.

3. Dans **nouvelle règle de normalisation** ou **modifier la règle de normalisation**, tapez un nom qui décrit le modèle numérique normalisé dans **nom** (par exemple, 5DigitExtension).

4. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

5. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :

   - **Premiers chiffres** (facultatifs) Spécifiez les premiers chiffres des numéros numérotés que vous voulez associer au modèle. Par exemple, type425 si vous voulez que le modèle corresponde à des numéros numérotés commençant par 425.

   - **Longueur** Spécifiez le nombre de chiffres dans le modèle correspondant, puis indiquez si vous souhaitez que le modèle corresponde à cette longueur exactement, qu’il corresponde à des numéros numérotés au moins de cette longueur ou qu’il corresponde à des numéros numérotés de n’importe quelle longueur.

   - **Chiffres à supprimer** (facultatif) Spécifiez le nombre de chiffres de départ à supprimer des numéros numérotés que vous voulez associer au modèle.

   - **Chiffres à ajouter** (facultatif) Spécifiez les chiffres à ajouter aux numéros numérotés à utiliser pour le modèle.

     Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez les **chiffres** vides, Type7 dans le champ **longueur** et sélectionnez **exactement**et spécifiez 0 dans les **chiffres à supprimer**, l’expression régulière résultante dans le **modèle à faire correspondre** est la suivante :

     ^ (\d{7}) $

6. Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :

   - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est ^ (\d{7}) $, $1 dans la règle de traduction représente les numéros numérotés à 7 chiffres.

   - Facultatif Tapez une valeur dans le champ **chiffres à ajouter** pour spécifier les chiffres devant être ajoutés au numéro traduit (par exemple, + 1425).

     Par exemple, si le modèle **à faire correspondre** contient ^{7}(\d) $ en tant que modèle pour les numéros numérotés et la **règle de traduction** contenant + 1425 $1 comme modèle pour les numéros de téléphone E. 164, la règle normalise 5550100 à + 14255550100.

7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

### <a name="to-define-a-normalization-rule-manually"></a>Pour définir une règle de normalisation manuellement

1. Ouvrir le panneau de configuration Skype entreprise Server

2. Facultatif Suivez les étapes de la rubrique [créer ou modifier un plan de numérotation dans Skype entreprise Server](dial-plans.md).

3. Dans **nouvelle règle de normalisation** ou **modifier la règle de normalisation**, tapez un nom qui décrit le modèle numérique normalisé dans **nom** (par exemple, nom de la normalisation rule5DigitExtension).

4. (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».

5. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.

   - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.

     Par exemple, si vous entrez ^ (\d{7}) $ dans **respecter ce modèle** et + 1425 $1 dans la **règle de traduction**, la règle normalise les 5550100 à + 14255550100.

7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.


