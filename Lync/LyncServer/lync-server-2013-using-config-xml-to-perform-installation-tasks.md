---
title: 'Lync Server 2013 : utilisation du fichier config. xml pour effectuer des tâches d’installation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adadafcbb5338f47aa13d25b3dfd39386935b30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="914f9-102">Utilisation de config. xml pour effectuer des tâches d’installation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="914f9-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="914f9-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="914f9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="914f9-p101">Bien que l’outil de personnalisation Office soit le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations suivantes ne peuvent être effectuées qu’avec le fichier Config.xml :</span><span class="sxs-lookup"><span data-stu-id="914f9-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="914f9-106">spécifier le chemin d’accès au point d’installation réseau ;</span><span class="sxs-lookup"><span data-stu-id="914f9-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="914f9-107">sélectionner les produits à installer ;</span><span class="sxs-lookup"><span data-stu-id="914f9-107">Select the products to install.</span></span>

  - <span data-ttu-id="914f9-108">configurer la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels ;</span><span class="sxs-lookup"><span data-stu-id="914f9-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="914f9-109">spécifier les options d’installation telles que le nom de l’utilisateur ;</span><span class="sxs-lookup"><span data-stu-id="914f9-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="914f9-110">copier la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office ;</span><span class="sxs-lookup"><span data-stu-id="914f9-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="914f9-111">ajouter ou supprimer des langues de l’installation.</span><span class="sxs-lookup"><span data-stu-id="914f9-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="914f9-112">Nous vous recommandons d’utiliser le fichier config. xml pour configurer l’installation en mode silencieux de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="914f9-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="914f9-113">Par défaut, le fichier config. XML qui est stocké dans le dossier du produit principal (par \\exemple, produit. WW) indique au programme d’installation d’installer ce produit.</span><span class="sxs-lookup"><span data-stu-id="914f9-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="914f9-114">Par exemple, le fichier config. xml dans le dossier suivant installe Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="914f9-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="914f9-115">\\\\partage\\\\du serveur\\Lync15 Lync. \\WW config. Xml</span><span class="sxs-lookup"><span data-stu-id="914f9-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="914f9-116">Les éléments config. XML les plus couramment utilisés pour l’installation de Lync 2013 sont répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="914f9-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="914f9-117">Éléments de Config.xml</span><span class="sxs-lookup"><span data-stu-id="914f9-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="914f9-118">Élément</span><span class="sxs-lookup"><span data-stu-id="914f9-118">Element</span></span></th>
<th><span data-ttu-id="914f9-119">Description</span><span class="sxs-lookup"><span data-stu-id="914f9-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="914f9-120">Configuration</span><span class="sxs-lookup"><span data-stu-id="914f9-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="914f9-p103">Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync</span><span class="sxs-lookup"><span data-stu-id="914f9-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="914f9-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="914f9-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="914f9-124">Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées pendant l’installation.</span><span class="sxs-lookup"><span data-stu-id="914f9-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="914f9-125">Utilisez les attributs suivants pour empêcher l’installation de Business Connectivity Services, qui inclut les composants partagés qui interfèrent avec Outlook 2010 :</span><span class="sxs-lookup"><span data-stu-id="914f9-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="914f9-126">ID =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="914f9-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="914f9-127">État =&quot;absent&quot;</span><span class="sxs-lookup"><span data-stu-id="914f9-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="914f9-128">Enfants =&quot;force&quot;</span><span class="sxs-lookup"><span data-stu-id="914f9-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="914f9-129">Display</span><span class="sxs-lookup"><span data-stu-id="914f9-129">Display</span></span></p></td>
<td><p><span data-ttu-id="914f9-p105">Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="914f9-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="914f9-132">CompletionNotice =&quot;oui&quot; | &quot;non&quot;(par défaut)</span><span class="sxs-lookup"><span data-stu-id="914f9-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="914f9-133">AcceptEULA =&quot;oui&quot; | &quot;non&quot;(par défaut)</span><span class="sxs-lookup"><span data-stu-id="914f9-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="914f9-134">Logging</span><span class="sxs-lookup"><span data-stu-id="914f9-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="914f9-p106">Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="914f9-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="914f9-137">Type =&quot;désactivé&quot; | &quot;standard&quot;(par défaut) | &quot;Commentaires&quot;</span><span class="sxs-lookup"><span data-stu-id="914f9-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="914f9-138">Template=”nomfichier.txt” (nom du fichier journal)</span><span class="sxs-lookup"><span data-stu-id="914f9-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="914f9-139">Paramètres</span><span class="sxs-lookup"><span data-stu-id="914f9-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="914f9-p107">Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="914f9-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="914f9-142">ID de paramètre&quot;=&quot; nom (nom de la propriété Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="914f9-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="914f9-143">Value =&quot;valeur&quot; (valeur à affecter à la propriété)</span><span class="sxs-lookup"><span data-stu-id="914f9-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="914f9-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="914f9-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="914f9-p108">Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :</span><span class="sxs-lookup"><span data-stu-id="914f9-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="914f9-147">Location = "chemin d’accès"</span><span class="sxs-lookup"><span data-stu-id="914f9-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="914f9-148">L’exemple suivant montre un fichier config. xml pour une installation en mode silencieux classique de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="914f9-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="914f9-149">Des informations détaillées sur l’utilisation du fichier config. xml pour effectuer des tâches d’installation et de <http://go.microsoft.com/fwlink/p/?linkid=267514>maintenance d’Office sont disponibles à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="914f9-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <http://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="914f9-150">Pour personnaliser le fichier Config.xml</span><span class="sxs-lookup"><span data-stu-id="914f9-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="914f9-151">Ouvrez le fichier Config.xml avec un éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="914f9-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="914f9-152">Recherchez les lignes qui contiennent les éléments que vous voulez changer.</span><span class="sxs-lookup"><span data-stu-id="914f9-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="914f9-153">Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="914f9-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="914f9-154">Veillez à supprimer les délimiteurs de commentaire, «\<\!-- » et « --\>».</span><span class="sxs-lookup"><span data-stu-id="914f9-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="914f9-155">Par exemple, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="914f9-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="914f9-156">Enregistrez le fichier Config.xml.</span><span class="sxs-lookup"><span data-stu-id="914f9-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

