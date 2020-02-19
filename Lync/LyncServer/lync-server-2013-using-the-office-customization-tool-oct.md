---
title: 'Lync Server 2013 : utilisation de l’outil de personnalisation Office (OPO)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04cf51d16c27a75d65b1936f2f95e1e5865ad63e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="ac9da-102">Utilisation de l’outil de personnalisation Office (OPO) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac9da-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac9da-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ac9da-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ac9da-104">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="ac9da-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="ac9da-105">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="ac9da-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="ac9da-106">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="ac9da-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="ac9da-107">Quand vous installez Office, le programme d’installation recherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="ac9da-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="ac9da-108">Le dossier mises à jour ne peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ac9da-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="ac9da-109">L’outil de personnalisation Office fait partie du programme d’installation et est inclus dans les versions de licence en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="ac9da-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="ac9da-110">Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers sources Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ac9da-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="ac9da-111">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ac9da-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="ac9da-112">Les administrateurs utilisent l’outil de personnalisation Office pour créer un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="ac9da-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="ac9da-113">Comme dans l’OPO de Microsoft Office 2010, les administrateurs peuvent personnaliser les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="ac9da-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="ac9da-114">**Programme d’installation** Permet de spécifier l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage, les versions antérieures d’Office à supprimer, les programmes personnalisés à exécuter pendant l’installation, les paramètres de sécurité et les propriétés d’installation.</span><span class="sxs-lookup"><span data-stu-id="ac9da-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="ac9da-115">**Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser l’installation des fonctionnalités Office.</span><span class="sxs-lookup"><span data-stu-id="ac9da-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="ac9da-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ac9da-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="ac9da-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="ac9da-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="ac9da-118">**Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="ac9da-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="ac9da-119">**Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer des\\comptes et d’exporter des paramètres et de spécifier des groupes d’envoi de réception.</span><span class="sxs-lookup"><span data-stu-id="ac9da-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="ac9da-120">Pour plus d’informations sur l’OPO <https://go.microsoft.com/fwlink/p/?linkid=267516>, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="ac9da-120">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

