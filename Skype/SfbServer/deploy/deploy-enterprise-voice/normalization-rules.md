---
title: Créer ou modifier une règle de normalisation dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Résumé : Découvrez comment définir, créer et modifier une règle de normalisation dans Skype Entreprise Server.'
ms.openlocfilehash: c624e9bb42b113a87c5774f90df77c23488d1b32
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773274"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>Créer ou modifier une règle de normalisation dans Skype Entreprise

**Résumé :** Découvrez comment définir, créer et modifier une règle de normalisation dans Skype Entreprise Server.

Définissez, créez et modifiez des règles de normalisation dans Skype Entreprise Server.

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle de normalisation à l’aide de la procédure Créer une règle de normalisation

1. Ouvrir Skype Entreprise Server panneau de commande

2. (Facultatif) Suivez les étapes de création ou de modification d’un plan de [numérotation Skype Entreprise Server](dial-plans.md) l’étape 11 ou modifier un [plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) de numérotation jusqu’à l’étape 10.

3. Dans **Nouvelle règle de normalisation** ou Modifier la règle de normalisation, tapez un nom qui décrit le modèle de numéro en cours de normalisation dans **Nom** (par exemple, 5DigitExtension). 

4. (Optionnel) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).

5. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :

   - **Chiffres de début** (facultatif) Spécifiez les premiers chiffres des numéros composés que vous souhaitez que le modèle corresponde. Par exemple, tapez 425 si vous souhaitez que le modèle corresponde aux numéros composés commençant par 425.

   - **Longueur** Spécifiez le nombre de chiffres dans le modèle correspondant et indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, qu’il corresponde aux numéros composés d’au moins cette longueur ou qu’il corresponde à des numéros composés de toute longueur.

   - **Chiffres à supprimer** (facultatif) Spécifiez le nombre de chiffres de début à supprimer des numéros composés que vous souhaitez que le modèle corresponde.

   - **Chiffres à ajouter** (facultatif) Spécifiez les chiffres à ajouter aux numéros composés que vous souhaitez que le modèle corresponde.

     Les valeurs que vous entrez dans ces champs apparaissent dans **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous laissez  les **chiffres** de début vides, tapez7 dans le champ Longueur et sélectionnez **Exactement**, et spécifiez 0 dans **chiffres** à supprimer, l’expression régulière résultante dans le modèle à mettre en correspondance est : 

     ^(\d{7})$

6. Dans **Règle de traduction**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 traduits :

   - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est ^(\d )$ alors $1 dans la règle de traduction représente des numéros composés à {7} 7 chiffres.

   - (Facultatif) Tapez une valeur dans les **chiffres** à ajouter pour spécifier les chiffres à ajouter au numéro traduit (par exemple, +1425).

     Par exemple,  si le modèle à suivre contient^(\d )$ comme modèle pour les numéros composés et que la règle de traduction contient +1425$1 comme modèle pour les numéros de téléphone E.164, la règle normalise {7} 5550100 à +14255550100. 

7. (Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, voir [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) (contenu éventuellement en anglais).

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

### <a name="to-define-a-normalization-rule-manually"></a>Pour définir une règle de normalisation manuellement

1. Ouvrir Skype Entreprise Server panneau de commande

2. (Facultatif) Suivez les étapes de [création ou de modification d’un plan](dial-plans.md)de numérotation dans Skype Entreprise Server .

3. Dans **Nouvelle règle** de normalisation ou Modifier la règle de normalisation, tapez un nom qui décrit le modèle de numéro en cours de normalisation dans **Nom** (par exemple, nommez la règle de normalisation5DigitExtension). 

4. (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple « Traduit les numéros de poste à 5 chiffres ».

5. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.

   - Dans **Règle de traduction**, précisez un modèle pour le format des numéros de téléphone E.164 traduits.

     Par exemple, si vous entrez ^(\d )$ dans Suivre ce modèle et +1425$1 dans la règle de traduction, la règle normalise {7} 5550100 à +14255550100.  

7. (Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.

8. (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.

9. Cliquez sur **OK** pour enregistrer la règle de normalisation.

10. Cliquez sur **OK** pour enregistrer le plan de numérotation.

11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.