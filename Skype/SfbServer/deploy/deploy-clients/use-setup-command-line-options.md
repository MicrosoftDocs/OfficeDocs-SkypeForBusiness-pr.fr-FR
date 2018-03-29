---
title: Utilisation des options de ligne de commande du programme d’installation dans Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="86156-103">Utilisation des options de ligne de commande du programme d’installation dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="86156-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86156-104">**Résumé :** Obtenir des informations sur les opérations de ligne de commande Setup.exe dans le programme d’installation Office.</span><span class="sxs-lookup"><span data-stu-id="86156-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="86156-105">La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="86156-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="86156-106">Au lieu d’utiliser les options de ligne de commande d’installation, vous allez généralement utiliser l’outil de personnalisation Office et le fichier Config.xml pour le programme d’installation et de la fonctionnalité de personnalisation des produits.</span><span class="sxs-lookup"><span data-stu-id="86156-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="86156-107">La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="86156-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="86156-108">**Options de ligne de commande d’installation de Office**</span><span class="sxs-lookup"><span data-stu-id="86156-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="86156-109">**Option de ligne de commande du programme d’installation**</span><span class="sxs-lookup"><span data-stu-id="86156-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="86156-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="86156-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86156-111">/admin</span><span class="sxs-lookup"><span data-stu-id="86156-111">/admin</span></span>  <br/> |<span data-ttu-id="86156-112">Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</span><span class="sxs-lookup"><span data-stu-id="86156-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="86156-113">/adminfile [chemin]</span><span class="sxs-lookup"><span data-stu-id="86156-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="86156-p102">Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="86156-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="86156-116">/config [chemin]</span><span class="sxs-lookup"><span data-stu-id="86156-116">/config [path]</span></span>  <br/> |<span data-ttu-id="86156-117">Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="86156-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="86156-118">Utilisez l’option /config pour spécifier le fichier Config.xml que vous avez personnalisé pour Skype pour les installations de l’entreprise, par exemple :`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="86156-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="86156-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="86156-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="86156-120">Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante.</span><span class="sxs-lookup"><span data-stu-id="86156-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="86156-121">Par exemple, vous pouvez utiliser le / modifier l’option pour ajouter ou supprimer des Skype pour les fonctionnalités d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="86156-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="86156-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="86156-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="86156-123">Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="86156-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="86156-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="86156-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="86156-125">Exécute le programme d’installation pour supprimer Skype pour les entreprises à partir de l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="86156-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="86156-126">Pour plus d’informations sur les options de ligne de commande d’installation, voir [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span><span class="sxs-lookup"><span data-stu-id="86156-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

