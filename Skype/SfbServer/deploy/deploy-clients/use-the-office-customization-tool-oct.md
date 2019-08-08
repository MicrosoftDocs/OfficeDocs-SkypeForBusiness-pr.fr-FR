---
title: Utiliser l’outil de personnalisation Office (OPO) dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé: comment utiliser l’outil de personnalisation Office avec le client Skype entreprise.'
ms.openlocfilehash: e7eb331c1b63a9e6a94ae3920e65ef57f426fbb0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234599"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="c0480-103">Utiliser l’outil de personnalisation Office (OPO) dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c0480-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="c0480-104">**Résumé:** Comment utiliser l’outil de personnalisation Office avec le client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c0480-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="c0480-105">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="c0480-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="c0480-106">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="c0480-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="c0480-107">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="c0480-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="c0480-108">Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="c0480-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="c0480-109">Le dossier mises à jour peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.</span><span class="sxs-lookup"><span data-stu-id="c0480-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="c0480-110">Le PTOM fait partie du programme d’installation et est uniquement utilisé pour les versions sous licence en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="c0480-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="c0480-111">Vous exécutez l’outil OCT en `setup.exe /admin` tapant à partir de la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers source d’Office.</span><span class="sxs-lookup"><span data-stu-id="c0480-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="c0480-112">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c0480-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="c0480-113">Les administrateurs utilisent l’OPO pour créer un fichier de personnalisation de l’installation. msp et peuvent personnaliser les domaines suivants:</span><span class="sxs-lookup"><span data-stu-id="c0480-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="c0480-114">**Configuration** Spécifie l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage et les versions antérieures d’Office à supprimer, ainsi que les programmes personnalisés à exécuter pendant installation, paramètres de sécurité et propriétés de l’installation.</span><span class="sxs-lookup"><span data-stu-id="c0480-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="c0480-115">**Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités d’Office.</span><span class="sxs-lookup"><span data-stu-id="c0480-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="c0480-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c0480-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="c0480-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="c0480-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="c0480-118">**Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="c0480-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="c0480-119">**Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer les comptes et d’exporter des paramètres, et de spécifier les groupes d’envoi/réception.</span><span class="sxs-lookup"><span data-stu-id="c0480-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="c0480-120">Pour plus d’informations sur le PTOM, voir [utiliser le PTOM pour personnaliser Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="c0480-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="c0480-121">Notez que ces informations s’appliquent également aux versions ultérieures d’Office.</span><span class="sxs-lookup"><span data-stu-id="c0480-121">Note that this information also applies to later versions of Office.</span></span>
  

