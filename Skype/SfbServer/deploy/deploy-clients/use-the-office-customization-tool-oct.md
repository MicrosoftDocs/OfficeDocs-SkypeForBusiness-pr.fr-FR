---
title: Utiliser l’Outil de personnalisation Office (PERSONNALISATION) dans Skype Entreprise Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Comment utiliser l’outil de personnalisation Office avec le client Skype Entreprise.'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100450"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="51dff-103">Utiliser l’Outil de personnalisation Office (PERSONNALISATION) dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="51dff-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="51dff-104">**Résumé :** Utilisation de l’outil de personnalisation Office avec le client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="51dff-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="51dff-105">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="51dff-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="51dff-106">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="51dff-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="51dff-107">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="51dff-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="51dff-108">Quand vous installez Office, le programme d’installation recherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="51dff-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="51dff-109">Le dossier Updates peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.</span><span class="sxs-lookup"><span data-stu-id="51dff-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="51dff-110">L' OCT fait partie de l’installation et est utilisé uniquement pour les versions avec licence en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="51dff-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="51dff-111">Vous exécutez l' OCT en tapant à la ligne de commande à partir de la racine du point d’installation réseau qui  `setup.exe /admin` contient les fichiers sources Office.</span><span class="sxs-lookup"><span data-stu-id="51dff-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="51dff-112">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="51dff-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="51dff-113">Les administrateurs utilisent l’PERSONNALISATION pour créer un fichier .msp de personnalisation de l’installation et peuvent personnaliser les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="51dff-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="51dff-114">**Installation** Permet de spécifier l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, des sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage, les versions antérieures d’Office à supprimer, les programmes personnalisés à exécuter pendant l’installation, les paramètres de sécurité et les propriétés d’installation.</span><span class="sxs-lookup"><span data-stu-id="51dff-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="51dff-115">**Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser l’installation des fonctionnalités Office.</span><span class="sxs-lookup"><span data-stu-id="51dff-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="51dff-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="51dff-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="51dff-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="51dff-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="51dff-118">**Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="51dff-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="51dff-119">**Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer des comptes et d’exporter des paramètres et de spécifier des groupes d’envoi/réception.</span><span class="sxs-lookup"><span data-stu-id="51dff-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="51dff-120">Pour plus d’informations sur l’PERSONNALISATION, voir Utiliser l' OCT [pour personnaliser Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="51dff-120">For information about the OCT, see [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="51dff-121">Notez que ces informations s’appliquent également aux versions ultérieures d’Office.</span><span class="sxs-lookup"><span data-stu-id="51dff-121">Note that this information also applies to later versions of Office.</span></span>
