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
description: 'Résumé : vue d’ensemble des méthodes et des outils d’installation de Skype entreprise.'
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220834"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="06ef7-103">Personnaliser l’installation du client Windows dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="06ef7-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="06ef7-104">**Résumé :** Vue d’ensemble des méthodes et des outils d’installation de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="06ef7-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="06ef7-105">Pour obtenir des informations sur l’installation de Skype entreprise qui est fournie avec Microsoft 365 et Office 365, consultez [la rubrique deploy the Skype for Business client in Microsoft 365 ou office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="06ef7-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="06ef7-106">Les administrateurs d’entreprise peuvent personnaliser l’installation Windows Installer (. msi) des versions de Skype entreprise sous licence en utilisant les méthodes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="06ef7-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="06ef7-107">Étant donné qu’aucun outil unique ne fournit toutes les options de personnalisation, vous utiliserez probablement une combinaison de ces méthodes dans votre déploiement de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="06ef7-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="06ef7-108">Vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="06ef7-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="06ef7-109">[Utilisez l’outil de personnalisation Office (OPO) dans Skype entreprise Server](use-the-office-customization-tool-oct.md) pour personnaliser les options et les fonctionnalités d’installation de Skype entreprise et d’autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="06ef7-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="06ef7-110">[Utilisez le fichier config. xml pour effectuer des tâches d’installation dans Skype entreprise Server](use-config-xml-to-perform-installation-tasks.md) afin de spécifier le chemin d’accès au point d’installation réseau et effectuer une installation sans assistance.</span><span class="sxs-lookup"><span data-stu-id="06ef7-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="06ef7-111">[Utilisez les options de ligne de commande du programme d’installation dans Skype entreprise Server](use-setup-command-line-options.md) pour spécifier le fichier config. XML à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="06ef7-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="06ef7-112">[Configurez les stratégies de démarrage client dans Skype entreprise Server](configure-client-bootstrapping-policies.md) à l’aide du composant logiciel enfichable MMC éditeur d’objets de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="06ef7-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="06ef7-113">Vous devrez probablement configurer d’autres options lors du déploiement de la suite de produits Office.</span><span class="sxs-lookup"><span data-stu-id="06ef7-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="06ef7-114">Les rubriques de cette section donnent une vue d’ensemble de ces outils de personnalisation et présentent des considérations spécifiques à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="06ef7-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="06ef7-115">Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="06ef7-115">Included are links to detailed Office help for each tool.</span></span> 
  

