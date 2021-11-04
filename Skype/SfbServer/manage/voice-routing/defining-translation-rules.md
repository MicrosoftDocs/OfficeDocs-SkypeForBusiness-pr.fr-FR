---
title: Définition de règles de traduction dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Entreprise Server Voix Entreprise les appels basés sur des numéros de téléphone normalisation au format E.164. Cela signifie que toutes les chaînes composés doivent être normalisées au format E.164 dans le but d’effectuer une recherche inversée de numéro (RNL) afin qu’elles soient traduites dans leur URI SIP correspondant. Skype Entreprise Server permet de manipuler l’ID appelé et la présentation de l’ID de l’appelant.
ms.openlocfilehash: 9dee0e90a9cd06abef43d190cc391861f4ad1438
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737720"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>Définition de règles de traduction dans Skype Entreprise Server

Skype Entreprise Server Voix Entreprise les appels basés sur des numéros de téléphone normalisation au format E.164. Cela signifie que toutes les chaînes composés doivent être normalisées au format E.164 dans le but d’effectuer une recherche inversée de numéro (RNL) afin qu’elles soient traduites dans leur URI SIP correspondant. Skype Entreprise Server permet de manipuler l’ID appelé et la présentation de l’ID de l’appelant.

Avec Skype Entreprise Server, le numéro de téléphone de l’appelé (c’est-à-dire, le numéro de téléphone appelé) peut être converti du format E.164 au format de numérotation local requis par l’homologue de la connexion (c’est-à-dire, la passerelle associée, le PBX ou la connexion SIP). Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.

## <a name="caller-id-presentation"></a>Présentation de l’ID de l’appelant

Skype Entreprise Server offre la possibilité de traduire également le numéro de téléphone de l’appelant (c’est-à-dire, le numéro de téléphone depuis qui l’appelant appelle) du format E.164 au format de numérotation local requis par l’homologue de la connexion. Par exemple, vous pouvez écrire une règle de traduction pour supprimer +44 au début d’une chaîne de numérotation et utiliser 0144 à la place.

**Pour configurer l’ID de l’appelant à l’aide Skype Entreprise Server panneau de configuration**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Déléguer les autorisations de configuration.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
4. Dans la page Configuration de la jonction, double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
5. Pour configurer la présentation de l’identification de l’appelant :
    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Règles de traduction du numéro d’appel**, cliquez sur les règles que vous voulez associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. 
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.
    - Pour copier une règle de traduction existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, cliquez sur **Copier,** puis cliquez sur **Coller**.
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

> [!Warning] 
> N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

## <a name="called-id-presentation"></a>Présentation de l’ID appelé

> [!Important]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Voix Entreprise peut servir d’*alternative* à la définition de règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de traduction sur le pair de jonction, car les deux règles risqueraient de provoquer un conflit. 

Vous pouvez employer l’une des méthodes suivantes pour créer ou modifier une règle de traduction :

