---
title: Personnaliser l’installation du client Windows dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Résumé : vue d’ensemble des méthodes et des outils d’installation pour Skype entreprise.'
ms.openlocfilehash: 4661a440cfcb85a097f7760e2dd8992faf9adb70
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768797"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="d9231-103">Personnaliser l’installation du client Windows dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d9231-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="d9231-104">**Résumé :** Vue d’ensemble des méthodes et des outils d’installation pour Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="d9231-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9231-105">Pour plus d’informations sur l’installation de Skype entreprise qui est fourni avec Office 365, voir [déployer le client Skype entreprise dans office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="d9231-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="d9231-106">Les administrateurs d’entreprise peuvent personnaliser l’installation Windows Installer (. msi) des versions sous licence en volume de Skype entreprise en utilisant les méthodes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="d9231-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="d9231-107">Dans la mesure où il n’existe aucune option de personnalisation disponible sur un seul outil, vous utiliserez probablement une combinaison de ces méthodes dans votre déploiement Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="d9231-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="d9231-108">Vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9231-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="d9231-109">[Utilisez l’outil de personnalisation Office (OPO) dans Skype entreprise Server](use-the-office-customization-tool-oct.md) pour personnaliser les options et fonctionnalités de configuration de Skype entreprise et d’autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="d9231-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="d9231-110">[Utilisez config. xml pour effectuer des tâches d’installation dans Skype entreprise Server](use-config-xml-to-perform-installation-tasks.md) afin de spécifier le chemin d’accès du point d’installation réseau et de procéder à l’installation silencieuse.</span><span class="sxs-lookup"><span data-stu-id="d9231-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="d9231-111">[Utilisez les options de la ligne de commande Setup dans Skype entreprise Server](use-setup-command-line-options.md) pour spécifier le fichier config. XML à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="d9231-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="d9231-112">[Configurez les stratégies d’amorçage client dans Skype entreprise Server](configure-client-bootstrapping-policies.md) à l’aide du composant logiciel enfichable Éditeur d’objets de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="d9231-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="d9231-113">D’autres options seront probablement à configurer lors du déploiement de la suite Office de produits.</span><span class="sxs-lookup"><span data-stu-id="d9231-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="d9231-114">Les rubriques de cette section donnent un aperçu de ces outils de personnalisation et présentent des remarques spécifiques à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="d9231-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="d9231-115">Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="d9231-115">Included are links to detailed Office help for each tool.</span></span> 
  

