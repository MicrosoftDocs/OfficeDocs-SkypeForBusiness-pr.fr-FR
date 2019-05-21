---
title: Définition de règles de normalisation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les règles de normalisation de Skype entreprise Server utilisent des expressions régulières du .NET Framework pour convertir les numéros de téléphone numérotés au format E. 164. en d’autres termes, les règles de normalisation emportent le numéro de téléphone composé par un utilisateur et convertissent ce numéro au format utilisé en interne par Skype entreprise Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274981"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Définition de règles de normalisation dans Skype entreprise Server

Les règles de normalisation de Skype entreprise Server utilisent des expressions régulières du .NET Framework pour convertir les numéros de téléphone numérotés au format E. 164. en d’autres termes, les règles de normalisation emportent le numéro de téléphone composé par un utilisateur et convertissent ce numéro au format utilisé en interne par Skype entreprise Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.

Pour plus d’informations sur les règles de normalisation, voir [plans de numérotation et règles de normalisation](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Pour plus d’informations sur la façon d’écrire des expressions régulières, voir [expressions régulières .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Pour définir ou modifier une règle de normalisation, vous pouvez utiliser l’une des méthodes suivantes:
- [Utiliser l’outil **créer une règle de normalisation** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laisser le panneau de configuration de Skype entreprise Server générer le modèle de correspondance et la règle de traduction correspondants Pour vous.
- [Rédigez manuellement des expressions régulières](#create-or-modify-a-normalization-rule-manually) pour définir les modèles correspondants et les règles de traduction. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Création ou modification d’une règle de normalisation à l’aide de l’onglet créer une règle de normalisation

Pour créer ou modifier une règle de normalisation dans le panneau de configuration Skype entreprise Server, procédez comme suit. 

**Pour définir une règle à l’aide de la création d’une règle de normalisation**

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez [autorisations de configuration de délégué](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype pour les entreprises, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Facultatif Suivez les étapes de la rubrique [créer un plan de numérotation](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) via l’étape 11 ou [modifier un plan de numérotation](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) via l’étape 10. 
4. Dans la section **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom décrivant le modèle de numéro en cours de normalisation dans le champ **Nom** (par exemple, **5DigitExtension**).
5. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, entrez les valeurs dans les champs suivants :
    - **Premiers chiffres**: (facultatif) Spécifiez les premiers chiffres des numéros numérotés que vous voulez associer au modèle. Par exemple, tapez **425** si vous souhaitez que le modèle suive les numéros composés commençant par 425.
    - **Longueur**: spécifiez le nombre de chiffres dans le modèle correspondant, puis indiquez si vous souhaitez que le modèle corresponde exactement à cette longueur, qu’il corresponde à des numéros qui utilisent au moins cette longueur ou que les numéros numérotés de n’importe quelle longueur.
    - **Chiffres à supprimer**: (facultatif) Spécifiez le nombre de chiffres de départ à supprimer des numéros numérotés que vous voulez associer au modèle.
    - **Chiffres à ajouter**: (facultatif) Spécifiez les chiffres à ajouter aux numéros numérotés à utiliser pour le modèle.
    
    Les valeurs que vous entrez dans ces champs s’affichent dans **Modèle à suivre** et **Règle de conversion**. Par exemple, si vous laissez **les chiffres de début** vides, tapez **7** dans le champ **longueur** , sélectionnez **exactement**et spécifiez **0** dans les **chiffres à supprimer**, l’expression régulière résultante dans le **modèle à faire correspondre** est la suivante:

    **^ (\d{7}) $**

7. Dans **Règle de conversion**, spécifiez comme suit le modèle du format des numéros de téléphone E.164 convertis :
    - Une valeur qui représente le nombre de chiffres spécifiés dans le modèle à suivre. Par exemple, si le modèle correspondant est **^ (\d{7}) $**, $1 dans la règle de traduction représente les numéros numérotés à 7 chiffres.
    - (Facultatif) Entrez une valeur dans le champ **Chiffres à ajouter** pour spécifier les chiffres à ajouter au numéro converti (par exemple, **+1425**).
    
    Par exemple, si le modèle **à faire correspondre** contient **^{7}(\d) $** en tant que modèle pour les numéros numérotés et la **règle de traduction** contenant **+ 1425 $1** comme modèle pour les numéros de téléphone E. 164, la règle normalise 5550100 à + 14255550100.

8. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.
    > [!Note] 
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez [tester le routage vocal](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**. 
    > [!Note]
    > Lorsque vous créez ou modifiez une règle de normalisation, vous devez exécuter la commande Valider tout pour publier la modification de configuration. Pour plus d’informations, reportez-vous [à la section publier les modifications en attente dans la configuration de routage](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Création ou modification manuelle d’une règle de normalisation

Suivez les étapes ci-dessous si vous voulez créer ou modifier une règle de normalisation manuellement.

**Pour définir une règle de normalisation manuellement**

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez [autorisations de configuration de délégué](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype pour les entreprises, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Facultatif Suivez les étapes de la rubrique [créer un plan de numérotation](GET LINK AFTER MIGRATION) via l’étape 11 ou [modifier un plan de numérotation](GET LINK AFTER MIGRATION) via l’étape 10.  
4. Dans **Nouvelle règle de normalisation** ou **Modifier une règle de normalisation**, entrez un nom qui décrive le modèle de numéro à normaliser dans **Nom** (par exemple, nommez la règle de normalisation **5DigitExtension**).
5. (Facultatif) Dans **Description**, entrez une description de la règle de normalisation (par exemple, « Traduit les postes à 5 chiffres »).
6. Dans **Créer une règle de normalisation**, cliquez sur **Modifier**.
7. Entrez ce qui suit dans Taper une expression régulière :
    - Dans **Suivre ce modèle**, indiquez le modèle que vous souhaitez utiliser pour le numéro de téléphone composé.
    - Dans **Règle de conversion**, précisez un modèle pour le format des numéros de téléphone E.164 convertis.

    Par exemple, si vous entrez **^ (\d{7}) $** dans **respecter ce modèle** et **+ 1425 $1** dans la **règle de traduction**, la règle normalise les 5550100 à + 14255550100.

8. (Facultatif) Si la règle de normalisation est convertie en un numéro de téléphone interne à votre entreprise, sélectionnez **Poste interne**.
9. (Facultatif) Entrez un numéro pour tester la règle de normalisation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!Note]
    > Vous pouvez enregistrer une règle de normalisation n’ayant pas encore passé le test afin de la reconfigurer ultérieurement. Pour plus d’informations, consultez [tester le routage vocal](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Cliquez sur **OK** pour enregistrer la règle de normalisation.
11. Cliquez sur **OK** pour enregistrer le plan de numérotation.
12. Sur la page **plan** de numérotation, cliquez sur **commi**t puis sur **valider tout**. 
