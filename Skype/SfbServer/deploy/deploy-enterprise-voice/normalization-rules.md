---
title: Créer ou modifier une règle de normalisation dans Skype pour les entreprises
ms.reviewer: ''
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
ms.openlocfilehash: 52f56280c747db702935405ea4c60383c58a6d78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874597"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Créer ou modifier une règle de normalisation dans Skype pour les entreprises

**Résumé :** Apprenez à définir, créer et modifier une règle de normalisation dans Skype pour Business Server.

Définir, créer et modifier des règles de normalisation dans Skype pour Business Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle de normalisation à l’aide de la section Créer une règle de normalisation

1. Ouvrez le panneau de configuration serveur Business Skype

2. (Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md) par le biais de l’étape 11 ou de [Modifier un Plan de numérotation](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) jusqu'à l’étape 10.

3. Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro à normaliser dans **nom** (par exemple, 5DigitExtension).

4. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

5. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :

   - **Chiffres de début** (Facultatif) Spécifiez les chiffres à gauche de numéros composés que vous souhaitez le modèle doit suivre. Par exemple, type425 si vous souhaitez que le modèle doit suivre composé nombres qui commencent à 425.

   - **Longueur** Spécifier le nombre de chiffres dans le modèle correspondant et indiquez si vous souhaitez le modèle doit correspondre exactement à cette longueur, correspondance des numéros qui se trouvent au moins cette longueur composés ou correspondance composé des numéros de n’importe quelle longueur.

   - **Chiffres à supprimer** (Facultatif) Spécifier le nombre de chiffres à supprimer des numéros composés de début vous souhaitez que le modèle doit suivre.

   - **Chiffres à ajouter** (Facultatif) Spécifier les chiffres à ajouter aux numéros composés souhaité le modèle doit suivre.

     Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez type7 vide, **les chiffres de début** dans le champ de **longueur** et sélectionnez **exactement**et spécifiez la valeur 0 dans les **chiffres à supprimer**, l’expression régulière qui en résulte dans le **modèle pour la correspondance** est :

     ^(\d{7})$

6. Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :

   - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est ^(\d{7})$ puis$ 1 dans la traduction de numéros composés de 7 chiffres représente la règle.

   - (Facultatif) Tapez une valeur dans le champ **chiffres à ajouter** pour spécifier les chiffres à être ajoutée au numéro traduit (par exemple, + 1425).

     Par exemple, si le **modèle à faire correspondre** contient ^(\d{7})$ comme modèle pour les numéros composés et contient de la **règle de traduction** + 1425$ 1 comme modèle pour E.164 numéros de téléphone, la règle numéro 5550100 + 14255550100.

7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

### <a name="to-define-a-normalization-rule-manually"></a>Pour définir une règle de normalisation manuellement

1. Ouvrez le panneau de configuration serveur Business Skype

2. (Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server](dial-plans.md).

3. Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro à normaliser dans **nom** (par exemple, nom de la normalisation rule5DigitExtension).

4. (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».

5. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.

   - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.

     Par exemple, si vous entrez ^(\d{7})$ dans **ce modèle de correspondance** et + 1425$ 1 dans **règle de traduction**, la règle numéro 5550100 + 14255550100.

7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.


