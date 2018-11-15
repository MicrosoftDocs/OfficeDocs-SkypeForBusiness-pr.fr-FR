---
title: Utiliser l’outil de personnalisation Office (OPO) dans Skype pour Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Résumé : Découvrez comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.'
ms.openlocfilehash: 6050a9e9c36fa62aff16994469e63a9689ab5958
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530677"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="613a2-103">Utiliser l’outil de personnalisation Office (OPO) dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="613a2-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="613a2-104">**Résumé :** Comment utiliser l’outil de personnalisation Office avec le Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="613a2-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="613a2-105">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="613a2-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="613a2-106">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="613a2-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="613a2-107">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="613a2-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="613a2-108">Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="613a2-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="613a2-109">Le dossier mises à jour peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale d’Office.</span><span class="sxs-lookup"><span data-stu-id="613a2-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="613a2-110">L’OPO fait partie du programme d’installation et elle est utilisée uniquement pour les versions de licences en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="613a2-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="613a2-111">Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient le bureau des fichiers sources.</span><span class="sxs-lookup"><span data-stu-id="613a2-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="613a2-112">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="613a2-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="613a2-113">Les administrateurs utilisent l’OPO pour créer un fichier .msp de personnalisation du programme d’installation et de personnaliser les zones suivantes :</span><span class="sxs-lookup"><span data-stu-id="613a2-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="613a2-114">**Programme d’installation** Permet de spécifier l’emplacement d’installation par défaut sur le client par défaut et le nom de l’organisation, les sources d’installation réseau supplémentaires, clé de produit, contrat de licence utilisateur final, afficher des versions antérieures d’Office à supprimer, programmes personnalisés à exécuter au cours de niveau installation, les paramètres de sécurité et les propriétés d’installation.</span><span class="sxs-lookup"><span data-stu-id="613a2-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="613a2-115">**Fonctionnalités** Utilisé pour configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités Office.</span><span class="sxs-lookup"><span data-stu-id="613a2-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="613a2-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="613a2-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="613a2-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="613a2-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="613a2-118">**Contenu supplémentaire** Permet d’ajouter ou supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="613a2-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="613a2-119">**Outlook** Utilisé pour personnaliser le profil d’Outlook par défaut d’un utilisateur, spécifier les paramètres Exchange, ajouter des comptes, supprimer des comptes et exporter les paramètres et spécifier les groupes d’envoi/réception.</span><span class="sxs-lookup"><span data-stu-id="613a2-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="613a2-120">Pour plus d’informations sur l’outil, consultez la rubrique [utiliser l’OPO pour personnaliser Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="613a2-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="613a2-121">Notez que ces informations s’applique également aux versions ultérieures d’Office.</span><span class="sxs-lookup"><span data-stu-id="613a2-121">Note that this information also applies to later versions of Office.</span></span>
  

