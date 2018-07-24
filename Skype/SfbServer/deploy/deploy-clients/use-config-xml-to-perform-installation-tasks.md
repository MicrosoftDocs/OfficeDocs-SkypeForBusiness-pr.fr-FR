---
title: Utiliser Config.xml pour effectuer des tâches d’installation dans Skype pour les clients d’entreprise
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.'
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003507"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="474ca-103">Utiliser Config.xml pour effectuer des tâches d’installation dans Skype pour les clients d’entreprise</span><span class="sxs-lookup"><span data-stu-id="474ca-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>
 
<span data-ttu-id="474ca-104">**Résumé :** comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="474ca-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>
  
<span data-ttu-id="474ca-p101">Même si l’outil de personnalisation Office est le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations ci-dessous ne peuvent être effectuées qu’avec le fichier Config.xml :</span><span class="sxs-lookup"><span data-stu-id="474ca-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>
  
- <span data-ttu-id="474ca-107">Spécifiez le chemin d’accès au point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="474ca-107">Specify the path of the network installation point.</span></span>
    
- <span data-ttu-id="474ca-108">Sélectionnez les produits à installer.</span><span class="sxs-lookup"><span data-stu-id="474ca-108">Select the products to install.</span></span>
    
- <span data-ttu-id="474ca-109">Configurez la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels.</span><span class="sxs-lookup"><span data-stu-id="474ca-109">Configure logging and the location of the Setup customization file and software updates.</span></span>
    
- <span data-ttu-id="474ca-110">Spécifiez les options d’installation, comme le nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="474ca-110">Specify installation options, such as user name.</span></span>
    
- <span data-ttu-id="474ca-111">Copiez la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office.</span><span class="sxs-lookup"><span data-stu-id="474ca-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>
    
- <span data-ttu-id="474ca-112">Ajoutez ou supprimez des langues dans l’installation.</span><span class="sxs-lookup"><span data-stu-id="474ca-112">Add or remove languages from the installation.</span></span>
    
<span data-ttu-id="474ca-113">Nous vous recommandons d’utiliser le fichier Config.xml pour configurer Skype pour une installation en mode silencieux Business.</span><span class="sxs-lookup"><span data-stu-id="474ca-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 
  
<span data-ttu-id="474ca-114">Par défaut, le fichier Config.xml qui est stocké dans le dossier principal du produit (par exemple, \ _produit_. WW) dirige le programme d’installation pour installer ce produit.</span><span class="sxs-lookup"><span data-stu-id="474ca-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="474ca-115">Par exemple, le fichier Config.xml dans le dossier suivant installe Skype pour les entreprises :</span><span class="sxs-lookup"><span data-stu-id="474ca-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>
  
- <span data-ttu-id="474ca-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="474ca-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>
    
<span data-ttu-id="474ca-117">Les éléments de Config.xml plus couramment utilisées pour Skype pour l’installation de l’entreprise sont répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="474ca-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>
  
<span data-ttu-id="474ca-118">**Éléments de Config.xml**</span><span class="sxs-lookup"><span data-stu-id="474ca-118">**Config.xml elements**</span></span>

