---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'En règle générale, le carnet d’adresses est déplacé en même temps que le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité :'
ms.openlocfilehash: 976717679a5a2f1dbdd1e2045cc5d5dfe43911e3
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888163"
---
# <a name="migrate-address-book"></a><span data-ttu-id="38d7e-104">Migrer le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="38d7e-104">Migrate Address Book</span></span>

<span data-ttu-id="38d7e-105">En règle générale, le carnet d’adresses est déplacé en même temps que le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="38d7e-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="38d7e-106">Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité :</span><span class="sxs-lookup"><span data-stu-id="38d7e-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="38d7e-107">Personnalisé les règles de normalisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="38d7e-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="38d7e-108">La valeur par défaut du paramètre **UseNormalizationRules** a été remplacée par false.</span><span class="sxs-lookup"><span data-stu-id="38d7e-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="38d7e-109">**Règles de normalisation du carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="38d7e-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="38d7e-110">Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="38d7e-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="38d7e-111">Si vous n’avez pas personnalisé les règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="38d7e-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="38d7e-112">Les règles de normalisation par défaut de Skype entreprise Server 2019 sont les mêmes que celles par défaut de l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="38d7e-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="38d7e-113">Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.</span><span class="sxs-lookup"><span data-stu-id="38d7e-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="38d7e-114">Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure décrite dans cette rubrique avant de pouvoir utiliser le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="38d7e-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="38d7e-115">Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou aux droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="38d7e-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="38d7e-116">**UseNormalizationRules défini sur false**</span><span class="sxs-lookup"><span data-stu-id="38d7e-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="38d7e-117">Si vous définissez la valeur de **UseNormalizationRules** sur false pour que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory (AD FS) sans que Skype entreprise Server 2019 applique des règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur true.</span><span class="sxs-lookup"><span data-stu-id="38d7e-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="38d7e-118">Suivez la procédure décrite plus loin dans cette section pour définir ces paramètres sur true.</span><span class="sxs-lookup"><span data-stu-id="38d7e-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="38d7e-119">Pour migrer des règles de normalisation personnalisées du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="38d7e-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="38d7e-120">Recherchez le fichier Company_Phone_Number_Normalization_Rules. txt à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool de pilotes Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="38d7e-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38d7e-121">Les règles de normalisation de votre carnet d’adresses sont installées dans votre répertoire de fichiers de composants Web ABS.</span><span class="sxs-lookup"><span data-stu-id="38d7e-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="38d7e-122">Le chemin d’accès est **$installedDriveLetter : \Program Files\Microsoft Skype entreprise Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**.</span><span class="sxs-lookup"><span data-stu-id="38d7e-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="38d7e-123">Ce fichier peut être copié et renommé en tant que **Company_Phone_Number_Normalization_Rules. txt** dans le répertoire racine du dossier partagé du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="38d7e-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="38d7e-124">Par exemple, dans le carnet d’adresses partagé dans **$serverX**, le chemin d’accès est semblable à ce qui suit : \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="38d7e-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="38d7e-125">Utilisez un éditeur de texte tel que le bloc-notes pour ouvrir le fichier Company_Phone_Number_Normalization_Rules. txt.</span><span class="sxs-lookup"><span data-stu-id="38d7e-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="38d7e-126">Certains types d’entrée ne fonctionnent pas correctement dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="38d7e-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="38d7e-127">Parcourez le fichier pour obtenir les types d’entrée décrits dans cette étape, modifiez-les comme vous le souhaitez et enregistrez les modifications apportées au dossier partagé du carnet d’adresses dans votre pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="38d7e-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="38d7e-128">Les chaînes qui comprennent des espaces blancs ou des signes de ponctuation peuvent entraîner l’échec des règles de normalisation, car ces caractères sont supprimés de la chaîne qui est en entrée dans les règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="38d7e-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="38d7e-129">Si vous avez des chaînes qui incluent des espaces blancs ou des signes de ponctuation requis, vous devez modifier les chaînes.</span><span class="sxs-lookup"><span data-stu-id="38d7e-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="38d7e-130">Par exemple, la chaîne suivante entraînera l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="38d7e-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="38d7e-131">La chaîne suivante n’entraînera pas l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="38d7e-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="38d7e-132">Pour définir UseNormalizationRules et IgnoreGenericRules sur true</span><span class="sxs-lookup"><span data-stu-id="38d7e-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="38d7e-133">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="38d7e-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="38d7e-134">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="38d7e-134">Do one of the following:</span></span>

   - <span data-ttu-id="38d7e-135">Si votre déploiement inclut uniquement Skype entreprise Server 2019, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true :</span><span class="sxs-lookup"><span data-stu-id="38d7e-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="38d7e-136">Si votre déploiement inclut une combinaison de Skype entreprise Server 2019 et une installation héritée, exécutez l’applet de commande suivante et affectez-la à chaque pool 2019 Skype entreprise Server dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="38d7e-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="38d7e-137">Attendez la fin de la réplication du magasin de gestion centrale sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="38d7e-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="38d7e-138">Modifiez le fichier de règles de normalisation du téléphone, « Company_Phone_Number_Normalization_Rules. txt », pour que votre déploiement efface le contenu.</span><span class="sxs-lookup"><span data-stu-id="38d7e-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="38d7e-139">Le fichier se trouve sur le partage de fichiers de chaque pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="38d7e-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="38d7e-140">Si le fichier n’est pas présent, créez-en un dans le dossier « Company_Phone_Number_Normalization_Rules. txt ».</span><span class="sxs-lookup"><span data-stu-id="38d7e-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="38d7e-141">Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="38d7e-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="38d7e-142">Exécutez l’applet de commande suivante sur chaque pool 2019 de Skype entreprise Server dans votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="38d7e-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


