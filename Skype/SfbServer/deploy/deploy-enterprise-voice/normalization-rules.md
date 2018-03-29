---
title: Création ou modification d’une règle de normalisation dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Résumé : Apprenez à définir, créer et modifier une règle de normalisation dans Skype pour Business Server 2015.'
ms.openlocfilehash: 5b55e5e930680d3c51908b77d44a80e2e74ef89c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business-2015"></a>Création ou modification d’une règle de normalisation dans Skype Entreprise 2015
 
**Résumé :** Apprenez à définir, créer et modifier une règle de normalisation dans Skype pour Business Server 2015.
  
Définir, créer et modifier des règles de normalisation dans Skype pour Business Server.
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>Pour définir une règle de normalisation à l’aide de la section Créer une règle de normalisation

1. Ouvrez Skype pour le panneau de configuration de Business Server
    
2. (Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md) à l’étape 11 ou de [Modifier un Plan d’appel](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) par le biais de l’étape 10.
    
3. Dans la **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro est normalisé dans le **nom** (par exemple, 5DigitExtension).
    
4. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
    
5. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    
   - **Démarrage des chiffres** (Facultatif) Spécifier les chiffres principaux de numéros composés, vous souhaitez que le modèle à faire correspondre. Par exemple, type425 si vous souhaitez que le modèle composé nombres qui commencent à 425.
    
   - **Longueur** Spécifier le nombre de chiffres dans le modèle de correspondance et indiquez si vous souhaitez que le modèle en fonction de cette longueur exactement, correspondance composé de nombres qui sont au moins cette longueur, ou correspondance composé des numéros de n’importe quelle longueur.
    
   - **Chiffres à supprimer** (Facultatif) Spécifier le nombre de chiffres à supprimer de numéros composés de démarrage, vous souhaitez que le modèle à faire correspondre.
    
   - **Chiffres à ajouter** (Facultatif) Spécifier des chiffres pour être ajouté aux numéros composés vous souhaitez que le modèle à faire correspondre.
    
    Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez les type7 vide, **les chiffres de départ** dans le champ **longueur** **exactement**et sélectionnez Spécifiez 0 **pour supprimer les**chiffres, l’expression régulière obtenue dans le **modèle pour la correspondance** est la suivante :
    
    ^(\d{7})$
    
6. Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :
    
   - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est ^ (\d{7})$ puis$ 1 dans la règle de traduction représente les numéros composés à 7 chiffres.
    
   - (Facultatif) Tapez une valeur dans le champ **chiffres à ajouter** pour spécifier les chiffres en début de liste le nombre traduit (par exemple, +1425).
    
    Par exemple, si le **modèle à faire correspondre** les $ de contains^(\d{7}) comme modèle pour les numéros composés et la **règle de traduction des** contient + 1425$ 1 comme modèle E.164 pour les numéros de téléphone, la règle normalise 5550100 à +14255550100.
    
7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
    
8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
    > [!NOTE]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez [Routage des communications vocales de Test](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx). 
  
9. Cliquez sur **OK** pour enregistrer la règle de normalisation.
    
10. Cliquez sur **OK** pour enregistrer le plan de numérotation.
    
11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**. 
    
    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  
### <a name="to-define-a-normalization-rule-manually"></a>Pour définir une règle de normalisation manuellement

1. Ouvrez Skype pour le panneau de configuration de Business Server
    
2. (Facultatif) Suivez les étapes de [créer ou modifier un plan de numérotation dans Skype pour Business Server 2015](dial-plans.md). 
    
3. Dans la **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, tapez un nom qui décrit le modèle de numéro en cours de normalisation de **nom** (par exemple, le nom de la rule5DigitExtension de normalisation).
    
4. (Facultatif) Dans le champ **Description**, entrez la description de la règle de normalisation, par exemple, « Traduit les numéros de poste à 5 chiffres ».
    
5. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.
    
6. Entrez ce qui suit dans **Taper une expression régulière** :
    
   - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    
   - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.
    
    Par exemple, si vous entrez ^ (\d{7})$ dans **correspond à ce modèle** et + 1425$ 1 dans une **règle de traduction**, la règle normalise 5550100 à +14255550100.
    
7. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
    
8. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    
9. Cliquez sur **OK** pour enregistrer la règle de normalisation.
    
10. Cliquez sur **OK** pour enregistrer le plan de numérotation.
    
11. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  