|<span data-ttu-id="474ca-119">**Élément**</span><span class="sxs-lookup"><span data-stu-id="474ca-119">**Element**</span></span>|<span data-ttu-id="474ca-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="474ca-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="474ca-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="474ca-121">Configuration</span></span>  <br/> |<span data-ttu-id="474ca-p103">Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)</span><span class="sxs-lookup"><span data-stu-id="474ca-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/> |
|<span data-ttu-id="474ca-124">Élément OptionState</span><span class="sxs-lookup"><span data-stu-id="474ca-124">OptionState</span></span>  <br/> | <span data-ttu-id="474ca-125">Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="474ca-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="474ca-126">Pour empêcher l’installation de Business Connectivity Services, qui inclut des composants partagés interféreront avec Outlook, utilisez les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="474ca-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="474ca-127">ID = « LOBiMain »</span><span class="sxs-lookup"><span data-stu-id="474ca-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="474ca-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="474ca-128">State="Absent"</span></span> <br/>  <span data-ttu-id="474ca-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="474ca-129">Children="Force"</span></span> <br/> |
|<span data-ttu-id="474ca-130">Display</span><span class="sxs-lookup"><span data-stu-id="474ca-130">Display</span></span>  <br/> | <span data-ttu-id="474ca-p105">Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="474ca-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="474ca-133">CompletionNotice = « Yes »</span><span class="sxs-lookup"><span data-stu-id="474ca-133">CompletionNotice="Yes"</span></span> | <span data-ttu-id="474ca-134">« No"(default)</span><span class="sxs-lookup"><span data-stu-id="474ca-134">"No"(default)</span></span> <br/>  <span data-ttu-id="474ca-135">AcceptEula = « Yes »</span><span class="sxs-lookup"><span data-stu-id="474ca-135">AcceptEula="Yes"</span></span> | <span data-ttu-id="474ca-136">« No"(default)</span><span class="sxs-lookup"><span data-stu-id="474ca-136">"No"(default)</span></span> <br/> |
|<span data-ttu-id="474ca-137">Journalisation</span><span class="sxs-lookup"><span data-stu-id="474ca-137">Logging</span></span>  <br/> | <span data-ttu-id="474ca-p106">Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="474ca-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="474ca-140">Type = « Off »</span><span class="sxs-lookup"><span data-stu-id="474ca-140">Type ="Off"</span></span> | <span data-ttu-id="474ca-141">« Standard</span><span class="sxs-lookup"><span data-stu-id="474ca-141">"Standard"(default)</span></span> | <span data-ttu-id="474ca-142">« Verbose »</span><span class="sxs-lookup"><span data-stu-id="474ca-142">"Verbose"</span></span> <br/>  <span data-ttu-id="474ca-143">Modèle = « _nom de fichier_.txt » (le nom du fichier journal)</span><span class="sxs-lookup"><span data-stu-id="474ca-143">Template=" _filename_.txt" (the name of the log file)</span></span>  <br/> |
|<span data-ttu-id="474ca-144">Paramètre</span><span class="sxs-lookup"><span data-stu-id="474ca-144">Setting</span></span>  <br/> | <span data-ttu-id="474ca-p107">Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="474ca-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="474ca-147">Setting Id = « _nom_» (le nom de la propriété Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="474ca-147">Setting Id=" _name_" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="474ca-148">Valeur = » _valeur_"(valeur à attribuer à la propriété)</span><span class="sxs-lookup"><span data-stu-id="474ca-148">Value=" _value_" (the value to assign to the property)</span></span>  <br/> |
|<span data-ttu-id="474ca-149">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="474ca-149">DistributionPoint</span></span>  <br/> | <span data-ttu-id="474ca-p108">Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :</span><span class="sxs-lookup"><span data-stu-id="474ca-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="474ca-152">Emplacement = » _chemin d’accès_»</span><span class="sxs-lookup"><span data-stu-id="474ca-152">Location=" _path_"</span></span>  <br/> |
   
<span data-ttu-id="474ca-153">L’exemple suivant montre un fichier Config.xml pour une installation sans assistance de le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="474ca-153">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="474ca-154">Des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer des tâches d’installation et de maintenance Office sont disponibles à l’adresse [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span><span class="sxs-lookup"><span data-stu-id="474ca-154">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>
  
## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="474ca-155">Pour personnaliser le fichier Config.xml</span><span class="sxs-lookup"><span data-stu-id="474ca-155">To customize the Config.xml file</span></span>

1. <span data-ttu-id="474ca-156">Ouvrez le fichier Config.xml avec un éditeur de texte, comme le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="474ca-156">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>
    
2. <span data-ttu-id="474ca-157">Recherchez les lignes qui contiennent les éléments à modifier.</span><span class="sxs-lookup"><span data-stu-id="474ca-157">Locate the lines that contain the elements you want to change.</span></span>
    
3. <span data-ttu-id="474ca-158">Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="474ca-158">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="474ca-159">Assurez-vous que vous supprimez les délimiteurs de commentaire, «\<!-- » et «--\>».</span><span class="sxs-lookup"><span data-stu-id="474ca-159">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="474ca-160">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="474ca-160">For example, use the following syntax:</span></span>
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. <span data-ttu-id="474ca-161">Enregistrez le fichier Config.xml.</span><span class="sxs-lookup"><span data-stu-id="474ca-161">Save the Config.xml file.</span></span>
    

