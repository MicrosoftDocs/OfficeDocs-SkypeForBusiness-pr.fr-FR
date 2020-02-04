---
title: 'Lync Server 2013 : déploiement de clients Lync'
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
ms.openlocfilehash: 3d7f4497fb6842befba3f5facf5de023b94b4a76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a><span data-ttu-id="6abf7-102">Déploiement de clients Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-102">Deploying Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6abf7-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6abf7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6abf7-104">Lync 2013 introduit une approche différente pour le déploiement du client.</span><span class="sxs-lookup"><span data-stu-id="6abf7-104">Lync 2013 introduces a different approach to client deployment.</span></span> <span data-ttu-id="6abf7-105">À partir de versions précédentes, Lync 2013 ne dispose plus de son propre programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="6abf7-105">In a departure from previous releases, Lync 2013 no longer has its own installer.</span></span> <span data-ttu-id="6abf7-106">À la place, Lync est inclus avec le programme d’installation d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-106">Instead, Lync is included with the Office 2013 setup program.</span></span> <span data-ttu-id="6abf7-107">Pour déployer Lync 2013 auprès des utilisateurs, vous pouvez utiliser les méthodes d’installation d’Office 2013 et les outils de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="6abf7-107">To deploy Lync 2013 to your users, you can use Office 2013 installation methods and customization tools.</span></span>

  - <span data-ttu-id="6abf7-108">Le programme d’installation d' **Office 2013** est un package d’installation basé sur Windows Installer, composé de plusieurs fichiers msi.</span><span class="sxs-lookup"><span data-stu-id="6abf7-108">**Office 2013 Windows Installer** is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="6abf7-109">Un package MSI de base indépendant de la langue est associé à un ou plusieurs packages spécifiques à la langue pour créer un produit complet.</span><span class="sxs-lookup"><span data-stu-id="6abf7-109">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="6abf7-110">La configuration assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6abf7-110">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="6abf7-111">Les rubriques de cette section expliquent comment utiliser et personnaliser le programme d’installation de Windows 2013 pour déployer Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-111">The topics in this section describe how to use and customize the Office 2013 Windows Installer to deploy Lync 2013.</span></span>

  - <span data-ttu-id="6abf7-112">**Office 2013 démarrer** en un clic est un programme d’installation qui diffuse les fichiers d’installation d’Office à l’utilisateur à partir du portail Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="6abf7-112">**Office 2013 Click-to-Run** is an installation program that streams Office setup files to the user from the Microsoft Office 365 portal.</span></span> <span data-ttu-id="6abf7-113">Les administrateurs peuvent personnaliser l’installation à l’aide de l’outil Déploiement d’Office pour « Démarrer en un clic ».</span><span class="sxs-lookup"><span data-stu-id="6abf7-113">Administrators can customize installation by using the Office Deployment Tool for Click-to-Run.</span></span> <span data-ttu-id="6abf7-114">Comme Office 2013 démarrer en un clic est essentiellement utilisé dans l’environnement Microsoft Office 365, cette méthode d’installation n’est pas décrite en détail dans cette section.</span><span class="sxs-lookup"><span data-stu-id="6abf7-114">Because Office 2013 Click-to-Run is primarily used in the Microsoft Office 365 environment, this installation method is not described in detail in this section.</span></span> <span data-ttu-id="6abf7-115">Des informations détaillées sur l’utilisation et la personnalisation de l’installation « démarrer en un clic » sont disponibles dans la documentation du kit de ressources Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-115">Detailed information about using and customizing Click-to-Run installation is available in the Office 2013 Resource Kit documentation.</span></span> <span data-ttu-id="6abf7-116">Les administrateurs peuvent également télécharger le programme Office 2013 « démarrer en un clic » et les fichiers source de langue vers un emplacement local, ce qui est utile lorsque vous souhaitez réduire la demande sur le réseau ou empêcher les utilisateurs d’installer un logiciel à partir d’Internet en raison de exigences en matière de sécurité d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6abf7-116">Administrators can also download the Office 2013 Click-to-Run program and language source files to an on-premises location, which is useful when you want to minimize the demand on the network or prevent users from installing software from the Internet because of corporate security requirements.</span></span>

<span data-ttu-id="6abf7-117">Les rubriques de cette section portent sur le déploiement de clients à l’aide du programme d’installation MSI d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-117">The topics in this section focus on how to deploy clients by using the Office 2013 MSI-based installer.</span></span> <span data-ttu-id="6abf7-118">Il doit s’agir de la documentation du kit de ressources Office 2013, qui décrit en détail la préparation de votre infrastructure, la personnalisation de l’installation et le déploiement d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-118">Your primary reference should be the Office 2013 Resource Kit documentation, which describes in detail how to prepare your infrastructure, customize setup, and deploy Office 2013.</span></span> <span data-ttu-id="6abf7-119">Néanmoins, vous devez utiliser la documentation Office conjointement avec les rubriques de cette section, qui pointent sur des considérations de déploiement spécifiques à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-119">However, you should use the Office documentation in conjunction with topics in this section, which point out deployment considerations that are specific to Lync 2013.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="6abf7-120">Le complément réunion en ligne pour Lync 2013, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, s’installe automatiquement avec Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6abf7-120">The Online Meeting Add-in for Lync 2013, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Lync 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="6abf7-121">Le programme d’installation d’Office 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="6abf7-121">The Office 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="6abf7-122">Le client Lync 2013 s’installe côte à côte avec d’autres clients Lync ou Office Communicator</span><span class="sxs-lookup"><span data-stu-id="6abf7-122">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6abf7-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6abf7-123">In This Section</span></span>

  - [<span data-ttu-id="6abf7-124">Personnalisation de l’installation du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-124">Customizing client installation in Lync Server 2013</span></span>](lync-server-2013-customizing-client-installation.md)

  - [<span data-ttu-id="6abf7-125">Personnalisation du comportement de Lync et de l’interface utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-125">Customizing Lync behavior and the user interface in Lync Server 2013</span></span>](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [<span data-ttu-id="6abf7-126">Personnalisation du complément réunion en ligne dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-126">Customizing the Online Meeting Add-in in Lync Server 2013</span></span>](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [<span data-ttu-id="6abf7-127">Configuration de la page de participation à une réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-127">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)

  - [<span data-ttu-id="6abf7-128">Configuration des versions clientes prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-128">Configuring supported client versions in Lync Server 2013</span></span>](lync-server-2013-configuring-supported-client-versions.md)

  - [<span data-ttu-id="6abf7-129">Configuration du mode de confidentialité Enhanced presence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abf7-129">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

