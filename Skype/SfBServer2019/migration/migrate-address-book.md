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
ms.localizationpriority: medium
description: 'En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes post-migration si vous avez personnalisé les étapes suivantes dans votre environnement hérité :'
ms.openlocfilehash: 0ef965ef67393604e257049681a64ffb3c5b8fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599719"
---
# <a name="migrate-address-book"></a>Migration du carnet d’adresses

En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes post-migration si vous avez personnalisé les étapes suivantes dans votre environnement hérité : 

- personnaliser les règles de normalisation du carnet d’adresses ;

- remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**. 


 **Règles de normalisation de carnet d’adresses**

Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool pilote. Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses. Les règles de normalisation par défaut Skype Entreprise Server 2019 sont les mêmes que pour l’installation héritée. Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.

> [!NOTE]
> Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation de carnet d’adresses, vous devez appliquer la procédure de cette rubrique pour pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou des droits équivalents. 

 **Valeur False affectée à UseNormalizationRules**

Si vous définissez la valeur de **UseNormalizationRules** sur False afin que les utilisateurs peuvent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans qu’Skype Entreprise Server 2019 applique des règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur True. Suivez la procédure décrite plus loin dans cette section pour affecter la valeur True à ces paramètres. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer des règles de normalisation de carnet d’adresses personnalisées

1. Recherchez le fichier Company_Phone_Number_Normalization_Rules.txt à la racine du dossier partagé du carnet d’adresses et copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool pilote Skype Entreprise Server 2019.

    > [!NOTE]
    > Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS. Le chemin **d’accès est $installedDriveLetter:\Program Files\Microsoft Skype Entreprise Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Ce fichier peut être copié  et renommé commeCompany_Phone_Number_Normalization_Rules.txtrépertoire racine du dossier partagé du carnet d’adresses. Par exemple, le carnet d’adresses partagé dans **$serverX**, le chemin d’accès sera similaire à : **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Ouvrez le fichier Company_Phone_Number_Normalization_Rules.txt dans un éditeur de texte, tel que le Bloc-notes.

3. Certains types d’entrées ne fonctionneront pas correctement Skype Entreprise Server 2019. Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.

    Les chaînes qui comportent des espaces ou des signes de ponctuation provoquent l’échec des règles de normalisation car ces caractères sont supprimés de la chaîne fournie comme entrée aux règles de normalisation. Si vous avez des chaînes qui comportent des espaces ou des signes de ponctuation obligatoires, vous devez modifier ces chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Microsoft Skype Entreprise Server 2019,** puis sur Skype Entreprise Server **Management Shell**.

2. Effectuez l'une des opérations suivantes :

   - Si votre déploiement inclut uniquement Skype Entreprise Server 2019, exécutez l’cmdlet suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur True : 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Si votre déploiement comprend une combinaison de Skype Entreprise Server 2019 et d’une installation héritée, exécutez l’cmdlet suivante et affectez-la à chaque pool Skype Entreprise Server 2019 de la topologie :

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendez que la réplication du magasin central de gestion se produise sur tous les pools.

4. Modifiez le fichier des règles de normalisation des numéros de téléphone, « Company_Phone_Number_Normalization_Rules.txt », afin que votre déploiement efface le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Skype Entreprise Server 2019. Si ce fichier n’est pas présent, créez un fichier vide nommé « Company_Phone_Number_Normalization_Rules.txt ».

5. Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.

6. Exécutez l’cmdlet suivante sur chaque pool Skype Entreprise Server 2019 dans votre déploiement :

   ```PowerShell
   Update-CsAddressBook
   ```


