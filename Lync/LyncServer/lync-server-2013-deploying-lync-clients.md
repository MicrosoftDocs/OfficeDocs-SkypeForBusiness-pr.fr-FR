---
title: 'Lync Server 2013 : déploiement de clients Lync'
description: 'Lync Server 2013 : déploiement de clients Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09b501fc721ac880c5cf7da0293e3aa9c6443722
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573430"
---
# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="a1e87-103">Déploiement de clients Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-103">Deploying Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e87-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a1e87-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a1e87-105">Lync 2013 présente une approche différente pour le déploiement de clients.</span><span class="sxs-lookup"><span data-stu-id="a1e87-105">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="a1e87-106">Dans les versions antérieures, Lync 2013 ne dispose plus de son propre programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="a1e87-106">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="a1e87-107">Au lieu de cela, Lync est inclus dans le programme d’installation d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-107">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="a1e87-108">Pour déployer Lync 2013 auprès de vos utilisateurs, vous pouvez utiliser les méthodes d’installation et les outils de personnalisation d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-108">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="a1e87-109">**Office 2013 Windows Installer** est un package d’installation basé sur Windows Installer qui se compose de plusieurs fichiers msi.</span><span class="sxs-lookup"><span data-stu-id="a1e87-109">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="a1e87-110">Un package MSI principal indépendant de la langue s’accompagne d’un ou plusieurs packages spécifiques à la langue pour en faire un produit complet.</span><span class="sxs-lookup"><span data-stu-id="a1e87-110">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="a1e87-111">Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1e87-111">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="a1e87-112">Les rubriques de cette section décrivent comment utiliser et personnaliser Office 2013 Windows Installer pour déployer Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-112">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="a1e87-113">**Office 2013 « démarrer en un clic »** est un programme d’installation qui diffuse les fichiers d’installation d’Office à l’utilisateur à partir du centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1e87-113">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft 365 admin center.</span></span> <span data-ttu-id="a1e87-114">Les administrateurs peuvent personnaliser l’installation à l’aide de l’outil Déploiement d’Office pour Office « Démarrer en un clic ».</span><span class="sxs-lookup"><span data-stu-id="a1e87-114">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="a1e87-115">Étant donné que Office 2013 « démarrer en un clic » est principalement utilisé dans l’environnement Microsoft 365, cette méthode d’installation n’est pas décrite en détail dans cette section.</span><span class="sxs-lookup"><span data-stu-id="a1e87-115">Because Office 2013 Click-to-Run is primarily used in the Microsoft 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="a1e87-116">Vous trouverez des informations détaillées sur l’utilisation et la personnalisation de l’installation d’Office « démarrer en un clic » dans la documentation du kit de ressources Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-116">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="a1e87-117">Les administrateurs peuvent également télécharger les fichiers de programme et de langue Office 2013 « démarrer en un clic » sur un emplacement local, ce qui est utile lorsque vous souhaitez réduire la demande sur le réseau ou empêcher les utilisateurs d’installer des logiciels à partir d’Internet en raison des exigences de sécurité de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1e87-117">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="a1e87-118">Les rubriques de cette section traitent de la façon de déployer des clients à l’aide du programme d’installation basé sur MSI Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-118">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="a1e87-119">Votre référence principale doit être la documentation du kit de ressources Office 2013, qui décrit en détail comment préparer votre infrastructure, personnaliser le programme d’installation et déployer Office 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-119">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="a1e87-120">Toutefois, vous devez utiliser la documentation Office conjointement avec les rubriques de cette section, qui indiquent les considérations de déploiement spécifiques à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-120">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="a1e87-121">Le complément de réunion en ligne pour Lync 2013, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a1e87-121">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="a1e87-122">Le programme d’installation d’Office 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="a1e87-122">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="a1e87-123">Le client Lync 2013 installe côte à côte avec d’autres clients Lync ou Office Communicator</span><span class="sxs-lookup"><span data-stu-id="a1e87-123">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1e87-124">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a1e87-124">In This Section</span></span>

  - [<span data-ttu-id="a1e87-125">Personnalisation de l’installation du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-125">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="a1e87-126">Personnalisation du comportement de Lync et de l’interface utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-126">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="a1e87-127">Personnalisation du complément de réunion en ligne dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-127">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="a1e87-128">Configuration de la page de participation aux réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-128">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="a1e87-129">Configuration des versions de client prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-129">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="a1e87-130">Configuration du mode de confidentialité améliorée de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e87-130">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