- [](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool) Utilisez l’outil Créer une règle de traduction pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le Panneau de configuration Skype Entreprise Server générer le modèle correspondant et la règle de traduction pour vous.
- [Écrivez manuellement des expressions régulières pour](#create-or-modify-a-translation-rule-manually) définir le modèle de correspondance et la règle de traduction.

> [!Note]
> Pour plus d’informations sur l’écriture d’expressions [régulières, voir .NET Framework Expressions régulières.](/dotnet/standard/base-types/regular-expressions) 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>Créer ou modifier une règle de traduction à l’aide de l’outil Créer une règle de traduction

Si vous souhaitez définir une règle de traduction, suivez ces étapes en entrant un ensemble de valeurs dans l’outil Créer une règle de traduction et en permettant au Panneau de configuration Skype Entreprise Server de générer le modèle correspondant et la règle de traduction pour vous. 

**Pour définir une règle à l’aide de l’outil Créer une règle de traduction**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Déléguer les autorisations de configuration.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Pour commencer la définition d’une [](GET LINK AFTER MIGRATION)règle de traduction, suivez les étapes de configuration d’une trunk avec déviation du média jusqu’à l’étape 10 ou configurez une trunk [sans](GET LINK AFTER MIGRATION) contournement de média à l’étape 9.
4. Sous **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. (Facultatif) Sous **Description**, tapez une description de la règle de traduction , par exemple, la numérotation longue distance internationale **des États-Unis.**
6. Dans la section **Créer une règle de traduction** de la boîte de dialogue, entrez des valeurs dans les champs suivants :
    - **Chiffres de début** : (Facultatif) Précisez les premiers chiffres des numéros que vous souhaitez faire correspondre avec le modèle. Par exemple, entrez + dans ce champ pour faire correspondre les numéros au format E.164 (commençant par un signe +).
    - **Longueur** : précisez le nombre de chiffres dans le modèle correspondant et choisissez si vous souhaitez que le modèle corresponde exactement à des numéros de cette longueur, à cette longueur au minimum et ou à une longueur quelconque. Par exemple, entrez **11** et sélectionnez l’option **Au moins** dans la liste déroulante pour faire correspondre les numéros dont la longueur est d’au minimum 11 chiffres.
    - **Chiffres à supprimer** : (Facultatif) Précisez le nombre de chiffres de début à supprimer. Par exemple, entrez **1** pour retirer le signe + au début du numéro.
    - **Chiffres à ajouter** : (Facultatif) Précisez les chiffres à ajouter aux numéros traduits. Par exemple, entrez **011** si vous souhaitez ajouter 011 aux numéros traduits au moment d’appliquer la règle.
    
    Les valeurs que vous entrez dans ces champs sont reflétées dans le modèle **à mettre** en correspondance et dans les **champs** de règle de traduction. Par exemple, si vous spécifiez les valeurs de l’exemple précédent, l’expression régulière résultante dans le champ **Pattern to matc** h est :
    
    **^\+(\d {9} \d+)$** 

    Le champ **Règle de traduction** spécifie un modèle pour le format des numéros traduits. Ce modèle comprend deux parties :
    - Une valeur (par exemple, **$1**) qui représente le nombre de chiffres dans le modèle correspondant.
    - (Facultatif) Une valeur que vous pouvez ajouter par simple saisie dans le champ **Chiffres à ajouter**.

    Si vous utilisez les valeurs de l’exemple précédent, **011$1** apparaît dans le champ **Règle de traduction**.
    
    Lorsque cette règle de traduction est appliquée, +441235551010 devient 011441235551010.
7. Cliquez sur **OK** pour enregistrer la règle de traduction.
8. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
9. Dans la page **Configuration de la** trunk n, cliquez sur **Valider,** puis sur **Valider tout.** 

> [!Note]
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier les modifications en attente de la configuration du routage des voix.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) 

### <a name="create-or-modify-a-translation-rule-manually"></a>Créer ou modifier une règle de traduction manuellement

Effectuez cette procédure si vous voulez définir une règle de traduction en écrivant une expression régulière pour le modèle correspondant et la règle de traduction. 

**Pour définir une règle de traduction manuellement**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Déléguer les autorisations de configuration.](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions)
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Pour commencer la définition d’une [](GET LINK AFTER MIGRATION)règle de traduction, suivez les étapes de configuration d’une trunk avec déviation du média jusqu’à l’étape 10 ou configurez une trunk [sans](GET LINK AFTER MIGRATION) contournement de média à l’étape 9.
4. Dans le champ **Nom** dans la page **Nouvelle règle de traduction** ou **Modifier la règle de traduction**, tapez un nom décrivant le modèle de numéro en cours de traduction.
5. (Facultatif) Dans **Description**, tapez une description de la règle de traduction ; par exemple, la numérotation longue distance internationale **des États-Unis.**
6. Cliquez sur **Modifier** au bas de la section **Créer une règle de traduction**.
7. Entrez les entrées suivantes dans Tapez **une expression régulière**:
    - Dans **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire.
    - Dans **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits.

    Par exemple, si vous entrez **^ \+ (\d {9} \d+)$** dans Suivre ce modèle et  **011$1 dans** la règle de traduction, la règle traduit +441235551010 en 011441235551010. 
8. Cliquez sur **OK** pour enregistrer la règle de traduction.
9. Cliquez sur **OK** pour enregistrer la configuration de la jonction.
10. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

> [!Note] 
> Chaque fois que vous créez ou modifiez une règle de traduction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier les modifications en attente de la configuration du routage des voix.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration)