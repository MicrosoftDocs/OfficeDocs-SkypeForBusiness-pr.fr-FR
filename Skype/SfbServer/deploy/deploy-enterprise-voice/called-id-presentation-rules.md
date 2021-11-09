---
title: Créer ou modifier une règle de traduction pour la présentation de l’ID appelé dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé : Découvrez comment définir une règle de traduction à l’aide de l’outil Créer une règle de traduction dans Skype Entreprise Server.'
ms.openlocfilehash: 82e737ddcd7ed7c17de3cdd968d31996e50074be
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864431"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Créer ou modifier une règle de traduction pour la présentation de l’ID appelé dans Skype Entreprise Server

**Résumé :** Découvrez comment définir une règle de traduction à l’aide de l’outil Créer une règle de traduction dans Skype Entreprise Server.

Si vous souhaitez définir une règle de traduction, suivez  ces étapes en entrant un ensemble de valeurs dans l’outil Créer une règle de traduction et en permettant au Panneau de configuration Skype Entreprise Server de générer le modèle correspondant et la règle de traduction pour vous. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, voir [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Pour commencer à définir une règle de traduction, suivez les étapes de la procédure de configuration d’une trunk avec déviation du média dans [Skype Entreprise Server](configure-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou configurez une trunk sans déviation du média dans [Skype Entreprise Server](configure-trunk-without-media-bypass.md) à l’étape 9.

3. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. (Facultatif) Sous **Description**, tapez une description de la règle de traduction, par exemple la numérotation longue distance US International.

5. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :

   - **Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).

   - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez 11 et sélectionnez Au moins dans la liste de listes listes pour faire correspondre les numéros d’au moins 11 chiffres.

   - **Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer. Par exemple, entrez 1 pour détroner le + du début du nombre.

   - **Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.

     Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :

     ^\+(\d {9} \d+)$

     Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :

   - Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.

   - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

     Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.

     Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.

6. Cliquez sur **OK** pour enregistrer la règle de traduction.

7. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

8. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

   > [!NOTE]
   > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

### <a name="to-define-a-translation-rule-manually"></a>Pour définir une règle de traduction manuellement

1. Ouvrir Skype Entreprise Server panneau de commande

2. Pour commencer à définir une règle de traduction, suivez les étapes de la procédure de configuration d’une trunk avec déviation du média dans [Skype Entreprise Server](configure-trunk-with-media-bypass.md) jusqu’à l’étape 10 ou configurez une trunk sans déviation du média dans [Skype Entreprise Server](configure-trunk-without-media-bypass.md) à l’étape 9.

3. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. (Facultatif) Dans **Description,** tapez une description de la règle de traduction, par exemple la numérotation longue distance us-international.

5. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.

   - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

     Par exemple, si vous entrez ^ (\d \d+)$ dans Suivre ce modèle et \+ {9} 011$1  dans la règle de traduction, la règle traduit +441235551010 en 011441235551010.

7. Cliquez sur **OK** pour enregistrer la règle de traduction.

8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

9. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

## <a name="see-also"></a>Voir aussi

[Configurer une trunk avec déviation du média dans Skype Entreprise Server](configure-trunk-with-media-bypass.md)

[Configurer une trunk sans contournement de média dans Skype Entreprise Server](configure-trunk-without-media-bypass.md)

[Publier les modifications en attente de la configuration du routage des Skype Entreprise](voice-route-config-changes.md)

[Déployer le contournement de média dans Skype Entreprise Server](deploy-media-bypass.md)