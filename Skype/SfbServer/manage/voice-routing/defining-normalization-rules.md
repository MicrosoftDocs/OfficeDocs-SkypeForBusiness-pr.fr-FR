---
title: Définition de règles de normalisation dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Entreprise Server règles de normalisation utilisent des expressions régulières .NET Framework pour convertir les numéros de téléphone composés au format E.164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertissent ce numéro au format utilisé en interne par Skype Entreprise Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.
ms.openlocfilehash: 97e3cada0ab95cbd3a457e2c5f71b1ead9d9ce23
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398848"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Définition de règles de normalisation dans Skype Entreprise Server

Skype Entreprise Server règles de normalisation utilisent des expressions régulières .NET Framework pour convertir les numéros de téléphone composés au format E.164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertissent ce numéro au format utilisé en interne par Skype Entreprise Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.

Pour plus d’informations sur les règles de normalisation, voir [Plans de numérotation et règles de normalisation](/previous-versions/office/lync-server-2013/lync-server-2013-dial-plans-and-normalization-rules).

Pour plus d’informations sur l’écriture d’expressions [régulières, voir .NET Framework Expressions régulières](/dotnet/standard/base-types/regular-expressions).

Vous pouvez utiliser l’une des méthodes suivantes pour définir ou modifier une règle de normalisation :
- [](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) Utilisez l’outil Créer une règle de normalisation pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le Panneau de configuration Skype Entreprise Server générer le modèle correspondant et la règle de traduction pour vous.
- [Écrivez manuellement des expressions régulières pour](#create-or-modify-a-normalization-rule-manually) définir le modèle de correspondance et la règle de traduction. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Créer ou modifier une règle de normalisation à l’aide de La création d’une règle de normalisation

Pour créer ou modifier une règle de normalisation dans le Panneau de Skype Entreprise Server, vous devez effectuer les étapes suivantes. 

**Pour définir une règle à l’aide de la section Créer une règle de normalisation**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Déléguer les autorisations de configuration](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise, voir Installer et ouvrir les [outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. (Facultatif) Suivez les étapes de [création d’un plan](../../deploy/deploy-enterprise-voice/dial-plans.md#to-create-a-dial-plan) de numérotation à l’étape 11 ou de modification d’un [plan](../../deploy/deploy-enterprise-voice/dial-plans.md#to-modify-a-dial-plan) de numérotation jusqu’à l’étape 10. 
4. Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **Postes5chiffres**).
5. (Optionnel) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    - **Chiffres de début** : (Facultatif) Spécifiez les premiers chiffres des numéros composés que vous souhaitez que le modèle corresponde. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    - **Longueur** : spécifiez le nombre de chiffres dans le modèle correspondant et indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, les numéros composés qui ont au moins cette longueur ou les numéros composés de n’importe quelle longueur.
    - **Chiffres à supprimer** : (Facultatif) Spécifiez le nombre de chiffres de début à supprimer des numéros composés que vous souhaitez que le modèle corresponde.
    - **Chiffres à ajouter** : (Facultatif) Spécifiez les chiffres à ajouter aux numéros composés que vous souhaitez que le modèle corresponde.
    
    Les valeurs que vous entrez dans ces champs apparaissent dans **Modèle à suivre** et **Règle de traduction**. Par exemple,  si vous laissez les **chiffres** de début vides, tapez **7** dans le champ Longueur sélectionnez **Exactement** et spécifiez **0** dans **Chiffres** à supprimer, l’expression régulière résultante dans le modèle à mettre en correspondance est :

    **^(\d{7})$**

7. Dans **Règle de traduction**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 traduits :
    - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est **^(\d{7})$**, alors $1 dans la règle de traduction représente des numéros composés à 7 chiffres.
    - (Optionnel) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro traduit (par exemple **+1425**).
    
    Par exemple, si  le modèle à suivre contient **^(\d{7})$** comme modèle pour les numéros composés  et que la règle de traduction contient **+1425$1 comme** modèle pour les numéros de téléphone E.164, la règle normalise 5550100 à +14255550100.

8. (Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.
    > [!Note] 
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, voir [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**. 
    > [!Note]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande Valider tout pour publier la modification de configuration. Pour plus d’informations, voir [Publier les modifications en attente de la configuration du routage des voix](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Créer ou modifier manuellement une règle de normalisation

Suivez cette procédure si vous souhaitez créer ou modifier manuellement une règle de normalisation.

**Pour définir une règle de normalisation manuellement**

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Déléguer les autorisations de configuration](/previous-versions/office/lync-server-2013/lync-server-2013-delegate-setup-permissions).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise, voir Installer et ouvrir les [outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. (Facultatif) Suivez les étapes de [création d’un plan](GET LINK AFTER MIGRATION) de numérotation à l’étape 11 ou de modification d’un [plan](GET LINK AFTER MIGRATION) de numérotation jusqu’à l’étape 10.  
4. Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom qui décrive le modèle de numéro à normaliser dans **Nom** (par exemple, nommez la règle de normalisation **Poste5chiffres**).
5. (Optionnel) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.
7. Entrez ce qui suit dans Taper une expression régulière :
    - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    - Dans **Règle de traduction**, précisez un modèle pour le format des numéros de téléphone E.164 traduits.

    Par exemple, si vous entrez **^(\d{7})$** dans  Suivre ce modèle et **+1425$1** dans la règle de **traduction, la** règle normalise 5550100 à +14255550100.

8. (Optionnel) Si la règle de normalisation se traduit par un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Optionnel) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.

    > [!Note]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, voir [Test voice routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Dans la page **Plan de** numérotation, cliquez sur **Commit**, puis sur **Valider tout**.