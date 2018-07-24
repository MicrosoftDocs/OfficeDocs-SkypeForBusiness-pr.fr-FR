---
title: Utilisez les options de ligne de commande du programme d’installation avec Skype pour les clients d’entreprise
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.'
ms.openlocfilehash: 13005f96b353b8648ed676ef68af54b76a99e48c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974451"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="3370f-103">Utilisez les options de ligne de commande du programme d’installation avec Skype pour les clients d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3370f-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="3370f-104">**Résumé :** Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.</span><span class="sxs-lookup"><span data-stu-id="3370f-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="3370f-105">La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="3370f-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="3370f-106">Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous allez généralement utiliser l’outil de personnalisation Office et le fichier Config.xml pour la personnalisation du programme d’installation et de la fonctionnalité de produit.</span><span class="sxs-lookup"><span data-stu-id="3370f-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="3370f-107">La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3370f-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="3370f-108">**Options de ligne de commande du programme d’installation Office**</span><span class="sxs-lookup"><span data-stu-id="3370f-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="3370f-109">**Options de ligne de commande du programme d’installation**</span><span class="sxs-lookup"><span data-stu-id="3370f-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="3370f-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="3370f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3370f-111">/admin</span><span class="sxs-lookup"><span data-stu-id="3370f-111">/admin</span></span>  <br/> |<span data-ttu-id="3370f-112">Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</span><span class="sxs-lookup"><span data-stu-id="3370f-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="3370f-113">/adminfile [chemin]</span><span class="sxs-lookup"><span data-stu-id="3370f-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="3370f-p102">Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="3370f-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="3370f-116">/config [chemin]</span><span class="sxs-lookup"><span data-stu-id="3370f-116">/config [path]</span></span>  <br/> |<span data-ttu-id="3370f-117">Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="3370f-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="3370f-118">Utilisez l’option /config pour spécifier le fichier Config.xml que vous avez personnalisé pour Skype pour les installations d’entreprise, par exemple :`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="3370f-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="3370f-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="3370f-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="3370f-120">Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante.</span><span class="sxs-lookup"><span data-stu-id="3370f-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="3370f-121">Par exemple, vous pouvez utiliser l’option pour ajouter ou supprimer des Skype pour les fonctionnalités d’entreprise / modify.</span><span class="sxs-lookup"><span data-stu-id="3370f-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="3370f-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="3370f-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="3370f-123">Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="3370f-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="3370f-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="3370f-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="3370f-125">Exécute le programme d’installation pour supprimer Skype pour les entreprises à partir de l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3370f-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


