---
title: Utiliser les options de la ligne de commande du programme d’installation avec les clients Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé: Découvrez les opérations de ligne de commande Setup. exe dans le programme d’installation d’Office.'
ms.openlocfilehash: a84c1f8a69bdff07dfec5e274932a522bf139c9a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234834"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="23776-103">Utiliser les options de la ligne de commande du programme d’installation avec les clients Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="23776-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="23776-104">**Résumé:** En savoir plus sur les opérations de ligne de commande Setup. exe dans le programme d’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="23776-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="23776-105">La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="23776-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="23776-106">Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utiliserez généralement l’outil de personnalisation Office et le fichier config. xml pour la configuration du produit et la personnalisation des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="23776-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="23776-107">La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="23776-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="23776-108">**Options de ligne de commande du programme d’installation Office**</span><span class="sxs-lookup"><span data-stu-id="23776-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="23776-109">**Options de ligne de commande du programme d’installation**</span><span class="sxs-lookup"><span data-stu-id="23776-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="23776-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="23776-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23776-111">/admin</span><span class="sxs-lookup"><span data-stu-id="23776-111">/admin</span></span>  <br/> |<span data-ttu-id="23776-112">Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</span><span class="sxs-lookup"><span data-stu-id="23776-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="23776-113">/adminfile [chemin]</span><span class="sxs-lookup"><span data-stu-id="23776-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="23776-p102">Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="23776-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="23776-116">/config [chemin]</span><span class="sxs-lookup"><span data-stu-id="23776-116">/config [path]</span></span>  <br/> |<span data-ttu-id="23776-117">Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="23776-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="23776-118">Utilisez l’option/config pour spécifier le fichier config. XML que vous avez personnalisé pour les installations Skype entreprise, par exemple:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="23776-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="23776-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="23776-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="23776-120">Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante.</span><span class="sxs-lookup"><span data-stu-id="23776-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="23776-121">Par exemple, vous pouvez utiliser l’option/Modify pour ajouter ou supprimer des fonctionnalités Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="23776-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="23776-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="23776-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="23776-123">Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="23776-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="23776-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="23776-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="23776-125">Exécute le programme d’installation pour supprimer Skype entreprise de l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="23776-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


