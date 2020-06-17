---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes de post-migration si vous avez personnalisé les éléments suivants dans votre environnement hérité :'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752836"
---
# <a name="migrate-address-book"></a>Faire migrer le carnet d’adresses

En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes de post-migration si vous avez personnalisé les éléments suivants dans votre environnement hérité : 

- personnaliser les règles de normalisation du carnet d’adresses ;

- remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**. 


 **Règles de normalisation de carnet d’adresses**

Si vous avez personnalisé des règles de normalisation de carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool pilote. Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses. Les règles de normalisation par défaut pour Skype entreprise Server 2019 sont les mêmes que celles par défaut pour l’installation héritée. Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.

> [!NOTE]
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights. 

 **Valeur False affectée à UseNormalizationRules**

Si vous définissez la valeur de **UseNormalizationRules** sur false afin que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans avoir Skype for Business Server 2019 appliquer des règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur true. Suivez la procédure décrite plus loin dans cette section pour affecter la valeur True à ces paramètres. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer des règles de normalisation de carnet d’adresses personnalisées

1. Recherchez le fichier Company_Phone_Number_Normalization_Rules.txt à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool pilote Skype entreprise Server 2019.

    > [!NOTE]
    > Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS. Le chemin d’accès est **$installedDriveLetter : \Program Files\Microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Ce fichier peut être copié et renommé en tant que **Company_Phone_Number_Normalization_Rules.txt** dans le répertoire racine du dossier partagé carnet d’adresses. Par exemple, le carnet d’adresses partagé dans **$serverX**, le chemin d’accès est similaire à : ** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Ouvrez le fichier Company_Phone_Number_Normalization_Rules.txt dans un éditeur de texte, tel que le Bloc-notes.

3. Certains types d’entrées ne fonctionnent pas correctement dans Skype entreprise Server 2019. Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.

    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules

1. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.

2. Effectuez l’une des opérations suivantes :

   - Si votre déploiement inclut uniquement Skype entreprise Server 2019, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true : 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si votre déploiement inclut une combinaison de Skype entreprise Server 2019 et d’une installation héritée, exécutez l’applet de commande suivante et affectez-la à chaque pool de Skype entreprise Server 2019 dans la topologie :

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendez que la réplication du magasin central de gestion se produise sur tous les pools.

4. Modifiez le fichier des règles de normalisation des numéros de téléphone, « Company_Phone_Number_Normalization_Rules.txt », afin que votre déploiement efface le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Skype entreprise Server 2019. Si ce fichier n’est pas présent, créez un fichier vide nommé « Company_Phone_Number_Normalization_Rules.txt ».

5. Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.

6. Exécutez l’applet de commande suivante sur chaque pool Skype entreprise Server 2019 de votre déploiement :

   ```PowerShell
   Update-CsAddressBook
   ```


