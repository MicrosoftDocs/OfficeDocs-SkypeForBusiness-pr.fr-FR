---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="bf5a3-102">Migrer le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="bf5a3-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf5a3-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="bf5a3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="bf5a3-104">En règle générale, le carnet d’adresses de Lync Server 2010 est migré en même temps que le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="bf5a3-105">Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement Lync Server 2010 :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="bf5a3-106">Définissez la propriété WMI **PartitionbyOU** pour regrouper les entrées du carnet d’adresses par unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="bf5a3-107">Personnalisé les règles de normalisation du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="bf5a3-108">La valeur par défaut du paramètre **UseNormalizationRules** a été remplacée par false.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="bf5a3-109">**Entrées du carnet d’adresses groupé**</span><span class="sxs-lookup"><span data-stu-id="bf5a3-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="bf5a3-110">Si vous définissez la propriété WMI **PartitionbyOU** sur true pour créer des carnets d’adresses pour chaque unité d’organisation, vous devez configurer l’attribut Active Directory **msRTCSIP-GroupingId** sur les utilisateurs et les contacts si vous voulez continuer à regrouper les entrées du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="bf5a3-111">Il est possible que vous souhaitiez regrouper les entrées du carnet d’adresses afin de limiter l’étendue des recherches dans le carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="bf5a3-112">Pour utiliser l’attribut **msRTCSIP-GroupingId** , écrivez un script pour remplir l’attribut, en attribuant la même valeur à tous les utilisateurs que vous voulez regrouper.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="bf5a3-113">Par exemple, attribuez une valeur unique à tous les utilisateurs d’une unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="bf5a3-114">**Règles de normalisation du carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="bf5a3-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="bf5a3-115">Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement Lync Server 2010, vous devez migrer les règles personnalisées vers votre pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="bf5a3-116">Si vous n’avez pas personnalisé les règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="bf5a3-117">Les règles de normalisation par défaut de Lync Server 2013 sont les mêmes que celles par défaut de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="bf5a3-118">Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf5a3-119">Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure décrite dans cette rubrique avant de pouvoir utiliser le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="bf5a3-120">Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou aux droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="bf5a3-121">**UseNormalizationRules défini sur false**</span><span class="sxs-lookup"><span data-stu-id="bf5a3-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="bf5a3-122">Si vous définissez la valeur de **UseNormalizationRules** sur false pour que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory (AD FS) sans que Lync Server 2013 applique des règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur true.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="bf5a3-123">Suivez la procédure décrite plus loin dans cette section pour définir ces paramètres sur true.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="bf5a3-124">Pour migrer des règles de normalisation personnalisées du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="bf5a3-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="bf5a3-125">Recherchez le fichier\_.\_txt\_du numéro\_de téléphone de l’entreprise à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool de pilotes 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf5a3-126">Les règles de normalisation de votre carnet d’adresses sont installées dans votre répertoire de fichiers de composants Web ABS.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="bf5a3-127">Le chemin d’accès est <STRONG>$installedDriveLetter : \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="bf5a3-128">Ce fichier peut être copié et renommé en tant &nbsp;que <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;dans le répertoire racine du dossier partagé du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="bf5a3-129">Par exemple, dans le carnet d’adresses <STRONG></STRONG>partagé dans&nbsp;$serverX, le chemin d’accès est semblable à ce qui suit : <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="bf5a3-130">Utilisez un éditeur de texte, tel que le bloc-notes,\_pour\_ouvrir\_le fichier\_de règles de normalisation des numéros de téléphone de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="bf5a3-131">Certains types d’entrée ne fonctionnent pas correctement dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="bf5a3-132">Parcourez le fichier pour obtenir les types d’entrée décrits dans cette étape, modifiez-les comme vous le souhaitez et enregistrez les modifications apportées au dossier partagé du carnet d’adresses dans votre pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="bf5a3-133">Les chaînes qui comprennent des espaces blancs ou des signes de ponctuation peuvent entraîner l’échec des règles de normalisation, car ces caractères sont supprimés de la chaîne qui est en entrée dans les règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="bf5a3-134">Si vous avez des chaînes qui incluent des espaces blancs ou des signes de ponctuation requis, vous devez modifier les chaînes.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="bf5a3-135">Par exemple, la chaîne suivante entraînera l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="bf5a3-136">La chaîne suivante n’entraînera pas l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="bf5a3-137">Pour définir UseNormalizationRules et IgnoreGenericRules sur true</span><span class="sxs-lookup"><span data-stu-id="bf5a3-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="bf5a3-138">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bf5a3-139">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="bf5a3-140">Si votre déploiement inclut uniquement Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="bf5a3-141">Si votre déploiement inclut une combinaison de Lync Server 2013 et de Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="bf5a3-142">Attendez la fin de la réplication du magasin de gestion centrale sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="bf5a3-143">Modifiez le fichier de règles de normalisation du téléphone,\_«\_\_règles\_de normalisation du numéro de téléphone de l’entreprise. txt », pour que votre déploiement efface le contenu.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="bf5a3-144">Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="bf5a3-145">Si le fichier n’est pas présent, créez-en un dans la section\_«\_\_règles\_de normalisation des numéros de téléphone de l’entreprise. txt ».</span><span class="sxs-lookup"><span data-stu-id="bf5a3-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="bf5a3-146">Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="bf5a3-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="bf5a3-147">Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 dans votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="bf5a3-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

