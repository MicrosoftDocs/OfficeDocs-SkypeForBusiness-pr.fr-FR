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
ms.openlocfilehash: b82db655a0b55858de9cdc32efd1a3f110247b54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="7accb-102">Utiliser l’outil de personnalisation Office (OPO) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7accb-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7accb-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7accb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7accb-104">L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations.</span><span class="sxs-lookup"><span data-stu-id="7accb-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="7accb-105">Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="7accb-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="7accb-106">Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau.</span><span class="sxs-lookup"><span data-stu-id="7accb-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="7accb-107">Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations.</span><span class="sxs-lookup"><span data-stu-id="7accb-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="7accb-108">Le dossier mises à jour peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="7accb-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="7accb-109">L’outil de personnalisation Office fait partie du programme d’installation et est inclus dans les versions de licence en volume du produit.</span><span class="sxs-lookup"><span data-stu-id="7accb-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="7accb-110">Vous exécutez l’outil OCT en `setup.exe /admin` tapant à partir de la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers source d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="7accb-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="7accb-111">Par exemple, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7accb-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="7accb-112">Les administrateurs utilisent l’outil de personnalisation Office pour créer un fichier .msp de personnalisation de l’installation.</span><span class="sxs-lookup"><span data-stu-id="7accb-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="7accb-113">Comme dans Microsoft Office 2010 OCT, les administrateurs peuvent personnaliser les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="7accb-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="7accb-114">**Configuration** Spécifie l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage et les versions antérieures d’Office à supprimer, ainsi que les programmes personnalisés à exécuter lors de l’installation, les paramètres de sécurité et les propriétés d’installation.</span><span class="sxs-lookup"><span data-stu-id="7accb-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="7accb-115">**Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités d’Office.</span><span class="sxs-lookup"><span data-stu-id="7accb-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="7accb-116">Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7accb-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="7accb-117">Ces derniers peuvent modifier la plupart des paramètres après l’installation.</span><span class="sxs-lookup"><span data-stu-id="7accb-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="7accb-118">**Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.</span><span class="sxs-lookup"><span data-stu-id="7accb-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="7accb-119">**Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer les\\comptes et d’exporter des paramètres, et de spécifier les groupes de réception.</span><span class="sxs-lookup"><span data-stu-id="7accb-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="7accb-120">Pour plus d’informations sur le PTOM <http://go.microsoft.com/fwlink/p/?linkid=267516>, voir.</span><span class="sxs-lookup"><span data-stu-id="7accb-120">For information about the OCT, see <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

