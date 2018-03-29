---
title: Utilisation de l’outil de personnalisation Office dans Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Comment faire pour utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.'
ms.openlocfilehash: b0e8dd399af7a75a6f575d554cbe6c25c4e8ffd3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server-2015"></a><span data-ttu-id="24f4d-103">Utilisation de l’outil de personnalisation Office dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="24f4d-103">Use the Office Customization Tool (OCT) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24f4d-104">**Résumé :** Comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="24f4d-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="24f4d-105">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="24f4d-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="24f4d-106">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="24f4d-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="24f4d-107">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="24f4d-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="24f4d-108">Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="24f4d-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="24f4d-109">Le dossier mises à jour peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="24f4d-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="24f4d-110">Les PTOM fait partie de l’installation et il est utilisé uniquement pour les versions de licences en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="24f4d-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="24f4d-111">Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient Office des fichiers source.</span><span class="sxs-lookup"><span data-stu-id="24f4d-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="24f4d-112">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="24f4d-112">For example, use the following:</span></span>
  
 `\\server\share\Office15\setup.exe /admin`
  
<span data-ttu-id="24f4d-113">Les administrateurs utilisent l’OPO pour créer un fichier .msp de personnalisation d’installation et de personnaliser les zones suivantes :</span><span class="sxs-lookup"><span data-stu-id="24f4d-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="24f4d-114">**Programme d’installation** Utilisé pour spécifier l’emplacement d’installation par défaut sur le client par défaut et le nom de l’organisation sources d’installation de réseau supplémentaires, clé de produit, contrat de licence utilisateur final, afficher au niveau des versions antérieures d’Office à supprimer, à des programmes personnalisés à exécuter lors de installation, les paramètres de sécurité et les propriétés de l’installation.</span><span class="sxs-lookup"><span data-stu-id="24f4d-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="24f4d-115">**Fonctionnalités** Utilisé pour configurer les paramètres de l’utilisateur et pour personnaliser la façon dont les fonctionnalités d’Office sont installées.</span><span class="sxs-lookup"><span data-stu-id="24f4d-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="24f4d-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="24f4d-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="24f4d-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="24f4d-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="24f4d-118">**Contenu supplémentaire** Utilisé pour ajouter ou supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="24f4d-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="24f4d-119">**Outlook** Utilisé pour personnaliser le profil Outlook de l’utilisateur par défaut, spécifier des paramètres Exchange, ajouter des comptes, supprimer des comptes et exporter les paramètres et spécifier des groupes d’envoi/réception.</span><span class="sxs-lookup"><span data-stu-id="24f4d-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="24f4d-120">Pour plus d’informations sur l’OPO, consultez [utiliser l’OPO pour personnaliser Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span><span class="sxs-lookup"><span data-stu-id="24f4d-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://technet.microsoft.com/library/cc179132.aspx).</span></span> <span data-ttu-id="24f4d-121">Notez que ces informations s’appliquent également à Office 2016.</span><span class="sxs-lookup"><span data-stu-id="24f4d-121">Note that this information also applies to Office 2016.</span></span>
  

