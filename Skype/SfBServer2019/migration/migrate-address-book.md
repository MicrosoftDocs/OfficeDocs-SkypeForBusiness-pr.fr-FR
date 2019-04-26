---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes postérieures à la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité :'
ms.openlocfilehash: 728ae97270cd8451178c6ef962f05e0351118119
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238423"
---
# <a name="migrate-address-book"></a>Migrer le carnet d’adresses

En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes postérieures à la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité : 

- Personnaliser les règles de normalisation du carnet d’adresses.

- Modifié la valeur par défaut pour le paramètre **UseNormalizationRules** sur False. 


 **Règles de normalisation de carnet d’adresses**

Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool pilote. Si vous n’avez pas personnalisées des règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses. Les règles de normalisation par défaut pour Skype pour Business Server 2019 sont les mêmes que les règles par défaut pour l’installation héritée. Suivez la procédure plus loin dans cette section pour migrer les règles de normalisation personnalisé.

> [!NOTE]
> Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure de cette rubrique avant de pouvoir utiliser le contrôle d’appel distant. La procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou droits équivalents. 

 **UseNormalizationRules a la valeur False**

Si vous définissez la valeur de **UseNormalizationRules** sur False afin que les utilisateurs peuvent utiliser des numéros de téléphone qu’ils sont définis dans les Services de domaine Active Directory sans avoir Skype pour Business Server 2019 appliquer les règles de normalisation, vous devez définir la ** UseNormalizationRules** et paramètres **IgnoreGenericRules** sur True. Suivez la procédure plus loin dans cette section pour définir ces paramètres sur True. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer le carnet d’adresses personnalisé des règles de normalisation

1. Recherchez le fichier Company_Phone_Number_Normalization_Rules.txt à la racine du dossier partagé de carnet d’adresses et copiez-le à la racine du dossier partagé du carnet d’adresses dans votre Skype pour le pool pilote Business Server 2019.

    > [!NOTE]
    > Les exemples de règles de normalisation du carnet d’adresses ont été installés dans votre répertoire de fichier de composant WebPart ABS. Est le chemin d’accès **$installedDriveLetter : \Program Files\Microsoft Skype pour Sample_Company_Phone_Number_Normalization_Rules.txt, qui du carnet de Files\Files\ Business Server 2019\Web Components\Address**. Ce fichier peut être copié et renommé en tant que **fichier Company_Phone_Number_Normalization_Rules.txt** au répertoire racine de l’adresse téléchargeable du dossier partagé. Par exemple, le carnet d’adresses partagé dans **$serverX**, le chemin d’accès sera similaire à : ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Utilisez un éditeur de texte, tel que le bloc-notes, ouvrez le fichier Company_Phone_Number_Normalization_Rules.txt.

3. Certains types d’entrées de fonctionnera pas correctement dans Skype pour Business Server 2019. Examinez le fichier pour les types d’entrées décrites dans cette étape, les modifier si nécessaire et enregistrez les modifications dans le dossier partagé de carnet d’adresses dans votre pool pilote.

    Chaînes qui sont requis règles de normalisation cause espace ni ponctuation car ces caractères sont supprimés en dehors de la chaîne qui est entrée dans les règles de normalisation. Si vous avez des chaînes qui contiennent des espaces requis ou la ponctuation, vous devez modifier les chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour définir la valeur true UseNormalizationRules et IgnoreGenericRules

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.

2. Effectuez l’une des actions suivantes :

   - Si votre déploiement comprend uniquement Skype pour Business Server 2019, exécutez la cmdlet suivante au niveau global pour modifier les valeurs des **paramètres UseNormalizationRules** et **IgnoreGenericRules** sur True : 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si votre déploiement comprend une combinaison de Skype pour Business Server 2019 et une installation héritée, exécutez la cmdlet suivante et l’affecter à chaque Skype pour Business Server 2019 pool dans la topologie :

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendez que la réplication du magasin Central de gestion se produise sur tous les pools.

4. Modifiez le fichier de règles de normalisation téléphonique, « Company_Phone_Number_Normalization_Rules.txt » pour votre déploiement effacer le contenu. Le fichier est enregistré sur le partage de fichiers de chaque Skype pour Business Server 2019 pool. Si le fichier n’est pas présent, puis créez un fichier vide nommé « Company_Phone_Number_Normalization_Rules.txt ».

5. Attendez quelques minutes pour tous les pools frontaux lire les nouveaux fichiers.

6. Exécutez l’applet de commande suivante sur chaque Skype pour le pool d’entreprise Server 2019 dans votre déploiement :

   ```
   Update-CsAddressBook
   ```


