---
title: Personnaliser l’installation du client Windows dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Résumé : Vue d’ensemble des méthodes et outils d’installation pour Skype Entreprise.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805714"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="902c3-103">Personnaliser l’installation du client Windows dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="902c3-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="902c3-104">**Résumé :** Vue d’ensemble des méthodes et outils d’installation pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="902c3-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="902c3-105">Pour plus d’informations sur l’installation de Skype Entreprise avec Microsoft 365 et Office 365, voir Déployer le client Skype Entreprise dans [Microsoft 365 ou Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="902c3-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="902c3-106">Les administrateurs d’entreprise peuvent personnaliser l’installation basée sur Windows Installer (.msi) des versions avec licence en volume de Skype Entreprise à l’aide des méthodes abordées dans cette section.</span><span class="sxs-lookup"><span data-stu-id="902c3-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="902c3-107">Étant donné qu’aucun outil ne fournit toutes les options de personnalisation, vous utiliserez probablement une combinaison de ces méthodes dans votre déploiement Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="902c3-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="902c3-108">Vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="902c3-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="902c3-109">[Utilisez l’Outil de personnalisation Office (PERSONNALISATION)](use-the-office-customization-tool-oct.md) dans Skype Entreprise Server pour personnaliser les options d’installation et les fonctionnalités de Skype Entreprise et d’autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="902c3-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="902c3-110">Utilisez Config.xml pour effectuer des [tâches d’installation](use-config-xml-to-perform-installation-tasks.md) dans Skype Entreprise Server afin de spécifier le chemin d’accès du point d’installation réseau et d’effectuer l’installation en mode silencieux.</span><span class="sxs-lookup"><span data-stu-id="902c3-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="902c3-111">[Utilisez les options de ligne de commande du programme](use-setup-command-line-options.md) d’installation dans Skype Entreprise Server pour spécifier le Config.xml à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="902c3-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="902c3-112">[Configurez les stratégies d’a bootstrapping](configure-client-bootstrapping-policies.md) des clients dans Skype Entreprise Server à l’aide du logiciel enfichable MMC Éditeur d’objets de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="902c3-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="902c3-113">Il y aura probablement d’autres options que vous souhaiterez configurer lors du déploiement de la suite de produits Office.</span><span class="sxs-lookup"><span data-stu-id="902c3-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="902c3-114">Les rubriques de cette section donnent une vue d’ensemble de ces outils de personnalisation et abordent les considérations spécifiques à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="902c3-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="902c3-115">Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="902c3-115">Included are links to detailed Office help for each tool.</span></span> 
  

