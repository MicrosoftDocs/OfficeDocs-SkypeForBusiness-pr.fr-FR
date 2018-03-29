---
title: Personnaliser l’installation du client Windows dans Skype pour Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Résumé : Vue d’ensemble des méthodes d’installation et des outils pour Skype pour les entreprises.'
ms.openlocfilehash: 8f74f3930e296d8f49eca4bf2a097c88883d7981
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-windows-client-installation-in-skype-for-business-server-2015"></a><span data-ttu-id="cfb69-103">Personnaliser l’installation du client Windows dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cfb69-103">Customize Windows client installation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cfb69-104">**Résumé :** Vue d’ensemble des méthodes d’installation et des outils pour Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="cfb69-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfb69-105">Pour plus d’informations d’installation sur Skype pour entreprise qui est fourni avec Office 365, voir [déployer le Skype pour client d’entreprise dans Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="cfb69-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="cfb69-106">Les administrateurs d’entreprise peuvent personnaliser l’installation de Windows Installer (.msi) des versions de licences en volume de Skype pour les entreprises en utilisant les méthodes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="cfb69-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="cfb69-107">Car aucun outil unique n’offre toutes les options de personnalisation, vous utiliserez probablement une combinaison de ces méthodes dans votre Skype pour le déploiement de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cfb69-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="cfb69-108">Vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="cfb69-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="cfb69-109">[Utilisez l’outil de personnalisation Office (OCT) dans Skype pour Business Server 2015](use-the-office-customization-tool-oct.md) pour personnaliser les options de configuration et les fonctionnalités de Skype pour les entreprises et les autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="cfb69-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="cfb69-110">[Utilisation des Config.xml pour effectuer des tâches d’installation dans Skype pour Business Server 2015](use-config-xml-to-perform-installation-tasks.md) pour spécifier le chemin d’accès du point d’installation réseau et effectuer l’installation en mode silencieux.</span><span class="sxs-lookup"><span data-stu-id="cfb69-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="cfb69-111">[Utilisez le programme d’installation des options de ligne de commande dans Skype pour Business Server 2015](use-setup-command-line-options.md) pour spécifier le fichier Config.xml à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="cfb69-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="cfb69-112">[Configurer les stratégies client amorçage dans Skype pour 2015 de serveur d’entreprise](configure-client-bootstrapping-policies.md) à l’aide du composant logiciel enfichable Éditeur d’objets de stratégie de groupe MMC.</span><span class="sxs-lookup"><span data-stu-id="cfb69-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="cfb69-113">Il y aura probablement des autres options, que vous devrez configurer lors du déploiement de la suite de produits Office.</span><span class="sxs-lookup"><span data-stu-id="cfb69-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="cfb69-114">Les rubriques de cette section donnent une vue d’ensemble de ces outils de personnalisation et de discuter des considérations spécifiques à Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="cfb69-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="cfb69-115">Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="cfb69-115">Included are links to detailed Office help for each tool.</span></span> 
  

