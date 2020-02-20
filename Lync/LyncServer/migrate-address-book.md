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
ms.openlocfilehash: 8581e36019cad7a3ac3aef80369e2daec6179f72
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="f6f1f-102">Faire migrer le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="f6f1f-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6f1f-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f6f1f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f6f1f-104">En règle générale, le carnet d’adresses Lync Server 2010 est migré avec le reste de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="f6f1f-105">Toutefois, vous devrez peut-être effectuer certaines étapes de post-migration si vous avez personnalisé les éléments suivants dans votre environnement Lync Server 2010 :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="f6f1f-106">définir la propriété WMI **PartitionbyOU** pour regrouper les entrées de carnet d’adresses par unité d’organisation ;</span><span class="sxs-lookup"><span data-stu-id="f6f1f-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="f6f1f-107">personnaliser les règles de normalisation du carnet d’adresses ;</span><span class="sxs-lookup"><span data-stu-id="f6f1f-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="f6f1f-108">remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="f6f1f-109">**Entrées de carnet d’adresses groupées**</span><span class="sxs-lookup"><span data-stu-id="f6f1f-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="f6f1f-p102">Si vous affectez la valeur True à la propriété WMI **PartitionbyOU** afin de créer des carnets d’adresses pour chaque unité d’organisation, vous devez définir l’attribut Active Directory **msRTCSIP-GroupingId** sur les utilisateurs et contacts si vous souhaitez continuer de regrouper les entrées de carnet d’adresses. Il peut être préférable de regrouper les entrées de carnet d’adresses pour limiter l’étendue des recherches dans les carnets d’adresses. Pour utiliser l’attribut **msRTCSIP-GroupingId**, écrivez un script pour remplir l’attribut, en affectant la même valeur pour tous les utilisateurs que vous souhaitez regrouper. Par exemple, affectez une valeur unique pour tous les utilisateurs d’une même unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-p102">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="f6f1f-114">**Règles de normalisation de carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="f6f1f-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="f6f1f-115">Si vous avez personnalisé des règles de normalisation de carnet d’adresses dans votre environnement Lync Server 2010, vous devez migrer les règles personnalisées vers votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="f6f1f-116">Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="f6f1f-117">Les règles de normalisation par défaut pour Lync Server 2013 sont les mêmes que les règles par défaut pour Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="f6f1f-118">Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6f1f-p104">Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation de carnet d’adresses, vous devez appliquer la procédure de cette rubrique pour pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou des droits équivalents.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="f6f1f-121">**Valeur False affectée à UseNormalizationRules**</span><span class="sxs-lookup"><span data-stu-id="f6f1f-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="f6f1f-122">Si vous définissez la valeur de **UseNormalizationRules** sur false afin que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans que Lync Server 2013 n’applique les règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur true.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="f6f1f-123">Suivez la procédure décrite plus loin dans cette section pour affecter la valeur True à ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="f6f1f-124">Pour migrer des règles de normalisation de carnet d’adresses personnalisées</span><span class="sxs-lookup"><span data-stu-id="f6f1f-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="f6f1f-125">Recherchez le fichier\_\_Rules\_de normalisation des numéros de téléphone\_de l’entreprise. txt dans la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool pilote Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6f1f-126">Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="f6f1f-127">Le chemin d’accès est <STRONG>$lettre_lecteur_installation:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="f6f1f-128">Ce fichier peut être copié et renommé &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;dans le répertoire racine du dossier partagé carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="f6f1f-129">Par exemple, le carnet d’adresses partagé <STRONG></STRONG>dans $serverX&nbsp;, le chemin d’accès est similaire à : <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="f6f1f-130">Utilisez un éditeur de texte, tel que le bloc-notes,\_pour\_ouvrir\_le fichier\_. txt des règles de normalisation des numéros de téléphone de la société.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="f6f1f-131">Certains types d’entrées ne fonctionnent pas correctement dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="f6f1f-132">Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="f6f1f-p108">Les chaînes qui comportent des espaces ou des signes de ponctuation provoquent l’échec des règles de normalisation car ces caractères sont supprimés de la chaîne fournie comme entrée aux règles de normalisation. Si vous avez des chaînes qui comportent des espaces ou des signes de ponctuation obligatoires, vous devez modifier ces chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="f6f1f-136">La chaîne suivante ne provoque pas l’échec de la règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="f6f1f-137">Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules</span><span class="sxs-lookup"><span data-stu-id="f6f1f-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="f6f1f-138">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f6f1f-139">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="f6f1f-140">Si votre déploiement inclut uniquement Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="f6f1f-141">Si votre déploiement inclut une combinaison de Lync Server 2013 et Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="f6f1f-142">Attendez que la réplication du magasin central de gestion se produise sur tous les pools.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="f6f1f-143">Modifiez le fichier de règles de normalisation téléphonique, «\_Company\_Phone\_Number Normalization\_Rules. txt », pour que votre déploiement efface le contenu.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="f6f1f-144">Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="f6f1f-145">Si le fichier n’est pas présent, créez un fichier vide nommé « Company\_Phone\_Number\_Normalization\_Rules. txt ».</span><span class="sxs-lookup"><span data-stu-id="f6f1f-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="f6f1f-146">Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="f6f1f-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="f6f1f-147">Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 de votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="f6f1f-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

