---
title: Utiliser Config.xml pour effectuer des tâches d’installation dans les clients Skype Entreprise
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : Comment utiliser le fichier Config.xml pour spécifier des instructions d’installation supplémentaires.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825184"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="20a1b-103">Utiliser Config.xml pour effectuer des tâches d’installation dans les clients Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="20a1b-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="20a1b-104">**Résumé :** Utilisation du fichier Config.xml pour spécifier des instructions d’installation supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="20a1b-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="20a1b-p101">Bien que l’outil de personnalisation Office soit le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations suivantes ne peuvent être effectuées qu’avec le fichier Config.xml :</span><span class="sxs-lookup"><span data-stu-id="20a1b-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="20a1b-107">spécifier le chemin d’accès au point d’installation réseau ;</span><span class="sxs-lookup"><span data-stu-id="20a1b-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="20a1b-108">sélectionner les produits à installer ;</span><span class="sxs-lookup"><span data-stu-id="20a1b-108">Select the products to install.</span></span>

- <span data-ttu-id="20a1b-109">configurer la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels ;</span><span class="sxs-lookup"><span data-stu-id="20a1b-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="20a1b-110">spécifier les options d’installation telles que le nom de l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="20a1b-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="20a1b-111">copier la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office ;</span><span class="sxs-lookup"><span data-stu-id="20a1b-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="20a1b-112">ajouter ou supprimer des langues de l’installation.</span><span class="sxs-lookup"><span data-stu-id="20a1b-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="20a1b-113">Nous vous recommandons d’utiliser le fichier Config.xml pour configurer l’installation silencieuse de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="20a1b-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="20a1b-114">Par défaut, le fichier Config.xml qui est stocké dans le dossier principal du produit (par exemple, \ _produit_). WW) dirige le programme d’installation pour installer ce produit.</span><span class="sxs-lookup"><span data-stu-id="20a1b-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="20a1b-115">Par exemple, le Config.xml dans le dossier suivant installe Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="20a1b-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="20a1b-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="20a1b-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="20a1b-117">Les Config.xml les plus couramment utilisés pour l’installation de Skype Entreprise sont répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="20a1b-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="20a1b-118">**Éléments de Config.xml**</span><span class="sxs-lookup"><span data-stu-id="20a1b-118">**Config.xml elements**</span></span>


| <span data-ttu-id="20a1b-119">**Élément**</span><span class="sxs-lookup"><span data-stu-id="20a1b-119">**Element**</span></span>              | <span data-ttu-id="20a1b-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="20a1b-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="20a1b-121">Configuration</span><span class="sxs-lookup"><span data-stu-id="20a1b-121">Configuration</span></span>  <br/>     | <span data-ttu-id="20a1b-122">Élément de niveau supérieur (obligatoire).</span><span class="sxs-lookup"><span data-stu-id="20a1b-122">Top-level element (required).</span></span> <span data-ttu-id="20a1b-123">Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)</span><span class="sxs-lookup"><span data-stu-id="20a1b-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="20a1b-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="20a1b-124">OptionState</span></span>  <br/>       | <span data-ttu-id="20a1b-125">Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="20a1b-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="20a1b-126">Utilisez les attributs suivants pour empêcher l’installation de Services Business Connectivity, qui inclut des composants partagés qui interfèrent avec Outlook :</span><span class="sxs-lookup"><span data-stu-id="20a1b-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="20a1b-127">Id="LOBiMain »</span><span class="sxs-lookup"><span data-stu-id="20a1b-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="20a1b-128">State="Absent »</span><span class="sxs-lookup"><span data-stu-id="20a1b-128">State="Absent"</span></span> <br/>  <span data-ttu-id="20a1b-129">Children="Force »</span><span class="sxs-lookup"><span data-stu-id="20a1b-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="20a1b-130">Afficher</span><span class="sxs-lookup"><span data-stu-id="20a1b-130">Display</span></span>  <br/>           | <span data-ttu-id="20a1b-p105">Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="20a1b-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="20a1b-133">CompletionNotice="Yes »</span><span class="sxs-lookup"><span data-stu-id="20a1b-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="20a1b-134">Logging</span><span class="sxs-lookup"><span data-stu-id="20a1b-134">Logging</span></span>  <br/>           | <span data-ttu-id="20a1b-p106">Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="20a1b-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="20a1b-137">Type ="Off »</span><span class="sxs-lookup"><span data-stu-id="20a1b-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="20a1b-138">Setting</span><span class="sxs-lookup"><span data-stu-id="20a1b-138">Setting</span></span>  <br/>           | <span data-ttu-id="20a1b-p107">Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="20a1b-p107">Specifies values for Windows Installer properties. Typical attributes include the following: </span></span><br/>  <span data-ttu-id="20a1b-141">Setting Id= » *name*" (nom de la propriété Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="20a1b-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="20a1b-142">Value= » *value*" (valeur à affecter à la propriété)</span><span class="sxs-lookup"><span data-stu-id="20a1b-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="20a1b-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="20a1b-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="20a1b-p108">Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :</span><span class="sxs-lookup"><span data-stu-id="20a1b-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute: </span></span><br/>  <span data-ttu-id="20a1b-146">Location= » *path*»</span><span class="sxs-lookup"><span data-stu-id="20a1b-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="20a1b-147">L’exemple suivant montre un fichier Config.xml pour une installation silencieuse classique du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="20a1b-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="20a1b-148">Des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer les tâches d’installation et de maintenance d’Office sont disponibles sur [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .</span><span class="sxs-lookup"><span data-stu-id="20a1b-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="20a1b-149">Pour personnaliser le fichier Config.xml</span><span class="sxs-lookup"><span data-stu-id="20a1b-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="20a1b-150">Ouvrez le fichier Config.xml avec un éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="20a1b-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="20a1b-151">Recherchez les lignes qui contiennent les éléments que vous voulez changer.</span><span class="sxs-lookup"><span data-stu-id="20a1b-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="20a1b-152">Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="20a1b-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="20a1b-153">Veillez à supprimer les délimiteur de commentaires « \<!--" and "--\> ».</span><span class="sxs-lookup"><span data-stu-id="20a1b-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="20a1b-154">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="20a1b-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="20a1b-155">Enregistrez le fichier Config.xml.</span><span class="sxs-lookup"><span data-stu-id="20a1b-155">Save the Config.xml file.</span></span>


