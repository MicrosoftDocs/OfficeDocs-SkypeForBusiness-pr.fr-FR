---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En règle générale, le carnet d’adresses est déplacé en même temps que le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité:'
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307118"
---
# <a name="migrate-address-book"></a>Migrer le carnet d’adresses

En règle générale, le carnet d’adresses est déplacé en même temps que le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité: 

- Personnalisé les règles de normalisation du carnet d’adresses.

- La valeur par défaut du paramètre **UseNormalizationRules** a été remplacée par false. 


 **Règles de normalisation du carnet d’adresses**

Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool de pilotes. Si vous n’avez pas personnalisé les règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses. Les règles de normalisation par défaut de Skype entreprise Server 2019 sont les mêmes que celles par défaut de l’installation héritée. Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.

> [!NOTE]
> Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure décrite dans cette rubrique avant de pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou aux droits équivalents. 

 **UseNormalizationRules défini sur false**

Si vous définissez la valeur de **UseNormalizationRules** sur false pour que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les **services de domaine Active Directory (AD FS) sans que Skype entreprise Server 2019 applique des règles de normalisation, vous devez définir Paramètres UseNormalizationRules** et **IgnoreGenericRules** sur true. Suivez la procédure décrite plus loin dans cette section pour définir ces paramètres sur true. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer des règles de normalisation personnalisées du carnet d’adresses

1. Recherchez le fichier Company_Phone_Number_Normalization_Rules. txt à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool de pilotes Skype entreprise Server 2019.

    > [!NOTE]
    > Les règles de normalisation de votre carnet d’adresses sont installées dans votre répertoire de fichiers de composants Web ABS. Le chemin d’accès est **$installedDriveLetter: \Program Files\Microsoft Skype entreprise Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**. Ce fichier peut être copié et renommé **Company_Phone_Number_Normalization_Rules. txt** dans le répertoire racine du dossier partagé du carnet d’adresses. Par exemple, dans le carnet d’adresses partagé dans **$serverX**, le chemin d’accès est semblable à ce qui suit: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Utilisez un éditeur de texte tel que le bloc-notes pour ouvrir le fichier Company_Phone_Number_Normalization_Rules. txt.

3. Certains types d’entrée ne fonctionnent pas correctement dans Skype entreprise Server 2019. Parcourez le fichier pour obtenir les types d’entrée décrits dans cette étape, modifiez-les comme vous le souhaitez et enregistrez les modifications apportées au dossier partagé du carnet d’adresses dans votre pool de pilotes.

    Les chaînes qui comprennent des espaces blancs ou des signes de ponctuation peuvent entraîner l’échec des règles de normalisation, car ces caractères sont supprimés de la chaîne qui est en entrée dans les règles de normalisation. Si vous avez des chaînes qui incluent des espaces blancs ou des signes de ponctuation requis, vous devez modifier les chaînes. Par exemple, la chaîne suivante entraînera l’échec de la règle de normalisation:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La chaîne suivante n’entraînera pas l’échec de la règle de normalisation:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour définir UseNormalizationRules et IgnoreGenericRules sur true

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Effectuez l’une des actions suivantes :

   - Si votre déploiement inclut uniquement Skype entreprise Server 2019, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si votre déploiement inclut une combinaison de Skype entreprise Server 2019 et une installation héritée, exécutez l’applet de commande suivante et affectez-la à chaque pool 2019 Skype entreprise Server dans la topologie:

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendez la fin de la réplication du magasin de gestion centrale sur tous les pools.

4. Modifiez le fichier de règles de normalisation du téléphone «Company_Phone_Number_Normalization_Rules. txt» pour que votre déploiement efface le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Skype entreprise Server 2019. Si le fichier n’est pas présent, créez-en un dans le dossier «Company_Phone_Number_Normalization_Rules. txt».

5. Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.

6. Exécutez l’applet de commande suivante sur chaque pool 2019 de Skype entreprise Server dans votre déploiement:

   ```
   Update-CsAddressBook
   ```


