---
title: Création ou modification d’une règle de conversion pour la présentation de l’ID de la personne appelée dans Skype Entreprise Server 2015
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Résumé : Découvrez comment définir une règle de traduction à l’aide de la génération un outil règle de traduction dans Skype pour Business Server 2015.'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a>Création ou modification d’une règle de conversion pour la présentation de l’ID de la personne appelée dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment définir une règle de traduction à l’aide de la génération un outil règle de traduction dans Skype pour Business Server 2015.
  
Suivez ces étapes si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil de **Création d’une règle de traduction** et de l’activation de Skype pour panneau Business Server générer le modèle de correspondance correspondant et règle de traduction pour vous. Vous pouvez également écrire manuellement une expression régulière pour définir le modèle correspondant et la règle de traduction. Pour plus d’informations, voir [créer ou modifier une règle de traduction manuellement](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>Pour définir une règle à l’aide de l’outil Créer une règle de traduction

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Pour commencer à définir une règle de traduction, procédez dans [configurer un tronc avec support ignorer dans Skype pour Business Server 2015](configure-trunk-with-media-bypass.md) via l’étape 10 ou [configurer un tronc sans media ignorer dans Skype pour Business Server 2015](configure-trunk-without-media-bypass.md) à 9.
    
3. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
    
4. (Facultatif) Sous **Description**, tapez une description de la règle de traduction, d’appel longue distance d’exemple nous International.
    
5. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    
   - **Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros E.164 format (qui commencent par +).
    
   - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez 11 et selectAt au moins dans la liste déroulante correspondant à des nombres qui sont au moins 11 chiffres.
    
   - **Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer. Par exemple, entrez 1 à retirer le + à partir du début du nombre.
    
   - **Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez 011 si vous souhaitez que 011 en début de liste numéros traduites lorsque la règle est appliquée.
    
    Les valeurs saisies dans ces champs sont reproduites dans les champs **Modèle à suivre** et **Règle de traduction**. Par exemple, si vous appliquez les valeurs de l’exemple précédent, l’expression régulière obtenue dans le champ **Modèle à suivre** est :
    
    ^\+(\d{9}\d+)$
    
    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    
   - Une valeur (par exemple, $1) qui représente le nombre de chiffres dans le modèle de correspondance
    
   - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.
    
    À l’aide de l’exemple précédent valeurs, 011$ 1 apparaît dans le champ **règle de traduction** .
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.
    
6. Cliquez sur **OK** pour enregistrer la règle de traduction.
    
7. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
    
8. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 
    
   > [!NOTE]
   > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  
### <a name="to-define-a-translation-rule-manually"></a>Pour définir une règle de traduction manuellement

1. Ouvrez Skype pour le panneau de configuration de Business Server
    
2. Pour commencer à définir une règle de traduction, procédez dans [configurer un tronc avec support ignorer dans Skype pour Business Server 2015](configure-trunk-with-media-bypass.md) via l’étape 10 ou [configurer un tronc sans media ignorer dans Skype pour Business Server 2015](configure-trunk-without-media-bypass.md) à 9.
    
3. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
    
4. (Facultatif) Dans la zone **Description**, tapez une description de la règle de traduction, par exemple nous International longue distance de numérotation.
    
5. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.
    
6. Entrez ce qui suit dans **Taper une expression régulière** :
    
   - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    
   - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.
    
    Par exemple, si vous entrez ^\+(\d{9}\d+)$ dans **ce modèle de correspondance** and011$ 1 dans une **règle de traduction**, la règle convertit +441235551010 à 011441235551010.
    
7. Cliquez sur **OK** pour enregistrer la règle de traduction.
    
8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
    
9. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 
    
    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  
## <a name="see-also"></a>Voir aussi

#### 

[Configurer une jonction avec le contournement de média dans Skype pour Business Server 2015](configure-trunk-with-media-bypass.md)
  
[Configurer un tronc sans media ignore dans Skype pour Business Server 2015](configure-trunk-without-media-bypass.md)
  
[Publier des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md)
#### 

[Déployer le contournement de média dans Skype pour Business Server 2015](deploy-media-bypass.md)

