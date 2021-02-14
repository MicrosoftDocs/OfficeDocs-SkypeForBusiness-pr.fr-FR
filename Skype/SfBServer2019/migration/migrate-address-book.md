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
description: 'En règle générale, le carnet d’adresses est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes post-migration si vous avez personnalisé les étapes suivantes dans votre environnement hérité :'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752836"
---
# <a name="migrate-address-book"></a><span data-ttu-id="1001d-104">Migration du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="1001d-104">Migrate Address Book</span></span>

<span data-ttu-id="1001d-105">En règle générale, le carnet d’adresses est migré avec le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="1001d-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="1001d-106">Toutefois, vous devrez peut-être effectuer certaines étapes post-migration si vous avez personnalisé les étapes suivantes dans votre environnement hérité :</span><span class="sxs-lookup"><span data-stu-id="1001d-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="1001d-107">personnaliser les règles de normalisation du carnet d’adresses ;</span><span class="sxs-lookup"><span data-stu-id="1001d-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="1001d-108">remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**.</span><span class="sxs-lookup"><span data-stu-id="1001d-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="1001d-109">**Règles de normalisation de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="1001d-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="1001d-110">Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="1001d-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="1001d-111">Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="1001d-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="1001d-112">Les règles de normalisation par défaut pour Skype Entreprise Server 2019 sont les mêmes que pour l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="1001d-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="1001d-113">Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.</span><span class="sxs-lookup"><span data-stu-id="1001d-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="1001d-p104">Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation de carnet d’adresses, vous devez appliquer la procédure de cette rubrique pour pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="1001d-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="1001d-116">**Valeur False affectée à UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="1001d-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="1001d-117">Si vous définissez la valeur de **UseNormalizationRules** sur False afin que les utilisateurs peuvent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans que Skype Entreprise Server 2019 applique des règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur True.</span><span class="sxs-lookup"><span data-stu-id="1001d-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="1001d-118">Suivez la procédure décrite plus loin dans cette section pour affecter la valeur True à ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="1001d-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="1001d-119">Pour migrer des règles de normalisation de carnet d’adresses personnalisées</span><span class="sxs-lookup"><span data-stu-id="1001d-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="1001d-120">Recherchez le fichier Company_Phone_Number_Normalization_Rules.txt à la racine du dossier partagé du carnet d’adresses et copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool pilote Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1001d-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1001d-121">Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS.</span><span class="sxs-lookup"><span data-stu-id="1001d-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="1001d-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="1001d-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="1001d-123">Ce fichier peut être copié  et renommé commeCompany_Phone_Number_Normalization_Rules.txtrépertoire racine du dossier partagé du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="1001d-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="1001d-124">Par exemple, le carnet d’adresses partagé dans **$serverX**, le chemin d’accès sera similaire à : **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span><span class="sxs-lookup"><span data-stu-id="1001d-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="1001d-125">Ouvrez le fichier Company_Phone_Number_Normalization_Rules.txt dans un éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="1001d-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="1001d-126">Certains types d’entrées ne fonctionneront pas correctement dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1001d-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="1001d-127">Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="1001d-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="1001d-p108">Les chaînes qui comportent des espaces ou des signes de ponctuation provoquent l’échec des règles de normalisation car ces caractères sont supprimés de la chaîne fournie comme entrée aux règles de normalisation. Si vous avez des chaînes qui comportent des espaces ou des signes de ponctuation obligatoires, vous devez modifier ces chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="1001d-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="1001d-131">La chaîne suivante ne provoque pas l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="1001d-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="1001d-132">Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules</span><span class="sxs-lookup"><span data-stu-id="1001d-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="1001d-133">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1001d-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1001d-134">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1001d-134">Do one of the following:</span></span>

   - <span data-ttu-id="1001d-135">Si votre déploiement inclut uniquement Skype Entreprise Server 2019, exécutez l’cmdlet suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur True :</span><span class="sxs-lookup"><span data-stu-id="1001d-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="1001d-136">Si votre déploiement inclut une combinaison de Skype Entreprise Server 2019 et d’une installation héritée, exécutez l’cmdlet suivante et affectez-la à chaque pool Skype Entreprise Server 2019 dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="1001d-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="1001d-137">Attendez que la réplication du magasin central de gestion se produise sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="1001d-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="1001d-138">Modifiez le fichier des règles de normalisation des numéros de téléphone, « Company_Phone_Number_Normalization_Rules.txt », afin que votre déploiement efface le contenu.</span><span class="sxs-lookup"><span data-stu-id="1001d-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="1001d-139">Le fichier se trouve sur le partage de fichiers de chaque pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1001d-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1001d-140">Si ce fichier n’est pas présent, créez un fichier vide nommé « Company_Phone_Number_Normalization_Rules.txt ».</span><span class="sxs-lookup"><span data-stu-id="1001d-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="1001d-141">Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="1001d-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="1001d-142">Exécutez l’cmdlet suivante sur chaque pool Skype Entreprise Server 2019 de votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="1001d-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


