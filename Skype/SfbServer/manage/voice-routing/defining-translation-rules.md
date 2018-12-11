---
title: Définition des règles de traduction dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server Enterprise Voice achemine les appels en fonction de numéros de téléphone normalisés au format E.164. Cela signifie que toutes les chaînes composés doivent être normalisés au format E.164 pour effectuer la recherche inversée de numéros (RNL) afin qu’ils peuvent être traduites à leur URI SIP correspondant. Skype pour Business Server offre la possibilité de manipuler l’ID appelé et la présentation d’ID de l’appelant.
ms.openlocfilehash: e3feda41a3057ea6f0ae6d7946f3e21e75ba7f81
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223002"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Définition des règles de traduction dans Skype pour Business Server

Skype pour Business Server Enterprise Voice achemine les appels en fonction de numéros de téléphone normalisés au format E.164. Cela signifie que toutes les chaînes composés doivent être normalisés au format E.164 pour effectuer la recherche inversée de numéros (RNL) afin qu’ils peuvent être traduites à leur URI SIP correspondant. Skype pour Business Server offre la possibilité de manipuler l’ID appelé et la présentation d’ID de l’appelant.

Avec Skype pour Business Server, le numéro de téléphone de la personne appelée (autrement dit, le numéro de téléphone appelé) pouvant être traduits du format E.164 au format de numérotation local qui est requis par l’homologue de jonction (c'est-à-dire, la passerelle associée, autocommutateur privé (PBX) ou SIP jonction). À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.

## <a name="caller-id-presentation"></a>Présentation des ID de l’appelant

Skype pour Business Server offre la possibilité de la traduction du numéro de téléphone de l’appelant (autrement dit, le numéro de téléphone qui appelle à partir de l’appelant) du format E.164 au format de numérotation local qui est requis par l’homologue de jonction. Par exemple, vous pouvez écrire une règle de conversion pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

**Pour configurer l’ID de l’appelant à l’aide de la Skype pour Business Server Control Panel**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez la rubrique [déléguer des autorisations d’installation](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour Business le panneau de configuration, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
4. Dans la page Configuration de la jonction, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
5. Pour configurer la présentation de l’identification de l’appelant :
    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Règles de conversion du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. 
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis cliquez sur **Afficher les détails**.
    - Pour copier une règle de traduction existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, cliquez sur **Copier**, puis cliquez sur **Coller**.
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

> [!Warning] 
> N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

## <a name="called-id-presentation"></a>Présentation de l’appelé ID

> [!Important]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Enterprise Voice est destinée à être utilisé comme une *alternative* à la configuration des règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction à une configuration de jonction Enterprise Voice si vous avez configuré les règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit. 

Vous pouvez utiliser une des méthodes suivantes pour créer ou modifier une règle de traduction :

- [Utiliser l’outil d’une règle de traduction Build](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) pour spécifier des valeurs de départ chiffres, longueur, chiffres à supprimer et chiffres à ajouter, puis indiquez le Skype pour le panneau de configuration serveur Business générer la règle correspondante correspondante pattern et translation pour vous.
- [Écriture d’expressions régulières manuellement](#create-or-modify-a-translation-rule-manually) pour définir la règle de correspondance pattern et translation.

> [!Note]
> Pour plus d’informations sur l’écriture d’expressions régulières, voir [Expressions régulières .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927). 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Créer ou modifier une règle de traduction à l’aide du créer un outil de la règle de traduction

Suivez ces étapes si vous souhaitez définir une règle de traduction en entrant un ensemble de valeurs dans la génération un outil de la règle de traduction et en activant la Skype pour Business Server Control Panel générer le modèle correspondant correspondant et la règle de traduction pour vous. 

**Pour définir une règle à l’aide de l’outil Créer une règle de traduction**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez la rubrique [déléguer des autorisations d’installation](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour Business le panneau de configuration, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement](GET LINK AFTER MIGRATION)par le biais de l’étape 10 ou [configurer une jonction sans media ignorer](GET LINK AFTER MIGRATION) jusqu'à l’étape 9.
4. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. (Facultatif) Sous **Description**, tapez une description de la règle de traduction - par exemple, **États-Unis International de numérotation longue distance**.
6. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    - **Chiffres de début** : (Facultatif) précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).
    - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **At least** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.
    - **Chiffres à supprimer** : (Facultatif) précisez le nombre de chiffres de début à supprimer. Par exemple, entrez **1** pour retirer le signe + au début du numéro.
    - **Chiffres à ajouter** : (Facultatif) précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.
    
    Les valeurs que vous entrez dans ces champs sont répercutées dans les champs de règle de **modèle pour la correspondance** et la **traduction** . Par exemple, si vous spécifiez les valeurs de l’exemple précédent, l’expression régulière qui en résulte dans le champ h **modèle doit respecter**l’est :
    
    **^\+(\d{9}\d+)$** 

    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    - Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.
    - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

    Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.
7. Cliquez sur **OK** pour enregistrer la règle de traduction.
8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
9. Dans la page n **Configuration de jonction**, cliquez sur **Valider**, puis cliquez sur **valider tout**. 

> [!Note]
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [publication en attente apportées à la configuration de routage voix](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

### <a name="create-or-modify-a-translation-rule-manually"></a>Créer ou modifier une règle de traduction manuellement

Si vous souhaitez définir une règle de traduction en écrivant une expression régulière pour le modèle de correspondance et une règle de traduction, procédez comme suit. 

**Pour définir une règle de traduction manuellement**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez la rubrique [déléguer des autorisations d’installation](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour Business le panneau de configuration, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Pour commencer à définir une règle de traduction, suivez les étapes décrites dans [Configure une jonction avec support de contournement](GET LINK AFTER MIGRATION)par le biais de l’étape 10 ou [configurer une jonction sans media ignorer](GET LINK AFTER MIGRATION) jusqu'à l’étape 9.
4. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. (Facultatif) Dans la zone **Description**, tapez une description de la règle de traduction ; par exemple, **États-Unis International de numérotation longue distance**.
6. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.
7. Entrez ce qui suit dans le Type d’une **Expression régulière**:
    - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

    Par exemple, si vous entrez ** ^ \+(\d{9}\d+)$** dans **ce modèle de correspondance** et **011$ 1** dans la **règle de traduction**, la règle traduira le numéro + 441235551010 comme suit, 011441235551010.
8. Cliquez sur **OK** pour enregistrer la règle de traduction.
9. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
10. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

> [!Note] 
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [publication en attente apportées à la configuration de routage voix](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 