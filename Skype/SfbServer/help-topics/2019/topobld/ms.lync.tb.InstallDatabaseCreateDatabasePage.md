---
title: Installer et créer des bases de données
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Vous sélectionnez les bases de données que vous souhaitez créer pour votre déploiement. Par défaut, la base de données sera créée sur le serveur SQL définies dans le site défini et sera automatiquement déployer et configurer les fichiers de base de données basés sur le serveur SQL que vous placez sur les bases de données.
ms.openlocfilehash: 6138608bc98b921ba90401e35bea584efe37a9cb
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21063009"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="68a6f-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="68a6f-104">Install and Create Databases</span></span>
 
<span data-ttu-id="68a6f-105">Vous sélectionnez les bases de données que vous souhaitez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="68a6f-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="68a6f-106">Par défaut, la base de données sera créée sur le serveur SQL définies dans le site défini et sera automatiquement déployer et configurer les fichiers de base de données basés sur le serveur SQL que vous placez sur les bases de données.</span><span class="sxs-lookup"><span data-stu-id="68a6f-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="68a6f-107">**Sélectionnez les bases de données que vous souhaitez créer**: activez la case à cocher de toute base de données que vous souhaitez déployer et configurer.</span><span class="sxs-lookup"><span data-stu-id="68a6f-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="68a6f-108">Activez la case à cocher d’une ou toutes les bases de données que vous allez déployer.</span><span class="sxs-lookup"><span data-stu-id="68a6f-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="68a6f-109">Le serveur SQL Server doit déjà être configuré pour l’instance (le cas échéant) et les ports de pare-feu doivent être ouvert pour prendre en charge l’instance que vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="68a6f-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="68a6f-110">Pour plus d’informations, consultez [Configurer SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="68a6f-110">For details, see [Configure SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="68a6f-111">**Avancé**: cliquez sur le serveur SQL Server et cliquez sur le bouton **Avancé** pour choisir des options de la base de données des emplacements de fichiers sur votre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68a6f-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="68a6f-112">Pour plus d’informations sur l’emplacement des fichiers de base de données avancées, voir [Base de données Installation à l’aide de Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="68a6f-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="68a6f-113">**Nouveau**: cliquez sur ce bouton vous renvoie à l’écran précédent (toujours soient pas disponibles, selon la façon dont vous êtes arrivés à cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="68a6f-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="68a6f-114">**Suivant**: ce bouton valide votre sélection dans la boîte de dialogue active et ouvre la boîte de dialogue suivante pour configurer des informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="68a6f-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="68a6f-115">**Annuler**: cliquez sur ce bouton sera quitter la configuration et ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="68a6f-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="68a6f-116">Certains, mais pas tous les écrans de configuration vous demandera si vous souhaitez fermer et ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="68a6f-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="68a6f-117">Si vous sélectionnez **Oui** ferme la configuration actuelle et fermer la configuration actuelle et revenir dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="68a6f-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="68a6f-118">Si vous sélectionnez **non** pour revenir à la boîte de dialogue configuration actuelle et vous permettent de continuer la configuration.</span><span class="sxs-lookup"><span data-stu-id="68a6f-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="68a6f-119">**Aide**: en cliquant sur le bouton **aide** affiche ces informations d’aide associées à la boîte de dialogue de configuration en cours.</span><span class="sxs-lookup"><span data-stu-id="68a6f-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

