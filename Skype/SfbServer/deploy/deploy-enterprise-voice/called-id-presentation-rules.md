---
title: Création ou modification d’une règle de traduction pour appeler une présentation dans Skype entreprise Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé : Découvrez comment définir une règle de traduction à l’aide de l’outil créer une règle de traduction dans Skype entreprise Server.'
ms.openlocfilehash: 1a1f363ad157775395f77ef3e3c2915e9226bfd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768197"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>Création ou modification d’une règle de traduction pour appeler une présentation dans Skype entreprise Server

**Résumé :** Découvrez comment définir une règle de traduction à l’aide de l’outil créer une règle de traduction dans Skype entreprise Server.

Suivez ces étapes si vous voulez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil **créer une règle de traduction** et en activant le panneau de configuration Skype entreprise Server pour générer les modèles correspondants et les règles de traduction correspondants. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, voir [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Skype entreprise Server via l'](configure-trunk-with-media-bypass.md) étape 10 ou [configurer un Trunk sans dérivation multimédia dans Skype entreprise Server à l'](configure-trunk-without-media-bypass.md) étape 9.

3. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. Facultatif Sous **Description**, tapez la description de la règle de traduction (par exemple, la numérotation internationale pour les appels longue distance).

5. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :

   - **Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).

   - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez 11 et selectAt moins dans la liste déroulante pour faire correspondre les nombres dont la longueur est d’au moins 11 chiffres.

   - **Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer. Par exemple, entrez 1 pour enlever le signe + du début du numéro.

   - **Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez 011 si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.

     Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :

     ^\+(\d{9}\d +) $

     Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :

   - Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle correspondant.

   - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

     Si vous utilisez les valeurs de l’exemple précédent, 011$1 apparaît dans le champ **Règle de traduction**.

     Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.

6. Cliquez sur **OK** pour enregistrer la règle de traduction.

7. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

8. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

   > [!NOTE]
   > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

### <a name="to-define-a-translation-rule-manually"></a>Pour définir une règle de traduction manuellement

1. Ouvrir le panneau de configuration Skype entreprise Server

2. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media bypass dans Skype entreprise Server via l'](configure-trunk-with-media-bypass.md) étape 10 ou [configurer un Trunk sans dérivation multimédia dans Skype entreprise Server à l'](configure-trunk-without-media-bypass.md) étape 9.

3. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.

4. Facultatif Dans **Description**, tapez la description de la règle de traduction (par exemple, la numérotation internationale internationale pour les appels longue distance).

5. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.

6. Entrez ce qui suit dans **Taper une expression régulière** :

   - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.

   - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

     Par exemple, si vous entrez ^\+(\d{9}\d +) $ dans **respecter ce modèle** and011 $1 dans la **règle de traduction**, la règle traduira + 441235551010 en 011441235551010.

7. Cliquez sur **OK** pour enregistrer la règle de traduction.

8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.

9. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

## <a name="see-also"></a>Voir aussi

[Configuration d’une Trunk with Media bypass dans Skype entreprise Server](configure-trunk-with-media-bypass.md)

[Configurer un Trunk sans dérivation multimédia dans Skype entreprise Server](configure-trunk-without-media-bypass.md)

[Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise](voice-route-config-changes.md)

[Déploiement du contournement multimédia dans Skype entreprise Server](deploy-media-bypass.md)

