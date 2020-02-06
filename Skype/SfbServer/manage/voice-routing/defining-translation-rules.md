---
title: Définir des règles de traduction dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype entreprise Server voix entreprise route les appels sur la base des numéros de téléphone normalisés au format E. 164. Cela signifie que toutes les chaînes numérotées doivent être normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL), afin de les traduire dans leur URI SIP correspondante. Skype entreprise Server vous permet de manipuler l’ID appelé et la présentation d’identification de l’appelant.
ms.openlocfilehash: cdcfe3a847e148461b97abed33df070057dcd00b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816984"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Définir des règles de traduction dans Skype entreprise Server

Skype entreprise Server voix entreprise route les appels sur la base des numéros de téléphone normalisés au format E. 164. Cela signifie que toutes les chaînes numérotées doivent être normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL), afin de les traduire dans leur URI SIP correspondante. Skype entreprise Server vous permet de manipuler l’ID appelé et la présentation d’identification de l’appelant.

Avec Skype entreprise Server, le numéro de téléphone du tiers (c’est-à-dire le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par l’homologue de Trunk (c’est-à-dire, la passerelle associée, le PBX ou le SIP). Trunk). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

## <a name="caller-id-presentation"></a>Présentation de l’identification de l’appelant

Skype entreprise Server vous permet également de traduire le numéro de téléphone de la personne qui appelle, c’est-à-dire le numéro de téléphone à partir duquel l’appelant appelle, le format E. 164 au format de numérotation local requis par l’homologue Trunk. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

**Pour configurer l’identification de l’appelant à l’aide du panneau de configuration Skype entreprise Server**

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez [autorisations de configuration de délégué](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype pour les entreprises, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
4. Dans la page Configuration de la jonction, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
5. Pour configurer la présentation de l’identification de l’appelant :
    - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. 
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**.
    - Pour copier une règle de traduction existante à utiliser comme point de départ pour la définition d’une nouvelle règle, cliquez sur le nom de la règle, cliquez sur **copier**, puis cliquez sur **coller**.
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

> [!Warning] 
> N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

## <a name="called-id-presentation"></a>Présentation de l’ID appelé

> [!Important]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme *alternative* à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit. 

Pour créer ou modifier une règle de traduction, vous pouvez utiliser l’une des méthodes suivantes :

- [Utiliser l’outil créer une règle de traduction](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laisser le panneau de configuration de Skype entreprise Server générer le modèle correspondant et la règle de traduction correspondants pour vous.
- [Rédigez manuellement des expressions régulières](#create-or-modify-a-translation-rule-manually) pour définir les modèles correspondants et les règles de traduction.

> [!Note]
> Pour plus d’informations sur la façon d’écrire des expressions régulières, voir [expressions régulières .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction

Suivez ces étapes si vous voulez définir une règle de traduction en entrant un ensemble de valeurs dans l’outil créer une règle de traduction et en activant le panneau de configuration Skype entreprise Server pour générer le modèle de correspondance et la règle de traduction correspondants pour vous. 

**Pour définir une règle à l’aide de l’outil Créer une règle de traduction**

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez [autorisations de configuration de délégué](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype pour les entreprises, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media Bypass](GET LINK AFTER MIGRATION)via l’étape 10 ou [configurer un Trunk sans média](GET LINK AFTER MIGRATION) par le biais de l’étape 9.
4. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. Facultatif Sous **Description**, tapez la description de la règle de traduction (par exemple, **Numérotation internationale américaine**).
6. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    - **Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).
    - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **At least** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.
    - **Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer. Par exemple, entrez **1** pour retirer le signe + au début du numéro.
    - **Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.
    
    Les valeurs que vous entrez dans ces champs sont reflétées dans les champs **modèle pour correspondre** et règle de **traduction** . Par exemple, si vous spécifiez les valeurs d’exemple ci-dessus, l’expression régulière résultante dans le **modèle Matc**est la suivante :
    
    **^\+(\d{9}\d +) $** 

    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    - Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.
    - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

    Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.
7. Cliquez sur **OK** pour enregistrer la règle de traduction.
8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
9. Dans la page **Trunk configuratio**n, cliquez sur **valider**, puis sur **valider tout**. 

> [!Note]
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la section publier les modifications en attente dans la configuration de routage](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx) 

### <a name="create-or-modify-a-translation-rule-manually"></a>Création ou modification manuelle d’une règle de traduction

Suivez ces étapes si vous voulez définir une règle de traduction en écrivant une expression régulière pour le modèle et la règle de traduction correspondants. 

**Pour définir une règle de traduction manuellement**

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez [autorisations de configuration de délégué](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype pour les entreprises, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans l’article [configurer un Trunk with Media Bypass](GET LINK AFTER MIGRATION)via l’étape 10 ou [configurer un Trunk sans média](GET LINK AFTER MIGRATION) par le biais de l’étape 9.
4. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. Facultatif Dans **Description**, tapez la description de la règle de traduction. par exemple, la **Numérotation internationale à la distance américaine**.
6. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.
7. Entrez les informations suivantes dans entrer une **expression régulière**:
    - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

    Par exemple, si vous entrez ** ^ \+(\d{9}\d +) $** dans **respecter ce modèle** et **011 $1** dans la **règle de traduction**, la règle traduira + 441235551010 à 011441235551010.
8. Cliquez sur **OK** pour enregistrer la règle de traduction.
9. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
10. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

> [!Note] 
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la section publier les modifications en attente dans la configuration de routage](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx) 
