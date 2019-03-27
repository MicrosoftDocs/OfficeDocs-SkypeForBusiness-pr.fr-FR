---
title: Définition des règles de normalisation dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour les règles de normalisation Business Server utiliser des expressions régulières .NET Framework pour traduire des numéros de téléphone composé au format E.164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertir ce numéro au format utilisé en interne par Skype pour Business Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.
ms.openlocfilehash: 8e32ac485763c626d7d4347bb194fb4c4f3dba44
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882473"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Définition des règles de normalisation dans Skype pour Business Server

Skype pour les règles de normalisation Business Server utiliser des expressions régulières .NET Framework pour traduire des numéros de téléphone composé au format E.164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertir ce numéro au format utilisé en interne par Skype pour Business Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.

Pour plus d’informations sur les règles de normalisation, voir [plans de numérotation et règles de normalisation](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Pour plus d’informations sur l’écriture d’expressions régulières, voir [Expressions régulières .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Vous pouvez utiliser une des méthodes suivantes pour définir ou modifier une règle de normalisation :
- [Utilisez l’outil **créer une règle de normalisation** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) pour spécifier des valeurs pour les chiffres, longueur, chiffres à supprimer et chiffres à ajouter, puis laissez Skype pour le panneau de configuration serveur Business générer la règle correspondante correspondante pattern et translation départ Pour vous.
- [Écriture d’expressions régulières manuellement](#create-or-modify-a-normalization-rule-manually) pour définir la règle de correspondance pattern et translation. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Créer ou modifier une règle de normalisation à l’aide de créer une règle de normalisation

Effectuez les étapes suivantes si vous souhaitez créer ou modifier une règle de normalisation dans Skype pour le panneau de configuration serveur Business. 

**Pour définir une règle à l’aide de créer une règle de normalisation**

1. Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez la rubrique [déléguer des autorisations d’installation](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour Business le panneau de configuration, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. (Facultatif) Suivez les étapes dans [créer un plan de numérotation](GET LINK AFTER MIGRATION) à l’étape 11 ou de [Modifier un plan de numérotation](GET LINK AFTER MIGRATION) jusqu'à l’étape 10. 
4. Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **5DigitExtension**).
5. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    - **Chiffres de début**: (facultatif) Indiquez les chiffres à gauche de numéros composés que le modèle doit suivre. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    - **Longueur**: spécifiez le nombre de chiffres dans la mise en correspondance de motif et indiquez si vous souhaitez le modèle doit correspondre exactement à cette longueur, correspondance des numéros qui se trouvent au moins cette longueur composés ou correspondance composé des numéros de n’importe quelle longueur.
    - **Chiffres à supprimer**: (facultatif) Indiquez le nombre de chiffres à supprimer des numéros composés de début vous souhaitez que le modèle doit suivre.
    - **Chiffres à ajouter**: (facultatif) Indiquez les chiffres à ajouter pour composer les numéros vous souhaitez que le modèle doit suivre.
    
    Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez **les chiffres de début** vide, type **7** dans le champ **durée** sélectionnez **exactement**, spécifiez la **valeur 0** dans les **chiffres à supprimer**, est l’expression régulière qui en résulte dans le **modèle à associer** :

    **^(\d{7})$**

7. Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :
    - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est **^(\d{7})$**, $1 dans la règle de traduction représente les numéros composés à 7 chiffres.
    - (Facultatif) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro converti (par exemple, **+1425**).
    
    Par exemple, si le **modèle à faire correspondre** contient **^(\d{7})$** , qui contient le modèle pour la **règle de traduction** et les numéros composés **+ 1425$ 1** comme modèle pour les numéros de téléphone E.164, la règle numéro 5550100 + 14255550100.

8. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    > [!Note] 
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, voir [routage des communications vocales Test](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**. 
    > [!Note]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande Valider tout pour publier la modification de configuration. Pour plus d’informations, voir [publication en attente apportées à la configuration de routage voix](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Création ou modification manuelle d’une règle de normalisation

Effectuez les étapes suivantes si vous souhaitez créer ou modifier une règle de normalisation manuellement.

**Pour définir une règle de normalisation manuellement**

1. Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez la rubrique [déléguer des autorisations d’installation](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour Business le panneau de configuration, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. (Facultatif) Suivez les étapes dans [créer un plan de numérotation](GET LINK AFTER MIGRATION) à l’étape 11 ou de [Modifier un plan de numérotation](GET LINK AFTER MIGRATION) jusqu'à l’étape 10.  
4. Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom qui décrive le modèle de numéro à normaliser dans **Nom** (par exemple, nommez la règle de normalisation **5DigitExtension**).
5. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.
7. Entrez ce qui suit dans Taper une expression régulière :
    - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.

    Par exemple, si vous entrez **^(\d{7})$** dans **ce modèle de correspondance** et **+ 1425$ 1** dans la **règle de traduction**, la règle numéro 5550100 + 14255550100.

8. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!Note]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, voir [routage des communications vocales Test](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Dans la page **Plan de numérotation** , cliquez sur **Commi**, puis cliquez sur **valider tout**. 
