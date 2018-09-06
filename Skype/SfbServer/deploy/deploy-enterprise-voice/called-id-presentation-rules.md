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
ms.openlocfilehash: 768538f861ec3c020b02fc9df4498350f9c13a4b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246794"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Créer ou modifier une règle de traduction pour présentation ID appelée Skype pour Business Server

**Résumé :** Découvrez comment définir une règle de traduction à l’aide de la version un outil de la règle de traduction dans Skype pour Business Server.

Suivez ces étapes si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant Skype pour Business Server Control Panel générer le modèle correspondant correspondant et la règle de traduction pour vous. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, voir [créer ou modifier une règle de traduction manuellement](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement dans Skype pour Business Server](configure-trunk-with-media-bypass.md) par le biais de l’étape 10 ou [configurer une jonction sans media contournement dans Skype pour Business Server](configure-trunk-without-media-bypass.md) jusqu'à l’étape 9.

3. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. (Facultatif) Sous **Description**, tapez une description de la règle de traduction pour exemple appel longue distance international.

5. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :

   - **Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).

   - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez 11 et selectAt moins dans la liste déroulante en correspondance des numéros qui se trouvent au moins à 11 chiffres.

   - **Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer. Par exemple, entrez 1 à retirer le + à partir du début du numéro.

   - **Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.

    Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :

    ^\+(\d{9}\d+)$

    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :

   - Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.

   - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

    Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.

    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.

6. Cliquez sur **OK** pour enregistrer la règle de traduction.

7. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

8. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

   > [!NOTE]
   > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

### <a name="to-define-a-translation-rule-manually"></a>Pour définir une règle de traduction manuellement

1. Ouvrez le panneau de configuration serveur Business Skype

2. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement dans Skype pour Business Server](configure-trunk-with-media-bypass.md) par le biais de l’étape 10 ou [configurer une jonction sans media contournement dans Skype pour Business Server](configure-trunk-without-media-bypass.md) jusqu'à l’étape 9.

3. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. (Facultatif) Dans la zone **Description**, tapez une description de la règle de traduction, par exemple appel longue distance International de numérotation.

5. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.

   - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

    Par exemple, si vous entrez ^\+(\d{9}\d+)$ dans **ce modèle de correspondance** and011$ 1 dans **règle de traduction**, la règle traduira le numéro + 441235551010 comme suit, 011441235551010.

7. Cliquez sur **OK** pour enregistrer la règle de traduction.

8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

9. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

## <a name="see-also"></a>Voir aussi

[Configurer une jonction avec contournement de média dans Skype pour Business Server](configure-trunk-with-media-bypass.md)

[Configurer une jonction sans contournement de média dans Skype pour Business Server](configure-trunk-without-media-bypass.md)

[Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md)

[Déployer le contournement de média dans Skype pour Business Server](deploy-media-bypass.md)

