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
# <a name="migrate-address-book"></a><span data-ttu-id="64f59-104">Migrer le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="64f59-104">Migrate Address Book</span></span>

<span data-ttu-id="64f59-105">En règle générale, le carnet d’adresses est migré avec le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="64f59-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="64f59-106">Toutefois, vous devrez peut-être effectuer certaines étapes postérieures à la migration si vous avez personnalisé les éléments suivants dans votre environnement hérité :</span><span class="sxs-lookup"><span data-stu-id="64f59-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="64f59-107">Personnaliser les règles de normalisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="64f59-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="64f59-108">Modifié la valeur par défaut pour le paramètre **UseNormalizationRules** sur False.</span><span class="sxs-lookup"><span data-stu-id="64f59-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="64f59-109">**Règles de normalisation de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="64f59-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="64f59-110">Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement hérité, vous devez migrer les règles personnalisées vers votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="64f59-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="64f59-111">Si vous n’avez pas personnalisées des règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="64f59-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="64f59-112">Les règles de normalisation par défaut pour Skype pour Business Server 2019 sont les mêmes que les règles par défaut pour l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="64f59-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="64f59-113">Suivez la procédure plus loin dans cette section pour migrer les règles de normalisation personnalisé.</span><span class="sxs-lookup"><span data-stu-id="64f59-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="64f59-114">Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure de cette rubrique avant de pouvoir utiliser le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="64f59-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="64f59-115">La procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="64f59-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="64f59-116">**UseNormalizationRules a la valeur False**</span><span class="sxs-lookup"><span data-stu-id="64f59-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="64f59-117">Si vous définissez la valeur de **UseNormalizationRules** sur False afin que les utilisateurs peuvent utiliser des numéros de téléphone qu’ils sont définis dans les Services de domaine Active Directory sans avoir Skype pour Business Server 2019 appliquer les règles de normalisation, vous devez définir la \*\* UseNormalizationRules\*\* et paramètres **IgnoreGenericRules** sur True.</span><span class="sxs-lookup"><span data-stu-id="64f59-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="64f59-118">Suivez la procédure plus loin dans cette section pour définir ces paramètres sur True.</span><span class="sxs-lookup"><span data-stu-id="64f59-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="64f59-119">Pour migrer le carnet d’adresses personnalisé des règles de normalisation</span><span class="sxs-lookup"><span data-stu-id="64f59-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="64f59-120">Recherchez le fichier Company_Phone_Number_Normalization_Rules.txt à la racine du dossier partagé de carnet d’adresses et copiez-le à la racine du dossier partagé du carnet d’adresses dans votre Skype pour le pool pilote Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64f59-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64f59-121">Les exemples de règles de normalisation du carnet d’adresses ont été installés dans votre répertoire de fichier de composant WebPart ABS.</span><span class="sxs-lookup"><span data-stu-id="64f59-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="64f59-122">Est le chemin d’accès **$installedDriveLetter : \Program Files\Microsoft Skype pour Sample_Company_Phone_Number_Normalization_Rules.txt, qui du carnet de Files\Files\ Business Server 2019\Web Components\Address**.</span><span class="sxs-lookup"><span data-stu-id="64f59-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="64f59-123">Ce fichier peut être copié et renommé en tant que **fichier Company_Phone_Number_Normalization_Rules.txt** au répertoire racine de l’adresse téléchargeable du dossier partagé.</span><span class="sxs-lookup"><span data-stu-id="64f59-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="64f59-124">Par exemple, le carnet d’adresses partagé dans **$serverX**, le chemin d’accès sera similaire à : \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="64f59-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="64f59-125">Utilisez un éditeur de texte, tel que le bloc-notes, ouvrez le fichier Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="64f59-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="64f59-126">Certains types d’entrées de fonctionnera pas correctement dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64f59-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="64f59-127">Examinez le fichier pour les types d’entrées décrites dans cette étape, les modifier si nécessaire et enregistrez les modifications dans le dossier partagé de carnet d’adresses dans votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="64f59-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="64f59-128">Chaînes qui sont requis règles de normalisation cause espace ni ponctuation car ces caractères sont supprimés en dehors de la chaîne qui est entrée dans les règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="64f59-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="64f59-129">Si vous avez des chaînes qui contiennent des espaces requis ou la ponctuation, vous devez modifier les chaînes.</span><span class="sxs-lookup"><span data-stu-id="64f59-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="64f59-130">Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="64f59-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="64f59-131">La chaîne suivante ne provoque pas l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="64f59-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="64f59-132">Pour définir la valeur true UseNormalizationRules et IgnoreGenericRules</span><span class="sxs-lookup"><span data-stu-id="64f59-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="64f59-133">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="64f59-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="64f59-134">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="64f59-134">Do one of the following:</span></span>

   - <span data-ttu-id="64f59-135">Si votre déploiement comprend uniquement Skype pour Business Server 2019, exécutez la cmdlet suivante au niveau global pour modifier les valeurs des **paramètres UseNormalizationRules** et **IgnoreGenericRules** sur True :</span><span class="sxs-lookup"><span data-stu-id="64f59-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="64f59-136">Si votre déploiement comprend une combinaison de Skype pour Business Server 2019 et une installation héritée, exécutez la cmdlet suivante et l’affecter à chaque Skype pour Business Server 2019 pool dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="64f59-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="64f59-137">Attendez que la réplication du magasin Central de gestion se produise sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="64f59-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="64f59-138">Modifiez le fichier de règles de normalisation téléphonique, « Company_Phone_Number_Normalization_Rules.txt » pour votre déploiement effacer le contenu.</span><span class="sxs-lookup"><span data-stu-id="64f59-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="64f59-139">Le fichier est enregistré sur le partage de fichiers de chaque Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="64f59-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="64f59-140">Si le fichier n’est pas présent, puis créez un fichier vide nommé « Company_Phone_Number_Normalization_Rules.txt ».</span><span class="sxs-lookup"><span data-stu-id="64f59-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="64f59-141">Attendez quelques minutes pour tous les pools frontaux lire les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="64f59-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="64f59-142">Exécutez l’applet de commande suivante sur chaque Skype pour le pool d’entreprise Server 2019 dans votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="64f59-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


